---
title: Văn bản ở chân trang của tệp PDF
linktitle: Văn bản ở chân trang của tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm văn bản vào chân trang của tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 180
url: /vi/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm văn bản vào phần chân trang của tệp PDF bằng Aspose.PDF cho .NET. Làm theo các bước dưới đây:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo văn bản chân trang

Tạo tem văn bản mới với văn bản bạn muốn thêm vào chân trang:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Bạn có thể tùy chỉnh văn bản bằng cách thay đổi các thuộc tính của nó như lề dưới, căn chỉnh ngang và căn chỉnh dọc.

## Bước 5: Thêm văn bản chân trang vào tất cả các trang

Đi qua tất cả các trang của tài liệu PDF và thêm dấu văn bản vào chân trang:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Bước 6: Lưu tài liệu PDF

Khi văn bản chân trang đã được thêm vào tất cả các trang, hãy lưu tài liệu PDF đã cập nhật:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

### Mã nguồn mẫu cho Textin Footer sử dụng Aspose.PDF for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Tạo chân trang
TextStamp textStamp = new TextStamp("Footer Text");

// Đặt thuộc tính của tem
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Thêm chân trang trên tất cả các trang
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

Xin chúc mừng! Bạn đã học cách thêm văn bản vào chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh chân trang bằng cách thêm văn bản bổ sung vào tài liệu PDF của mình.

### Câu hỏi thường gặp về văn bản ở chân trang của tệp PDF

#### Hỏi: Mục đích của việc thêm văn bản vào phần chân trang của tài liệu PDF là gì?

Đáp: Việc thêm văn bản vào chân trang của tài liệu PDF cho phép bạn đưa vào những thông tin quan trọng, chẳng hạn như thông báo bản quyền, số trang, phiên bản tài liệu hoặc bất kỳ văn bản nào khác mà bạn muốn xuất hiện nhất quán ở cuối mỗi trang.

#### Câu hỏi: Làm cách nào để mã nguồn C# được cung cấp có thể thêm văn bản vào phần chân trang của tài liệu PDF?

Đáp: Mã này thể hiện quy trình mở tài liệu PDF hiện có, tạo dấu văn bản với văn bản chân trang mong muốn, tùy chỉnh thuộc tính văn bản, thêm dấu văn bản vào tất cả các trang và cuối cùng lưu tài liệu PDF cập nhật có văn bản chân trang được thêm vào.

#### Hỏi: Tôi có thể sửa đổi hình thức của văn bản chân trang, chẳng hạn như phông chữ, kích thước, màu sắc và căn chỉnh không?

 Trả lời: Có, bạn có thể tùy chỉnh hình thức của văn bản chân trang bằng cách sửa đổi các thuộc tính của`TextStamp` sự vật. Ví dụ về mã bao gồm các thuộc tính cài đặt như lề dưới, căn chỉnh ngang và căn chỉnh dọc. Bạn cũng có thể điều chỉnh phông chữ, kích thước, màu sắc và các thuộc tính liên quan đến văn bản khác.

#### Hỏi: Có thể thêm văn bản khác nhau vào chân trang của mỗi trang không?

 Đáp: Có, bạn có thể thêm văn bản khác nhau vào chân trang của mỗi trang bằng cách tạo các văn bản riêng biệt.`TextStamp` các đối tượng có nội dung văn bản hoặc thuộc tính khác nhau, sau đó thêm chúng vào các trang cụ thể nếu cần.

#### Hỏi: Làm cách nào để đảm bảo văn bản chân trang xuất hiện nhất quán trên mọi trang của tài liệu PDF?

Đáp: Bằng cách sử dụng vòng lặp lặp qua tất cả các trang của tài liệu PDF và thêm cùng một dấu văn bản vào mỗi trang, bạn đảm bảo rằng văn bản chân trang xuất hiện nhất quán trên mỗi trang.

#### Hỏi: Tôi có thể thêm nhiều dòng văn bản hoặc định dạng văn bản chân trang bằng dấu ngắt dòng không?

 Đáp: Có, bạn có thể thêm nhiều dòng văn bản vào chân trang bằng cách thêm dấu ngắt dòng trong chuỗi văn bản. Ví dụ: bạn có thể sử dụng chuỗi thoát`\n` để chỉ ra ngắt dòng trong văn bản.

#### Hỏi: Điều gì xảy ra nếu tôi muốn thêm nội dung khác nhau vào đầu trang và chân trang của cùng một tài liệu PDF?

Đáp: Để thêm nội dung khác nhau vào phần đầu trang và chân trang, bạn hãy làm theo các bước tương tự cho cả hai phần. Đoạn mã này minh họa việc thêm văn bản vào chân trang; bạn có thể sử dụng cách tiếp cận tương tự để thêm văn bản vào tiêu đề.

#### Hỏi: Có thể thêm hình ảnh hoặc các thành phần khác bên cạnh văn bản chân trang bằng phương pháp này không?

Trả lời: Mặc dù mã được cung cấp thể hiện cụ thể việc thêm văn bản vào chân trang, nhưng bạn có thể mở rộng phương pháp này để thêm các thành phần khác như hình ảnh, đường kẻ, hình dạng hoặc bất kỳ nội dung nào khác vào phần chân trang bằng thư viện Aspose.PDF.