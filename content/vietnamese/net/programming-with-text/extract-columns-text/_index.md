---
title: Trích xuất văn bản cột trong tệp PDF
linktitle: Trích xuất văn bản cột trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất cột văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 150
url: /vi/net/programming-with-text/extract-columns-text/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất văn bản cột trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn trích xuất văn bản cột, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Mở tài liệu PDF
 Mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và truyền đường dẫn đến tệp PDF đầu vào.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Bước 5: Điều chỉnh kích thước phông chữ
Giảm kích thước phông chữ của các đoạn văn bản đi 0,7 lần để tăng khả năng đọc và thể hiện văn bản dạng cột tốt hơn.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Bước 6: Trích xuất văn bản từ các cột
 Lưu tài liệu PDF đã sửa đổi vào luồng bộ nhớ và tải lại dưới dạng tài liệu mới. Sau đó, sử dụng`TextAbsorber` lớp để trích xuất văn bản từ các cột.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Bước 7: Lưu văn bản đã trích xuất
Lưu văn bản đã trích xuất vào tệp văn bản theo đường dẫn tệp đầu ra đã chỉ định.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để trích xuất văn bản cột bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Cần phải giảm kích thước phông chữ ít nhất 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã trích xuất thành công các cột văn bản từ một tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này cung cấp hướng dẫn từng bước về cách trích xuất các cột văn bản từ tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# đi kèm cung cấp bản trình diễn thực tế về các quy trình cần thiết.

#### H: Tôi nên nhập những không gian tên nào?

A: Trong tệp mã mà bạn định trích xuất các cột văn bản, hãy bao gồm các lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Xác định vị trí đường thẳng`string dataDir = "YOUR DOCUMENT DIRECTORY";` trong mã và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để mở một tài liệu PDF hiện có?

 A: Ở Bước 4, bạn sẽ mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và cung cấp đường dẫn đến tệp PDF đầu vào.

#### H: Tại sao phải điều chỉnh kích thước phông chữ?

A: Bước 5 bao gồm việc giảm kích thước phông chữ của các đoạn văn bản theo hệ số 0,7. Điều chỉnh này giúp tăng khả năng đọc và thể hiện văn bản dạng cột chính xác hơn.

#### H: Làm thế nào để trích xuất văn bản từ các cột?

 A: Bước 6 bao gồm việc lưu tài liệu PDF đã sửa đổi vào luồng bộ nhớ, tải lại dưới dạng tài liệu mới và sau đó sử dụng`TextAbsorber` lớp để trích xuất văn bản từ các cột.

#### H: Mục đích của việc lưu văn bản đã trích xuất là gì?

A: Ở Bước 7, bạn sẽ lưu văn bản đã trích xuất vào tệp văn bản theo đường dẫn tệp đầu ra đã chỉ định.

#### H: Tại sao phải giảm kích thước phông chữ trước khi trích xuất?

A: Giảm kích thước phông chữ giúp đảm bảo văn bản được trích xuất được căn chỉnh đúng trong các cột, mang lại hình ảnh chính xác hơn so với bố cục gốc.

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã có được kiến thức và kỹ năng cần thiết để trích xuất các cột văn bản từ tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản kết quả đã được lưu vào tệp đầu ra đã chỉ định.