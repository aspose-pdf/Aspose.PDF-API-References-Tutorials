---
title: Trích xuất văn bản bằng thiết bị Text
linktitle: Trích xuất văn bản bằng thiết bị Text
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất văn bản từ tài liệu PDF bằng Text Device trong Aspose.PDF cho .NET.
type: docs
weight: 210
url: /vi/net/programming-with-text/extract-text-using-text-device/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất văn bản từ tài liệu PDF bằng Text Device trong Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Mở tài liệu PDF
 Mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và truyền đường dẫn đến tệp PDF đầu vào.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Bước 5: Trích xuất văn bản bằng Text Device
 Tạo một`StringBuilder` đối tượng để giữ văn bản đã trích xuất. Lặp lại qua từng trang của tài liệu và sử dụng`TextDevice` để trích xuất văn bản từ mỗi trang.

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
 Chỉ định đường dẫn tệp đầu ra và lưu văn bản đã trích xuất vào tệp văn bản bằng cách sử dụng`File.WriteAllText` phương pháp.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Mã nguồn mẫu cho Trích xuất văn bản bằng thiết bị văn bản sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Chuỗi để giữ văn bản đã trích xuất
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Tạo thiết bị văn bản
		TextDevice textDevice = new TextDevice();
		// Thiết lập tùy chọn trích xuất văn bản - thiết lập chế độ trích xuất văn bản (Raw hoặc Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Chuyển đổi một trang cụ thể và lưu văn bản vào luồng
		textDevice.Process(pdfPage, textStream);
		// Chuyển đổi một trang cụ thể và lưu văn bản vào luồng
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Đóng luồng bộ nhớ
		textStream.Close();
		// Lấy văn bản từ luồng bộ nhớ
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Lưu văn bản đã trích xuất vào tệp văn bản
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã trích xuất thành công văn bản từ tài liệu PDF bằng Text Device trong Aspose.PDF cho .NET. Văn bản trích xuất đã được lưu vào tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này cung cấp hướng dẫn về cách trích xuất văn bản từ tài liệu PDF bằng tính năng Text Device trong Aspose.PDF cho .NET. Mã nguồn C# đi kèm trình bày các bước cần thiết để thực hiện nhiệm vụ này.

#### H: Tôi nên nhập những không gian tên nào?

A: Trong tệp mã mà bạn định trích xuất văn bản, hãy bao gồm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Trong mã, hãy tìm dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để mở một tài liệu PDF hiện có?

 A: Ở Bước 4, bạn sẽ mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và cung cấp đường dẫn đến tệp PDF đầu vào.

#### H: Làm thế nào để trích xuất văn bản bằng Text Device?

 A: Bước 5 bao gồm việc tạo ra một`StringBuilder` đối tượng để giữ văn bản đã trích xuất. Sau đó, bạn sẽ lặp lại qua từng trang của tài liệu và sử dụng`TextDevice` cùng với`TextExtractionOptions` để trích xuất văn bản từ mỗi trang.

#### H: Làm thế nào để lưu văn bản đã trích xuất vào một tệp?

 A: Ở Bước 6, bạn sẽ chỉ định đường dẫn tệp đầu ra và sử dụng`File.WriteAllText`phương pháp lưu văn bản đã trích xuất vào tệp văn bản.

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học cách tận dụng tính năng Text Device trong Aspose.PDF cho .NET để trích xuất văn bản từ tài liệu PDF. Văn bản đã trích xuất đã được lưu vào tệp đầu ra được chỉ định, cho phép bạn thao tác và sử dụng nội dung đã trích xuất khi cần.