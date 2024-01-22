---
title: Thêm trường biểu mẫu trong tài liệu PDF bằng Java
linktitle: Thêm trường biểu mẫu trong tài liệu PDF bằng Java
second_title: Aspose.PDF API xử lý PDF Java
description: Tìm hiểu cách thêm các trường biểu mẫu tương tác vào tài liệu PDF của bạn bằng Java và Aspose.PDF cho Java. Tạo các biểu mẫu PDF thân thiện với người dùng một cách dễ dàng.
type: docs
weight: 10
url: /vi/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## Giới thiệu

Việc thêm các trường biểu mẫu vào tài liệu PDF sẽ nâng cao chức năng của nó bằng cách cho phép người dùng nhập dữ liệu trực tiếp vào tài liệu. Điều này có thể cực kỳ hữu ích cho nhiều mục đích khác nhau, chẳng hạn như tạo biểu mẫu, khảo sát hoặc báo cáo có thể điền được với nội dung do người dùng tạo.

Chúng tôi sẽ sử dụng Aspose.PDF cho Java, một thư viện mạnh mẽ giúp đơn giản hóa thao tác PDF trong các ứng dụng Java. Với Aspose.PDF, bạn có thể dễ dàng tạo, sửa đổi và thao tác với tài liệu PDF, bao gồm cả việc thêm các trường biểu mẫu một cách linh hoạt.

## Thiết lập môi trường

Trước khi chúng ta đi sâu vào mã, bạn cần thiết lập môi trường phát triển của mình. Thực hiện theo các bước sau:

1.  Tải xuống Aspose.PDF cho Java: Truy cập trang web Aspose và tải xuống phiên bản mới nhất của Aspose.PDF cho Java. Bạn có thể tìm nó[đây](https://releases.aspose.com/pdf/java/).

2. Cài đặt Aspose.PDF: Sau khi tải xuống, hãy cài đặt Aspose.PDF bằng cách làm theo hướng dẫn cài đặt được cung cấp trên trang web.

3. Tạo một dự án Java: Tạo một dự án Java mới trong Môi trường phát triển tích hợp (IDE) ưa thích của bạn và đưa thư viện Aspose.PDF vào dự án của bạn.

## Tạo một tài liệu PDF mới

Hãy bắt đầu bằng cách tạo một tài liệu PDF mới. Trong ví dụ này, chúng tôi sẽ tạo một tệp PDF đơn giản có tiêu đề và một số hướng dẫn.

```java
// Nhập thư viện Aspose.PDF
import com.aspose.pdf.*;

public class AddFormFieldPDF {
    public static void main(String[] args) {
        // Tạo một tài liệu PDF mới
        Document doc = new Document();

        // Thêm một trang vào tài liệu
        Page page = doc.getPages().add();

        // Thêm tiêu đề
        TextFragment title = new TextFragment("Feedback Form");
        title.getTextState().setFontSize(18);
        title.getTextState().setFont(FontRepository.findFont("Arial"));
        page.getParagraphs().add(title);

        // Thêm hướng dẫn
        TextFragment instructions = new TextFragment("Please provide your feedback below:");
        instructions.getTextState().setFontSize(12);
        page.getParagraphs().add(instructions);

        // Lưu tài liệu vào một tập tin
        doc.save("FeedbackForm.pdf");
    }
}
```

Trong đoạn mã này, chúng tôi tạo một tài liệu PDF mới, thêm trang và chèn tiêu đề cũng như một số hướng dẫn.

## Thêm trường biểu mẫu

Bây giờ, hãy chuyển sang thêm các trường biểu mẫu vào tài liệu PDF của chúng tôi. Chúng tôi sẽ bao gồm các trường văn bản, hộp kiểm và nút radio để tạo biểu mẫu phản hồi tương tác.

### Trường văn bản

Trường văn bản cho phép người dùng nhập văn bản. Đây là cách bạn có thể thêm trường văn bản:

```java
// Tạo trường văn bản
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // Đặt kiểu đường viền
textField.setPartialName("txtName"); // Đặt tên trường
textField.setMultiline(false); // Vô hiệu hóa nhiều dòng
page.getAnnotations().add(textField);
```

### Hộp kiểm

Các hộp kiểm được sử dụng cho các tùy chọn nhị phân (ví dụ: câu hỏi có/không). Dưới đây là cách thêm hộp kiểm:

```java
// Tạo một hộp kiểm
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // Đặt tên trường
checkboxField.setChecked(false); // Ban đầu không được chọn
page.getAnnotations().add(checkboxField);
```

### Nút chọn

Nút radio được sử dụng khi người dùng cần chọn một tùy chọn từ một nhóm. Mỗi tùy chọn là một nút radio riêng biệt nhưng chúng thuộc cùng một nhóm. Dưới đây là cách thêm nút radio:

```java
// Tạo nút radio
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // Đặt tên trường cho tùy chọn 1
option2.setPartialName("optNo"); // Đặt tên trường cho tùy chọn 2

//Thêm tùy chọn vào nhóm nút radio
RadioButtonOptionField[] options = {option1, option2};
RadioButtonField radioButtonField = new RadioButtonField(page, options);
page.getAnnotations().add(radioButtonField);
```

Với các ví dụ về mã này, bạn có thể thêm trường văn bản, hộp kiểm và nút radio vào tài liệu PDF của mình. Đảm bảo tùy chỉnh các thuộc tính của chúng nếu cần, chẳng hạn như tên trường và giá trị mặc định.

## Tùy chỉnh các trường biểu mẫu

Tùy chỉnh các trường biểu mẫu cho phép bạn kiểm soát giao diện và hành vi của chúng. Bạn có thể thay đổi các thuộc tính như kích thước phông chữ, màu văn bản, kiểu đường viền, v.v.

### Thay đổi thuộc tính trường

Giả sử bạn muốn thay đổi kích thước phông chữ và màu văn bản của trường văn bản:

```java
textField.getTextState().setFontSize(14);
textField.getTextState().setForegroundColor(Color.getGreen());
```

### Xác thực trường

Bạn cũng có thể đặt quy tắc xác thực cho các trường biểu mẫu. Ví dụ: bạn có thể yêu cầu người dùng nhập địa chỉ email hợp lệ vào trường văn bản:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## Đặt giá trị trường

Để điền trước dữ liệu vào các trường biểu mẫu, bạn có thể đặt giá trị mặc định của chúng theo chương trình. Điều này rất hữu ích cho việc tạo mẫu hoặc điền trước thông tin đã biết.

```java
textField.setValue("John Doe"); // Đặt giá trị mặc định cho trường văn bản
checkboxField.setChecked(true); // Chọn hộp kiểm theo mặc định
```

## Gửi biểu mẫu và xác nhận

Việc thêm các trường biểu mẫu chỉ là một nửa câu chuyện; bạn cũng sẽ muốn

 để cho phép gửi và xác nhận biểu mẫu.

### Nộp mẫu

Để cho phép người dùng gửi dữ liệu biểu mẫu, bạn cần chỉ định một hành động, chẳng hạn như gửi email hoặc gửi tới máy chủ web. Dưới đây là ví dụ về cách thiết lập nút gửi:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://yourserver.com/submit", SubmitFormActionType.URL, "FeedbackForm.pdf"));
page.getAnnotations().add(submitButton);
```

### Xác thực mẫu

Xác thực đảm bảo rằng đầu vào của người dùng đáp ứng các tiêu chí cụ thể. Chẳng hạn, bạn có thể xác thực trường số điện thoại để chỉ chấp nhận các số:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## Lưu và xuất

Sau khi bạn đã tạo và tùy chỉnh tài liệu PDF của mình bằng các trường biểu mẫu, đã đến lúc lưu hoặc xuất tài liệu đó. Aspose.PDF cung cấp nhiều tùy chọn khác nhau cho việc này.

### Lưu vào tệp cục bộ

Để lưu tài liệu PDF vào một tệp cục bộ, hãy sử dụng mã sau:

```java
doc.save("FeedbackForm.pdf");
```

### Lưu vào luồng

 Để lưu tài liệu PDF vào một luồng, bạn có thể sử dụng`OutputStream` lớp học:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## Phần kết luận

Trong hướng dẫn toàn diện này, chúng tôi đã khám phá cách thêm các trường biểu mẫu vào tài liệu PDF bằng Java và Aspose.PDF cho Java. Bạn đã học cách tạo trường văn bản, hộp kiểm và nút radio, tùy chỉnh thuộc tính của chúng, đặt giá trị mặc định, bật gửi và xác thực biểu mẫu cũng như lưu/xuất tài liệu PDF.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể thiết lập danh sách thả xuống ở dạng PDF?

 Để tạo danh sách thả xuống (hộp tổ hợp) ở dạng PDF, bạn có thể sử dụng`ComboBoxField` lớp được cung cấp bởi Aspose.PDF cho Java. Thực hiện theo cách tiếp cận tương tự như được hiển thị cho các trường biểu mẫu khác và tùy chỉnh các tùy chọn bằng cách sử dụng`AddItem` phương pháp. Bạn có thể tìm thấy tài liệu chi tiết về điều này trên trang web Aspose.

### Aspose.PDF cho Java có tương thích với các thư viện và khung công tác Java khác không?

Có, Aspose.PDF cho Java tương thích với nhiều thư viện và khung công tác Java khác nhau. Bạn có thể tích hợp nó vào các ứng dụng Java của mình, cho dù bạn đang sử dụng Spring, JavaFX hay các khung công tác phổ biến khác. Đảm bảo kiểm tra tài liệu và tài nguyên để biết các nguyên tắc tích hợp cụ thể.

### Tôi có thể bảo vệ bằng mật khẩu biểu mẫu PDF được tạo bằng Aspose.PDF cho Java không?

Tuyệt đối! Aspose.PDF for Java cho phép bạn thêm mật khẩu bảo vệ vào tài liệu PDF của mình, bao gồm cả biểu mẫu. Bạn có thể đặt cả mật khẩu cấp người dùng và cấp chủ sở hữu để hạn chế quyền truy cập và quyền. Tham khảo tài liệu để biết hướng dẫn chi tiết về cách triển khai tính năng bảo mật này.

### Làm cách nào tôi có thể trích xuất dữ liệu được gửi qua biểu mẫu PDF?

Để trích xuất dữ liệu được gửi qua biểu mẫu PDF, bạn sẽ cần xử lý việc gửi biểu mẫu trên máy chủ hoặc chương trình phụ trợ ứng dụng của mình. Khi người dùng gửi biểu mẫu, bạn có thể nhận dữ liệu và xử lý dữ liệu đó nếu cần. Aspose.PDF cung cấp các công cụ để trích xuất dữ liệu biểu mẫu theo chương trình từ tài liệu PDF ở phía máy chủ.

### Tôi có thể tự động tạo các biểu mẫu PDF dựa trên thông tin đầu vào của người dùng không?

Có, bạn có thể tự động tạo các biểu mẫu PDF dựa trên thông tin đầu vào của người dùng bằng cách sử dụng Aspose.PDF for Java. Tùy thuộc vào đầu vào của người dùng hoặc logic ứng dụng, bạn có thể tạo tài liệu PDF với các trường biểu mẫu và bố cục khác nhau. Tính linh hoạt này giúp có thể tạo các biểu mẫu tùy chỉnh phù hợp với nhu cầu hoặc tình huống cụ thể của người dùng.