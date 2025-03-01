# Mapping the Fate of the Dead Korean
## Requirements
This project is to establish an website which provides overview for the human rights 
1) Overview - Human Rights in North Korea
    - Constitutional Law
    - Statistics Data (focused on health and welfare) - OpenAPI
      - Website: https://kosis.kr/bukhan/statisticsList/statisticsListIndex.do?menuId=M_01_01_01&vwcd=MT_BUKHAN&rootId=101_001&parmTabId=M_01_01_01
2) N

## Project Development Schedule

| Week | Goals | Details |
|------|-------|---------|
| 1월 24일 ~ 1월 30일 | 프로젝트 초기 설정 및 데이터 준비 | - 프로젝트 요구사항 분석 및 설계<br>- PDF 데이터를 구조화된 형식으로 변환<br>- 데이터 전처리 및 정리 |
| 1월 31일 ~ 2월 6일 | 백엔드(Spring Boot) 개발 시작 | - Spring Boot 프로젝트 생성<br>- 데이터베이스 설계 및 연동<br>- REST API 설계 및 구현 |
| 2월 7일 ~ 2월 13일 | 프론트엔드(React) 개발 시작 | - React 프로젝트 생성<br>- 공통 레이아웃 및 기본 UI 구성<br>- Spring Boot API와 연동 |
| 2월 14일 ~ 2월 20일 | Python AI 분석 시스템 구축 | - Flask/FastAPI로 Python API 구축<br>- 데이터 분석 및 시각화 기능 구현<br>- Python ↔ Spring Boot 통신 구축 |
| 2월 21일 ~ 2월 27일 | 데이터 시각화 통합 | - 데이터 시각화 구현 (차트, 지도)<br>- Python 분석 결과 React에 통합<br>- 사용자 인터랙션 추가 |
| 2월 28일 ~ 3월 5일 | 고급 기능 추가 및 최적화 | - 데이터 필터링 및 검색 기능 구현<br>- 머신러닝 모델 추가<br>- Spring Boot 성능 최적화 |
| 3월 6일 ~ 3월 12일 | 테스트 및 오류 수정 | - 단위 및 통합 테스트 수행<br>- 사용자 테스트 및 디버깅 |
| 3월 13일 ~ 3월 21일 | 최종 배포 및 문서화 | - Docker 기반 배포 준비<br>- 최종 문서화 및 배포 완료 |

## 1주차 (1월 24일 ~ 1월 30일): 프로젝트 초기 설정 및 데이터 준비
**목표:** 프로젝트 구조 설계 및 데이터 준비.

**세부 일정:**
- 프로젝트 요구사항 분석 및 전체 설계 확정.
- 폴더 구조 설정:
  - `frontend/`, `backend/`, `ai-services/` 디렉토리 생성.
- PDF 데이터를 CSV/JSON 등 구조화된 형식으로 변환:
  - Python의 `PyPDF2`, `pandas`를 사용하여 데이터 추출.
  - PDF 내 텍스트 데이터를 정리(예: 처형 장소, 암매장 위치, 증언 데이터).
- 데이터 전처리:
  - 데이터 정리 및 결측값 처리.
  - 주요 열(위치, 날짜, 사건 유형 등) 정의.

---

## 2주차 (1월 31일 ~ 2월 6일): 백엔드(Spring Boot) 개발 시작
**목표:** Spring Boot로 API 서버 설정 및 초기 데이터 연결.

**세부 일정:**
- Spring Boot 프로젝트 생성 및 기본 설정 (Maven 사용).
- Hibernate와 PostgreSQL 연동:
  - 초기 데이터베이스 테이블 설계 (JPA 엔티티 생성).
  - PDF에서 정리한 데이터를 데이터베이스에 삽입.
- REST API 설계 및 구현:
  - 데이터 조회 API (`/locations`, `/testimonies` 등).
  - 필터링 및 정렬 기능 추가.
- 테스트:
  - Postman 또는 Swagger를 통해 API 테스트.

---

## 3주차 (2월 7일 ~ 2월 13일): 프론트엔드(React) 개발 시작
**목표:** React 기반 기본 UI 구현.

**세부 일정:**
- React 프로젝트 생성 (Create React App 또는 Vite).
- 페이지 구성:
  - **홈 페이지:** 프로젝트 소개.
  - **대시보드 페이지:** 데이터를 시각화하는 공간.
- 초기 컴포넌트 생성:
  - 공통 레이아웃 (Header, Footer).
  - 데이터 테이블 컴포넌트.
- Spring Boot API 연동:
  - `Axios`를 사용해 백엔드 API와 통신.
  - 초기 데이터 표시 (테이블 형태).

---

## 4주차 (2월 14일 ~ 2월 20일): Python AI 분석 시스템 구축
**목표:** Python으로 데이터 분석 및 AI 기능 개발.

**세부 일정:**
- Flask/FastAPI로 Python API 서버 구축.
- 주요 기능 개발:
  - 데이터 분석: 처형 장소 및 암매장 패턴 분석.
  - 시각화: `Matplotlib` 및 `Plotly`를 사용해 그래프 생성.
- 데이터 전달:
  - Spring Boot -> Python -> Spring Boot의 통신 흐름 구현.
  - JSON 형식으로 분석 결과 반환.
- 테스트:
  - Python API를 Postman으로 테스트.

---

## 5주차 (2월 21일 ~ 2월 27일): 데이터 시각화 통합
**목표:** 프론트엔드에서 분석 결과를 시각화.

**세부 일정:**
- React에서 데이터 시각화 구현:
  - **차트:** `Chart.js` 또는 `Plotly`로 라인 차트, 바 차트 생성.
  - **지도:** `Leaflet` 또는 `Google Maps API`로 GIS 데이터 표시.
- 사용자 인터랙션 추가:
  - 특정 데이터를 클릭하면 세부 정보 표시 (Modal 또는 Popup).
- Python 분석 결과 통합:
  - React와 Python의 통신 결과를 실시간 반영.

---

## 6주차 (2월 28일 ~ 3월 5일): 고급 기능 추가 및 최적화
**목표:** 고급 기능 및 데이터 필터링/검색 기능 구현.

**세부 일정:**
- React에 데이터 필터링 기능 추가:
  - 날짜, 장소, 사건 유형별 필터링.
- Python 머신러닝 모델 통합:
  - 예측 모델 추가 (예: 잠재적 암매장 위치 예측).
- Spring Boot 성능 최적화:
  - API 캐싱 (Ehcache 또는 Redis 활용).
  - 요청 속도 최적화.

---

## 7주차 (3월 6일 ~ 3월 12일): 테스트 및 오류 수정
**목표:** 전체 시스템 테스트 및 오류 수정.

**세부 일정:**
- 단위 테스트:
  - React, Spring Boot, Python 각각의 단위 테스트 수행.
- 통합 테스트:
  - React ↔ Spring Boot ↔ Python 간 데이터 흐름 확인.
- 사용자 테스트:
  - 가상 사용자를 설정하고 실제 시나리오 실행.
- 최종 디버깅:
  - 성능 및 보안 문제 수정.

---

## 8주차 (3월 13일 ~ 3월 21일): 최종 배포
**목표:** 최종 배포 및 문서화.

**세부 일정:**
- 배포 준비:
  - Docker 컨테이너 설정 및 Docker Compose 파일 구성.
  - AWS, Heroku, 또는 Azure에 배포.
- 문서화:
  - README.md 작성 (프로젝트 개요, 설치 방법).
  - API 명세서 작성.
- 최종 점검:
  - 배포 후 사용자 경험 개선 작업.

---

## 산출물
- **1주차:** 정리된 데이터 (CSV/JSON).
- **2~3주차:** 백엔드 API 및 기본 프론트엔드.
- **4~5주차:** Python AI 분석 결과 및 통합.
- **6주차:** 고급 기능(필터링, 예측).
- **7~8주차:** 테스트 완료 및 배포된 웹사이트.