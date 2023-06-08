# opensw23-ten
Text-To-Speech project
## Team Introduction

|이름|학번|역할|
|:------:|:---:|:---:|
|김영준|201911162|리더 / 발표자|
|박상준|201911173|테스터 / ppt제작|
|신민석|202011316|데이터셋 제작|
|김수형|202211276|데이터셋 제작|

## Topic Introduction
### References
1. https://github.com/fatchord/WaveRNN  
2. [Efficient Neural Audio Synthesis](https://arxiv.org/abs/1802.08435)  

![TTS구조](https://github.com/opensw23-ten/opensw23-ten/assets/127181370/d72feddc-9444-441f-b2c5-60c4d4b63b3f)  
img source : https://commons.wikimedia.org/wiki/File:TTS_System.svg   

**저희가 선택한 오픈소스는 TTS입니다.**

- TTS(Text to Speech)는 '음성합성'으로 일정한 음성 단위로 분할한 후 입력받은 텍스트를 따라 필요한 음성단위들을 이어 붙여 말소리를 인위적으로 만들어 내는 기술입니다.
- python quick_start.py -u --input_text "샘플 텍스트" 커맨드를 사용해 사용자가 입력한 샘플 텍스트("String)를 음성(".wav)으로 바꿔줍니다.

|INPUT|OUTPUT|
|:------:|:---:|
|TEXT("String")|Speech(".wav")|

샘플데이터를 사용한 [Results](#results)는 아래와 같습니다.
## Results
### Inputs
- 주의 사항  
1. 특정 브라우저(크롬 등)에서 실행 시, 정책에 의해 음소거되어 있을 수 있어 음소거 해제 후 청취 가능합니다.

2. 해당 예시 파일은 readme.md에 업로드하기 위해 확장명이 .mp4로 변경되었음을 알려드립니다.  
(기존 확장명 : .wav)
3. 현재 해당 모델은 [LJ Speech](https://keithito.com/LJ-Speech-Dataset/) 영어 data로 학습되었음을 알려드립니다.
4. [ python quick_start.py -u --input_text "input" ] 에서 input값을 변경하며 생성된 음성파일입니다.
5. 다음 표와 같이 실행 데이터를 생성했습니다.

|영어 Text|한글 Text|혼합 Text|문장 여러개|
|:------:|:---:|:---:|:---:|
|15개|15개|10개|10개|
 
***다음은 대표 Output 8개입니다.***

#### 1. Hello my name is konkuk.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/7d2a7afc-7bce-4fec-84d9-07269d3846c3
> 영어로 구성된 Text는 정확한 발음을 하는 음성이 생성됩니다.
#### 2. hello, my name is joon
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/d8ecbd73-c782-48d6-8171-4efefa9117be
> 문장이 끝나는 것을 알려주지 않으면 음성파일이 늘어지게 됩니다.
#### 3. 배가 너무 고파요!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/1dfa34d3-757a-4c86-88aa-4d3b88d2ee22
> 한국어로 구성된 문장은 어눌한 발음으로 생성됩니다.
#### 4. 영화 트루먼쇼의 명대사는 In case I don't see you, Good afternoon, Good evening, and Good night.입니다.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/2d984469-3949-4dc8-ae6a-8575ff17ff7c
> 한국어와 영어가 섞인 문장에서는 한국어 발음은 어눌하지만 영어는 제대로 발음되는 것을 확인했습니다.
#### 5. 불닭볶음면은 많이 맵습니다.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/9f7b5655-adf7-4ad4-8bb0-3674428ba7ca
> 받침이 많은 문장은 기존 한국어로 된 문장보다 더 좋지 않은 발음으로 생성됩니다.
#### 6. This is English Sample Text for collaboration with Korean. 그리고 이건 영어와 같이 사용하기 위한 한국어 샘플 파일입니다!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/2240ad2a-2202-4a7f-8039-fe14a6dca8c0
> 영어 한문장, 한글 한문장을 동시에 input으로 넣게 되면 문장 끝에 오류가 생깁니다.
#### 7. First sentance for test. Second sentance for test!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/8d79e01d-a4a7-457b-ac91-1d0f50c49b09
> 영어로 구성된 두 개의 문장이면 정상적인 발음으로 생성됩니다.  
#### 8. 첫 번째 문장입니다. 두 번째 문장입니다.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/6ef357d1-c6d7-4698-8014-5f7ff9c21cf6
> 한글로 구성된 두 개의 문장이면 많이 어눌한 발음으로 생성됩니다.

더 많은 예시가 궁금하시다면 [클릭](https://opensw23-ten.github.io/sample/)

## Analysis/Visualization
1. **영어로 구성된 TEXT**는 문장이 여러개로 구성되어도 제대로 된 음성을 제공합니다.

2. 음성으로 변환할 text를 입력할 때, **문장의 끝을 알려주는 '.' , '!' , '?'** 가 들어가지 않으면 음성파일이 제대로 끝나지 않는 현상이 발생합니다.
3. 영어 데이터로 학습된 모델에 **한국어** 를 넣어 실행시켜 보아도 정확하지 않지만 알아들을 수 있을 정도의 음성파일을 생성합니다.  
    * 이는 **unicodedata** 라이브러리를 통해 한글 문자를 초성, 중성, 종성으로 구분되어 해당 음절을 바탕으로 생성할 수 있기 때문입니다.
    * 받침이 많은 단어가 발음될 때는 많이 어눌하게 발음됩니다.  
4. 저희 목소리로 녹음 후 학습 모델을 생성해보았습니다.
    * 그래프가 오른쪽 아래 일직선 형태로 뚜렷한 선이 나오면 제대로 학습된 모델이지만 데이터셋과 시간 부족으로 끝까지 학습되지 않음
    * 2000회 이상 학습 후, Loss값은 감소하지만 그래프 상에서 뚜렷한 변화가 보이지 않는 것을 관찰함.
    * 정확한 학습을 위해선 충분히 많은 데이터 개수와 학습 시간이 필요하다는 것을 알게 됨.  
      ( 기존 모델 학습 데이터 개수는 13100개 )
    * 충분히 학습이 되지 않고 출력된 음성은 많은 잡음이 섞여서 나오게 됨.  ***잡음이 많이 섞여 재생됩니다. 유의해주세요.***  

|학습 횟수|데이터 개수|Loss|소요 시간|
|:------:|:---:|:---:|:---:|
|3427회|223개|2.904 -> 0.4316|약 8시간|

**input :  안녕하세요 제 이름은 건국.**

https://github.com/opensw23-ten/opensw23-ten/assets/127181370/856c392f-88e4-44a7-ac27-c94a3f278b89

![attention](https://github.com/opensw23-ten/opensw23-ten/assets/127181370/ac03837a-2aec-4d98-bf57-cb35d7359bcf)

## Installation  
### Requirements
OS : Windows 10 이상, Linux Ubuntu 20.04 버전 실행 확인  
Python 버전 3.6 이상, 3.8 이하  
Pytorch 1 이상 With CUDA
- 해당 repository를 clone합니다.
```
git clone https://github.com/opensw23-ten/opensw23-ten.git
cd opensw23-ten
```

- 아래 명령어로 [Pytorch 설치](https://pytorch.org/get-started/previous-versions/)  
```
pip install torch==2.0.0+cu118 torchvision==0.15.1+cu118 torchaudio==2.0.1 --index-url https://download.pytorch.org/whl/cu118  
```

- 아래 명령어로 나머지 모듈 설치  
```
pip install -r requirements.txt  
```
**만약 설치 중 오류가 발생한다면**
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
아래 input을 넣게 되면 위 [Results](#results)와 같은 결과를 얻을 수 있습니다.  

***주의사항 : 문장에 끝에는 끝을 알 수 있는 '.' or '!' or '?'를 넣지 않을 시 오류가 발생할 수 있습니다.***
> input 1 : Hello my name is konkuk.  
> input 2 : hello, my name is joon  
> input 3 : 배가 너무 고파요!  
> input 4 : 영화 트루먼쇼의 명대사는 In case I don't see you, Good afternoon, Good evening, and Good night.입니다.  
> input 5 : 불닭볶음면은 많이 맵습니다.  
> input 6 : This is English Sample Text for collaboration with Korean. 그리고 이건 영어와 같이 사용하기 위한 한국어 샘플 파일입니다!  
> input 7 : First sentance for test. Second sentance for test!  
> input 8 : 첫 번째 문장입니다. 두 번째 문장입니다.  

- 만약 input 없이 명령어를 실행시키면 default로 설정된 6개의 text로 파일을 생성합니다.
```
python quick_start.py
```
> 1. Scientists at the CERN laboratory say they have discovered a new particle.  
> 2. There's a way to measure the acute emotional intelligence that has never gone out of style.  
> 3. President Trump met with other leaders at the Group of 20 conference.  
> 4. The Senate's bill to repeal and replace the Affordable Care-Act is now imperiled.  
> 5. Generative adversarial network or variational auto-encoder.  
> 6. Basilar membrane and otolaryngology are not auto-correlations.  

- **생성된 wav파일은 새로 생성되는 quick_start폴더 아래 위치합니다.**
## Presentation
