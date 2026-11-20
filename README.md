<p align="center">
  <img src="assets/ui-ux-skill-banner.png" alt="UI/UX Skill — macOS 원칙을 바탕으로 한, 프레임워크와 무관한 데스크톱 UI/UX 스킬" width="560">
</p>

<p align="center"><b>한국어</b> · <a href="README.en.md">English</a></p>

# UI/UX Skill

Codex나 Claude Code에게 데스크톱 앱 화면을 맡길 때, 창 동작·작업 흐름·접근성·검증까지 같이 챙기게 하는 작은 스킬이에요.

기준은 Apple macOS Human Interface Guidelines이고, SwiftUI든 Qt든 Electron이든 구현 기술은 나중에 정해도 돼요.
규칙을 긴 지침 하나로 두지 않고 300자도 안 되는 모듈 여섯 개로 쪼갰어요. `SKILL.md`는 "언제 어느 모듈을 읽을지"만
알려 주고, 에이전트는 지금 단계에 필요한 것만 읽으니까 문맥을 적게 써요. 일곱 파일을 다 읽어도 1,048자예요.

- `macos.md`, `research.md` — 기본. 데스크톱 원칙, 그리고 Refero·Mobbin·Uiverse에서 비슷한 화면을 찾아 고른 이유 적기
- `flow.md`, `visual.md` — 빈 상태·로딩·오류·완료·되돌리기, 위계와 아이콘. "hover만으로 기능을 숨기지 않기"처럼 화면을 보고 지켰는지 알 수 있게 썼어요
- `platforms.md` — 기술과 상관없는 명세를 먼저 쓰고, 대상 환경의 기본 컴포넌트로 옮기기
- `verify.md` — 작은 창, 다크 모드, 큰 글자, 키보드, 스크린리더, 대비를 확인하고 핵심 작업을 직접 해 보기

참고 조사는 [Refero](https://refero.design/ios-apps), [Mobbin](https://mobbin.com/), [Uiverse](https://uiverse.io/)에서 하고,
기준은 [Apple macOS HIG](https://developer.apple.com/design/human-interface-guidelines/designing-for-macos/)예요.
모바일 화면은 데스크톱에 맞게 다시 설계하고, 참고한 화면이나 자산을 그대로 베끼지는 않게 했어요.

## 적용 데모

스킬을 적용해서 만든 작업 목록 데모 **Relay · 데모**예요. 넓은 창에선 사이드바, 좁은 창에선 가로 탭이 되고,
시스템 다크 모드와 움직임 줄이기를 따라가요. 데이터는 메모리에만 있어서 새로고침하면 처음으로 돌아가요.

<p align="center">
  <img src="preview-desktop.png" alt="Relay · 데모의 밝은 모드 넓은 창. 왼쪽 사이드바와 오늘 할 일 목록, 오늘 진행률 카드" width="100%">
</p>

<table>
  <tr>
    <td width="62%"><img src="preview-dark.png" alt="같은 화면을 시스템 다크 모드로 본 모습" width="100%"></td>
    <td width="38%"><img src="preview-small.png" alt="좁은 창에서 사이드바가 오늘, 전체, 완료 가로 탭으로 바뀐 모습" width="100%"></td>
  </tr>
</table>

## 설치

같은 폴더를 Codex와 Claude Code에서 그대로 써요.

```bash
# Codex: $CODEX_HOME/skills/ui-ux-skill (기본값은 아래), 요청에 $ui-ux-skill을 붙여서 호출
git clone https://github.com/lsy041015/ui-ux-skill.git ~/.codex/skills/ui-ux-skill

# Claude Code 전역 (Windows: %USERPROFILE%\.claude\skills\ui-ux-skill)
git clone https://github.com/lsy041015/ui-ux-skill.git ~/.claude/skills/ui-ux-skill

# 또는 프로젝트 전용
git clone https://github.com/lsy041015/ui-ux-skill.git .claude/skills/ui-ux-skill
```

Claude Code에선 새 세션부터 데스크톱 UI/UX 요청에 알아서 불러오고, `/ui-ux-skill`로 직접 부를 수도 있어요.
업데이트는 받은 폴더에서 `git pull`이면 돼요.

예: “`$ui-ux-skill`을 사용해 할 일 관리 앱의 데스크톱 화면을 설계하고, 키보드와 작은 창 동작까지 검토해줘.”

## 아쉬운 점

버전 표기나 테스트는 없고, 데모 소스 코드도 저장소에 없어요(스크린샷만 있어요). 참고 조사는 외부 사이트 세 곳에
접속돼야 하고, 안 되면 에이전트가 그렇다고 말하는 데서 끝나요. 라이선스 파일은 없어요.

<sub>[다른 프로젝트 보기](https://github.com/lsy041015)</sub>
