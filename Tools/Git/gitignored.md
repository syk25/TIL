# .gitignore 작성법
### 정의
.gitignore에 기재 된 파일이나 폴더는 커밋시 제외된다.

### 제외 고려대상
- 폴더
- 파일
- 폴더 안의 파일
- 폴더 안의 특정 확장자 전부
- 하위 폴더 포함 폴더 안의 특정 확장자 전부

### 예제
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