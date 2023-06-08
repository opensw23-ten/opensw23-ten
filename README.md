# opensw23-ten
Text-To-Speech project
## Team Introduction
  김영준 : 201911162 리더  
  박상준 : 201911173 코더  
  신민석 : 202011316 github expert  
  김수형 : 202211276 발표자  
## Topic Introduction
### References
1. https://github.com/fatchord/WaveRNN  
2. [Efficient Neural Audio Synthesis](https://arxiv.org/abs/1802.08435)  

![TTS_System](https://upload.wikimedia.org/wikipedia/commons/b/b5/TTS_System.svg)  
img source : https://commons.wikimedia.org/wiki/File:TTS_System.svg   

**저희가 선택한 오픈소스는 TTS입니다.**

- TTS(Text to Speech)는 '음성합성'으로 일정한 음성 단위로 분할한 후 입력받은 텍스트를 따라 필요한 음성단위들을 이어 붙여 말소리를 인위적으로 만들어 내는 기술입니다.
- python quick_start.py -u --input_text "샘플 텍스트" 커맨드를 사용해 사용자가 입력한 샘플 텍스트를 음성으로 바꿔줍니다.  
- 자신만의 모델을 트레이닝 시킬 수 있습니다.

샘플데이터를 사용한 [Results](#results)는 아래와 같습니다.
## Results
### Inputs
- 주의 사항  
1. 특정 브라우저(크롬 등)에서 실행 시, 정책에 의해 음소거되어 있을 수 있어 음소거 해제 후 청취 가능합니다.
2. 해당 예시 파일은 readme.md에 업로드하기 위해 확장명이 .mp4로 변경되었음을 알려드립니다.  
(기존 확장명 : .wav)
3. 현재 해당 모델은 [LJ Speech](https://keithito.com/LJ-Speech-Dataset/) 영어 data로 학습되었음을 알려드립니다.
### Default input
*[ python quick_start.py ] 를 실행하여 default 문장으로 생성된 음성파일입니다.*  
- 6개의 default값으로 파일 생성
#### 1. Scientists at the CERN laboratory say they have discovered a new particle.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/219ab256-f910-4513-98b8-d13fad673995
#### 2. There's a way to measure the acute emotional intelligence that has never gone out of style.  
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/e8af7b4d-29f3-4b27-baa6-c5498801e17e
#### 3. President Trump met with other leaders at the Group of 20 conference.  
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/94bc8df2-fd03-4c98-ac49-cdc438d8972f
#### 4. The Senate's bill to repeal and replace the Affordable Care-Act is now imperiled.  
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/f6825aab-d57b-44d7-b743-42e2b7a9cf7f
#### 5. Generative adversarial network or variational auto-encoder.  
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/c2835e2d-38db-4963-95f4-8b172b7e7a78
#### 6. Basilar membrane and otolaryngology are not auto-correlations.  
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/9102158a-02c1-469d-bf12-b60fc24daa35

### User input
*[ python quick_start.py -u --input_text "input" ] 에서 input값을 변경하며 생성된 음성파일입니다.*
- 8개의 input으로 파일 생성
#### 1. Hello my name is konkuk.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/7d2a7afc-7bce-4fec-84d9-07269d3846c3
#### 2. Hello, we are majoring computer science.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/940604f4-d15b-4795-98f6-31e2275fee3b
#### 3. Today is June first.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/499bba74-2bab-45f6-8426-27ea118e4cc4
#### 4. Topic of this class is opensource.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/d77f7c28-01f2-466f-b6c9-4a4d76c3be62
#### 5. We are opensource software team ten!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/7354ab80-2703-4a96-a377-1e1d4fa916e0
#### 6. This is the result of sample text!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/c7c2cb7f-b8ec-40fd-904d-decd95ef4499
#### 7. 안녕하세요! 저희 팀 이름은 TEN입니다.
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/cf28a3dd-3d8e-4dc6-9344-d8568cf341e6
#### 8. 배가 너무 고파요!
https://github.com/opensw23-ten/opensw23-ten/assets/127181370/1dfa34d3-757a-4c86-88aa-4d3b88d2ee22

더 많은 예시가 궁금하시다면 [클릭](https://opensw23-ten.github.io/sample/)

## Analysis/Visualization
1. 음성으로 변환할 text를 입력할 때, 문장의 끝을 알려주는 '.' , '!' , '?'가 들어가지 않으면 음성파일이 제대로 끝나지 않는 현상이 발생합니다.
  
2. 영어 데이터로 학습된 모델에 한국어를 넣어 실행시켜 보아도 정확하지 않지만 알아들을 수 있을 정도의 음성파일을 생성합니다.  
    * 이는 unicodedata 라이브러리를 통해 한글 문자를 초성, 중성, 종성으로 구분되어 해당 음절을 바탕으로 생성할 수 있기 때문입니다.  
4. 저희 목소리로 녹음 후 학습 모델을 생성해보았습니다.
    * 학습 횟수 : 3472회 / 데이터 개수 : 223개 / Loss : 2.904 -> 0.4316 / 약 8시간 소요
    * 그래프가 오른쪽 아래 일직선 형태로 뚜렷한 선이 나오면 제대로 학습된 모델이지만 데이터셋과 시간 부족으로 끝까지 학습되지 않음
    * 2000회 이상 학습 후, Loss값은 감소하지만 그래프 상에서 뚜렷한 변화가 보이지 않는 것을 관찰함.
    * 출력된 음성은 많은 잡음이 섞여서 나오게 됨.  ***잡음이 많이 섞여 재생됩니다. 유의해주세요.***  

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
> 1. Scientists at the CERN laboratory say they have discovered a new particle.  
> 2. There's a way to measure the acute emotional intelligence that has never gone out of style.  
> 3. President Trump met with other leaders at the Group of 20 conference.  
> 4. The Senate's bill to repeal and replace the Affordable Care-Act is now imperiled.  
> 5. Generative adversarial network or variational auto-encoder.  
> 6. Basilar membrane and otolaryngology are not auto-correlations.  

- **생성된 wav파일은 새로 생성되는 quick_start폴더 아래 위치합니다.**
## Presentation
