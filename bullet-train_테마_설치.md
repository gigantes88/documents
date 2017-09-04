# oh-my-zsh 용 bullet-train 설치!

## 1. bullet-train 테마 다운로드

[다운로드](https://raw.githubusercontent.com/caiogondim/bullet-train-oh-my-zsh-theme/master/bullet-train.zsh-theme)

다운로드를 클릭하면 bullet-train 테마가 다운로드 된다.

바로 다운로드가 안되면 마우스 오른쪽 버튼을 눌러 다른이름으로 저장해 'bullet-train.zsh-theme'로 저장한다.(확장자 .zsh-theme 확인)

---

## 2. bullet-train 테마파일 옮기기

맥 유저의 경우 oh-my-zsh를 다른 경로에 설치하지 않았다면 아래와 같은 경로일 것이다.

```bash
$ ~/.oh-my-zsh/themes/
```

아까 다운받은 파일을 저 디렉토리로 옮긴다.

파인더로 옮기려면  command + shift + > 를 누르면 숨긴파일이 보인다. 이를 통해 옮겨도 된다.

---

## 3. .zshrc 수정

터미널에서 아래와 같은 명령어를 치면 oh-my-zsh 설정파일이 열린다.

```bash
$ open ~/.zshrc
```

이후 중간에 있는 ZSH_THEME를 아래와 같이 바꾸고
터미널 또는 iterm2를 재시작 하면 bullet-train 테마로 변경된다.

```
ZSH_THEME="bullet-train"
```

---

## 참고 링크

- [bullet-train](https://github.com/caiogondim/bullet-train.zsh)
