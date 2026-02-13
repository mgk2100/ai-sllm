# sl-sw-sllm 인벤토리 부록

## 디렉터리 트리 요약(Depth 2)
- `preprocess/`
- `unsloth/train/`
- `vLLM/embedding/`, `vLLM/sllm/`
- 루트 스크립트: `cpt_data_create.sh`, `github2025_data_filtering.sh`

## 기술 스택 근거
- LLM/오케스트레이션: `langchain`, `langchain-openai` (`requirements.txt`)
- 실험 설정: `hydra-core` (`requirements.txt`)
- 학습 코드: `unsloth/train/cpt_train.py`
- 환경변수 템플릿: `.env.example`

## 참고 파일
- `README.md`
- `requirements.txt`
- `.env.example`
- `github2025_data_filtering.sh`
- `cpt_data_create.sh`
- `preprocess/run_sft_example.sh`
- `unsloth/train/cpt_train.py`
