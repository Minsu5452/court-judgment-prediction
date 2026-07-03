# 법원 판결 예측 경진대회

[![Python](https://img.shields.io/badge/python-3.10-3776AB?logo=python&logoColor=white)](https://www.python.org) [![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

장문의 법률 판결문을 읽고 양 당사자 중 어느 쪽이 승소했는지 예측했습니다. 토크나이저 노이즈를 줄이는 전처리와 DeBERTa-v3 파인튜닝으로 데이콘 NLP 대회 리더보드 2위를 기록했습니다.

## 개요

| 항목 | 내용 |
| --- | --- |
| 대회 | 법원 판결 예측 AI 경진대회 |
| 기간 | 2023.06.05 – 2023.07.03 |
| 주최 / 주관 | 데이콘 / 데이콘 |
| 평가지표 | Accuracy |
| 결과 | 2위 |
| 과제 | 판결문 기반 승소 당사자 이진 분류 |
| 모델 | DeBERTa-v3 fine-tuning |

## 접근

- 장문 판결문에서 약어·구두점·복합 명사 패턴을 정리해 토크나이저 노이즈를 줄였습니다.
- spaCy 문장 분리와 길이 통계로 train/test 텍스트 분포를 점검했습니다.
- `nlpaug` 기반 데이터 증강을 실험해 학습 데이터의 다양성을 넓혔습니다.
- DeBERTa-v3를 파인튜닝해 최종 분류 모델을 만들었습니다.

## 저장소 구성

```text
.
├── notebooks/
│   └── spacy_deberta_v3_solution.ipynb
├── reports/
│   └── award_certificate.pdf
└── requirements.txt
```

## 수상 자료

- 수상 확인서: [`reports/award_certificate.pdf`](reports/award_certificate.pdf)

## 공개 범위

대회 원본 데이터, 전처리 CSV, 모델 가중치, 제출 파일은 포함하지 않았습니다. 데이터는 대회 참가자에게만 제공되어 그대로 재현하기는 어렵고, 저장소에는 접근 방식을 담은 노트북만 남겼습니다.

## 링크

- [대회 페이지](https://dacon.io/competitions/official/236112/overview/description)
- [최종 리더보드](https://dacon.io/competitions/official/236112/leaderboard)
- [코드 공유](https://dacon.io/competitions/official/236112/codeshare/8480)

## 라이선스

Apache License 2.0. 자세한 내용은 [LICENSE](LICENSE)에 있습니다.
