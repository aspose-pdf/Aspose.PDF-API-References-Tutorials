---
title: Đặt tập lệnh Java
linktitle: Đặt tập lệnh Java
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để đặt JavaScript trong các trường biểu mẫu trong tệp PDF.
type: docs
weight: 270
url: /vi/net/programming-with-forms/set-java-script/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng thư viện Aspose.PDF cho .NET để xác định JavaScript trong trường biểu mẫu của tài liệu PDF. Chúng tôi sẽ chỉ cho bạn cách định cấu hình các tác vụ JavaScript để thực hiện các thao tác cụ thể trên trường văn bản.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose.

## Bước 1: Cấu hình thư mục tài liệu

 Bước đầu tiên là định cấu hình thư mục tài liệu chứa tệp PDF bạn muốn làm việc. Bạn có thể dùng`dataDir` biến để chỉ định đường dẫn thư mục.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải tệp PDF đầu vào

Trong bước này, chúng tôi sẽ tải tệp PDF đầu vào bằng cách sử dụng`Document` lớp Aspose.PDF.

```csharp
// Tải tập tin PDF đầu vào
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Đảm bảo rằng tệp PDF đầu vào có trong thư mục tài liệu được chỉ định.

## Bước 3: Truy cập trường TextBox

 Để áp dụng JavaScript cho một trường văn bản cụ thể, trước tiên chúng ta cần truy cập vào trường đó. Trong ví dụ này, chúng tôi giả sử trường văn bản có tên là "textbox1". Sử dụng`doc.Form["textbox1"]` phương pháp để có được tương ứng`TextBoxField` sự vật.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Đảm bảo trường văn bản được chỉ định tồn tại trong tệp PDF đầu vào.

## Bước 4: Định cấu hình hành động JavaScript

 Bây giờ chúng ta đã truy cập vào trường văn bản, chúng ta có thể định cấu hình các hành động JavaScript được liên kết với trường này. Trong ví dụ này, chúng ta sẽ sử dụng hai hành động:`OnModifyCharacter` Và`OnFormat` . Những hành động này sẽ được xác định bằng cách sử dụng`JavascriptAction` các đối tượng.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Hãy nhớ tùy chỉnh các hành động JavaScript theo nhu cầu của bạn.

## Bước 5: Đặt giá trị trường ban đầu

Trước khi lưu tệp PDF kết quả, chúng ta có thể đặt giá trị ban đầu cho trường văn bản. Trong ví dụ này, chúng tôi sẽ đặt giá trị "123" cho trường.

```csharp
field.Value = "123";
```

Tùy chỉnh giá trị này theo nhu cầu của bạn.

## Bước 6: Lưu tệp PDF kết quả

 Bây giờ chúng ta đã hoàn tất việc thiết lập trường văn bản và các tác vụ JavaScript, chúng ta có thể lưu tệp PDF thu được bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Lưu kết quả PDF
doc.Save(dataDir);
```

Đảm bảo chỉ định đường dẫn và tên tệp đầy đủ cho tệp PDF kết quả.


### Mã nguồn mẫu cho Đặt tập lệnh Java bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải tập tin PDF đầu vào
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 chữ số sau điểm
// Không có dấu phân cách
// Kiểu âm = trừ
// Không có tiền tệ
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Đặt giá trị trường ban đầu
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Lưu kết quả PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã tìm hiểu cách sử dụng thư viện Aspose.PDF cho .NET để đặt JavaScript trong trường biểu mẫu của tài liệu PDF. Bằng cách làm theo các bước đã nêu, bạn có thể tùy chỉnh các tác vụ JavaScript để thực hiện các thao tác khác nhau trên các trường văn bản. Vui lòng khám phá thêm các tính năng của Aspose.PDF cho .NET để mở rộng khả năng thao tác với tệp PDF.


### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET để thêm JavaScript vào các thành phần biểu mẫu khác, chẳng hạn như hộp kiểm và nút radio không?

 Trả lời: Có, Aspose.PDF cho .NET cho phép bạn thêm JavaScript vào các thành phần biểu mẫu khác nhau, bao gồm hộp kiểm, nút radio và danh sách thả xuống. Bạn có thể dùng`JavascriptAction` lớp để xác định các hành động JavaScript cho các thành phần biểu mẫu khác nhau.

#### Câu hỏi: Có thể xác thực dữ liệu nhập của người dùng bằng JavaScript trong các trường biểu mẫu không?

 Đáp: Có, bạn có thể sử dụng JavaScript để xác thực dữ liệu nhập của người dùng vào các trường biểu mẫu. Bằng cách xác định các hành động JavaScript như`OnBlur` hoặc`OnKeystroke` đối với trường biểu mẫu, bạn có thể xác thực dữ liệu đã nhập và hiển thị thông báo lỗi nếu cần.

#### Câu hỏi: Tôi có thể thực thi các hàm JavaScript phức tạp bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể thực thi các hàm JavaScript phức tạp bằng Aspose.PDF cho .NET. Bạn có thể linh hoạt xác định các hàm JavaScript tùy chỉnh và gọi chúng trong`JavascriptAction`.

#### Câu hỏi: Aspose.PDF cho .NET có hỗ trợ các sự kiện JavaScript ngoài những sự kiện được đề cập trong hướng dẫn này không?

 Đáp: Có, Aspose.PDF for .NET hỗ trợ nhiều sự kiện JavaScript, bao gồm`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Và`OnMouseUp`, trong số những người khác. Bạn có thể sử dụng những sự kiện này để kích hoạt các hành động JavaScript dựa trên tương tác của người dùng.

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET để trích xuất mã JavaScript từ các tài liệu PDF hiện có không?

 Trả lời: Aspose.PDF for .NET cung cấp khả năng trích xuất mã JavaScript từ các tài liệu PDF hiện có. Bạn có thể dùng`JavascriptAction` class và các phương thức liên quan khác để truy cập và phân tích các hành động JavaScript ở dạng PDF.