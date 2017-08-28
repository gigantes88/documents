# zsh 및 oh-my-zsh 설치!

## 1. Mac용 패키지매니저 Homebrew 설치

### 1.1 Homebrew 설치

MacOS용 패키지 매니저인 Homebrew를 설치한다. Homebrew를 설치하면 애플에서 제공하지 않는 다양한 패키지를 손쉽게 설치할 수 있도록 도와준다.  
아래 코드를 터미널에 입력.

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

--- 

### 1.2 Homebrew 삭제
Homebrew를 잘못 설치해 삭제후 재설치 하려면 아래 코드를 터미널에 입력하면 된다.

    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"

---

## 2. zsh 설치

Homebrew 설치가 완료되면 zsh 설치가 가능해진다. 터미널에서 아래 코드를 입력하면 zsh이 설치된다.

    brew install zsh

---

## 3. 기존 bash를 zsh로 변경

zsh를 정상적으로 설치했다면, shell 등록을 하고 기존의 bash를 zsh로 변경한다. 아래 코드를 통해 zsh의 링크위치를 알아낸다. 

    $ which zsh

이후 시스템이 zsh를 인식할 수 있도록 아래 코드를 입력한다.

    sudo vi /etc/shells

아래 코드를 작성하면 shell을 zsh로 변경돼 새로운 쉘 환경을 사용할 준비가 된다.  

iterm2 또는 터미널을 재시작해 zsh이 정상적으로 작동하는지 확인한 다음, oh-my-zsh를 설치한다.

    $ chsh -s path/zsh

---

## 4. oh-my-zsh 설치

oh-my-zsh는 Robby Russell이 배포한 오픈소스 터미널 프레임워크다. 개발자들 사이에서 많이 쓰이는 테마는 agnoster 테마로 컬러 테마인 solarized dark에 가장 잘 어울린다.  
아래 코드를 입력해 oh-my-zsh를 설치한다.

    curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh

이후 oh-my-zsh를 사용하도록 아래 코드를 작성하면 zsh 사용을 위한 준비가 완료된다. 이 명령어를 실행하면  

> Changing shell for (Username).

이 뜨는데 자신의 Mac 비밀번호를 입력하면 된다.

    chsh -s /usr/local/bin/zsh

---

## 5. agnoster 테마 설정

### 5.1 zsh 테마 수정

테마를 설정하려면 zsh의 환경파일인 .zshrc를 수정하면 된다.  
아래 코드를 입력하면 

    open ~/.zshrc

.zshrc 파일이 텍스트편집기로 열린다.
내용 중간에 아래와 같은 문구가 있을 것이다.

> ZSH_THEME="robbyrussell"

여기서 ***robbyrussell*** 을 자신이 원하는 테마로 수정하면 된다. (oh-my-zsh 테마는 5.2에서 확인)

여기서는 가장 많이 사용하는 테마인 agnoster를 사용할 것이므로

> ZSH_THEME="agnoster"

라고 적어준다.

---

### 5.2 oh-my-zsh 테마 목록

oh-my-zsh 설치가 완료 됐다면 이제 테마를 설정할 시간이다. 
아래 링크를 따라 들어가면 oh-my-zsh에서 사용할 수 있는 테마들의 목록과 프리뷰를 볼 수 있다.  

링크 : [oh-my-zsh 테마](https://github.com/robbyrussell/oh-my-zsh/wiki/External-themes)

---

### 5.3 iterm2에 Solarized Dark 테마 설정

iterm2에 agnoster 테마와 잘 어울리는 Solarized Dark를 설정하는 방법이다. 

> cmd + ,  

를 눌러 설정 창을 연 후 아래와 같이 수행한다.

> Profiles -> Colors -> Color Presets... -> Solarized Dark를 선택 

그러면 배경색이 시안성 좋은 어두운 푸른색으로 바뀐다.

---

### 5.4 agnoster 테마로 인한 폰트깨짐 해결법

---

#### 5.4.1 Mac에 Meslo 파워라인 폰트 설치

테마에 따라서 폰트가 깨져 물음표로 나오는 경우가 있다. 
아래 코드를 iterm2에 입력하면 폰트가 깨지는 것을 확인 할 수 있다.

    echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699"

폰트가 깨지는 것을 확인했다면 터미널환경에서 깨지지 않는 폰트를 다운받아 적용하면 된다. 대표적으로 많이 쓰이는 폰트는 Meslo다. 아래 링크를 따라가서 폰트를 다운받으면 된다.  

링크에 들어가면 다양한 Meslo 폰트들이 있는데 여기서는 **Meslo LG S DZ Regular for Powerline.ttf** 를 적용했다.

링크 : [Meslo 폰트 다운](https://github.com/powerline/fonts/tree/master/Meslo%20Dotted)

---

#### 5.4.2 iterm2에 폰트 적용

Mac에 **Meslo LG S DZ Regular for Powerline.ttf** 를 설치했으면 이제 iterm2에 폰트를 적용해보자.

> cmd + ,  

를 눌러 설정 창을 연 후 아래와 같이 수행하면 폰트깨짐이 해결된다. 

> Profiles -> Text -> Change Font -> **Meslo LG S DZ Regular for Powerline** 를 선택 

---

## 6. 터미널에 표시되는 이름 삭제

iterm2를 실행하면 명령어 프롬프트에 아래와 같은 Mac 이름이 자리를 차지해 지저분해 보인다.

     peter@Peterui-MacBook-Pro

따라서 터미널에서 다음 코드를 작성해 .zshrc 텍스트창을 띄운 후

    open ~/.zshrc

파일 내용 맨 마지막에 아래 코드를 추가하면 **Peterui-MacBook-Pro** 의 이름이 삭제된다. (# <- 를 삽입하면 주석처리됨)

    prompt_context() {
      if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
      prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
      fi
    }

이름 전체를 삭제하려면 아래 코드를 작성하면 된다.

    prompt_context(){}


.zshrc 파일을 수정후 iterm2에서 아래 코드를 입력해 재실행하면 이름이 삭제된 것을 확인할 수 있다.

    source ~/.zshrc

---

## 7. 터미널 문법 강조

터미널에서 Homebrew를 통해 **zsh-syntax-highlighting**을 설치한다.

    brew install zsh-syntax-highlighting

.zshrc 텍스트창을 띄운 후

    open ~/.zshrc

파일내용 맨 마지막에 아래 코드를 삽입한다.

    source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

---

## 8. 멀티라인 사용과 커서 변경

쉘에서 긴 명령어를 입력할 때 화면이 작으면 명령 커서가 자꾸 오른쪽으로 밀려나는 현상이 발생한다. 특히 agnoster 테마는 싱글라인으로 표시되어 이러한 문제가 더 자주 발생한다. 이를 해결하려면 zsh를 멀티라인으로 바꿔줘야한다.  

iterm2에서 아래와 같이 입력해서 테마 디렉토리로 들어간다.

    cd ~/.oh-my-zsh/themes

이 디렉토리에는 oh-my-zsh 테마가 들어있다. 터미널에 **ls** 입력하면 테마가 죽 나열될 것이다.

    ls

리스트 중 맨 위에 **agnoster.zsh-theme**가 보일 것이다. cmd를 누른 상태에서 **agnoster.zsh-theme**를 클릭해 에디터창으로 연다.  

맨 아래를 보면 

    ## Main prompt
    build_prompt() {
        RETVAL=$?
        prompt_status
        prompt_virtualenv
        prompt_context
        prompt_dir
        prompt_git
        prompt_bzr
        prompt_hg
        prompt_end
    }

라고 써있을 것이다. 이 내용을 아래와 같이 변경한다.

    ## Main prompt
    build_prompt() {
        RETVAL=$?
        prompt_status
        prompt_virtualenv
        prompt_context
        prompt_dir
        prompt_git
        prompt_bzr
        prompt_hg
        prompt_newline # 멀티라인 적용
        prompt_end
    }

마지막으로 멀티라인을 적용하고 커서를 변경하려면 위 코드 아래에 다음과 같이 작성하면 된다.

    # 멀티라인 적용, 커버모양 변경
        prompt_newline() {
        if [[ -n $CURRENT_BG ]]; then
            echo -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR
        %(?.%F{$CURRENT_BG}.%F{red})❯%f"

        else
            echo -n "%{%k%}"
        fi

        echo -n "%{%f%}"
        CURRENT_BG=''
    }

---

## 참고 링크

- [Ulgoon's Blog](https://blog.ulgoon.com/my-dev-environment/)
- [꿈 많은 개발자가 되자](http://thdev.tech/mac/2016/05/01/Mac-ZSH-Install.html)
- [초보몽키의 개발공부로그](https://wayhome25.github.io/etc/2017/03/12/zsh-alias/)
- [totuworld's tech blog](http://totuworld.github.io/2016/04/08/zsh2line/)