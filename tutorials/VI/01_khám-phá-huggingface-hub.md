# Hội thảo : Khám phá Hugging Face Hub

<aside>

💡 **Chào mừng các bạn!**

Chúng tôi đã tập hợp một bộ công cụ mà bất kỳ ai cũng có thể sử dụng để dễ dàng chuẩn bị cho các hội thảo, sự kiện, bài tập về nhà, hoặc lớp học. Nội dung hoàn toàn độc lập có thể dễ dàng kết hợp với các tài liệu khác. Nội dung này hoàn toàn **miễn phí** và sử dụng các công nghệ Mã nguồn mở nổi tiếng (`transformers`, `gradio`, v.v.).
  
Bạn có thể tìm thấy tất cả các bài hướng dẫn và tài liệu mà chúng tôi đã tổng hợp [tại đây](https://www.notion.so/Education-Toolkit-7b4a9a9d65ee4a6eb16178ec2a4f3599).

</aside>

**Thời lượng:** 20 đến 40 phút

**Mục tiêu:** Tìm hiểu cách sử dụng hiệu quả [nền tảng Hub](http://hf.co) miễn phí để có thể cộng tác trong hệ sinh thái và trong các nhóm các dự án Học máy (ML).

Mục tiêu học tập:

- Tìm hiểu và khám phá hơn 30,000 mô hình được chia sẻ trên Hub.
- Tìm hiểu các phương pháp hiệu quả để tìm đúng mô hình và bộ dữ liệu phù hợp cho bài toán của riêng bạn.
- Học cách đóng góp và cộng tác.
- Khám phá các bản thử nghiệm Học máy được tạo bởi cộng đồng.

**Định dạng:** Có thể là bài thực hành ngắn hoặc bài về nhà.

**Đối tượng:** Sinh viên ở mọi trình độ quan tâm đến cách sử dụng các mô hình hiện có hoặc cách chia sẻ các mô hình của họ.

**Điều kiện cơ bản**:

- Hiểu biết ở mức độ vững về Học máy.
- (Tùy chọn, nhưng khuyến khích) Có kinh nghiệm sử dụng Git ([tài liệu](https://learngitbranching.js.org/))

## **Tại sao lại là Hub?**

Hub là một nền tảng tập trung, nơi mọi người có thể chia sẻ và khám phá các mô hình, các bộ dữ liệu, và các bản thử nghiệm Học máy. Vấn đề "Giải AI" sẽ không được giải quyết bởi một công ty duy nhất, mà bằng văn hóa chia sẻ kiến thức và nguồn lực. Vì lý do này, Hub hướng tới việc xây dựng bộ sưu tập các mô hình, các bộ dữ liệu, và các bản thử nghiệm mã nguồn mở phong phú nhất.

Dưới đây là một số thông tin về Hugging Face Hub:

- Có hơn 30,000 mô hình mở.
- Có các mô hình cho Xử lý Ngôn ngữ Tự nhiên (NLP), Thị giác Máy tính, Âm thanh/Giọng nói, và Học Tăng cường!
- Có những mô hình phục vụ cho hơn 180 ngôn ngữ.
- Bất kỳ thư viện Học máy nào cũng có thể tận dụng Hub: từ TensorFlow và PyTorch cho đến các tích hợp nâng cao với spaCy, SpeechBrain, và 20 thư viện khác.

## Khám phá một mô hình

Cùng bắt đầu khám phá các mô hình thôi! Bạn có thể truy cập 30,000 mô hình tại [hf.co/models](http://hf.co/models). Bạn sẽ thấy [gpt2](https://huggingface.co/gpt2) là một trong những mô hình có nhiều lượt tải xuống nhất. Hãy bấm vào nó.

Trang web sẽ đưa bạn đến thẻ mô hình khi bạn bấm vào một mô hình. Thẻ mô hình là một công cụ ghi lại các mô hình, cung cấp thông tin hữu ích về các mô hình và rất cần thiết cho việc khám phá cũng như tái tạo mô hình.

Giao diện có rất nhiều thành phần, vì vậy hãy cùng nhau xem qua chúng tại: [https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- Ở trên cùng, bạn có thể tìm thấy các **thẻ** khác nhau cho các tác vụ (*Text Generation* tương ứng Tạo văn bản, *Image Classification* tương ứng Phân loại Hình ảnh, v.v.), các khung (*PyTorch*, *TensorFlow*, v.v.), ngôn ngữ mô hình sử dụng (*English*, *Arabic*, v.v.), và giấy phép (ví dụ: *MIT*).

![](../../images/mode_card_tags.png)

- Ở cột bên phải, bạn có thể nghịch với mô hình trực tiếp trên trình duyệt bằng cách sử dụng *Inference API*. GPT2 là một mô hình tạo văn bản, vì vậy nó sẽ tạo ra văn bản dựa trên dữ liệu đầu vào ban đầu. Hãy thử nhập nội dung như  “It was a bright and sunny day.” (“Hôm nay là một ngày nắng đẹp.”).

![](../../images/model_card_inference_api.png)

- Ở chính giữa, bạn có thể xem qua nội dung của thẻ mô hình. Nó có các phần như Mục đích sử dụng & giới hạn, Quy trình huấn luyện, và Thông tin trích dẫn.

![](../../images/model_card_content.png)

Tất cả những dữ liệu này đến từ đâu? Tại Hugging Face, mọi thứ đều có trong **kho lưu trữ Git** và có nguồn mở. Bạn có thể nhấn vào tab “Files and Versions” tương ứng Tệp và Phiên bản, tab này sẽ cho phép bạn xem tất cả các tệp trong kho, bao gồm cả các trọng số của mô hình. Thẻ mô hình là một tệp **([README.md](http://README.md))** mà phía trên đầu nội dung chứa siêu dữ liệu chẳng hạn như các thẻ.

![](../../images/model_card_git.png)

Vì tất cả các mô hình đều dựa trên kho lưu trữ Git, bạn có thể kiểm soát các phiên bản tức thì. Giống như GitHub, bạn có thể thực hiện các thao tác như clone (sao chép) Git, add (thêm), commit (cam kết), branch (phân nhánh) và push (đẩy). Nếu bạn chưa bao giờ sử dụng Git, chúng tôi khuyến khích bạn tham khảo [tài liệu này](https://learngitbranching.js.org/).

**Thử thách 1**. Mở tệp `config.json` của kho lưu trữ GPT2. Tệp cấu hình chứa các siêu tham số cũng như thông tin hữu ích để tải mô hình. Từ tệp này, hãy trả lời câu hỏi dưới đây:

- Hàm kích hoạt là phần nào?
- Kích thước bộ từ vựng là bao nhiêu?

## **Khám phá các mô hình**

Cho tới phần này, chúng ta đã khám phá một mô hình duy nhất. Hãy thoải mái tìm hiểu! Ở bên trái của [https://huggingface.co/models](https://huggingface.co/models), bạn có thể lọc các mô hình theo những tiêu chí khác nhau:

- **Các tác vụ:** Hub hỗ trợ hàng tá tác vụ trong các lĩnh vực khác nhau: Thị giác Máy tính, Xử lý Ngôn ngữ Tự nhiên, Âm thanh, v.v. Bạn có thể nhấp vào +13 để xem tất cả các tác vụ có sẵn.
  - **Các thư viện:** Mặc dù Hub ban đầu được xây dựng cho các mô hình Transformers, Hub có tích hợp thêm với hàng tác các thư viện khác. Bạn có thể tìm thấy các mô hình của Keras, spaCy, allenNLP, v.v.
- **Các bộ dữ liệu:** Hub cũng lưu trữ hàng nghìn bộ dữ liệu mà bạn sẽ tìm hiểu thêm về sau.

![](../../images/model_card_filters.png)

- **Các ngôn ngữ:** Nhiều mô hình trên Hub có liên quan đến NLP. Bạn có thể tìm thấy các mô hình phục vụ hàng trăm ngôn ngữ, bao gồm cả các ngôn ngữ ít tài nguyên.

**Thử thách 2**. Có bao nhiêu mô hình token classification (phân loại token) bằng tiếng Anh?

**Thử thách 3**. Nếu bạn phải chọn một mô hình tiếng Tây Ban Nha cho bài toán Nhận dạng Giọng nói Tự động, bạn sẽ chọn mô hình nào? (Nó có thể là bất kì mô hình nào cho tác vụ và ngôn ngữ này).

## Thêm một mô hình

Giả sử bạn muốn tải một mô hình lên Hub. Mô hình này có thể là một mô hình từ bất kỳ thư viện Học máy nào: Scikit-learn, Keras, Transformers, v.v.

Hãy cùng đi qua các bước dưới đây:

1. Truy cập [huggingface.co/new](http://huggingface.co/new) để tạo kho lưu trữ mô hình mới. Kho lưu trữ bạn tạo có thể thiết lập chế độ công khai hoặc riêng tư.
2. Bạn bắt đầu với một kho lưu trữ công khai có sẵn thẻ mô hình. Bạn có thể tải mô hình của bạn sử dụng giao diện người dùng Web hoặc sử dụng Git. Nếu bạn chưa bao giờ sử dụng Git trước đó, chúng tôi khuyên bạn chỉ nên sử dụng giao diện Web. Bạn có thể bấm vào Add File tương ứng Thêm tệp và kéo và thả các tệp bạn muốn thêm. Nếu bạn muốn hiểu toàn bộ quy trình làm việc, hãy bắt đầu với phương pháp Git.

    1. Cài đặt cả git và git-lfs trên hệ thống của bạn.
        1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
        2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). Các tệp lớn cần được tải lên bằng Git LFS. Git không hoạt động tốt khi tệp của bạn vượt một vài megabyte, điều thường xảy ra trong Học máy. Mô hình Học máy có thể lên đến gigabyte hoặc terabyte! 🤯
    2. Sao chép kho lưu trữ bạn vừa tạo

        ```python
        git clone https://huggingface.co/<your-username>/<your-model-id>
        ```

    3. Vào bên trong thư mục và khởi tạo Git LFS
        1. Không bắt buộc. Chúng tôi đã cung cấp một danh sách các phần mở rộng tệp phổ biến cho các tệp lớn trong `.gitattributes`. Nếu các tập dữ liệu bạn muốn tải lên không được đề cập trong `.gitattributes`, bạn có thể thêm bằng câu lệnh dưới đây:

            ```python
            git lfs track "*.your_extension"
            ```

            ```python
             git lfs install
            ```

    4. Thêm tệp của bạn vào kho lưu trữ. Các tệp phụ thuộc vào khung/thư viện bạn sử dụng. Nhìn chung, quan trọng là bạn cung cấp tất cả các thứ cần thiết để tải mô hình. Ví dụ:
        1. Với TensorFlow, ta có thể muốn tải lên SavedModel hoặc tệp `h5`.
        2. Với PyTorch, ta thường sử dụng `pytorch_model.bin`.
        3. Với Scikit-Learn, ta thường là một tệp `joblib`.

        Dưới đây là 1 ví dụ trong Python khi lưu 1 mô hình Scikit-Learn.

        ```python
        from sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        from joblib import dump, load
        dump(reg, 'model.joblib')
        ```

    5. Cam kết và đẩy các tệp của bạn lên (đảm bảo tệp đã lưu nằm trong kho lưu trữ)

    ```python
    git add .
    git commit -m "First model version"
    git push
    ```

Và chúng ta đã hoàn thành! Bạn có thể kiểm tra kho lưu trữ của mình với tất cả các tệp được thêm gần đây!

![](../../images/model_card_updated_repo.png)

Giao diện người dùng cho phép bạn khám phá các tệp mô hình và các cam kết cũng như xem sự thay đổi ở mỗi cam kết.

**Thử thách 4**. Đến lượt bạn rồi! Hãy tải lên một mô hình của thư viện bạn tuỳ chọn.

Giờ thì mô hình đã được lưu trong Hub, những người khác có thể tìm thấy chúng! Bạn cũng có thể cộng tác với những người khác một cách dễ dàng bằng cách tạo một tổ chức. Lưu trữ thông qua Hub cho phép một nhóm cập nhật kho lưu trữ và làm những việc bạn có thể đã quen thuộc, chẳng hạn như làm việc trong các nhánh và cộng tác. Hub cũng cho phép lập phiên bản trong các mô hình của bạn: nếu checkpoint của mô hình đột nhiên bị hỏng, bạn luôn có thể quay lại phiên bản trước đó.

Ở đầu `README`, bạn có thể tìm thấy một số siêu dữ liệu. Bạn sẽ chỉ tìm thấy giấy phép thời điểm hiện tại, nhưng bạn có thể thêm nhiều thứ khác. Hãy thử một số trong số đó:

```yaml
 tags:
- es       # Nó sẽ tự động được phát hiện là dạng thẻ ngôn ngữ.
- bert     # Bạn có thể thêm các thẻ bổ sung để lọc.
- text-classification # Nó sẽ tự động được phát hiện là dạng thẻ tác vụ.
datasets:
- llamas # Nó sẽ liến kết đến một bộ dữ liệu trên Hub nếu có tồn tại.
```

**Thử thách 5**. Sử dụng [tài liêụ](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined), thay đổi ví dụ mặc định trong tiện ích con.

Siêu dữ liệu cho phép mọi người khám phá mô hình của bạn một cách nhanh chóng. Mô hình của bạn bây giờ sẽ hiển thị khi bạn tìm kiếm các mô hình phân loại văn bản bằng tiếng Tây Ban Nha. Mô hình cũng sẽ hiển thị khi nhìn vào tập dữ liệu.

Khoan đã ... bộ dữ liệu?

## Các bộ dữ liệu

Với các quy trình Học máy, bạn thường có một tập dữ liệu để huấn luyện mô hình. Hub lưu trữ khoảng 3,000 bộ dữ liệu có nguồn mở và có thể sử dụng miễn phí trên nhiều miền. Trên hết, thư viện mã nguồn mở [`datasets`](https://huggingface.co/docs/datasets/) cho phép sử dụng dễ dàng các bộ dữ liệu này, kể cả những bộ dữ liệu khổng lồ, tận dụng tính năng đầy tiện ích như phát trực tuyến. Bài thực hành này sẽ không đi cụ thể vào từng thư viện, nhưng sẽ giải thích cách khám phá chúng.

Tương tự như mô hình, bạn có thể truy cập [https://hf.co/datasets](https://hf.co/datasets). Ở bên trái, bạn có thể tìm thấy các bộ lọc khác nhau dựa trên tác vụ, giấy phép và kích thước của tập dữ liệu.

Hãy cùng khám phá [GLUE](https://huggingface.co/datasets/glue), một bộ dữ liệu nổi tiếng phục vụ cho việc kiểm thử hiệu suất các mô hình NLP.

- Tương tự với kho lưu trữ mô hình, bạn có thẻ dữ liệu lưu trữ bộ dữ liệu. Nếu bạn kéo xuống một chút, bạn sẽ tìm thấy những thông tin như tóm tắt về bộ dữ liệu, cấu trúc dữ liệu, và hơn thế nữa.

![](../../images/datasets_card.png)

- Ở trên cùng, bạn có thể khám phá một phần của tập dữ liệu trực tiếp trong trình duyệt. Bộ dữ liệu GLUE được chia thành nhiều tập dữ liệu con (hoặc tập con) mà bạn có thể chọn, chẳng hạn như COLA và QNLI.

  ![](../../images/datasets_slices.png)

- Ở bên phải của thẻ dữ liệu, bạn có thể thấy một danh sách các mô hình được huấn luyện trên bộ dữ liệu này.

![](../../images/datasets_models_trained.png)

**Thử thách 6**. Tìm kiếm bộ dữ liệu Common Voice. Trả lời những câu hỏi sau:

- Bộ dữ liệu Common Voice có thể được sử dụng cho những tác vụ nào?
- Có bao nhiêu ngôn ngữ được đề cập trong bộ dữ liệu này?
- Bộ dữ liệu được tách ra thành những tệp con nào?

## Các bản thử nghiệm Học máy

Chia sẻ các mô hình và bộ dữ liệu của bạn là một điều tuyệt vời, nhưng việc tạo một bản thử nghiệm mang tính tương tác và công khai thậm chí còn thú vị hơn. Bản thử nghiệm của các mô hình là một phần ngày càng quan trọng của hệ sinh thái, cho phép:

- các nhà phát triển mô hình dễ dàng **trình bày** thành quả công việc của họ cho nhiều đối tượng, chẳng hạn như trong các bài thuyết trình, hội nghị, và các dự án khóa học của các bên liên quan;
- tăng **khả năng tái tạo** trong Học máy bằng cách hạ thấp rào cản để kiểm thử mô hình;
- chia sẻ với các đối tượng không chuyên về kỹ thuật **tầm ảnh hưởng của mô hình**;
- xây dựng một hồ sơ danh mục **Học máy**.

Có các khung mã nguồn mở trên nền Python như Gradio và Streamlit cho phép xây dựng các bản thử nghiệm này rất dễ dàng, và có các công cụ như Hugging Face [Spaces](http://hf.co/spaces/launch) cho phép lưu trữ và chia sẻ chúng. Với tư cách là một bài thực hành tiếp nối, chúng tôi khuyến khích bạn nên thực hiện bài hướng dẫn **Xây dựng và lưu trữ bản thử nghiệm Học máy với Gradio và Hugging Face***.

> Trong bài hướng dẫn này, bạn có thể:
>
> - Khám phá các bản thử nghiệm Học máy do cộng đồng tạo ra.
> - Xây dựng bản thử nghiệm nhanh cho mô hình Học máy với Python sử dụng thư viện `gradio`.
> - Lưu trữ các bản thử nghiệm miễn phí trên Hugging Face Spaces.
> - Thêm bản thử nghiệm của bạn vào Hugging Face để phục vụ cho lớp học hoặc hội nghị của bạn.
>
> **_Thời lượng: 20-40 phút_**
>
> 👉 [bấm vào đây để truy cập bài hướng dẫn](https://colab.research.google.com/github.com/huggingface/education-toolkit/tree/main/02_ml-demos-with-gradio.ipynb).
