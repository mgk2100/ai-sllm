# sl-sw-sllm 아키텍처 분석

## 상위 컴포넌트
- `preprocess/`: 데이터 필터링 및 SFT/CPT 데이터 생성 스크립트
- `unsloth/train/`: LoRA 기반 CPT 학습 코드
- `vLLM/`: 임베딩/서빙 관련 예시 구성
- 루트 shell 스크립트: 배치형 실행 엔트리

## 런타임 구성
- Python 스크립트 실행 환경(venv 기반)
- 주요 라이브러리: `langchain`, `langchain-openai`, `hydra-core`
- 외부 연동: Azure OpenAI 환경변수(`.env.example`)

## 주요 엔트리포인트
- `preprocess/filtering_github2025.py`
- `preprocess/make_autosar_cpt_data.py`
- `preprocess/sft_data_generate.py`
- `unsloth/train/cpt_train.py`
- `cpt_data_create.sh`, `github2025_data_filtering.sh`

## 데이터/요청 흐름 요약
1. 전처리 스크립트가 원천 코드/데이터를 필터링 및 JSON 데이터셋으로 변환
2. 생성된 데이터셋을 학습 스크립트(`cpt_train.py`) 입력으로 사용
3. 학습 산출물을 저장하고 추후 vLLM 계층에서 활용 가능한 형태로 연계
