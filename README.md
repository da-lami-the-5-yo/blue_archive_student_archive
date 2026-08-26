# 블루 아카이브 전교생 마스터 아카이브 (Blue Archive Master Archive)

## 📌 프로젝트 개요
넥슨게임즈의 학원 청춘 이야기 RPG **《블루 아카이브(Blue Archive)》**에 등장하는 **모든 학생(정식 출시 학생, 미출시 학생 후보, 미출시 시즈널 배리에이션 전원)**의 프로필, 소속 학원/동아리 계층 구조, 다국어 명칭(KR/EN/JP), 스탯/역할군 정보 및 **100% 검증된 고화질 공식 일러스트레이션**을 체계적으로 수집·정리한 통합 데이터베이스입니다.

---

## 📊 종합 통계
| 항목 | 수치 | 세부 내용 |
| :--- | :--- | :--- |
| **총 학생/시즈널 수** | **298명** | 키보토스 전원 1:1 디렉토리 매핑 완료 |
| ├ 정식 출시 학생 | **193명** | SchaleDB 원본 일러스트 3종(`official_portrait`, `collection`, `lobby`) 보유 |
| ├ 미출시 학생 후보 | **62명** | 총학생회, FOX 소대, 칠수인, 하이랜더, 와일드헌트 등 공식 인게임 스탠딩 CG 보유 |
| └ 미출시 시즈널 | **43명** | 파자마, 사복, 해적수영복, 우주전함 정장, 드레스 등 공식 스토리 스탠딩 CG 보유 |
| **총 저장 이미지 수** | **735장** | 전수 해시 검증 완료 (학생 간 혼입/중복 0건) |
| **비주얼 커버리지** | **97.0%** | 298명 중 289명 고해상도 공식 비주얼 보유 (미보유 9명은 뇌제 등 텍스트 언급 캐릭터) |

---

## 📁 디렉토리 구조 표준 (`School-Club-Student-Seasonal`)
```text
학교명/
  └── 동아리명/
        └── 학생명/
              └── 시즈널(기본/수영복/새해/정장/드레스 등)/
                    ├── info.json (다국어 메타데이터, 스탯, 프로필)
                    ├── 공식/ (SchaleDB 원본 포트레이트/로비/컬렉션 & 공식 스탠딩 CG)
                    ├── 준공식/
                    └── 비공식/
                          ├── rank00/
                          └── rank01/
```

---

## 🛠️ 이미지 품질 검증 및 결함 수정 (QA)
1. **타 캐릭터 이미지 혼입(Cross-Contamination) 전수 제거**:
   - 외부 booru 검색 엔진의 광역 폴백으로 인해 일부 미출시 학생 폴더에 중복 유입되었던 공용 이미지(63개 파일)를 전수 격리 및 영구 삭제.
   - MD5 해시 분석 결과, **서로 다른 학생 폴더 간 중복 파일 0건(100% 고유 에셋)**을 검증 완료.
2. **공식 원본 고해상도 에셋 1:1 매핑 다운로드**:
   - 정식 출시 193명 전원: SchaleDB 원본 Repository에서 추출한 `official_portrait.webp`, `official_collection.webp`, `official_lobby.webp` 직접 다운로드.
   - 미출시 학생 62명 및 미출시 시즈널 43명: 블루 아카이브 공식 게임 클라이언트 및 위키 아카이브의 공식 스탠딩 CG(`official_wiki_portrait.png`) 매핑 완료.
3. **반응형 웹 대시보드 (`index.html`)**:
   - 한국어, 영어, 일본어 다국어 실시간 검색.
   - 학원별 / 상태별(정식 출시, 미출시 학생, 미출시 시즈널) 원클릭 필터링.
   - 반응형 카드 및 고해상도 포트레이트 뷰어 제공.

---

## 🔗 GitHub 원격 저장소 및 백업 상태
- **원격 저장소**: `https://github.com/giyeopkim/blue_archive_student_archive`
- **푸시 완료 브랜치**:
  - `main`: 프로젝트 기본 문서 및 기반 구조 커밋 (`87d7b50`)
  - `feature/full-archive-expansion`: 298명 학생 디렉토리, 735개 공식 에셋, `index.html` 전체 커밋 (`8d80cb7`)
- **Pull Request 생성 링크**:
  - [👉 원클릭 Pull Request 열기 (feature/full-archive-expansion → main)](https://github.com/giyeopkim/blue_archive_student_archive/pull/new/feature/full-archive-expansion)
- **로컬 독립 Git 번들 파일**:
  - `/home/user/blue_archive_student_archive.bundle` (80 MB, 모든 커밋과 브랜치 포함)
