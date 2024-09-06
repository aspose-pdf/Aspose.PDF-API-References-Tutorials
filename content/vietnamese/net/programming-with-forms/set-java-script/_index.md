---
title: Đặt Java Script
linktitle: Đặt Java Script
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để thiết lập JavaScript vào các trường biểu mẫu trong tệp PDF.
type: docs
weight: 270
url: /vi/net/programming-with-forms/set-java-script/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng thư viện Aspose.PDF cho .NET để xác định JavaScript trong trường biểu mẫu của tài liệu PDF. Chúng tôi sẽ chỉ cho bạn cách cấu hình các hành động JavaScript để thực hiện các thao tác cụ thể trên trường văn bản.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.PDF dành cho .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose.

## Bước 1: Cấu hình thư mục tài liệu

 Bước đầu tiên là cấu hình thư mục tài liệu nơi tệp PDF bạn muốn làm việc được đặt. Bạn có thể sử dụng`dataDir` biến để chỉ định đường dẫn thư mục.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải tệp PDF đầu vào

 Trong bước này, chúng tôi sẽ tải tệp PDF đầu vào bằng cách sử dụng`Document` lớp Aspose.PDF.

```csharp
// Tải tệp PDF đầu vào
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Đảm bảo rằng tệp PDF đầu vào có trong thư mục tài liệu được chỉ định.

## Bước 3: Truy cập vào trường TextBox

 Để áp dụng JavaScript cho một trường văn bản cụ thể, trước tiên chúng ta cần truy cập vào trường đó. Trong ví dụ này, chúng ta giả sử trường văn bản được gọi là "textbox1". Sử dụng`doc.Form["textbox1"]` phương pháp để có được tương ứng`TextBoxField` sự vật.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Đảm bảo trường văn bản được chỉ định có trong tệp PDF đầu vào.

## Bước 4: Cấu hình hành động JavaScript

 Bây giờ chúng ta đã truy cập vào trường văn bản, chúng ta có thể cấu hình các hành động JavaScript liên quan đến trường này. Trong ví dụ này, chúng ta sẽ sử dụng hai hành động:`OnModifyCharacter` Và`OnFormat` . Những hành động này sẽ được xác định bằng cách sử dụng`JavascriptAction` đồ vật.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Hãy tùy chỉnh các hành động JavaScript theo nhu cầu của bạn.

## Bước 5: Thiết lập giá trị trường ban đầu

Trước khi lưu PDF kết quả, chúng ta có thể đặt giá trị ban đầu cho trường văn bản. Trong ví dụ này, chúng ta sẽ đặt giá trị "123" cho trường.

```csharp
field.Value = "123";
```

Tùy chỉnh giá trị này theo nhu cầu của bạn.

## Bước 6: Lưu PDF kết quả

 Bây giờ chúng ta đã hoàn tất việc thiết lập trường văn bản và hành động JavaScript, chúng ta có thể lưu tệp PDF kết quả bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Lưu PDF kết quả
doc.Save(dataDir);
```

Hãy chắc chắn chỉ định đường dẫn đầy đủ và tên tệp cho tệp PDF kết quả.


### Mã nguồn mẫu cho Set Java Script sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải tệp PDF đầu vào
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 chữ số sau dấu chấm
// Không có dấu phân cách
// Phong cách tiêu cực = trừ
// Không có tiền tệ
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Đặt giá trị trường ban đầu
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Lưu PDF kết quả
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng thư viện Aspose.PDF cho .NET để đặt JavaScript vào trường biểu mẫu của tài liệu PDF. Bằng cách làm theo các bước được nêu, bạn có thể tùy chỉnh các hành động JavaScript để thực hiện nhiều thao tác khác nhau trên các trường văn bản. Hãy thoải mái khám phá thêm các tính năng của Aspose.PDF cho .NET để mở rộng khả năng thao tác với các tệp PDF.


### Câu hỏi thường gặp

#### H: Tôi có thể sử dụng Aspose.PDF cho .NET để thêm JavaScript vào các thành phần biểu mẫu khác, chẳng hạn như hộp kiểm và nút radio không?

 A: Có, Aspose.PDF cho .NET cho phép bạn thêm JavaScript vào nhiều thành phần biểu mẫu khác nhau, bao gồm hộp kiểm, nút radio và danh sách thả xuống. Bạn có thể sử dụng`JavascriptAction` lớp để xác định các hành động JavaScript cho các phần tử biểu mẫu khác nhau.

#### H: Có thể xác thực dữ liệu đầu vào của người dùng bằng JavaScript trong các trường biểu mẫu không?

 A: Có, bạn có thể sử dụng JavaScript để xác thực dữ liệu đầu vào của người dùng trong các trường biểu mẫu. Bằng cách xác định các hành động JavaScript như`OnBlur` hoặc`OnKeystroke` đối với trường biểu mẫu, bạn có thể xác thực dữ liệu đã nhập và hiển thị thông báo lỗi nếu cần.

#### H: Tôi có thể thực thi các hàm JavaScript phức tạp bằng Aspose.PDF cho .NET không?

 A: Có, bạn có thể thực hiện các hàm JavaScript phức tạp bằng Aspose.PDF cho .NET. Bạn có thể linh hoạt định nghĩa các hàm JavaScript tùy chỉnh và gọi chúng trong`JavascriptAction`.

#### H: Aspose.PDF cho .NET có hỗ trợ các sự kiện JavaScript khác ngoài những sự kiện được đề cập trong hướng dẫn này không?

 A: Có, Aspose.PDF cho .NET hỗ trợ nhiều sự kiện JavaScript, bao gồm`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Và`OnMouseUp`, trong số những thứ khác. Bạn có thể sử dụng các sự kiện này để kích hoạt các hành động JavaScript dựa trên tương tác của người dùng.

#### H: Tôi có thể sử dụng Aspose.PDF cho .NET để trích xuất mã JavaScript từ các tài liệu PDF hiện có không?

 A: Aspose.PDF cho .NET cung cấp khả năng trích xuất mã JavaScript từ các tài liệu PDF hiện có. Bạn có thể sử dụng`JavascriptAction` lớp và các phương pháp liên quan khác để truy cập và phân tích các hành động JavaScript ở dạng PDF.