---
title: PDF sang XPS
linktitle: PDF sang XPS
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước chuyển đổi PDF sang XPS bằng Aspose.PDF cho .NET.
type: docs
weight: 220
url: /vi/net/document-conversion/pdf-to-xps/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi tệp PDF sang định dạng XPS (Đặc tả giấy XML) bằng Aspose.PDF cho .NET. Định dạng XPS là định dạng tệp dựa trên XML được sử dụng để thể hiện các tài liệu dưới dạng điện tử. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể chuyển đổi tệp PDF sang định dạng XPS.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tải tài liệu PDF
Trong bước này, chúng tôi sẽ tải tệp PDF nguồn bằng Aspose.PDF cho .NET. Thực hiện theo mã dưới đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực tế nơi chứa tệp PDF của bạn.

## Bước 2: Khởi tạo các tùy chọn lưu XPS
Sau khi tải tệp PDF, chúng tôi sẽ khởi tạo các tùy chọn lưu XPS. Sử dụng mã sau đây:

```csharp
// Khởi tạo các tùy chọn lưu XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Bước 3: Lưu tệp XPS kết quả
Bây giờ chúng tôi sẽ lưu tệp PDF đã chuyển đổi ở định dạng XPS. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Đoạn mã trên lưu tệp PDF đã chuyển đổi ở định dạng XPS với tên tệp`"PDFToXPS_out.xps"`.


### Mã nguồn ví dụ cho PDF sang XPS bằng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tài liệu PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Khởi tạo các tùy chọn Lưu XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Lưu tài liệu XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước chuyển đổi tệp PDF sang định dạng XPS bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, giờ đây bạn có thể chuyển đổi tệp PDF sang định dạng XPS. Tính năng này hữu ích khi bạn muốn xem hoặc in tài liệu PDF ở định dạng XPS.

### Câu hỏi thường gặp

#### Câu hỏi: Định dạng XPS có phù hợp với khả năng tương thích đa nền tảng không?

Trả lời: Định dạng XPS, là định dạng tệp dựa trên XML, độc lập với nền tảng và có thể xem được trên nhiều hệ điều hành và thiết bị khác nhau. Các tệp XPS được hỗ trợ trên nền tảng Windows theo mặc định và một số ứng dụng và trình xem của bên thứ ba có thể có sẵn cho các nền tảng khác.

#### Câu hỏi: Aspose.PDF cho .NET có thể xử lý các tệp PDF phức tạp có nhiều trang và hình ảnh trong quá trình chuyển đổi XPS không?

Trả lời: Có, Aspose.PDF cho .NET có thể xử lý các tệp PDF phức tạp với nhiều trang và hình ảnh trong quá trình chuyển đổi XPS. Nó giữ lại chính xác bố cục, hình ảnh và nội dung văn bản của PDF trong khi chuyển đổi sang định dạng XPS.

#### Hỏi: Có thể chỉ định các cài đặt hoặc tùy chọn bổ sung trong quá trình chuyển đổi XPS không?

 Trả lời: Có, Aspose.PDF cho .NET cung cấp nhiều tùy chọn và cài đặt khác nhau có thể được tùy chỉnh trong quá trình chuyển đổi XPS. Bạn có thể kiểm soát việc nén hình ảnh, nhúng phông chữ và các cài đặt khác bằng cách sử dụng`XpsSaveOptions` lớp học.

#### Câu hỏi: Có thể chuyển đổi các tệp PDF được bảo vệ bằng mật khẩu sang định dạng XPS bằng Aspose.PDF cho .NET không?

 Trả lời: Có, Aspose.PDF for .NET hỗ trợ chuyển đổi các tệp PDF được bảo vệ bằng mật khẩu sang định dạng XPS. Khi tải tệp PDF được bảo vệ bằng mật khẩu, bạn có thể cung cấp mật khẩu bằng cách sử dụng`Document` hàm tạo của lớp hoặc bằng cách thiết lập`Password` thuộc tính trước khi tải tệp PDF.