# git-hooks

Git hook 모음

## post-commit.fix-mac-sourcetree-hangul-author

Mac에서 Sourcetree를 사용할 때 사용자 이름을 한글로 사용할 경우 PC 사용자에게는 `ㅅㅣㄴㅅㅡㅇㅇㅕㅂ`과 같이 나오는 문제를 해결하는 post-commit hook.

`~/.gitauthor`에 아래와 같이 사용할 이름과 이메일을 작성한다.

```
신승엽
flysky@flysky.kr
```

`post-commit.fix-mac-sourcetree-hangul-author`를 사용하고 싶은 git 저장소의 `.git/hooks/post-commit`으로 저장하고 **실행 권한**을 준다.

Mac용 Sourcetree에서 UI를 통해 이름을 한글로 설정할 경우 PC 사용자는 자모가 분리된 상태로 보여지게 된다. UI를 사용하지 않고 `git config` 명령어를 사용하여 직접 설정하면 해결이 되지만 한번이라도 Sourcetree의 설정 UI로 들어가게 되면 다시 되돌아 가게되는 문제가 있다.

이 hook을 이용하면 `--amend` 옵션을 사용하여 커밋의 author 정보를 다시 쓰게 된다.
