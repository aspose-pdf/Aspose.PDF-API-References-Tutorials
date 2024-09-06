---
title: Trích xuất toàn bộ văn bản trong tệp PDF
linktitle: Trích xuất văn bản AllIn PDF File
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất toàn bộ văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 180
url: /vi/net/programming-with-text/extract-text-all/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất toàn bộ văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn trích xuất văn bản, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Mở tài liệu PDF
 Mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và truyền đường dẫn đến tệp PDF đầu vào.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Bước 5: Trích xuất toàn bộ văn bản
 Tạo một`TextAbsorber`đối tượng để trích xuất văn bản từ tài liệu. Sau đó, chấp nhận bộ hấp thụ cho tất cả các trang.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Bước 6: Lấy văn bản đã trích xuất
 Truy cập văn bản được trích xuất từ`TextAbsorber` sự vật.

```csharp
string extractedText = textAbsorber.Text;
```

## Bước 7: Lưu văn bản đã trích xuất
 Tạo một`TextWriter` và mở tệp mà bạn muốn lưu văn bản đã trích xuất. Ghi văn bản đã trích xuất vào tệp và đóng luồng.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Mã nguồn mẫu cho Trích xuất toàn bộ văn bản bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Tạo đối tượng TextAbsorber để trích xuất văn bản
TextAbsorber textAbsorber = new TextAbsorber();
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages.Accept(textAbsorber);
// Lấy văn bản đã trích xuất
string extractedText = textAbsorber.Text;
// Tạo một trình ghi và mở tệp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Viết một dòng văn bản vào tập tin
tw.WriteLine(extractedText);
// Đóng luồng
tw.Close();
```

## Phần kết luận
Bạn đã trích xuất thành công toàn bộ văn bản từ tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này đóng vai trò như một hướng dẫn giúp bạn trích xuất toàn bộ văn bản từ tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# đi kèm cung cấp hướng dẫn từng bước để thực hiện nhiệm vụ này.

#### H: Tôi nên nhập những không gian tên nào?

A: Trong tệp mã mà bạn định trích xuất văn bản, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Xác định vị trí đường thẳng`string dataDir = "YOUR DOCUMENT DIRECTORY";` trong mã và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để mở một tài liệu PDF hiện có?

 A: Ở Bước 4, bạn sẽ mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và cung cấp đường dẫn đến tệp PDF đầu vào.

#### H: Làm thế nào để trích xuất toàn bộ văn bản từ tài liệu?

 A: Bước 5 bao gồm việc tạo ra một`TextAbsorber` đối tượng để trích xuất văn bản từ tài liệu PDF. Sau đó, bạn sẽ chấp nhận bộ hấp thụ cho tất cả các trang.

#### H: Làm thế nào để truy cập vào văn bản đã trích xuất?

 A: Bước 6 hướng dẫn bạn truy cập vào văn bản đã trích xuất từ`TextAbsorber` sự vật.

#### H: Làm thế nào để lưu văn bản đã trích xuất vào một tệp?

 A: Ở Bước 7, bạn sẽ tạo một`TextWriter`, mở tệp mà bạn muốn lưu văn bản đã trích xuất, ghi văn bản đã trích xuất vào tệp, sau đó đóng luồng.

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học cách trích xuất toàn bộ văn bản từ tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản được trích xuất đã được lưu vào tệp đầu ra được chỉ định, cho phép bạn phân tích và thao tác nội dung văn bản của tài liệu.