---
title: Văn bản ở chân trang của tệp PDF
linktitle: Văn bản ở chân trang của tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Học cách thêm văn bản vào chân trang của tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 180
url: /vi/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm văn bản vào chân trang của tệp PDF bằng Aspose.PDF cho .NET. Thực hiện theo các bước dưới đây:

## Bước 1: Chuẩn bị dự án

Hãy đảm bảo rằng bạn đã cài đặt Aspose.PDF cho .NET và tạo một dự án C#.

## Bước 2: Nhập không gian tên

Thêm các không gian tên sau vào tệp nguồn C# của bạn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Mở tài liệu

Mở tài liệu PDF hiện có bằng đường dẫn được cung cấp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Hãy nhớ thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo văn bản chân trang

Tạo một dấu văn bản mới với nội dung bạn muốn thêm vào chân trang:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Bạn có thể tùy chỉnh văn bản bằng cách thay đổi các thuộc tính của văn bản như lề dưới, căn chỉnh theo chiều ngang và căn chỉnh theo chiều dọc.

## Bước 5: Thêm văn bản chân trang vào tất cả các trang

Duyệt qua tất cả các trang của tài liệu PDF và thêm dấu văn bản vào chân trang:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Bước 6: Lưu tài liệu PDF

Sau khi thêm văn bản chân trang vào tất cả các trang, hãy lưu tài liệu PDF đã cập nhật:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

### Mã nguồn mẫu cho Textin Footer sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Tạo chân trang
TextStamp textStamp = new TextStamp("Footer Text");

// Thiết lập thuộc tính của tem
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Thêm chân trang vào tất cả các trang
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Lưu tệp PDF đã cập nhật
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Phần kết luận

Xin chúc mừng! Bạn đã học được cách thêm văn bản vào chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh chân trang của mình bằng cách thêm văn bản bổ sung vào tài liệu PDF.

### Câu hỏi thường gặp về văn bản ở chân trang của tệp PDF

#### H: Mục đích của việc thêm văn bản vào chân trang của tài liệu PDF là gì?

A: Thêm văn bản vào chân trang của tài liệu PDF cho phép bạn đưa vào những thông tin quan trọng như thông báo bản quyền, số trang, phiên bản tài liệu hoặc bất kỳ văn bản nào khác mà bạn muốn xuất hiện nhất quán ở cuối mỗi trang.

#### H: Mã nguồn C# được cung cấp thực hiện chức năng thêm văn bản vào phần chân trang của tài liệu PDF như thế nào?

A: Mã này minh họa quy trình mở một tài liệu PDF hiện có, tạo dấu văn bản với văn bản chân trang mong muốn, tùy chỉnh thuộc tính văn bản, thêm dấu văn bản vào tất cả các trang và cuối cùng là lưu tài liệu PDF đã cập nhật với văn bản chân trang đã thêm vào.

#### H: Tôi có thể thay đổi giao diện của văn bản chân trang như phông chữ, kích thước, màu sắc và căn chỉnh không?

 A: Có, bạn có thể tùy chỉnh giao diện của văn bản chân trang bằng cách sửa đổi các thuộc tính của`TextStamp` đối tượng. Ví dụ mã bao gồm các thuộc tính thiết lập như lề dưới, căn chỉnh ngang và căn chỉnh dọc. Bạn cũng có thể điều chỉnh phông chữ, kích thước, màu sắc và các thuộc tính liên quan đến văn bản khác.

#### H: Có thể thêm văn bản khác nhau vào chân trang của mỗi trang không?

 A: Có, bạn có thể thêm văn bản khác nhau vào chân trang của mỗi trang bằng cách tạo riêng biệt`TextStamp` các đối tượng có nội dung văn bản hoặc thuộc tính khác nhau, sau đó thêm chúng vào các trang cụ thể khi cần.

#### H: Làm thế nào để đảm bảo văn bản chân trang xuất hiện nhất quán trên mọi trang của tài liệu PDF?

A: Bằng cách sử dụng vòng lặp lặp qua tất cả các trang của tài liệu PDF và thêm cùng một dấu văn bản vào mỗi trang, bạn đảm bảo rằng văn bản chân trang xuất hiện nhất quán trên mọi trang.

#### H: Tôi có thể thêm nhiều dòng văn bản hoặc định dạng văn bản chân trang bằng ngắt dòng không?

 A: Có, bạn có thể thêm nhiều dòng văn bản vào chân trang bằng cách bao gồm ngắt dòng trong chuỗi văn bản. Ví dụ, bạn có thể sử dụng chuỗi thoát`\n` để chỉ ra một dòng ngắt trong văn bản.

#### H: Điều gì xảy ra nếu tôi muốn thêm nội dung khác nhau vào phần đầu trang và phần chân trang của cùng một tài liệu PDF?

A: Để thêm nội dung khác nhau vào phần đầu trang và phần chân trang, bạn sẽ làm theo các bước tương tự cho cả hai phần. Mã này minh họa cách thêm văn bản vào phần chân trang; bạn có thể sử dụng cách tiếp cận tương tự để thêm văn bản vào phần đầu trang.

#### H: Có thể thêm hình ảnh hoặc các thành phần khác bên cạnh văn bản chân trang bằng cách sử dụng phương pháp này không?

A: Mặc dù mã được cung cấp minh họa cụ thể cách thêm văn bản vào chân trang, nhưng bạn có thể mở rộng cách tiếp cận để thêm các thành phần khác như hình ảnh, đường kẻ, hình dạng hoặc bất kỳ nội dung nào khác vào phần chân trang bằng thư viện Aspose.PDF.