# Cover Entry Design

## Goal

Add a cover entry page that lets users choose which OY service image review tool to open. The current app opens directly into the 올영매장 banner review tool; after this change, users should first see a simple Notion-like hub with cards for 올영매장 and 올리브베러.

## Scope

- Add a cover page titled "이미지 검수 도구 모음".
- Keep the existing 올영매장 review tool intact and reachable from the cover page.
- Add an 올리브베러 entry that is clickable and opens an empty placeholder review screen.
- Do not implement 올리브베러 validation logic in this branch.
- Preserve the current static single-file app architecture.

## UX Writing

### Cover Header

```text
이미지 검수 도구 모음

OY 서비스 상품 이미지, 배너 등 제작 전, 유형별 기준을 빠르게 확인하고 이미지를 검수할 수 있는 도구예요.
아래에서 검수할 서비스를 선택해주세요.
```

### Notice

```text
💡 작업 전 꼭 확인해주세요
1. 서비스별 배너 가이드는 서로 다를 수 있어요.
2. 작업 중인 서비스에 맞는 검수 도구를 선택해주세요.
3. 검수 결과는 제작 전 확인용이에요. 최종 업로드 전 운영 가이드를 함께 확인해주세요.
```

### Feedback

```text
📞 피드백 및 문의
올영매장 담당자: 김보라 / 올리브베러 담당자: 심다희 · 박지현
팀: 커머스 프로덕트 디자인팀
피드백: 슬랙 DM
```

### Cards

```text
올영매장 배너 검수

올영매장에 노출되는 스토어 썸네일과 증정품 이미지를 검수 · 제작할 수 있는 도구예요.

검수 도구로 이동하기 →
```

```text
올리브베러 배너 검수

올리브베러 상품 이미지를 검수 · 제작할 수 있는 도구예요.

검수 도구로 이동하기 →
```

## Layout

The cover page should follow the referenced Notion cover style:

- White page background.
- Large bold page title.
- Short description below the title.
- Plain notice and feedback text blocks.
- Two-column card grid on desktop.
- Single-column card list on narrow screens.
- Cards use light borders, generous padding, and minimal decoration.

## Card Interaction States

Each service card should have clear interactive states:

- Default: white background, light border, neutral text.
- Hover: slightly darker border, subtle shadow or lift, link text darkens.
- Pressed: card visually compresses or shadow reduces.
- Selected: after navigation, the active service card or current screen state should be distinguishable if the user returns to the cover or if a persistent header/nav is shown.

The selected state should be understated, using a stronger border and subtle background tint rather than a heavy filled treatment.

## Navigation

- Initial app state: show the cover page.
- Clicking "올영매장 배너 검수" opens the existing review tool.
- Clicking "올리브베러 배너 검수" opens a placeholder page.
- Each service page should provide a simple way to return to the cover page.

## Olivebetter Placeholder

The 올리브베러 placeholder should be intentionally empty and implementation-ready:

- Show the service title.
- Use a short message indicating that the tool area is ready for future implementation.
- Avoid "준비중" language on the cover card, because the user requested that the card be clickable.

## Technical Notes

- Keep the implementation inside `index.html`.
- Add a lightweight screen state such as `cover`, `oy-store`, and `olivebetter`.
- Avoid changing the existing validation logic unless needed to hide/show it correctly.
- Preserve current tab states inside the 올영매장 tool.
- Keep the README link issue in mind when this branch is later merged: `origin/main` has the newer GitHub Pages URL.

## Verification

- Opening the app shows the cover page first.
- 올영매장 card opens the existing tool and existing tabs still work.
- 올리브베러 card opens the placeholder page.
- Return-to-cover navigation works from both service pages.
- Card default, hover, pressed, and selected states are visible.
- Layout remains usable on desktop and mobile widths.
