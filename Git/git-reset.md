## 1. 이전 커밋 삭제
`git reset HEAD^`
- `--soft` : default, 커밋 이전으로 돌아감, 파일 변경사항은 그대로
- `--hard` : 커밋 이전의 파일 상태로 돌아감

## 2. 새로운 커밋 푸쉬
`git push origin master -f`  
: force로 해야 remote repo에 반영 가능함