---
title: Trích xuất văn bản bằng thiết bị văn bản
linktitle: Trích xuất văn bản bằng thiết bị văn bản
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất văn bản từ tài liệu PDF bằng Thiết bị văn bản trong Aspose.PDF cho .NET.
type: docs
weight: 210
url: /vi/net/programming-with-text/extract-text-using-text-device/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất văn bản từ tài liệu PDF bằng Thiết bị văn bản trong Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Mở tài liệu PDF
 Mở tài liệu PDF hiện có bằng cách sử dụng`Document`constructor và chuyển đường dẫn đến tệp PDF đầu vào.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Bước 5: Trích xuất văn bản bằng Text Device
 Tạo một`StringBuilder` đối tượng để giữ văn bản được trích xuất. Lặp lại qua từng trang của tài liệu và sử dụng một`TextDevice` để trích xuất văn bản từ mỗi trang.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Bước 6: Lưu văn bản đã trích xuất
 Chỉ định đường dẫn tệp đầu ra và lưu văn bản được trích xuất vào tệp văn bản bằng cách sử dụng`File.WriteAllText` phương pháp.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Mã nguồn mẫu để trích xuất văn bản bằng thiết bị văn bản bằng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Chuỗi để giữ văn bản được trích xuất
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Tạo thiết bị văn bản
		TextDevice textDevice = new TextDevice();
		// Đặt tùy chọn trích xuất văn bản - đặt chế độ trích xuất văn bản (Nguyên hoặc Thuần)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Chuyển đổi một trang cụ thể và lưu văn bản vào luồng
		textDevice.Process(pdfPage, textStream);
		// Chuyển đổi một trang cụ thể và lưu văn bản vào luồng
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Đóng luồng bộ nhớ
		textStream.Close();
		// Nhận văn bản từ luồng bộ nhớ
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Lưu văn bản được trích xuất trong tệp văn bản
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã trích xuất thành công văn bản từ tài liệu PDF bằng Thiết bị văn bản trong Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này cung cấp hướng dẫn về cách trích xuất văn bản từ tài liệu PDF bằng tính năng Thiết bị văn bản trong Aspose.PDF cho .NET. Mã nguồn C# đi kèm minh họa các bước cần thiết để đạt được nhiệm vụ này.

#### Câu hỏi: Tôi nên nhập những không gian tên nào?

Đáp: Trong tệp mã mà bạn dự định trích xuất văn bản, hãy bao gồm các lệnh sử dụng sau ở đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 Đáp: Trong đoạn mã, hãy tìm dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Hỏi: Làm cách nào để mở tài liệu PDF hiện có?

 Đáp: Ở Bước 4, bạn sẽ mở tài liệu PDF hiện có bằng cách sử dụng`Document` constructor và cung cấp đường dẫn đến tệp PDF đầu vào.

#### Câu hỏi: Làm cách nào để trích xuất văn bản bằng Thiết bị văn bản?

 Đáp: Bước 5 liên quan đến việc tạo một`StringBuilder` đối tượng để giữ văn bản được trích xuất. Sau đó, bạn sẽ duyệt qua từng trang của tài liệu và sử dụng một`TextDevice` cùng với`TextExtractionOptions` để trích xuất văn bản từ mỗi trang.

#### Hỏi: Làm cách nào để lưu văn bản đã trích xuất vào một tập tin?

 Trả lời: Ở Bước 6, bạn sẽ chỉ định đường dẫn tệp đầu ra và sử dụng`File.WriteAllText`phương pháp lưu văn bản được trích xuất vào một tệp văn bản.

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học cách tận dụng tính năng Thiết bị văn bản trong Aspose.PDF dành cho .NET để trích xuất văn bản từ tài liệu PDF. Văn bản trích xuất đã được lưu vào một tệp đầu ra được chỉ định, cho phép bạn thao tác và sử dụng nội dung được trích xuất khi cần thiết.