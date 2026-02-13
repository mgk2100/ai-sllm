# sl-sw-sllm 실행 런북

## 선행 조건
- Python 3.10+
- GPU 학습 환경(학습 단계 수행 시)
- Azure OpenAI 자격정보(데이터 생성 단계 수행 시)

## 실행 명령어

### 의존성 설치
```bash
pip install -r requirements.txt
```

### GitHub 2025 데이터 필터링
```bash
bash github2025_data_filtering.sh 1500
```

### CPT 데이터 생성
```bash
bash cpt_data_create.sh
```

### SFT 데이터 생성 예시
```bash
bash preprocess/run_sft_example.sh
```

### CPT 학습(설정 기반)
```bash
python unsloth/train/cpt_train.py
```

## 주요 환경변수 키(값 제외)
- `AZURE_OPENAI_API_KEY`
- `AZURE_OPENAI_ENDPOINT`
- `AZURE_OPENAI_VERSION`

## 장애 시 확인 순서
1. 입력 데이터 경로(`data/...`) 존재 여부 확인
2. Azure OpenAI 환경변수 주입 상태 확인
3. 학습 시 GPU 메모리/드라이버 상태 확인
4. Hydra 설정 파일 경로와 파라미터 일치 여부 확인
