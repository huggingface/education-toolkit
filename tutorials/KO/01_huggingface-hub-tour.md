# 워크숍: Hugging Face Hub 투어

<aside>

💡 **환영합니다!**

이 자료는 대학 강사들이 실습, 과제 또는 수업을 쉽게 준비할 수 있는 콘텐츠를 모았습니다. 모든 콘텐츠는 무료이며 독립적이기에 기존 교육과정에 쉽게 통합될 수 있고, 잘 알려진 오픈소스 기술 (`transformers`, `gradio` 등) 을 사용합니다.

Hugging Face 팀 멤버에게 튜토리얼 강연을 요청하기 위해서는 [ML demo.cratization 투어](https://www.notion.so/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652)를 참조해주세요.

튜토리얼 이외에도 ML에 대한 자세한 내용 또는 강좌 콘텐츠 설계에 도움이 되는 다른 리소스도 찾을 수 있습니다.

</aside>

**소요시간:** 20 ~ 40분

**목표:** 머신러닝(ML) 프로젝트에서 생태계 및 팀 내에서 협업할 수 있도록 무료인 [Hub platform](http://hf.co)을 효율적으로 사용하는 방법을 학습합니다.

학습 목표:

- Hugging Face Hub에 공유된 30,000 개의 모델을 살펴봅니다. 
- 작업에 적합한 모델과 데이터셋을 찾는 효과적인 방법을 소개합니다.
- ML 프로젝트를 공동 작업할 수 있는 워크플로를 소개합니다.
- 커뮤니티가 만든 ML 데모를 탐색해봅니다.

**형식:** 짧은 실습 혹은 숙제

**대상:** 기존 모델을 사용하거나 모델을 공유하는 데 관심이 있는 모든 학생.

**선수지식**

- 머신러닝에 대한 높은 이해
- (선택 사항이지만 권장됨) Git 사용 경험 ([resource](https://learngitbranching.js.org/))

## **왜 Hub인가?**

Hub는 모델, 데이터셋 및 ML 데모를 누구나 공유하고 탐색할 수 있는 중앙 플랫폼입니다.  "AI로 해결하기" 문제는 단일 기업이 아니라 지식과 자원을 공유하는 문화로 해결될 것입니다. 따라서 Hub는 가장 광범위한 오픈소스 모델, 데이터셋 및 데모 컬렉션을 구축하는 것을 목표로 합니다.

Hugging Face Hub에 대한 몇 가지 사실:

- 30,000 개가 넘는 공개된 모델이 있습니다다.
- 자연어 처리, 컴퓨터 비전, 오디오/스피치, 강화 학습 모델이 있습니다!
- 180개 이상의 언어를 지원하는 모델이 있습니다.
- TensorFlow, PyTorch부터 spaCy, SpeechBrain와 20개 라이브러리와의 고급 통합에 이르기까지 Hub에서 다양한 ML 라이브러리를 이용할 수 있습니다.

## 단일 모델 탐색

모델 탐색을 시작해봅시다. 30,000 개의 모델을 [hf.co/models](http://hf.co/models)에서 찾을 수 있습니다. 다운로드 수가 가장 많은 모델 중 하나인 [gpt2](https://huggingface.co/gpt2)가 보입니다. 해당 모델을 클릭합시다. 

모델을 클릭하면 웹 사이트에서 모델 카드로 이동합니다. 모델 카드는 모델을 문서화하는 도구이며 모델에 대한 유용한 정보를 제공하고 검색과 재현에 필수적으로 사용됩니다.

인터페이스에는 많은 컴포넌트가 있습니다. 각 컴포넌트를 살펴보겠습니다.:

[https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- 상단에는 작업(*text generation*, *image classification* 등), 프레임워크(*PyTorch*, *TensorFlow* 등), 모델의 언어(*English*, *Arabic*, *etc.*), 라이선스(*예 : MIT*) 등의 다양한 태그가 있습니다.

![](../../images/mode_card_tags.png)

- 오른쪽 열에는 *Inference API*를 사용해 브라우저에서 직접 모델을 사용할 수 있습니다. GPT2는 텍스트 생성 모델이므로 초기 입력이 주어지면 추가 텍스트를 생성합니다. “It was a bright and sunny day.”와 같이 입력해 보세요.

![](../../images/model_card_inference_api.png)

- 중간에서는 모델 카드 내용을 살펴볼 수 있습니다. 용도 & 제한 사항, 학습 절차 및 인용 정보와 같은 부분이 있습니다.

![](../../images/model_card_content.png)

모든 데이터는 어디에서 왔을까요? Hugging Face는 모든 것이 **Git 저장소**를 기반으로 하며 오픈소스입니다. “Files and Versions” 탭을 클릭하면 모델 가중치를 포함한 모든 저장소 파일들을 볼 수 있습니다. 모델 카드는 콘텐츠 상단에 태그와 같은 메타데이터가 포함된 마크다운 파일 **([README.md](http://README.md))** 입니다.

![](../../images/model_card_git.png)

모든 모델은 Git 기반 저장소이므로 기본적으로 버전을 제어할 수 있습니다. Github와 똑같이 Git Clone, Add, Commit, Branch, Push가 가능합니다. 이전에 Git을 사용한 적이 없다면 다음 [resource](https://learngitbranching.js.org/)를 참고하세요.

**문제 1**. GPT2 저장소의 `config.json` 파일을 엽니다. config 파일에는 하이퍼 파라미터와 모델 불러오기에 대한 유용한 정보가 포함되어 있습니다. config 파일을 보고 다음 질문에 대답하세요. 

- 활성화 함수(activation function)는 무엇입니까?
- 단어 집합 개수(vocabulary size)는 얼마입니까?

## **여러 모델 탐색**

지금까지 단일 모델을 탐색했습니다. [https://huggingface.co/models](https://huggingface.co/models) 화면의 왼쪽에서 다양한 항목을 필터링할 수 있습니다. 

- **Tasks:** 컴퓨터 비전, 자연어 처리, 오디오 등 다양한 영역에서 수십 가지 작업을 지원합니다. +13을 클릭하면 사용 가능한 모든 작업을 볼 수 있습니다.
  - **Libraries:** Hub는 초기에 Transformer 모델을 위한 것이었지만 수십 개의 라이브러리와 통합되었습니다. Keras, spaCy, allenNLP 등의 모델을 찾을 수 있습니다.
- **Datasets:** Hub는 수천 개의 데이터셋도 호스팅합니다. 나중에 자세히 알아볼 것입니다.

![](../../images/model_card_filters.png)

- **Languages:** Hub의 많은 모델이 NLP와 관련되어 있습니다. 자원이 적은 언어를 포함하여 수백 가지 언어에 대한 모델을 찾을 수 있습니다.

**문제 2**. 영어로 된 토큰 분류(Token Classification) 모델은 몇 개입니까?

**문제 3**.  자동 음성 인식을 위한 스페인어 모델을 선택해야 한다면 무엇을 선택하시겠습니까? 

## 모델 추가

Hub에 모델을 업로드한다고 가정하겠습니다. Scikit-learn, Keras, Transformers 등 모든 ML 라이브러리의 모델이 업로드될 수 있습니다.

다음 단계를 살펴봅시다:

1. [huggingface.co/new](http://huggingface.co/new)에서 새로운 모델 저장소를 생성합니다. 저장소는 public하거나 private하게 만들 수 있습니다
2. 모델 카드가 있는 public 저장소로 시작합니다. 웹 UI 혹은 GIt을 이용해서 모델을 업로드할 수 있습니다. Git을 처음 사용한다면 웹 인터페이스를 사용하세요. Files 탭에서 `Add File` 을 클릭하면 파일을 생성하거나 업로드할 수 있습니다. 전체적인 워크플로를 알고 싶다면 Git을 사용하십시오.

    1. git과 git-lfs를 설치합니다.
        1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
        2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). 대용량 파일은 Git LFS로 업로드해야 합니다. 파일이 특정 MB보다 커지면 Git이 제대로 작동하지 않습니다. ML 모델의 크기는 GB, TB가 될 수 있습니다! 🤯

    2. 방금 만든 저장소를 Clone 합니다. 
        ```python
        git clone https://huggingface.co/<your-username>/<your-model-id>
        ```

    3. 폴더로 이동해 Git LFS를 초기화합니다.
        1. 선택사항. `.gitattributes`에는 큰 파일에 대한 일반적인 파일 확장자(common file extensions) 목록이 있습니다. 업로드할 파일이 `.gitattributes` 에 추가되지 않은 경우 아래의 코드를 실행하세요. 

            ```python
            git lfs track "*.your_extension"
            ```

            ```python
             git lfs install
            ```

    4. 저장소에 파일을 추가합니다. 파일은 프레임워크/라이브러리에 따라 다릅니다. 중요한 것은 모델을 로드하는 데 필요한 모든 산출물을 추가하는 것입니다. 예를 들어: 
        1. TensorFlow의 경우, 저장된 모델 혹은 `h5` 파일.
        2. PyTorch의 경우, `pytorch_model.bin`.
        3. Scikit-Learn의 경우, `joblib` 파일.

        아래 코드는 Scikit-Learn 모델을 저장하는 파이썬(Python) 예시입니다. 

        ```python
        from sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        from joblib import dump, load
        dump(reg, 'model.joblib')
        ```

    5. 파일을 Commit 하고 Push 합니다. (저장한 파일이 저장소 내에 있는지 확인하세요.)

    ```python
    git add .
    git commit -m "First model version"
    git push
    ```

모델을 업로드하는 모든 작업이 끝났습니다. 최근에 추가된 모든 파일을 저장소에서 확인할 수 있습니다.

![](../../images/model_card_updated_repo.png)

웹 UI에서 모델 파일과 Commit을 탐색하고 각 Commit에 따른 차이를 볼 수 있습니다. 

**문제 4**. ML 라이브러리를 사용해 더미 모델을 생성한 후 모델을 업로드해봅시다.

모델을 Hub에 있으므로, 다른 사용자가 찾을 수 있습니다. 또 단체(Organization)를 만들어 다른 사용자와 쉽게 협업할 수 있습니다. Hub를 통해 호스팅하면 팀은 저장소를 업데이트하고 브랜치에서 작업하거나 협업할 수 있습니다. 또한 Hub에서 모델의 버전 관리를 할 수 있습니다. 만약 모델의 체크포인트에 문제가 발생하면 언제든지 이전 버전으로 돌아갈 수 있습니다. 

`README`의 상단에서 일부 메타데이터를 찾을 수 있습니다. 지금은 라이선스만 볼 수 있지만 더 많은 것을 추가할 수 있습니다. 아래는 그 예시입니다.

```yaml
 tags:
- es       # 자동으로 감지되는 언어 태그입니다. 
- bert     # 필터링을 위해 태그를 추가할 수 있습니다.
- text-classification # 자동으로 감지되는 작업 태그입니다. 
datasets:
- llamas # Hub의 데이터셋이 존재하는 경우 이 데이터셋에 연결됩니다.
```

**문제 5**. [문서](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined)를 보고 위젯의 기본 예시를 변경하세요.

메타데이터를 사용하면 모델을 빠르게 찾을 수 있습니다. 이제 스페인어 텍스트 분류 모델을 검색하면 업로드한 모델이 표시됩니다. 모델은 데이터셋을 살펴볼 때도 표시됩니다.

잠깐만...데이터셋?

## Datasets

ML 파이프라인은 일반적으로 모델을 훈련할 데이터셋이 있습니다. Hub는 여러 도메인에서 자유롭게 사용할 수 있는 약 3000 개의 오픈소스 데이터셋을 호스팅합니다. 오픈소스 `datasets` [라이브러리](https://huggingface.co/docs/datasets/)는 스트리밍과 같은 매우 편리한 기능을 사용해 데이터셋을 간단하게 사용할 수 있습니다. 이 실습은 datasets 라이브러리를 살펴보지는 않지만 라이브러리를 탐색하는 방법을 설명합니다.

모델과 유사하게 [https://hf.co/datasets](https://hf.co/datasets)에서 데이터셋을 찾을 수 있습니다. 화면 좌측에는 작업, 라이선스, 데이터셋 크기에 따라 다양한 필터를 볼 수 있습니다. 

NLP 성능 테스트에 사용되는 유명한 데이터셋인 [GLUE](https://huggingface.co/datasets/glue) 데이터셋을 살펴봅시다.

- 모델 저장소와 유사하게 데이터셋을 문서화하는 데이터셋 카드가 있습니다. 화면을 조금 내리면 데이터셋의 요약, 구조 등을 찾을 수 있습니다. 

![](../../images/datasets_card.png)

- 데이터셋 카드 상단에서 직접 데이터셋 일부를 확인할 수 있습니다. GLUE 데이터셋은 COLA, QNLI와 같이 복수의 하위 데이터셋으로 나뉩니다. 

  ![](../../images/datasets_slices.png)

- 데이터셋 카드의 우측은 해당 데이터셋으로 학습한 모델의 목록을 확인할 수 있습니다. 

![](../../images/datasets_models_trained.png)

**문제 6**. Common Voice 데이터셋을 탐색하고 다음 질문에 대답하세요.

- Common Voice 데이터셋을 사용할 수 있는 작업은 무엇입니까?
- 이 데이터셋에는 몇 개의 언어가 포함되어 있습니까?
- 데이터셋 분할은 무엇입니까?

## 머신러닝(ML) 데모

모델 및 데이터셋을 공유하는 것은 좋지만, 공개적으로 사용할 수 있는 대화형 데모를 만드는 것은 더 좋습니다. 모델의 데모는 생태계에서 점점 더 중요해지고 있습니다. 데모는 :

- 모델 개발자가 이해관계자, 프레젠테이션, 학회, 연구 프로젝트 등 폭넓은 청중에게 쉽게 **발표**할 수 있도록 합니다. 
- 모델을 테스트하기 위한 장벽을 낮추어 머신러닝의 **재현성**을 높입니다. 
- **모델의 영향**을 일반 대중과 공유할 수 있게 합니다.
- 머신러닝 **포트폴리오**를 만들 수 있습니다.

Gradio와 Streamlit 같은 오픈소스 파이썬(Python) 프레임워크는 데모를 매우 쉽게 만들 수 있으며 Hugging Face [Spaces](http://hf.co/spaces/launch)를 사용해 데모를 호스팅하고 공유할 수 있습니다. 다음 튜토리얼은 **Gradio와 Hugging Face를 사용한 머신러닝 데모 및 호스팅** 을 실습합니다.

> 이 튜토리얼은:
>
> - 커뮤니티가 만든 다양한 ML 데모를 탐색해봅니다.
> - `gradio` 파이썬(python) 라이브러리를 사용해 손쉽게 ML 데모를 만들 수 있습니다.
> - 수업이나 학회때 사용할 수 있는 Hugging Face Spaces 무료 호스팅 사용법을 소개합니다.
>
> ***소요시간: 20-40 분***
>
> 👉 [튜토리얼 바로가기](https://colab.research.google.com/github.com/huggingface/education-toolkit/tree/main/tutorials/EN/02_ml-demos-with-gradio.ipynb)
