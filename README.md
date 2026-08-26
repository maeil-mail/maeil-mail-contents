# maeil-mail-contents

매일메일(`maeil-mail.kr`) 기술 면접 질문 콘텐츠 아카이브입니다.
사이트의 question 1~311번(결번 9개 제외, **총 302문항**)을 프론트엔드/백엔드로 나누고,
다시 세부 카테고리 폴더로 분류해 보관합니다.

각 문서 상단에는 원본 질문 제목과 출처 URL이 프론트매터로 기록되어 있습니다.

```yaml
---
title: 'OSIV(Open Session In View) 옵션에 대해서 설명해주세요.'
category: backend
subcategory: spring
questionId: 1
source: https://www.maeil-mail.kr/question/1
---
```

## 목차

| 구분 | 파일 ID 기준 | 카테고리 기준 |
|---|---|---|
| Frontend | [frontend/toc.md](./frontend/toc.md) | [frontend/toc-category.md](./frontend/toc-category.md) |
| Backend | [backend/toc.md](./backend/toc.md) | [backend/toc-category.md](./backend/toc-category.md) |

## 폴더 구조

### Backend (152문항)

| 폴더 | 주제 | 문항 수 |
|---|---|---|
| [`backend/database/`](./backend/database/) | Persistence와 데이터베이스 | 25 |
| [`backend/network/`](./backend/network/) | 네트워크, HTTP와 웹 인프라 | 25 |
| [`backend/os/`](./backend/os/) | 운영체제, 동시성과 런타임 | 23 |
| [`backend/java/`](./backend/java/) | 자바 언어, 컬렉션과 자료구조 | 21 |
| [`backend/spring/`](./backend/spring/) | Spring과 애플리케이션 계층 | 21 |
| [`backend/infrastructure/`](./backend/infrastructure/) | 분산 시스템, 캐시와 운영 인프라 | 17 |
| [`backend/testing/`](./backend/testing/) | 테스트, 보안과 관측 가능성 | 11 |
| [`backend/architecture/`](./backend/architecture/) | 아키텍처, 객체지향과 설계 패턴 | 9 |

### Frontend (150문항)

| 폴더 | 주제 | 문항 수 |
|---|---|---|
| [`frontend/javascript/`](./frontend/javascript/) | JavaScript 기초와 런타임 | 31 |
| [`frontend/typescript/`](./frontend/typescript/) | TypeScript, 번들링과 생태계 도구 | 22 |
| [`frontend/react/`](./frontend/react/) | React 핵심 개념과 렌더링 | 21 |
| [`frontend/browser/`](./frontend/browser/) | 브라우저, DOM과 Web API | 20 |
| [`frontend/network/`](./frontend/network/) | 네트워크, 보안과 캐싱 전략 | 20 |
| [`frontend/css/`](./frontend/css/) | CSS, UI와 사용자 경험 | 16 |
| [`frontend/nextjs/`](./frontend/nextjs/) | Next.js와 현대적인 React 아키텍처 | 14 |
| [`frontend/testing/`](./frontend/testing/) | 테스트, 품질과 협업 판단 | 6 |

## 파일 이름 규칙

`be-N.md` / `fe-N.md`의 `N`은 이 저장소가 백엔드/프론트엔드별로 매긴 순번이며, 매일메일 사이트의 question ID와는 다릅니다.
두 값의 대응 관계는 각 `toc.md`의 `원본` 열과 문서 프론트매터의 `questionId`에서 확인할 수 있습니다.
