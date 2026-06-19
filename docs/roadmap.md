# 📊 pandas 학습 로드맵

> 목표: **기초부터 실무 데이터 분석까지** — Series/DataFrame 기본기부터 입출력, 정제, 그룹 연산, 시계열, 시각화까지 단계별로 익힌다.

- **버전**: pandas 3.0.3 / numpy 2.4.6 / Python 3.13+
- **실습 환경**: Jupyter (dev 의존성에 포함)
- 각 단계는 `학습 → 실습 노트북 → 미니 과제` 순으로 진행하는 것을 권장한다.

---

## 0. 준비 단계

- [ ] 가상환경(`.venv`) 및 의존성 확인 (`pandas`, `numpy`, `jupyter`)
- [ ] Jupyter Lab/Notebook 실행 확인
- [ ] 실습용 디렉터리 구조 잡기 (`notebooks/`, `data/`)
- [ ] pandas / numpy import 컨벤션 익히기 (`import pandas as pd`, `import numpy as np`)

---

## 1. 자료구조 기초 (Foundations)

**핵심 개념**: pandas의 두 축인 `Series`와 `DataFrame`을 이해한다.

- [ ] `Series` — 1차원 라벨 배열, 인덱스 개념
- [ ] `DataFrame` — 2차원 테이블, 행/열/인덱스
- [ ] `Index` 객체와 라벨 vs 위치 구분
- [ ] dtype 이해 (int, float, object, category, datetime, **nullable / Arrow 백엔드**)
- [ ] `pd.NA`, `NaN`, `None`의 차이 (pandas 3.0 기준)

> 💡 pandas 3.0부터 문자열 기본 dtype이 PyArrow 기반으로 바뀌는 등 변화가 있으니 버전별 차이에 유의.

---

## 2. 데이터 입출력 (I/O)

**핵심 개념**: 다양한 소스에서 데이터를 읽고 쓴다.

- [ ] CSV: `read_csv` / `to_csv` (구분자, 인코딩, `dtype`, `parse_dates`)
- [ ] Excel: `read_excel` / `to_excel`
- [ ] JSON / Parquet (`read_parquet` — 대용량·실무 표준)
- [ ] 클립보드, SQL (`read_sql`) 맛보기
- [ ] 읽기 옵션 튜닝 (`nrows`, `usecols`, `chunksize`)

---

## 3. 인덱싱 & 선택 (Indexing & Selection)

**핵심 개념**: 원하는 데이터를 정확히 골라낸다.

- [ ] `[]`, `.loc[]`, `.iloc[]` 차이와 사용법
- [ ] 불리언 인덱싱 (조건 필터링)
- [ ] `query()` 메서드
- [ ] `isin()`, `between()`
- [ ] `set_index()` / `reset_index()`
- [ ] MultiIndex (계층적 인덱스) 기초

---

## 4. 데이터 정제 (Cleaning)

**핵심 개념**: 지저분한 실데이터를 분석 가능한 형태로 만든다.

- [ ] 결측치 처리: `isna()`, `dropna()`, `fillna()`, `interpolate()`
- [ ] 중복 처리: `duplicated()`, `drop_duplicates()`
- [ ] 타입 변환: `astype()`, `to_numeric()`, `to_datetime()`
- [ ] 문자열 처리: `.str` 접근자 (`split`, `replace`, `contains`, 정규식)
- [ ] 이상치(outlier) 탐지/처리
- [ ] `rename()`, 컬럼 정리

---

## 5. 변형 & 연산 (Transformation)

**핵심 개념**: 데이터를 가공하고 파생 변수를 만든다.

- [ ] `apply()` / `map()` / `applymap`(→`map`) 차이
- [ ] 벡터화 연산 vs 반복문 (성능 관점)
- [ ] `assign()`으로 파생 컬럼 추가
- [ ] `cut()`, `qcut()` — 구간화/범주화
- [ ] 정렬: `sort_values()`, `sort_index()`, `rank()`

---

## 6. 그룹 연산 (GroupBy)

**핵심 개념**: "분할-적용-결합(split-apply-combine)" 패턴.

- [ ] `groupby()` 기본
- [ ] 집계: `agg()`, 다중 집계, named aggregation
- [ ] `transform()` vs `apply()` vs `filter()`
- [ ] `pivot_table()`, `crosstab()`
- [ ] `value_counts()`, `nunique()`

---

## 7. 결합 (Combining Data)

**핵심 개념**: 여러 데이터셋을 하나로 합친다.

- [ ] `concat()` — 행/열 방향 이어붙이기
- [ ] `merge()` — SQL 스타일 조인 (inner/left/right/outer)
- [ ] `join()` — 인덱스 기반 결합
- [ ] 키 충돌, suffix, indicator 옵션
- [ ] 와이드 ↔ 롱 변환: `melt()`, `pivot()`, `stack()` / `unstack()`

---

## 8. 시계열 (Time Series)

**핵심 개념**: 날짜/시간 데이터를 다룬다.

- [ ] `datetime` 인덱스, `date_range()`
- [ ] 리샘플링: `resample()` (업/다운샘플링)
- [ ] 이동 통계: `rolling()`, `expanding()`, `shift()`
- [ ] 시간대(timezone) 처리
- [ ] `.dt` 접근자

---

## 9. 시각화 (Visualization)

**핵심 개념**: 분석 결과를 그림으로 본다.

- [ ] `DataFrame.plot()` 기본 (matplotlib 백엔드)
- [ ] 라인/바/히스토그램/박스/산점도
- [ ] 그룹별 시각화
- [ ] (선택) seaborn 연계

---

## 10. 성능 & 실무 팁 (Performance & Best Practices)

**핵심 개념**: 크고 느린 데이터를 효율적으로.

- [ ] 메모리 절약: `category` dtype, downcasting
- [ ] 벡터화 / `eval()` / `query()`
- [ ] `chunksize`로 대용량 처리
- [ ] 메서드 체이닝 & `pipe()`로 가독성 높은 파이프라인
- [ ] Copy-on-Write (pandas 3.0 기본 동작) 이해
- [ ] PyArrow 백엔드 활용

---

## 🎯 종합 프로젝트 (Capstone)

학습 마무리로 실제 데이터셋 하나를 골라 전 과정을 적용한다.

- [ ] 데이터 수집 → 정제 → 탐색적 분석(EDA) → 시각화 → 인사이트 정리
- [ ] 추천 데이터셋 예: Titanic, NYC Taxi, 공공데이터포털 CSV 등

---

## 📚 참고 자료

- [pandas 공식 문서](https://pandas.pydata.org/docs/)
- [10 minutes to pandas](https://pandas.pydata.org/docs/user_guide/10min.html)
- [pandas Cookbook](https://pandas.pydata.org/docs/user_guide/cookbook.html)
