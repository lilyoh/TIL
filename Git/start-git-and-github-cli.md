## Git 초기화와 로컬 저장소

특정 폴더에서 git으로 버전 관리를 하고 싶다면

1. 원하는 폴더에서 git 초기화를 하면 그 때부터 가능

   `git init`

2. git 초기화를 하면 .git 이라는 숨겨진 폴더가 만들어짐

   ㄴ 이게 로컬 저장소

3. 로컬 저장소에 내가 만든 버전 정보, 원격 저장소 주소 등이 저장됨
4. 원격 저장소에서 내 컴퓨터로 코드를 받아오면 로컬 저장소가 자동으로 생김
5. 한 폴더에 하나의 로컬 저장소만 유지해야 함

## 첫 번째 버전 만들기

덩어리란? 커밋 commit =  하나의 버전

커밋으로 만들길 원하는 파일만 선택하는 명령어 = add

git 사용자 정보 등록

1. git 전역 사용자 설정 (github의 닉네임과 이메일 입력)

```java
git config --global user.name "lilyoh"
git config --global user.email "lilyoh628@gmail.com"
```

버전 생성 실습

1. vs code에서 README.md, index.html 파일 생성
2. 원하는 파일만 선택하기

```java
git add README.md
```

3. 메세지를 달아 커밋으로 만들기

```java
git commit -m "프로젝트 설명 파일 추가"
```

4. 생성한 커밋 보기