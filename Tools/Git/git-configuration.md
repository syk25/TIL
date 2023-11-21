# 사용자 설정
## 설정범위
- System : 시스템 내의 모든 사용자
- Global : 한 사용자의 모든 repository
- local : 하나의 repository
~~~git
$ git config --system
$ git gonfig --global
$ git config --local
~~~

### 설정시 명령어
ex. Global Git 사용자 설정(이메일, 이름)
~~~git
$ git config --global user.email "abc@abc.com"
$ git config --global user.name "Hong Gil-Dong"
~~~

설정확인
~~~git
$ git config --list
~~~

