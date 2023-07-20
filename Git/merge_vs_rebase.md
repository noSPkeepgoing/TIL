# Git Merge vs Rebase

## 서론 🤨

### merge란?

`merge` 는 서로 다른 branch 의 작업 내용을 하나의 branch 로 통합하기 위한 명령어

### rebase란?

`rebase` 는 특정 브랜치를 base (기준) 로 놓고, 커밋 이력을 정렬하겠다는 명령어

결국 `merge`와 `rebase` 모두 branch를 합쳐주기위해 사용하는 것이 아닌가?
같은 일을 수행하는 명령어가 왜 두 개나 필요한 것일까?

## 본론 🧐

### merge의 특징

`git merge`를 하게되는 경우 merge를 하는 커밋 로그가 main HEAD부분에 남게 된다.
![git merge](https://velog.velcdn.com/images/sunpaaaa/post/bc105a5c-691c-4bd8-971c-039685d273e2/image.png)

통합 기록을 볼 수 있어 어느 시점에서 무슨 브랜치가 통합되었는지 명시적으로 알 수 있지만 브랜치가 많아질수록 깃 히스토리가 복잡해져 가독성이 떨어진다.

### rebase의 특징

`git rebase` 는 하나의 줄기처럼 commit 이력을 이어준다.
![git rebase](https://velog.velcdn.com/images/sunpaaaa/post/663d7f1d-661c-4253-8b42-9034c9f5e0db/image.png)
또한 rebase 이후 commit id가 달라진 것으로 보아 복사가 되어 새롭게 형성되었다는 것을 알 수 있다.
![git rebase commit id](https://velog.velcdn.com/images/sunpaaaa/post/642c0a7f-e024-4e94-9c29-d0861854c067/image.png)

커밋을 새로쓰고 재정렬하기 때문에 커밋 트리가 완전히 달라진다. 이는 깃 히스토리의 높은 가독성을 보장하지만 비교적 많은 충돌의 위험을 야기한다.

## 정리 🤓

### merge와 rebase의 공통점✨

branch를 합친다!

### merge와 rebase의 차이점✨

rebase를 이용하면 git history를 관리할 수 있다!
