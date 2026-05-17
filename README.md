# 온기록 On-record

요양보호사가 행정 기록에 묶이지 않고 돌봄에 집중할 수 있도록 돕는 방문돌봄 기록 보조 프로토타입입니다.

현장 음성, 일정, 보호 이벤트를 바탕으로 돌봄 일지를 구조화하고, 기관 관리자·간호사·복지사·가족에게 필요한 형태로 보고서를 재구성하는 흐름을 데모합니다.

Production: https://idea-black-two.vercel.app

## Prototype

| 기관 관리자 화면 | 요양보호사 앱 |
| --- | --- |
| <img src="assets/readme/admin-dashboard.jpg" alt="기관 관리자 대시보드" width="100%"> | <img src="assets/readme/worker-app.jpg" alt="요양보호사 모바일 앱" width="100%"> |

## Why

방문돌봄 현장에서는 두 손과 시선이 항상 어르신에게 향합니다. 하지만 식사량, 정서 변화, 복약, 위험 상황은 팀 전체가 공유해야 하는 중요한 정보입니다.

온기록은 “두 손은 어르신께, 기록은 AI가”라는 방향으로 설계했습니다. 동의된 근무 시간 안에서 돌봄에 필요한 정보만 정리하고, 불필요한 사생활 정보는 남기지 않는 기록 보조 도구를 목표로 합니다.

## Key Flow

```mermaid
flowchart LR
  A["출근 및 동의 확인"] --> B["방문 중 음성 기록"]
  B --> C["AI 체크리스트 생성"]
  C --> D["요양보호사 검토 및 수정"]
  D --> E["역할별 보고서 재구성"]
  E --> F["기관·간호사·복지사·가족 공유"]
  B --> G["위험 신호 감지"]
  G --> H["보호 모드 및 증거 기록"]
```

## Core Features

- 음성 기반 돌봄 기록 구조화
- 식사, 복약, 정서 변화, 서비스 제공 항목 체크리스트화
- 간호사·사회복지사·가족 등 수신자별 보고서 재구성
- 민감정보 마스킹과 전송 전 보호사 검토
- 폭언·충돌 상황 감지 시 보호 모드와 증거 기록 시뮬레이션
- 기관 관리자용 보고서·보호 이벤트 대시보드

## Architecture

```mermaid
flowchart TB
  subgraph Worker["요양보호사 앱"]
    W1["출근/동의"]
    W2["방문 기록"]
    W3["체크리스트"]
    W4["보고서 전송"]
  end

  subgraph DemoAI["데모 AI 레이어"]
    A1["음성 기록 변환"]
    A2["식이·복약 알림"]
    A3["민감정보 마스킹"]
    A4["보호 이벤트 판단"]
  end

  subgraph Admin["기관 관리자"]
    M1["오늘 현황"]
    M2["보고서 수신함"]
    M3["보호 이벤트"]
    M4["인력·수급자 관리"]
  end

  Worker --> DemoAI --> Admin
```

현재 구현은 정적 HTML 프로토타입입니다. 실제 백엔드, 인증, 저장소, 모델 호출은 연결하지 않았고 발표용 흐름과 인터랙션을 중심으로 구성했습니다.

## Project Structure

```text
.
├── index.html          # 화면, 스타일, 데모 데이터, 인터랙션
├── voice/              # 음성 안내 및 보호 이벤트 데모 자산
├── assets/readme/      # README 화면 캡처
├── vercel.json         # Vercel 정적 배포 설정
└── .github/            # 이슈, PR, 검증 워크플로우
```

기획 및 GUI 참고 문서는 로컬 `docs/`에 보관하며, 공개 저장소에는 포함하지 않습니다.

## Local Preview

```bash
python3 -m http.server 4173
```

```text
http://127.0.0.1:4173
```

## Deployment

GitHub `main` 브랜치가 Vercel에 연결되어 있습니다.

```bash
git pull origin main
git add .
git commit -m "Update prototype"
git push origin main
```

`main`에 push하면 Vercel production 배포가 자동으로 갱신됩니다.
