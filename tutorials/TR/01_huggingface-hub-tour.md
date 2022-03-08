# Atölye: Hugging Face Hub'da Bir Tur
<aside>

💡 **Hoş Geldiniz!**

Üniversite eğitmenlerinin kolayca laboratuvar, ödev veya ders hazırlamak için kullanabilecekleri bir araç seti oluşturduk. İçerik, mevcut müfredata kolayca dahil edilebilecek ve kendi kendine yetebilecek şekilde tasarlanmıştır. Bu içerik **ücretsizdir** ve yaygın olarak bilinen Açık Kaynak teknolojilerini (`transformers`, `gradio`, vb.) kullanır.

Alternatif olarak, Hugging Face ekibinden birinden [ML demo.cratization turu](https://www.notion.so/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652) girişimi aracılığıyla sınıfınız için eğitimleri yapmasını isteyebilirsiniz!

Derlediğimiz tüm eğitimleri ve kaynakları [burada](https://www.notion.so/Education-Toolkit-7b4a9a9d65ee4a6eb16178ec2a4f3599) bulabilirsiniz.

</aside>

**Süre:** 20 ila 40 dakika

**Hedef:** Ekosistemde ve Makine Öğrenimi (Machine Learning - ML) projelerinde ekipler içinde işbirliği yapabilmek için ücretsiz [Hub platformunu](http://hf.co) nasıl verimli bir şekilde kullanacağınızı öğrenin.

Öğrenme hedefleri:

- Hub'da paylaşılan 30.000'den fazla model hakkında bilgi edinin ve keşfedin.
- Göreviniz için uygun modelleri ve veri kümelerini bulmanın verimli yollarını öğrenin.
- Nasıl katkıda bulunacağınızı ve ortak çalışmayı öğrenin.
- Topluluk tarafından oluşturulan makine öğrenimi demolarını keşfedin.

**Format:** Ya kısa laboratuvar ya da ev ödevi

**Kitle:** Mevcut modelleri kullanmak veya modellerini paylaşmakla ilgilenen her alandan öğrenciler.

**Önkoşullar**

- Genel olarak Makine Öğrenimi hakkında bilgi sahibi olmak.
- (İsteğe bağlı, ancak teşvik edilir) Git tecrübesine sahip olmak ([kaynak](https://learngitbranching.js.org/))

## **Neden Hub?**

Hub, herkesin modelleri, veri kümelerini ve makine öğrenimi demolarını paylaşabileceği ve keşfedebileceği merkezi bir platformdur. "Yapay zekayı çözme" sorunu tek bir şirket tarafından değil, bilgi ve kaynakları paylaşma kültürüyle çözülecektir. Bu nedenle, Hub, en kapsamlı Açık Kaynak modelleri, veri kümeleri ve demolar koleksiyonunu oluşturmayı amaçlamaktadır.

İşte Hugging Face Hub hakkında bazı gerçekler:

- 30.000'den fazla genel model var.
- Doğal Dil İşleme, Bilgisayarlı Görü, Ses/Konuşma ve Pekiştirmeli Öğrenme için modeller var!
- 180'den fazla dil için modeller var.
- Herhangi bir ML kütüphanesi Hub'dan yararlanabilir: TensorFlow ve PyTorch'tan spaCy, SpeechBrain ve diğer 20 kütüphane ile gelişmiş entegrasyonlara kadar.

## Bir modeli keşfetmek

Modellerin keşfine başlayalım. 30.000 modele [hf.co/models](http://hf.co/models) adresinden ulaşabilirsiniz. En çok indirilen modellerden birinin [gpt2](https://huggingface.co/gpt2) olduğunu göreceksiniz. Üzerine tıklayalım.

Bir modele tıkladığınızda web sitesi sizi model kartına götürecektir. Model kartı, modelleri belgeleyen, modeller hakkında faydalı bilgiler sağlayan ve keşfedilebilirlik ve yeniden üretilebilirlik için gerekli olan bir araçtır.

Arayüzün birçok bileşeni var, o yüzden bunların üzerinden geçelim:

[https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- En üstte, görev (*metin oluşturma, görüntü sınıflandırma*, vb.), frameworkler (*PyTorch*, *TensorFlow*, vb.), modelin dili (*İngilizce*, *Arapça*, *vb.*) ve lisans (*ör. MIT*) gibi şeyler için farklı **etiketler** bulabilirsiniz.

![](../../images/mode_card_tags.png)

- Sağ sütunda, *Inference (Çıkarım) API'sini* kullanarak modelle doğrudan tarayıcıda oynayabilirsiniz. GPT2 bir metin oluşturma modelidir, bu nedenle bir girdi verildiğinde ek metin üretecektir. "It was a bright and sunny day." gibi bir şey yazmayı deneyin.

![](../../images/model_card_inference_api.png)

- Orta kısımda model kart içeriğine göz atabilirsiniz. Amaçlanan kullanımlar ve sınırlamalar, Eğitim prosedürü ve Alıntı Bilgileri gibi bölümleri vardır.

![](../../images/model_card_content.png)

Bütün bu veriler nereden geliyor? Hugging Face'de her şey **Git repolarında** bulunur ve açık kaynaklıdır. Model ağırlıkları dahil tüm repo dosyalarını görmenizi sağlayacak olan “Files and Versions” (Dosyalar ve Sürümler) sekmesine tıklayabilirsiniz. Model kartı, içeriğin üstünde etiketler gibi meta veriler içeren bir markdown dosyasıdır **([README.md](http://README.md))**.

![](../../images/model_card_git.png)

Tüm modeller Git tabanlı repolar olduğundan, herhangi bir ayarlamaya ihtiyaç duymadan versiyon kontrolü özelliğine sahip olursunuz. GitHub'da olduğu gibi Git clone, add, commit, branch ve push gibi şeyleri yapabilirsiniz. Git'i daha önce hiç kullanmadıysanız [şu kaynağı](https://learngitbranching.js.org/) öneririz.

**Görev 1**. GPT2 reposunun `config.json` dosyasını açın. Yapılandırma dosyası, hiperparametrelerin yanı sıra modeli yüklemek için faydalı bilgiler içerir. Bu dosya üzerinden şu sorulara cevap verin:

- Aktivasyon fonksiyonu hangisidir?
- Kelime haznesi boyutu nedir?

## **Modelleri Keşfetmek**

Şimdiye kadar, tek bir modeli araştırdık. Hadi biraz daha açılalım! [https://huggingface.co/models](https://huggingface.co/models) sayfasının solunda, farklı şeyler için filtre uygulayabilirsiniz:

- **Görevler:** Farklı alanlarda düzinelerce görev için destek vardır: Bilgisayarlı Görü, Doğal Dil İşleme, Ses ve daha fazlası. Mevcut tüm görevleri görmek için +13'e tıklayabilirsiniz.
   - **Kütüphaneler:** Hub orijinal olarak transformer modelleri için olmasına rağmen, Hub'ın düzinelerce kitaplık ile entegrasyonu vardır. Keras, spaCy, allenNLP ve daha fazlasının modellerini bulabilirsiniz.
- **Veri Kümeleri:** Hub binlerce veri kümesini de barındırır, ki bunu birazdan göreceksiniz.

![](../../images/model_card_filters.png)

- **Diller:** Hub'daki modellerin çoğu NLP ile ilgilidir. Düşük kaynaklı diller de dahil olmak üzere yüzlerce dil için modeller bulabilirsiniz.

**Görev 2**. İngilizce'de kaç tane token sınıflandırma modeli var?

**Görev 3**. Otomatik Konuşma Tanıma için bir İspanyol modeli seçmeniz gerekseydi, hangisini seçerdiniz? (Bu görev ve dil için herhangi bir model olabilir)

## Model ekleme

Hub'a bir model yüklemek istediğinizi varsayalım. Bu model, herhangi bir ML kitaplığının bir modeli olabilir: Scikit-learn, Keras, Transformers, vb.

Hadi adım adım gidelim:

1. Yeni bir model reposu oluşturmak için [huggingface.co/new](http://huggingface.co/new) adresine gidin. Yaptığınız depolar açık veya gizli olabilir.
2. Model kartı olan bir açık repo ile başlarsınız. Modelinizi Web arayüzü kullanarak veya Git ile yükleyebilirsiniz. Git'i daha önce hiç kullanmadıysanız, sadece Web arayüzünü kullanmanızı öneririz. Dosya Ekle'ye tıklayıp eklemek istediğiniz dosyaları sürükleyip bırakabilirsiniz. İş akışını tümüyle anlamak istiyorsanız Git yaklaşımıyla gidelim.

    1. Sisteminize git ve git-lfs'yi kurun.
         1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
         2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). Büyük dosyaların Git LFS ile yüklenmesi gerekir. Dosyalarınız birkaç megabaytın üzerinde olduğunda Git iyi çalışmaz, ki bu ML alanında sık olan bir durumdur. ML modelleri gigabaytlarca veya terabaytlarca boyutta olabilir! 🤯
    
    2. Yeni oluşturduğunuz repoyu klonlayın

        ```python
        git clone https://huggingface.co/<kullanıcı-adınız>/<model-id-numaranız>
        ```

    3. Dizine gidin ve Git LFS'yi başlatın
         1. İsteğe bağlı. '.gitattributes' içinde büyük dosyalar için yaygın dosya uzantılarının bir listesini zaten sağladık, eğer yüklemek istediğiniz dosyaların uzantıları '.gitattributes' dosyası içinde yoksa, şöyle yapmanız gerekebilir:

            ```python
            git lfs track "*.uzantınız"
            ```

            ```python
             git lfs install
            ```
    
    4. Dosyalarınızı repoya ekleyin. Dosyalar, kullandığınız frameworklere/kütüphanelere bağlıdır. Genel olarak önemli olan, modeli yüklemek için gereken tüm yapıları sağlamanızdır. Örneğin:
         1. TensorFlow için bir SavedModel veya `h5` dosyası yüklemek isteyebilirsiniz.
         2. PyTorch için bu genellikle bir `pytorch_model.bin` dosyasıdır.
         3. Scikit-Learn için bu genellikle bir `joblib` dosyasıdır.

         İşte Python'da bir Scikit-Learn model dosyasını kaydetme örneği.

         ```python
        from sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        from joblib import dump, load
        dump(reg, 'model.joblib')
        ```

    5. Commit ve push kullanarak dosyalarınızı yükleyin (kaydettiğiniz dosyanın repo içerisinde olduğundan emin olun)

    ```python
    git add .
    git commit -m "First model version"
    git push
    ```

Ve işimiz bitti! Reponuzu en son eklenen tüm dosyalarla kontrol edebilirsiniz!

![](../../images/model_card_updated_repo.png)

Kullanıcı Arayüzü, model dosyalarını ve commitleri keşfetmenize ve her bir committe ortaya çıkan farkı görmenize olanak tanır.

**Görev 4**. Sıra sizde! Seçtiğiniz kitaplığın kukla bir modelini yükleyin.

Artık model Hub'da olduğuna göre, diğerleri onu bulabilir! Ayrıca bir organizasyon oluşturarak başkalarıyla kolayca ortak çalışabilirsiniz. Hub aracılığıyla dosyalarınızı barındırmak, bir ekibin; repoları güncellemek, branchlerde çalışmak ve ortak çalışmak gibi alışık olabileceğiniz şeyleri yapmasına olanak tanır. Hub ayrıca modellerinizde versiyon oluşturmayı da sağlar: bir model kontrol noktası aniden bozulursa, her zaman önceki bir sürüme geri dönebilirsiniz.

`README`nin üst kısmında bazı meta veriler bulabilirsiniz. Şu anda yalnızca lisansı bulacaksınız, ancak daha fazla şey ekleyebilirsiniz. Bunlardan birkaçını deneyelim:

```yaml
 tags:
- es       # Bu otomatik olarak bir dil etiketi şeklinde algılanacaktır.
- bert     # Filtreleme için ek etiketler belirtebilirsiniz.
- text-classification # Bu otomatik olarak bir görev etiketi şeklinde algılanacaktır.
datasets:
- llamas # Bu eğer Hub'da mevcut ise bir veri kümesine bağlantı sağlayacaktır.
```

**Görev 5**. [Dökümantasyonu](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined) kullanarak widget'taki varsayılan örneği değiştirin.

Meta veriler, insanların modelinizi hızlı bir şekilde keşfetmesini sağlar. Modeliniz artık İspanyolca metin sınıflandırma modellerini aradığınızda görünecektir. Model, veri kümesine bakıldığında da görünecektir.

Bir saniye... veri kümeleri?

## Veri Kümeleri

ML işlem hatlarıyla (pipeline), genellikle modeli eğitmek için bir veri kümeniz olur. Hub, açık kaynaklı ve birden çok alanda kullanımı ücretsiz olan yaklaşık 3000 veri kümesini barındırır. Üstüne üstlük, açık kaynaklı `datasets` [kütüphanesi](https://huggingface.co/docs/datasets/), akıcı veri işleme (streaming) gibi çok uygun özellikleri kullanarak çok büyük olanlar da dahil olmak üzere bu veri kümelerinin kolay kullanımına olanak tanır. Bu laboratuvarda kütüphaneyi işlemeyeceğiz, ancak bunların nasıl keşfedileceğini açıklayacağız.

Modellere benzer şekilde [https://hf.co/datasets](https://hf.co/datasets) adresine gidebilirsiniz. Sol tarafta; göreve, lisansa ve veri kümesinin boyutuna göre farklı filtreler bulabilirsiniz.

NLP modellerinin performansını test etmek için kullanılan ünlü bir veri kümesi olan [GLUE](https://huggingface.co/datasets/glue) veri kümesini inceleyelim.

- Model repolarına benzer şekilde, veri kümesini belgeleyen bir veri kümesi kartınız vardır. Biraz aşağı kaydırırsanız, özet, yapı gibi şeyleri bulacaksınız.

![](../../images/datasets_card.png)

- En üstte, veri kümesinin bir dilimini doğrudan tarayıcıda keşfedebilirsiniz. GLUE veri kümesi, COLA ve QNLI gibi seçebileceğiniz birden çok alt veri kümesine (veya alt kümeye) bölünmüştür.

   ![](../../images/datasets_slices.png)

- Veri seti kartının sağ tarafında bu veri seti üzerinde eğitilmiş modellerin listesini görebilirsiniz.

![](../../images/datasets_models_trained.png)

**Görev 6**. Common Voice veri kümesini arayın. Şu soruları cevaplayın:

- Common Voice veri kümesi hangi görevler için kullanılabilir?
- Bu veri setinde kaç dil kapsanıyor?
- Veri kümesi bölmeleri hangileridir?

## ML Demoları

Modellerinizi ve veri kümelerinizi paylaşmak harikadır, ancak etkileşimli, herkese açık bir demo oluşturmak daha da havalıdır. Model demoları, ekosistemin giderek daha önemli bir parçası haline geliyor. Demolar şunları sağlar:

- model geliştiricilerin çalışmalarını paydaş sunumları, konferanslar ve kurs projeleri gibi geniş bir kitleye kolayca **sunabilmek**
- bir modeli test etme engelini azaltarak makine öğreniminde **tekrarlanabilirliği** artırmak
- teknik bilgisi olmayan bir kitleyle **bir modelin etkisini** paylaşmak
- bir makine öğrenimi **portföyü** oluşturmak

Bu demoları çok kolay bir şekilde oluşturmaya izin veren Gradio ve Streamlit gibi Açık Kaynaklı Python frameworkleri ve onları barındırmaya ve paylaşmaya izin veren Hugging Face [Spaces](http://hf.co/spaces/launch) gibi araçlar vardır. Bu laboratuvarı takip edecek şekilde, **Gradio & Hugging Face ile Makine Öğrenimi Demoları Oluşturun ve Barındırın** eğitimini yapmanızı öneririz.

> Bu eğitimde şunları elde edeceksiniz:
>
> - Topluluk tarafından oluşturulan ML demolarını keşfetmek.
> - "gradio" kitaplığını kullanarak Python'da makine öğrenimi modeliniz için hızlı bir demo oluşturmak
> - Hugging Face Spaces ile demoları ücretsiz olarak barındırmak
> - Sınıfınız veya konferansınız için demonuzu Hugging Face kuruluşuna eklemek
>
> ***Süre: 20-40 dakika***
>
> 👉 [eğitime erişmek için burayı tıklayın](https://colab.research.google.com/github.com/huggingface/education-toolkit/tree/main/tutorials/TR/02_ml-demos-with-gradio.ipynb)
