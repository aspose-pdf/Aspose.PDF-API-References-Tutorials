---
title: Văn bản trong tiêu đề của tệp PDF
linktitle: Văn bản trong tiêu đề của tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm văn bản vào tiêu đề của tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 190
url: /vi/net/programming-with-stamps-and-watermarks/text-in-header/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm văn bản vào tiêu đề của tệp PDF bằng Aspose.PDF cho .NET. Làm theo các bước dưới đây:

## Bước 1: Chuẩn bị dự án

Đảm bảo bạn đã cài đặt Aspose.PDF cho .NET và tạo dự án C#.

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
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo văn bản tiêu đề

Tạo tem văn bản mới với văn bản bạn muốn thêm vào tiêu đề:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Bạn có thể tùy chỉnh văn bản bằng cách thay đổi các thuộc tính của nó như lề trên, căn chỉnh ngang và căn chỉnh dọc.

## Bước 5: Thêm văn bản tiêu đề vào tất cả các trang

Đi qua tất cả các trang của tài liệu PDF và thêm dấu văn bản vào tiêu đề:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Bước 6: Lưu tài liệu PDF

Khi văn bản tiêu đề đã được thêm vào tất cả các trang, hãy lưu tài liệu PDF đã cập nhật:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

### Mã nguồn mẫu cho Tiêu đề Textin sử dụng Aspose.PDF for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Tạo tiêu đề
TextStamp textStamp = new TextStamp("Header Text");

// Đặt thuộc tính của tem
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Thêm tiêu đề trên tất cả các trang
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm văn bản vào tiêu đề của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh tiêu đề của mình bằng cách thêm văn bản bổ sung vào tài liệu PDF của mình.

### Câu hỏi thường gặp về văn bản trong tiêu đề của tệp PDF

#### Hỏi: Mục đích của việc thêm văn bản vào tiêu đề của tài liệu PDF là gì?

Đáp: Việc thêm văn bản vào tiêu đề của tài liệu PDF cho phép bạn bao gồm thông tin quan trọng, chẳng hạn như tiêu đề, tên tài liệu, ngày tháng hoặc bất kỳ văn bản nào khác mà bạn muốn xuất hiện nhất quán ở đầu mỗi trang.

#### Câu hỏi: Làm cách nào để mã nguồn C# được cung cấp có thể bổ sung văn bản vào tiêu đề của tài liệu PDF?

Đáp: Mã này thể hiện quy trình mở tài liệu PDF hiện có, tạo dấu văn bản với văn bản tiêu đề mong muốn, tùy chỉnh thuộc tính văn bản, thêm dấu văn bản vào tất cả các trang và cuối cùng lưu tài liệu PDF đã cập nhật với văn bản tiêu đề đã thêm.

#### Hỏi: Tôi có thể sửa đổi hình thức của văn bản tiêu đề, chẳng hạn như phông chữ, kích thước, màu sắc và căn chỉnh không?

 Trả lời: Có, bạn có thể tùy chỉnh giao diện của văn bản tiêu đề bằng cách sửa đổi các thuộc tính của`TextStamp`sự vật. Ví dụ về mã bao gồm các thuộc tính cài đặt như lề trên, căn chỉnh ngang và căn chỉnh dọc. Bạn cũng có thể điều chỉnh phông chữ, kích thước, màu sắc và các thuộc tính liên quan đến văn bản khác.

#### Hỏi: Có thể thêm văn bản khác nhau vào tiêu đề của mỗi trang không?

 Đáp: Có, bạn có thể thêm văn bản khác nhau vào tiêu đề của mỗi trang bằng cách tạo các văn bản riêng biệt.`TextStamp` các đối tượng có nội dung văn bản hoặc thuộc tính khác nhau, sau đó thêm chúng vào các trang cụ thể nếu cần.

#### Hỏi: Làm cách nào để đảm bảo văn bản tiêu đề xuất hiện nhất quán trên mọi trang của tài liệu PDF?

Đáp: Bằng cách sử dụng vòng lặp lặp qua tất cả các trang của tài liệu PDF và thêm cùng một dấu văn bản vào mỗi trang, bạn đảm bảo rằng văn bản tiêu đề xuất hiện nhất quán trên mỗi trang.

#### Hỏi: Tôi có thể thêm nhiều dòng văn bản hoặc định dạng văn bản tiêu đề bằng dấu ngắt dòng không?

 Đáp: Có, bạn có thể thêm nhiều dòng văn bản vào tiêu đề bằng cách đưa dấu ngắt dòng vào chuỗi văn bản. Ví dụ: bạn có thể sử dụng chuỗi thoát`\n` để chỉ ra ngắt dòng trong văn bản.

#### Hỏi: Điều gì xảy ra nếu tôi muốn thêm nội dung khác nhau vào đầu trang và chân trang của cùng một tài liệu PDF?

Đáp: Để thêm nội dung khác nhau vào phần đầu trang và chân trang, bạn hãy làm theo các bước tương tự cho cả hai phần. Đoạn mã này minh họa việc thêm văn bản vào tiêu đề; bạn có thể sử dụng cách tiếp cận tương tự để thêm văn bản vào chân trang.

#### Hỏi: Có thể thêm hình ảnh hoặc các thành phần khác cùng với văn bản tiêu đề bằng phương pháp này không?

Trả lời: Mặc dù mã được cung cấp thể hiện cụ thể việc thêm văn bản vào tiêu đề, nhưng bạn có thể mở rộng phương pháp này để thêm các thành phần khác như hình ảnh, đường kẻ, hình dạng hoặc bất kỳ nội dung nào khác vào phần tiêu đề bằng thư viện Aspose.PDF.
