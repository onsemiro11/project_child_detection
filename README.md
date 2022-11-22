# project_child_detection

### 주제: 어린이 존재여부 파악 후, 운전자에게 먼저 알러주는 서비스

[프로젝트 과정]

1. 데이터 수집 : AIhub 사이트에서 데이터를 가져옴.
2. 전처리
   - 데이터 용량이 커서 주제에 가장 관련이 있는 데이터만 남기고 모두 삭제하여 용량 최소화 진행
   - 분석을 하기 위해 json 파일에 있는데 영상데이터의 정보들을 frame단위로 캡쳐
   - frame에 맞는 json 정보를 가져와서 child를 1, adult를 0으로 하여 encoding을 진행.
3. 분석 & 결과
  
(SSD- Single Shot multibox Detector)
  - import libraries
  - 데이터 경로 작성
  - make vgg
  - make extras
  - loc 및 conf 모듈 구현
  - L2 Norm
  - DBox
  - SSD 모델 설립
  - Decode
  - nm_supperession
  - Detect
  - Multi Box Loss : 평가지표 결과 추출
  - 어린이 어른 데이터셋 구현
  - 신경망 구현
  - 손실함수 구현 및 학습
  
(Yolo v5 - You only look once)
  - 모델을 진행하기 전에 Yolo 좌표로 변환해주는 과정 진행
  - yaml 파일 작성
  - 모델 구현
  - tensorboard로 결과값 확인
  - webcam으로 분석 결과 확인
