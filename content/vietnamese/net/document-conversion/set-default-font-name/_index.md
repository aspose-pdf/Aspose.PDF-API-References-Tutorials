---
title: Đặt tên phông chữ mặc định
linktitle: Đặt tên phông chữ mặc định
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để đặt tên phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 270
url: /vi/net/document-conversion/set-default-font-name/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách đặt tên phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET. Đôi khi, khi trích xuất hình ảnh từ tệp PDF, bạn có thể gặp phải vấn đề thiếu phông chữ. Bằng cách chỉ định tên phông chữ mặc định, bạn có thể đảm bảo rằng văn bản được trích xuất sẽ được hiển thị chính xác. Thực hiện theo các bước bên dưới để đặt tên phông chữ mặc định trong tệp PDF.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tải tài liệu PDF
 Bước đầu tiên là tải tài liệu PDF vào một`Document` sự vật. Sử dụng mã sau đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Mã để thêm
}
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực tế nơi chứa tệp PDF của bạn.

## Bước 2: Đặt tên phông chữ mặc định
 Tiếp theo, chúng ta sẽ đặt tên phông chữ mặc định bằng cách sử dụng`DefaultFontName` tùy chọn của`RenderingOptions` sự vật. Sử dụng mã sau đây:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Mã để thêm
     }
}
```

 Hãy chắc chắn để thay thế`"Arial"` với tên phông chữ mong muốn.

## Bước 3: Trích xuất hình ảnh
Tiếp theo, chúng tôi sẽ trích xuất hình ảnh từ trang được chỉ định của tài liệu PDF. Sử dụng mã sau đây:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Đảm bảo ghi rõ số trang chính xác trong`pdfDocument.Pages[1]`.

### Mã nguồn ví dụ cho Đặt tên phông chữ mặc định bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt tên phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET. Bằng cách chỉ định tên phông chữ mặc định, bạn có thể đảm bảo rằng văn bản được trích xuất sẽ được hiển thị chính xác. Sử dụng phương pháp này để giải quyết vấn đề thiếu phông chữ khi trích xuất hình ảnh từ tệp PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng C#. Nó cung cấp nhiều chức năng khác nhau, bao gồm đặt tên phông chữ mặc định trong tệp PDF.

#### Hỏi: Tại sao tôi cần đặt tên phông chữ mặc định trong tệp PDF?

Đáp: Đặt tên phông chữ mặc định rất hữu ích khi trích xuất văn bản từ tài liệu PDF. Nếu tệp PDF chứa văn bản có phông chữ không có sẵn trên máy trích xuất, việc chỉ định tên phông chữ mặc định sẽ đảm bảo hiển thị văn bản chính xác.

#### Câu hỏi: Làm cách nào tôi có thể tải tài liệu PDF và đặt tên phông chữ mặc định bằng Aspose.PDF cho .NET?

 Đáp: Để tải tài liệu PDF và đặt tên phông chữ mặc định, bạn có thể sử dụng`Document`lớp để tải tệp PDF và`RenderingOptions.DefaultFontName` thuộc tính để chỉ định tên phông chữ mặc định mong muốn.

#### Hỏi: Tôi có thể chọn bất kỳ phông chữ nào làm tên phông chữ mặc định không?

Trả lời: Có, bạn có thể chọn bất kỳ phông chữ nào có sẵn trên máy trích xuất làm tên phông chữ mặc định. Sử dụng phông chữ gần giống với phông chữ bị thiếu trong tệp PDF gốc để đảm bảo hiển thị văn bản chính xác.

#### Hỏi: Việc đặt tên phông chữ mặc định có phải là thay đổi vĩnh viễn đối với tệp PDF không?

Trả lời: Không, việc đặt tên phông chữ mặc định bằng Aspose.PDF cho .NET là thay đổi tạm thời được thực hiện trong quá trình trích xuất văn bản. Nó không sửa đổi tệp PDF gốc.