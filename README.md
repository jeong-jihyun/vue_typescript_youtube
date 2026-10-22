# vue_typescript_youtube

**유튜브 강좌를 따라 만든 "Hyrule Jobs"(젤다 세계관 구인 목록) Vue 3 + TypeScript 연습 프로젝트**입니다. (2025-01, Vue CLI 5)
직업 5개를 카드 목록으로 보여 주고, 버튼으로 **제목 / 급여 / 위치 순**으로 정렬합니다. 정렬이 바뀔 때 목록이 부드럽게 이동하는 효과(`transition-group`)가 들어 있습니다.

## 화면 구성

| 요소 | 내용 |
| --- | --- |
| 헤더 | 하트 아이콘 + `Hyrule Jobs`, 정렬 버튼 3개 (`order by title` / `salary` / `location`) |
| 목록 | 직업(농장 일꾼, 채석공, 플루트 연주자 등)별 제목·위치, 급여(루피 아이콘), 설명 글 |
| 정렬 | 선택한 기준으로 오름차순 정렬, 위에 `Ordered by …` 표시 |

## 코드 구성

| 파일 | 역할 |
| --- | --- |
| `src/App.vue` | 직업 데이터(`ref<Job[]>`)와 정렬 기준(`ref<OrderTerm>`) 관리, 버튼 이벤트 |
| `src/components/JobsList.vue` | 정렬된 목록 표시 (`computed`로 정렬, props 타입 지정) |
| `src/types/Job.ts` | 직업 데이터 형태 (`title`, `location`, `salary`, `id`) |
| `src/types/OrderTerm.ts` | 정렬 기준 형태 (`"location" \| "title" \| "salary"`) |
| `src/components/HelloWorld.vue` | Vue CLI 기본 파일 (화면에서 쓰지 않음) |
| `src/assets/` | 글꼴(Hylia Serif), 아이콘, 전역 CSS |

## 사용 기술

| 구분 | 내용 |
| --- | --- |
| 화면 | Vue 3.2+ (Composition API, `defineComponent`) |
| 언어 | TypeScript 4.5 |
| 개발 환경 | Vue CLI 5 (webpack, Babel, ESLint 7) |

## 실행 명령

| 명령 | 설명 |
| --- | --- |
| `yarn serve` | 개발 서버 (http://localhost:8080) |
| `yarn build` | 배포용 파일 생성 (`dist/`) |
| `yarn lint` | 코드 검사 |

## 실행 방법

```bash
git clone https://github.com/jeong-jihyun/vue_typescript_youtube.git
cd vue_typescript_youtube
yarn install
yarn serve
```

Node.js 22에서 `yarn install --frozen-lockfile`, `yarn build`, 린트(오류 0건)가 성공하는 것을 확인했습니다. (브라우저 화면은 확인하지 못했습니다.)

## 개선 내역 (2026-10)

| 구분 | 문제 | 수정 내용 |
| --- | --- | --- |
| 화면 오타 | 정렬 버튼 글자가 `order by titile` | `order by title`로 수정 |

## 앞으로 손보면 좋은 점

- 직업 설명 글은 모든 카드에 같은 `Lorem ipsum` 연습용 문장입니다.
- 직업 데이터가 `App.vue` 안에 고정되어 있습니다. 서버나 JSON 파일에서 가져오도록 바꾸면 실제 목록 앱이 됩니다.
- `HelloWorld.vue`와 `App.vue`의 주석 처리된 연습 코드를 정리하면 읽기 쉬워집니다.
- 테스트 코드가 없습니다.
