Git Command
===================


Git의 기본적인 커맨드

----------

https://git-scm.com/book/ko/v2

**git status**
현재 작업상태 확인

**git shortlog  , git log**  
작업 히스토리 확인

**git add .**
workspace에서 local git server로 작업내용 stage  올리기

**git commit -am "message"**
local git server로 작업내용 저장

**git push [원격저장소] [로컬저장소 브랜치]**
remote git server로 저장

**git fetch**
local git server 랑 remote git server랑 변경내용 확인

**git pull**
변경내용을 local git server로 받기

**git checkout [branch]**

# 브랜치 이동
branch는
master = test완료된 branch
release는 테스트 branch
[feature]  개인 작업용 branch

**git checkout -b dev_[initial]**

**git merge [가지고올 branch]**
