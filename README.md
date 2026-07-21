# Dot Mole Whack

Tactile Worlds와 DotPad 환경을 고려한 반응속도 기반 웹 게임 프로토타입입니다.

5×4 격자에서 무작위로 나타나는 두더지를 방향키로 찾아 `Enter` 또는 `Space`로 잡습니다. 점수와 콤보가 오르고, 두더지를 놓치면 생명이 줄어듭니다.

## 실행

별도 빌드 과정 없이 `index.html`을 브라우저에서 열면 실행됩니다.

- 방향키: 커서 이동
- Enter / Space: 두더지 잡기
- N: 새 게임
- `?embed=1`: Tactile Worlds 임베드 모드

## 접근성 및 연동

- `window.TW_TTS.speak()`이 있으면 플랫폼 음성 안내를 사용합니다.
- 플랫폼 밖에서는 콘솔 출력으로 대체됩니다.
- DotPad 버튼은 향후 Web Bluetooth SDK 연결 지점입니다.

## 배포

`main` 브랜치가 갱신되면 GitHub Actions가 GitHub Pages에 자동 배포합니다.
