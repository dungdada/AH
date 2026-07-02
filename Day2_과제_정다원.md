# Git Day2 과제_정다원

### GitHub 계정과 저장소 생성
- 원격 저장소(Remote Repository): 인터넷상에 있는 Git 저장소로, 여러 사람이 코드를 공유하고 백업하는 역할을 하며 협업의 창구

- 저장소 생성: GitHub 계정을 만든 뒤 새 Repository를 생성하면 원격 저장소 주소(URL)가 발급됨

- 원격 연결 명령어:
  - git remote add origin 원격주소: 로컬 저장소에 원격 저장소를 연결(git과 github)

  - git remote -v: 현재 연결된 원격 저장소 목록을 확인

- git push / git pull
  - 기능: 로컬 저장소와 원격 저장소를 동기화

  - git push: 로컬에서 커밋한 내용을 원격 저장소로 업로드. 처음 전송 시 git push -u origin main 형식을 주로 사용

  - git pull: 원격 저장소의 새로운 변경 사항을 내려받아 로컬에 반영

### 협업 실습 및 도구
- README: Repository에 대한 설명, 개요 등을 쓸 때 사용 (거이 모든 repository에 들어간다)
- Clone vs. Fork
  - Clone: 원격 저장소를 그대로 로컬로 복사, 해당 저장소에 push 권한이 있는 팀 내부 협업 시 주로 사용함(제일 처음 복사 -> 분업 및 작업, 작업중인것 보다는 기본 틀을 복사하는 느낌)

  - Fork: 타인의 저장소를 내 GitHub 계정으로 복사. 원본에 직접 push 권한이 없을 때 사용하고, 주로 오픈소스 기여 방식에 사용

- Pull Request (PR) 및 Code Review
  - Pull Request: 내가 변경한 사항을 원본 저장소에 반영해달라고 요청하는 과정. 
  
    ->변경 내용 설명과 리뷰 요청이 포함되며 병합 전 최종 검증 단계

  - Code Review: 코드를 병합하기 전에 팀원들이 함께 확인, 검토 (버그 확인 등) 
  
    -> 코드 중심으로 리뷰하고 승인 후 병합하는 것이 원칙
- Issue
  - 할 일, 버그 리포트, 기능 요청 등 (Issue)
  - PullRequest와 Issue를 연결하여 프로젝트의 작업을 체계적으로 관리할 수 있음

### 자주 사용하는 명령어
- 조회 및 비교
  - git show: 특정 커밋 하나(기본값은 HEAD)의 변경 내용(diff), 메시지, 작성자, 날짜 등을 집중적으로 살펴볼 때 사용

  - git diff: Working Directory, Staging Area, 커밋 간의 차이점을 비교하여 변경 사항을 점검하거나 충돌 원인을 분석할 때 사용

  - git blame: 파일의 각 줄을 누가, 언제, 어떤 커밋에서 수정했는지 추적

- 임시 저장 및 수정
  - git stash: 현재 작업 중인 변경 사항을 커밋하지 않고 임시로 치워둘 때 사용
  
    ->브랜치 이동이나 긴급 수정 시 유용하며, pop 명령어로 다시 적용할 수 있다

  - git commit --amend: 마지막 커밋을 수정하거나 새로운 파일 추가/제거를 반영하여 새 커밋으로 교체할 때 사용
- 되돌리기 (Reset & Revert)
  - git reset: 브랜치의 기준을 과거 커밋으로 이동시켜 히스토리를 변경. 
  
    --hard 옵션 사용 시 모든 변경 내용이 삭제

  - git revert: 히스토리를 보존하면서 특정 커밋을 취소하는 새로운 커밋을 생성(협업 중 롤백)