# Dot Mole Whack

Tactile Worlds와 DotPad 환경을 위한 접근성 반응속도 게임입니다.

5×4 격자에서 무작위로 나타나는 두더지를 화면, 키보드 또는 DotPad로 찾아 잡습니다. 연속 명중하면 콤보 보너스를 얻고, 두더지를 놓치면 생명이 줄어듭니다.

## 실행

- 게임: https://byeol-coder.github.io/dot-mole-whack/
- 임베드: https://byeol-coder.github.io/dot-mole-whack/?embed=1

별도의 빌드 과정은 없습니다. `main` 브랜치가 갱신되면 GitHub Actions가 GitHub Pages에 자동 배포합니다.

## 조작

| 입력 | 동작 |
| --- | --- |
| 방향키 | 커서 이동 |
| Enter / Space | 두더지 잡기 |
| H | 도움말 |
| R | 현재 상태 음성 안내 |
| N | 새 게임 |
| 화면의 칸 터치·클릭 | 해당 칸으로 이동하고 잡기 |

DotPad에서는 F1/F2로 좌우, F3/F4로 위아래 이동하고 전체 패닝키로 잡습니다.

## 접근성

- 실제 `TW_TTS` 스크립트 연결
- 서버 TTS 실패 시 브라우저 음성합성 폴백
- ARIA grid, 실시간 상태 영역, 키보드 포커스, 모달 포커스 지원
- `prefers-reduced-motion` 및 모바일·임베드 레이아웃 지원
- SDK나 기기가 없어도 화면·키보드·터치로 플레이 가능

## DotPad 연결

게임 화면에서 **닷패드 연결**을 누르면 Web Bluetooth 기기 선택 창이 열립니다.

필수 조건:

- HTTPS 환경
- Chrome 89+ 또는 Web Bluetooth를 지원하는 Edge
- 사용자의 직접적인 버튼 클릭
- Bluetooth가 켜진 DotPad
- 브라우저의 Bluetooth 권한 허용

게임은 DotPad Web SDK v3.0.0을 연결 시점에 동적으로 불러옵니다. 5×4 논리 보드를 기기의 실제 그래픽 셀 크기로 변환하고, 각 2×4 핀을 한 바이트로 인코딩해 출력합니다. SDK 로딩이나 기기 연결이 실패해도 일반 웹 플레이는 유지됩니다.

## Tactile Worlds 연동

`?embed=1`은 투명 배경과 압축 레이아웃을 적용합니다. 부모 프레임에는 다음 메시지를 전달합니다.

- `game-ready`
- `game-start`
- `game-complete`
