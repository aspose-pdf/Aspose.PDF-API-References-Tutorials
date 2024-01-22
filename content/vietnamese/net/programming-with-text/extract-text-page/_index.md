---
title: Trích xuất trang văn bản trong tệp PDF
linktitle: Trích xuất trang văn bản trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất văn bản từ một trang cụ thể trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 200
url: /vi/net/programming-with-text/extract-text-page/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất văn bản từ một trang cụ thể trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã mà bạn muốn trích xuất văn bản, hãy thêm các lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Mở tài liệu PDF
 Mở tài liệu PDF hiện có bằng cách sử dụng`Document`constructor và chuyển đường dẫn đến tệp PDF đầu vào.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Bước 5: Trích xuất văn bản từ một trang cụ thể
 Tạo một`TextAbsorber` đối tượng để trích xuất văn bản từ tài liệu. Chấp nhận phần hấp thụ cho trang mong muốn bằng cách truy cập nó thông qua`Pages` bộ sưu tập của`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Bước 6: Lấy văn bản được trích xuất
 Truy cập văn bản được trích xuất từ`TextAbsorber` sự vật.

```csharp
string extractedText = textAbsorber.Text;
```

## Bước 7: Lưu văn bản đã trích xuất
 Tạo một`TextWriter` và mở tệp nơi bạn muốn lưu văn bản được trích xuất. Viết văn bản được trích xuất vào tệp và đóng luồng.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Mã nguồn mẫu cho Trang trích xuất văn bản bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Tạo đối tượng TextAbsorber để trích xuất văn bản
TextAbsorber textAbsorber = new TextAbsorber();
//Chấp nhận bộ hấp thụ cho một trang cụ thể
pdfDocument.Pages[1].Accept(textAbsorber);
// Lấy văn bản được trích xuất
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Tạo một nhà văn và mở tập tin
TextWriter tw = new StreamWriter(dataDir);
// Viết một dòng văn bản vào tập tin
tw.WriteLine(extractedText);
// Đóng luồng
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã trích xuất thành công văn bản từ một trang cụ thể của tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này hướng dẫn bạn quy trình trích xuất văn bản từ một trang cụ thể trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# đi kèm minh họa các bước cần thiết để đạt được nhiệm vụ này.

#### Câu hỏi: Tôi nên nhập những không gian tên nào?

Đáp: Trong tệp mã mà bạn dự định trích xuất văn bản, hãy bao gồm các lệnh sử dụng sau ở đầu tệp:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 Đáp: Trong đoạn mã, hãy tìm dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Hỏi: Làm cách nào để mở tài liệu PDF hiện có?

 Đáp: Ở Bước 4, bạn sẽ mở tài liệu PDF hiện có bằng cách sử dụng`Document` constructor và cung cấp đường dẫn đến tệp PDF đầu vào.

#### Hỏi: Làm cách nào để trích xuất văn bản từ một trang cụ thể?

 Đáp: Bước 5 liên quan đến việc tạo một`TextAbsorber` đối tượng để trích xuất văn bản từ tài liệu PDF. Sau đó, bạn sẽ chấp nhận phần hấp thụ cho trang mong muốn bằng cách truy cập nó thông qua`Pages` bộ sưu tập của`pdfDocument`.

#### Hỏi: Làm cách nào để truy cập văn bản được trích xuất?

 Đáp: Bước 6 hướng dẫn bạn cách truy cập văn bản được trích xuất từ`TextAbsorber` sự vật.

#### Hỏi: Làm cách nào để lưu văn bản đã trích xuất vào một tập tin?

 Đáp: Ở Bước 7, bạn sẽ tạo một`TextWriter`, mở tệp nơi bạn muốn lưu văn bản được trích xuất, ghi văn bản được trích xuất vào tệp rồi đóng luồng.

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học cách trích xuất văn bản từ một trang cụ thể của tài liệu PDF bằng Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào một tệp đầu ra được chỉ định, cho phép bạn nhắm mục tiêu và phân tích nội dung văn bản từ các trang cụ thể.