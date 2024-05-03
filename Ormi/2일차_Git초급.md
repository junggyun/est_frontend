# 2일차 (2024-05-03)

## Git 초급

### Git

- 분산 버전 관리 시스템

### GitHub

- Git 저장소 호스팅을 지원하는 웹 서비스

### CLI

- `git pull`: 코드를 원격 저장소에서 가져옵니다.
- `git add .`: 새로운 버전을 만들기 위한 준비작업을 진행합니다. 변경된 소스코드들을 등록합니다.
- `git commit`: 새로운 버전을 만듭니다.
- `git push`: 원격저장소에 코드를 올립니다.

### CLI 사용 예시

- 포트폴리오를 만들고 있는 취업 준비생

  1. repo 생성(README.me 생성 체크)
  2. code > `git@github.com:terranking1/TIL.git` 복사
  3. 내 컴퓨터 폴더에서 git bash를 실행
  4. `git clone git@github.com:terranking1/TIL.git .`
  5. 파일 수정, 삭제, 추가 진행
  6. `git add .`
  7. `git commit -m '{커밋메시지}'`
  8. `git push`

- 이후 아래 과정을 반복하면서 프로젝트 진행
  1. 파일 수정, 삭제, 추가 진행
  2. `git add .`
  3. `git commit -m '{커밋메시지}'`
  4. `git push`

---

- 신입사원으로 입사한 A와 B

  1. 레포지토리 초대 요청
  2. (A) `git clone git@github.com:terranking1/TIL.git .`
  3. (B) `git clone git@github.com:terranking1/TIL.git .`
  4. (A)
     1. 업무 지시에 따른 코드 수정
     2. `git add .`
     3. `git commit -m '{커밋메시지}'`
     4. `git push`
  5. (B)
     1. `git pull`
     2. 업무 지시에 따른 코드 수정
     3. `git add .`
     4. `git commit -m '{커밋메시지}'`
     5. `git push`
  6. (A)
     1. `git pull`
     2. 업무 지시에 따른 코드 수정
     3. `git add .`
     4. `git commit -m '{커밋메시지}'`
     5. `git push`

  - 반복

## 기타

- 1일 1커밋 도전
- 깃헙 이슈생성, 깃헙 프로젝트, 깃헙 위키 해볼 것!!!
- 프로젝트 README.md 작성 시 WBS 중요! ERD 매우 중요!!!!! (머메이드 이용할 것)
- h1태그는 문서 당 1개
- 이력서 작성 시 주의할 점
  - Javascript X
  - JavaScript O
  - github X
  - GitHub O
  - 등등
