# MS의 리얼 리뷰 · 구매링크 허브

네이버 블로그 「MS의 리얼 리뷰」의 제품 구매링크를 모아 둔 모바일 우선 페이지입니다.
GitHub Pages로 서비스됩니다 → **https://kimmoonsu1993.github.io/**

## 구조

- **홈** — 프로필(MS의 리얼 리뷰 + 채널 링크)과 컬렉션 카드 목록
- **컬렉션** — `#tesla` : 테슬라 모델Y 모음 (출고기 #5 용품 21종 · 구매링크 32개)
  - 번호 검색(`5`, `⑭`), 카테고리 필터(수납·정리 / 충전·거치 / 외장·보호 / 실내·기타)
  - 아이템별 `알리` · `네이버` · `쿠팡` 링크 버튼
  - 딥링크: `https://kimmoonsu1993.github.io/#tesla/i14` → ⑭번 아이템으로 바로 이동

파일은 `index.html` 하나(HTML + CSS + 바닐라 JS, 빌드 없음)와 `.nojekyll` 뿐입니다.

## 아이템 추가·수정

`index.html` 안의 `ITEMS` 배열을 고치면 됩니다.

```js
{ no:"①", d:"1", cat:"c1", icon:"🗄️", name:"아이템 이름",
  desc:"한 줄 설명", note:"짧은 메모",
  links:[ L.ali("https://s.click.aliexpress.com/e/..."),
          L.naver("https://naver.me/...") ] }
```

- `no` 표시 번호, `d` 검색용 숫자(= 딥링크 `#tesla/i{d}`), `icon` 이모지
- `cat` 카테고리: `c1` 수납·정리 / `c2` 충전·거치 / `c3` 외장·보호 / `c4` 실내·기타
- 하위 품목이 여러 개면 `parts:[{name, sub, links:[...]}]`
- `note`에 `warn:true`를 주면 주의사항 색으로 표시됩니다.

## 새 컬렉션 추가

1. `index.html`의 `<section id="viewTesla">`를 복제해 `viewHawaii` 같은 섹션을 만들고
2. 홈의 `.collection` 카드(`href="#hawaii"`)를 하나 더 추가한 뒤
3. `route()`의 정규식(`/^tesla/`)에 새 컬렉션 이름을 넣습니다.

## 링크 원칙

- 제휴 URL은 **실제 발행된 블로그 글에 들어 있는 링크만** 사용합니다. 임의로 만들거나 고치지 않습니다.
- 제휴 링크에는 `rel="noopener noreferrer sponsored"`, 비제휴 상품 페이지에는 `sponsored`를 붙이지 않습니다.
- 대가성 고지는 홈과 컬렉션 하단에 표시합니다.

현재 수록 링크: 알리익스프레스 20 · 알리 비제휴 상품 페이지 1 · 네이버 쇼핑 10 · 쿠팡 1 = **32개**
