# Excel2JSON

Excel 파일을 JSON 형식으로 변환하는 도구입니다.

## 개요

Excel(.xlsx) 파일을 읽어서 JSON 형식으로 변환합니다. 여러 시트가 있는 경우 특정 시트를 선택하여 변환할 수 있습니다.

## 주요 기능

- Excel 파일을 JSON으로 변환
- 특정 시트 선택 가능
- 한글 인코딩 지원 (UTF-8-sig)
- 날짜/시간 자동 변환

## 사용 방법

```bash
python excel2json.py [옵션] <source_file.xlsx>
```

### 옵션

- `-f, --force`: 기존 파일 덮어쓰기
- `-o, --outfile`: 출력 파일 경로 지정
- `-s, --sheet`: 변환할 시트 이름 지정
- `-q, --quiet`: 조용한 모드

### 예제

```bash
# 기본 변환
python excel2json.py xls/NutrientsByFood.xlsx

# 특정 시트 변환
python excel2json.py -s 20221208 xls/NutrientsByFood.xlsx

# 출력 파일 지정
python excel2json.py -o output.json xls/NutrientsByFood.xlsx
```

## 요구사항

- Python 3.12
- pandas
- openpyxl
- simplejson

## 설치

### uv 설치

#### Windows
```powershell
# PowerShell에서 실행
irm https://astral.sh/uv/install.ps1 | iex
```

#### macOS / Linux
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

설치 후 터미널을 재시작하거나 다음 명령어로 PATH에 추가:
```bash
export PATH="$HOME/.cargo/bin:$PATH"
```

### 가상환경 설정

```bash
# Python 3.12 가상환경 생성
uv venv --python 3.12

# 가상환경 활성화
# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate
```

### 패키지 설치

```bash
# uv를 사용한 패키지 설치
uv pip install -r requirements.txt
```

## 파일 구조

- `excel2json.py`: 메인 변환 스크립트
- `xls/`: 예제 Excel 파일 디렉토리

## 출력 형식

JSON 파일은 각 행을 딕셔너리로 변환한 배열 형식으로 저장됩니다.

```json
[
  {
    "컬럼1": "값1",
    "컬럼2": "값2"
  },
  ...
]
```

---

해당 프로젝트는 Examples-Python의 Private Repository에서 공개 가능한 수준의 소스를 Public Repository로 변환한 것입니다.

