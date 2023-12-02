# Embedded Redis 설정
## 의존성 추가
~~~
dependencies {
    // redisson client
    implementation group: 'org.redisson', name: 'redisson', version: '3.24.3'

    // embedded redis
    implementation('com.github.codemonstur:embedded-redis:1.0.0') {
        exclude group: "org.slf4j", module: "slf4j-simple"
    }
}
~~~
build.gradle에 위의 의존성을 추가한다. 
embedded redis의 경우 Mac OS 에 M1 칩일 경우 다른 버전으로 하게 될 경우 오류가 날 수 현재 위의 의존성을 추가하는 것을 권장한다.

## application.yml 설정하기
~~~yaml
spring:
  redis:
    host: 127.0.0.1
    port: 6739
~~~
어플리케이션 실행 시 embedded redis는 호스트와 포트번호가 자동적으로 주어지게끔 설정한다.

## 소스코드에 config 설정
### 서버 객체 빈으로 등록
~~~java
import jakarta.annotation.PostConstruct;
import jakarta.annotation.PreDestroy;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.context.annotation.Configuration;
import redis.embedded.RedisServer;

import java.io.IOException;

@Configuration
public class LocalRedisConfig {
    @Value("${spring.redis.port}")
    private int redisPort;
    private RedisServer redisServer;
    
    @PostConstruct
    public void startRedis() throws IOException {
        redisServer = new RedisServer(redisPort);
        redisServer.start();
    }
    @PreDestroy
    public void stopRedis() throws IOException {
        if (redisServer != null) {
            redisServer.stop();
        } }
}

~~~
1. @Configuration 어노테이션 붙이기
2. 포트번호를 받을 변수를 선언하기

### 저장소 접근 설정
~~~java
import org.redisson.Redisson;
import org.redisson.api.RedissonClient;
import org.redisson.config.Config;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class RedisRepositoryConfig {
    @Value("${spring.redis.host}")
    private String redisHost;
    @Value("${spring.redis.port}")
    private int redisPort;
    @Bean
    public RedissonClient redissonClient() {
        Config config = new Config();
        config.useSingleServer().setAddress("redis://" + redisHost + ":" + redisPort);
        return Redisson.create(config);
    }
}
~~~