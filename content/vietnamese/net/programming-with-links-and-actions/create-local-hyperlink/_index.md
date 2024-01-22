---
title: Tạo siêu liên kết cục bộ trong tệp PDF
linktitle: Tạo siêu liên kết cục bộ trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng tạo siêu liên kết cục bộ trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-links-and-actions/create-local-hyperlink/
---
Tạo siêu liên kết cục bộ trong tệp PDF cho phép bạn tạo các liên kết có thể nhấp để đưa người dùng đến các trang khác trong cùng một tài liệu PDF. Với Aspose.PDF for .NET, bạn có thể dễ dàng tạo các liên kết như vậy bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Trong bước này, bạn cần chỉ định đường dẫn đến thư mục mà bạn muốn lưu tệp PDF thu được. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Tạo một phiên bản của Tài liệu

 Chúng ta sẽ tạo một thể hiện của`Document` class để thể hiện tài liệu PDF của chúng tôi. Đây là mã tương ứng:

```csharp
Document doc = new Document();
```

## Bước 4: Thêm trang và văn bản bằng siêu liên kết

Trong bước này, chúng tôi sẽ thêm một trang vào tài liệu PDF của mình và thêm một số văn bản chứa các siêu liên kết cục bộ. Chúng tôi sẽ xác định các trang mục tiêu cho mỗi liên kết. Đây là mã tương ứng:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Bước 5: Lưu tài liệu đã cập nhật

 Bây giờ hãy lưu tệp PDF đã cập nhật bằng cách sử dụng`Save` phương pháp của`doc` sự vật. Đây là mã tương ứng:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu để Tạo siêu liên kết cục bộ bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo phiên bản tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Tạo phiên bản đoạn văn bản
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Tạo phiên bản siêu liên kết cục bộ
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Đặt trang đích cho ví dụ liên kết
link.TargetPageNumber = 7;
// Đặt siêu liên kết TextFragment
text.Hyperlink = link;
//Thêm văn bản vào bộ sưu tập đoạn văn của Trang
page.Paragraphs.Add(text);
// Tạo phiên bản TextFragment mới
text = new TextFragment("link page number test to page 1");
// TextFragment nên được thêm vào trên trang mới
text.IsInNewPage = true;
// Tạo một phiên bản siêu liên kết cục bộ khác
link = new LocalHyperlink();
// Đặt trang đích cho siêu liên kết thứ hai
link.TargetPageNumber = 1;
// Đặt liên kết cho TextFragment thứ hai
text.Hyperlink = link;
// Thêm văn bản vào bộ sưu tập đoạn văn của đối tượng trang
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Lưu tài liệu đã cập nhật
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để tạo siêu liên kết cục bộ trong tệp PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để tạo các liên kết có thể nhấp vào để đưa người dùng đến các trang khác trong cùng một tài liệu.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng siêu liên kết nâng cao.

### Câu hỏi thường gặp về tạo siêu liên kết cục bộ trong tệp PDF

#### Câu hỏi: Siêu liên kết cục bộ trong tệp PDF là gì?

Trả lời: Các siêu liên kết cục bộ trong tệp PDF là các liên kết có thể nhấp vào để điều hướng người dùng đến các trang khác nhau trong cùng một tài liệu. Các liên kết này tăng cường điều hướng và cho phép người đọc truy cập nhanh vào các phần có liên quan.

#### Hỏi: Các siêu liên kết cục bộ có thể mang lại lợi ích cho tài liệu PDF của tôi như thế nào?

Đáp: Các siêu liên kết cục bộ cung cấp một cách hiệu quả để kết nối nội dung liên quan trong cùng một tài liệu PDF. Chúng cải thiện trải nghiệm người dùng bằng cách cho phép người đọc nhanh chóng chuyển đến các phần cụ thể mà không cần cuộn qua toàn bộ tài liệu.

#### Câu hỏi: Aspose.PDF cho .NET hỗ trợ việc tạo siêu liên kết cục bộ như thế nào?
Trả lời: Aspose.PDF for .NET cung cấp hỗ trợ toàn diện để tạo siêu liên kết cục bộ. Hướng dẫn từng bước được cung cấp trong hướng dẫn này trình bày cách thêm siêu liên kết cục bộ vào tài liệu PDF của bạn bằng C#.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của siêu liên kết cục bộ không?

Trả lời: Có, bạn có thể tùy chỉnh hình thức của siêu liên kết cục bộ, bao gồm màu và kiểu văn bản, để đảm bảo chúng phù hợp với thiết kế tài liệu của bạn và mang lại trải nghiệm hình ảnh nhất quán.

#### Hỏi: Có thể tạo nhiều siêu liên kết cục bộ trong một trang PDF không?

Đ: Chắc chắn rồi! Bạn có thể tạo nhiều siêu liên kết cục bộ trong một trang PDF, cho phép người đọc chuyển đến các phần hoặc trang khác nhau nếu cần. Mỗi siêu liên kết cục bộ có thể được điều chỉnh cho phù hợp với mục tiêu tương ứng của nó.

#### Hỏi: Tôi có thể liên kết đến các phần cụ thể của một trang bằng siêu liên kết cục bộ không?

Trả lời: Mặc dù các siêu liên kết cục bộ thường điều hướng đến toàn bộ trang, nhưng bạn có thể tạo liên kết hoặc dấu trang trong tài liệu PDF của mình để đạt được liên kết được nhắm mục tiêu. Aspose.PDF for .NET hỗ trợ nhiều tùy chọn siêu liên kết khác nhau.

#### Hỏi: Làm cách nào tôi có thể xác minh rằng các siêu liên kết cục bộ của tôi đang hoạt động chính xác?

Đáp: Bằng cách làm theo hướng dẫn và mã mẫu được cung cấp, bạn có thể tự tin tạo các siêu liên kết cục bộ chức năng. Bạn có thể kiểm tra các liên kết bằng cách mở tài liệu PDF đã tạo và nhấp vào văn bản siêu liên kết.

#### Câu hỏi: Có bất kỳ hạn chế nào khi sử dụng siêu liên kết cục bộ không?

Đáp: Siêu liên kết cục bộ là một cách hiệu quả để nâng cao khả năng dẫn hướng tài liệu nhưng điều quan trọng là phải đảm bảo rằng cấu trúc của tài liệu vẫn rõ ràng và trực quan. Các siêu liên kết và neo được gắn nhãn chính xác sẽ góp phần mang lại trải nghiệm tích cực cho người dùng.

#### Câu hỏi: Tôi có thể tạo siêu liên kết cục bộ trong bảng hoặc hình ảnh không?

Trả lời: Có, bạn có thể tạo các siêu liên kết cục bộ trong các thành phần khác nhau của tài liệu PDF, bao gồm bảng, hình ảnh và văn bản. Aspose.PDF for .NET cung cấp tính linh hoạt trong việc thêm siêu liên kết vào các loại nội dung khác nhau.