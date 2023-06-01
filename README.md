# opensw23-ten
Text-To-Speech project
## Team Introduction
  김영준 : 201911162 리더  
  박상준 : 201911173 코더  
  신민석 : 202011316 github expert  
  김수형 : 202211276 발표자  
## Topic Introduction
### References
https://github.com/fatchord/WaveRNN

저희가 선택한 오픈소스는 TTS입니다.

- TTS(Text to Speech)는 '음성합성'으로 일정한 음성 단위로 분할한 후 입력받은 텍스트를 따라 필요한 음성단위들을 이어 붙여 말소리를 인위적으로 만들어 내는 기술입니다.
- python quick_start.py -u --input_text "샘플 텍스트" 커맨드를 사용해 사용자가 입력한 샘플 텍스트를 음성으로 바꿔줍니다.  
- 자신만의 모델을 트레이닝 시킬 수 있습니다.

샘플데이터를 사용한 Result는 아래와 같습니다.
## Results
https://opensw23-ten.github.io/sample/
### Inputs
- 주의 사항  
1. 특정 브라우저(크롬 등)에서 실행 시, 정책에 의해 음소거되어 있을 수 있어 음소거 해제 후 청취 가능합니다.
2. 해당 예시 파일은 readme.md에 업로드하기 위해 확장명이 .mp4로 변경되었음을 알려드립니다. (기존 확장명 : .wav)
#### Hello my name is konkuk.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/7d2a7afc-7bce-4fec-84d9-07269d3846c3
#### Hello, we are majoring computer science.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/940604f4-d15b-4795-98f6-31e2275fee3b
#### Today is June first.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/499bba74-2bab-45f6-8426-27ea118e4cc4
#### Topic of this class is opensource.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/d77f7c28-01f2-466f-b6c9-4a4d76c3be62
#### We are opensource software team ten!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/7354ab80-2703-4a96-a377-1e1d4fa916e0
#### This is the result of sample text!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/c7c2cb7f-b8ec-40fd-904d-decd95ef4499
#### 안녕하세요! 저희 팀 이름은 TEN입니다.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/cf28a3dd-3d8e-4dc6-9344-d8568cf341e6
#### 배가 너무 고파요!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/1dfa34d3-757a-4c86-88aa-4d3b88d2ee22

## Analysis/Visualization

## Installation  
### Requirements
OS : Windows 10 이상, Linux Ubuntu 20.04 버전 실행 확인  
Python 버전 3.6 이상, 3.8 이하  
Pytorch 1 이상 With CUDA
- 아래 명령어로 [Pytorch 설치](https://pytorch.org/get-started/previous-versions/)  
```
pip install torch==2.0.0+cu118 torchvision==0.15.1+cu118 torchaudio==2.0.1 --index-url https://download.pytorch.org/whl/cu118  
```

- 아래 명령어로 나머지 모듈 설치  
```
pip install -r requirements.txt  
```
만약 설치 중 오류가 발생한다면
1. 'numba'패키지가 설치되어 있는지 확인합니다. 만약 설치가 안되어 있다면 아래 명령어를 통해 설치를 합니다.
```
pip install numba
```
2. 다음 명령어를 통해 'numba'패키지가 제대로 설치되었는지 확인합니다.
```
pip show numba
```
3. 만약 패키지가 설치되어 있었다면 버전 문제가 있을 수 있으므로 최신 버전으로 업데이트합니다.
```
pip install --upgrade numba
```
4. 만약 위 단계로도 해결이 안된다면 'librosa'패키지 설치의 문제일 수도 있으므로 해당 패키지를 재설치 합니다.
```
pip uninstall librosa
pip install librosa
```

### Quick Start  
- 아래 명령어로 TTS 프로그램을 실행합니다.  
```
python quick_start.py -u --input_text "input"
```

이때 "input"에는 원하는 문자열을 넣을 수 있습니다.  
아래 input을 넣게 되면 위 sample과 같은 결과를 얻을 수 있습니다.
> input 1 : Hello my name is konkuk.  
> input 2 : Hello, we are majoring computer science.  
> input 3 : Today is June first.  
> input 4 : Topic of this class is opensource.  
> input 5 : We are opensource software team ten!  
> input 6 : This is the result of sample text!  
> input 7 : 안녕하세요! 저희 팀 이름은 TEN입니다.  
> input 8 : 배가 너무 고파요!  

- 만약 input 없이 명령어를 실행시키면 default로 설정된 6개의 text로 파일을 생성합니다.
```
python quick_start.py
```
## Presentation
