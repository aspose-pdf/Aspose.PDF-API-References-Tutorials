---
title: Tạo liên kết tài liệu
linktitle: Tạo liên kết tài liệu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng tạo liên kết đến các tài liệu PDF khác bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-links-and-actions/create-document-link/
---
Liên kết tới tài liệu khác trong tệp PDF cho phép bạn tạo các liên kết có thể nhấp để chuyển hướng người dùng đến các tài liệu PDF khác. Với Aspose.PDF for .NET, bạn có thể dễ dàng tạo các liên kết như vậy bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF mà bạn muốn thêm liên kết đến tài liệu khác. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Mở tài liệu PDF

Bây giờ chúng tôi sẽ mở tài liệu PDF mà chúng tôi muốn thêm liên kết vào tài liệu khác bằng mã sau:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Bước 4: Tạo liên kết đến tài liệu khác

 Trong bước này, chúng ta sẽ tạo liên kết đến một tài liệu khác bằng cách sử dụng`LinkAnnotation` chú thích. Chúng tôi sẽ chỉ định tọa độ và khu vực của liên kết, cũng như hành động điều hướng đến tài liệu bên ngoài. Đây là mã tương ứng:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Bước 5: Lưu file cập nhật

 Bây giờ hãy lưu tệp PDF đã cập nhật bằng cách sử dụng`Save` phương pháp của`document` sự vật. Đây là mã tương ứng:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Mã nguồn mẫu để Tạo liên kết tài liệu bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Tạo đường link
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Lưu tài liệu đã cập nhật
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để liên kết đến các tài liệu khác bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để tạo các liên kết có thể nhấp vào trong tệp PDF của mình, chuyển hướng người dùng đến các tài liệu khác.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng nâng cao của liên kết tương tác.

### Câu hỏi thường gặp về tạo liên kết tài liệu

#### Hỏi: Liên kết tài liệu trong tệp PDF là gì?

Trả lời: Liên kết tài liệu trong tệp PDF là các liên kết có thể nhấp vào để hướng người dùng đến các tài liệu PDF khác. Các liên kết này nâng cao khả năng điều hướng bằng cách cung cấp một cách hiệu quả để kết nối nội dung liên quan và tạo điều kiện cho trải nghiệm đọc liền mạch.

#### Hỏi: Tôi có thể hưởng lợi từ việc tạo liên kết tài liệu như thế nào?

Đáp: Tạo liên kết tài liệu cho phép bạn thiết lập kết nối giữa các phần hoặc chủ đề khác nhau trong tài liệu PDF của mình. Tính năng này cho phép người dùng truy cập thông tin bổ sung hoặc các tài liệu liên quan một cách dễ dàng.

#### Câu hỏi: Aspose.PDF cho .NET hỗ trợ tạo liên kết tài liệu như thế nào?

Đáp: Aspose.PDF for .NET đơn giản hóa quá trình tạo liên kết tài liệu bằng cách cung cấp một bộ API toàn diện. Hướng dẫn từng bước được nêu trong hướng dẫn này trình bày cách thêm liên kết tài liệu vào tệp PDF của bạn.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của các liên kết tài liệu không?

Đ: Chắc chắn rồi! Aspose.PDF for .NET cung cấp các tùy chọn tùy chỉnh về giao diện liên kết tài liệu, bao gồm màu sắc, kiểu dáng và hiệu ứng di chuột. Bạn có thể điều chỉnh giao diện để phù hợp với thiết kế tài liệu của mình.

#### Hỏi: Có thể liên kết đến các phần hoặc trang cụ thể trong tài liệu khác không?

Đáp: Có, bạn có thể tạo liên kết điều hướng người dùng đến các trang hoặc phần cụ thể trong tài liệu PDF khác. Aspose.PDF for .NET cung cấp tính linh hoạt để xác định vị trí mục tiêu trong tài liệu được liên kết.

#### Câu hỏi: Làm cách nào tôi có thể đảm bảo rằng các liên kết tài liệu của tôi hoạt động tốt?

Đáp: Bằng cách làm theo hướng dẫn và mã mẫu được cung cấp, bạn có thể tự tin tạo các liên kết tài liệu chức năng. Bạn có thể kiểm tra các liên kết bằng cách mở tài liệu PDF đã tạo và nhấp vào liên kết.

#### Hỏi: Tôi có thể tạo nhiều liên kết tài liệu trong một tệp PDF không?

 Đ: Chắc chắn rồi! Bạn có thể tạo nhiều liên kết tài liệu trong một tài liệu PDF bằng cách sử dụng`LinkAnnotation`chú thích. Điều này cho phép bạn cung cấp cho người dùng quyền truy cập vào nhiều tài liệu liên quan từ các phần khác nhau.

#### Hỏi: Có bất kỳ hạn chế nào khi liên kết tới các tài liệu bên ngoài không?

Đáp: Khi liên kết đến các tài liệu bên ngoài, hãy đảm bảo rằng các tài liệu được liên kết có thể truy cập được và nằm trong các đường dẫn đã chỉ định. Điều quan trọng nữa là phải xem xét quyền của người dùng và tính tương thích của các tài liệu được liên kết.

#### Hỏi: Tôi có thể liên kết tới các tài liệu được lưu trữ trên web hoặc các kho lưu trữ trực tuyến không?

Đáp: Mặc dù hướng dẫn này tập trung vào việc liên kết đến các tài liệu cục bộ, Aspose.PDF dành cho .NET cũng hỗ trợ liên kết đến các URL web hoặc kho lưu trữ trực tuyến. Bạn có thể điều chỉnh mã được cung cấp để tạo liên kết tài liệu dựa trên web.