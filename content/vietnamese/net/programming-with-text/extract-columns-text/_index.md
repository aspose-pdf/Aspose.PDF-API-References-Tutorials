---
title: Trích xuất văn bản cột trong tệp PDF
linktitle: Trích xuất văn bản cột trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất văn bản cột trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 150
url: /vi/net/programming-with-text/extract-columns-text/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất văn bản cột trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã nơi bạn muốn trích xuất văn bản cột, hãy thêm lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Mở tài liệu PDF
 Mở tài liệu PDF hiện có bằng cách sử dụng`Document`constructor và chuyển đường dẫn đến tệp PDF đầu vào.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Bước 5: Điều chỉnh cỡ chữ
Giảm kích thước phông chữ của các đoạn văn bản xuống hệ số 0,7 để nâng cao khả năng đọc và thể hiện văn bản theo cột tốt hơn.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Bước 6: Trích xuất văn bản từ cột
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
Lưu văn bản được trích xuất vào tệp văn bản tại đường dẫn tệp đầu ra được chỉ định.

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
	// Cần giảm cỡ chữ ít nhất 70%
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
Bạn đã trích xuất thành công văn bản cột từ tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này cung cấp hướng dẫn từng bước về cách trích xuất các cột văn bản từ tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# đi kèm cung cấp minh họa thực tế về các quy trình được yêu cầu.

#### Câu hỏi: Tôi nên nhập những không gian tên nào?

Đáp: Trong tệp mã mà bạn dự định trích xuất các cột văn bản, hãy bao gồm các lệnh sử dụng sau ở đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 A: Xác định vị trí dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` trong mã và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Hỏi: Làm cách nào để mở tài liệu PDF hiện có?

 Đáp: Ở Bước 4, bạn sẽ mở tài liệu PDF hiện có bằng cách sử dụng`Document` constructor và cung cấp đường dẫn đến tệp PDF đầu vào.

#### Q: Tại sao kích thước phông chữ được điều chỉnh?

Đáp: Bước 5 liên quan đến việc giảm kích thước phông chữ của các đoạn văn bản xuống hệ số 0,7. Điều chỉnh này giúp tăng cường khả năng đọc và thể hiện chính xác hơn văn bản theo cột.

#### Câu hỏi: Làm cách nào để trích xuất văn bản từ các cột?

 Đáp: Bước 6 bao gồm việc lưu tài liệu PDF đã sửa đổi vào luồng bộ nhớ, tải lại dưới dạng tài liệu mới và sau đó sử dụng`TextAbsorber` lớp để trích xuất văn bản từ các cột.

#### Hỏi: Mục đích của việc lưu văn bản đã trích xuất là gì?

Trả lời: Ở Bước 7, bạn sẽ lưu văn bản được trích xuất vào một tệp văn bản tại đường dẫn tệp đầu ra được chỉ định.

#### Q: Tại sao phải giảm cỡ chữ trước khi trích xuất?

Đáp: Việc giảm kích thước phông chữ giúp đảm bảo rằng văn bản được trích xuất căn chỉnh chính xác trong các cột, mang lại cách trình bày chính xác hơn về bố cục ban đầu.

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã có được kiến thức và kỹ năng cần thiết để trích xuất các cột văn bản từ tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản kết quả đã được lưu vào tệp đầu ra được chỉ định.