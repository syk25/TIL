# .gitignore 작성법
### 1. 정의
.gitignore에 기재 된 파일이나 폴더는 커밋시 제외된다.

### 2. 제외 고려대상
- 폴더
- 파일
- 폴더 안의 파일
- 폴더 안의 특정 확장자 전부
- 하위 폴더 포함 폴더 안의 특정 확장자 전부

### 3. 예제
~~~gitignore
# [상황] docs 폴더 내에 docs-under 폴더와 test.txt 파일이 존재한다
# test.txt 파일 제외
test.txt
# docs 폴더 제외
/docs
# docs 폴더 내의 test2.txt 파일 제외
/docs/test2.txt
# docs 폴더 내의 특정 확장자 전부 제외
/docs/*.txt
# docs 폴더 내의 하위 폴더 포함 txt 확장자 전부 제외
/docs/**/*.txt

~~~

###  [4. 탬플릿 생성 웹](https://www.toptal.com/developers/gitignore)</br>
언어, 프레임워크를 키워드로 검색시 탬플릿을 생성해주는 웹서비스