---
layout:	post
title: Remapping Alt_R to Hangul on Ubuntu
---

Tested environment: Ubuntu 20.04; IBus; Thinkpad X1C (7th)

Ubuntu에서 한국어 입력 수단으로 IBus Hangul을 사용해왔다.
Toggle key로는 `Alt_R`키를 설정하여 사용했는데, 언젠가부터 Chrome에서 `Alt_R`을
개별적으로 사용하기 시작했는지 toggle이 되지 않는 문제가 발생하였다.
이에 따라 toggle key를 `shift + space`로 바꿔서 몇 달간 사용해 왔는데,
이만저만 불편한게 아니다.
영문 또는 한글에서 shift를 필요로 하는 단어 (ex. FIFO, 예)와 `shift`를 이어서
빠르게 칠 때 의도치 않게 toggle이 발생하는 일이 흔히 발생했다.
결국 기존에 사용하던 `Alt_R` 키를 다시 사용하고자 문제를 다시 찾아봤는데,
오른쪽 Alt 키를 시스템에서 "Alt_R"으로 인식하기 때문이라고 한다.
이를 "Hangul"로 인식하게 만들어 주면 된다고 하는데, 인터넷에서 찾은 방법들
다들 몇 가지 맘에 안 드는 점이 있었다.

1. xmodmap을 사용한 방법  
시스템 재시작마다 리셋되지 않도록, `.xinitrc` 등을 통해 알아서 설정을 적용해주는
방법이 있다던데, 내 경우 제대로 작동하지 않았다.
우회적인 방법으로 시스템 시작 후 몇 초 sleep한 뒤 설정을 적용해주는
시작 프로그램을 등록하는 방법이 있는데, 이는 방식이 마음에 안 들었다.

2. altwin 파일을 직접 수정하는 방법  
`/usr/share/X11/xkb/symbols/altwin` 파일에서 `Alt_R`을 `Hangul`로 바꿔주는
방법이 있는데, 이런 내부 설정 파일을 유저가 건드리는 것은 좋은 방법이라
생각하지 않는다.
가능한 한 frontend tool을 사용하고 싶었다.

하지만 다른 방법을 찾을 수 없어, 2.의 방법을 임시로 사용하고 있었다.
그러다 오늘 `ctrl` - `caps lock` key swapping 방법을 찾아보다가
gnome-tweak-tool에서 `Alt_R`키를 `Hangul`키로 remapping하는 설정을
우연히 발견했다.

gnome-tweak-tool을 설치한 뒤, 다음 경로에서 설정할 수 있다.
```
tweaks > Keyboard & Mouse > Additional Layout Options >
Korean Hangul/Hanja keys > Make right Alt a Hangul key
```

만족스럽다.

참고로 `ctrl` - `caps lock` key swapping의 경우 다음 경로에서 설정 가능하다:
```
tweaks > Keyboard & Mouse > Additional Layout Options >
Ctrl position > Swap Ctrl and Caps Lock
```
