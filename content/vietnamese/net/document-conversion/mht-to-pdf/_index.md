---
title: MHT sang PDF
linktitle: MHT sang PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để chuyển đổi MHT sang PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 70
url: /vi/net/document-conversion/mht-to-pdf/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi tệp MHT sang PDF bằng Aspose.PDF cho .NET. MHT (MIME HTML) là định dạng được sử dụng để lưu một trang web hoàn chỉnh, bao gồm hình ảnh và nội dung liên quan. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể chuyển đổi tệp MHT sang định dạng PDF.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tải file MHT
Trong bước này, chúng tôi sẽ tải tệp MHT bằng Aspose.PDF cho .NET. Thực hiện theo mã dưới đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Tải tài liệu
Document document = new Document(dataDir + "test.mht", options);
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực nơi chứa tệp MHT của bạn.

## Bước 2: Chuyển đổi MHT sang PDF
Sau khi tải file MHT, chúng ta có thể tiến hành chuyển đổi sang PDF. Sử dụng mã sau đây:

```csharp
// Lưu kết quả đầu ra dưới dạng tài liệu PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Đoạn mã trên chuyển đổi tệp MHT sang định dạng PDF và lưu dưới dạng tên tệp`"MHTToPDF_out.pdf"`.

### Mã nguồn ví dụ cho MHT sang PDF bằng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Tải tài liệu
Document document = new Document(dataDir  + "test.mht", options);
// Lưu kết quả đầu ra dưới dạng tài liệu PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước chuyển đổi tệp MHT sang PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, giờ đây bạn có thể chuyển đổi tệp MHT sang định dạng PDF. Tính năng này có thể hữu ích khi bạn cần chuyển đổi toàn bộ trang web thành tài liệu PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF for .NET có hỗ trợ chuyển đổi tệp MHT có hình ảnh nhúng sang PDF không?

Trả lời: Có, Aspose.PDF for .NET hỗ trợ chuyển đổi tệp MHT có hình ảnh nhúng sang PDF. Thư viện có thể xử lý toàn bộ nội dung trang web, bao gồm hình ảnh và các tài nguyên liên quan, đồng thời chuyển đổi nó thành tài liệu PDF.

#### H: Tôi có thể tùy chỉnh đầu ra PDF trong quá trình chuyển đổi MHT sang PDF không?

Trả lời: Có, Aspose.PDF for .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh đầu ra PDF trong quá trình chuyển đổi MHT sang PDF. Bạn có thể đặt các thuộc tính như kích thước trang, hướng, lề, v.v. để kiểm soát hình thức của tài liệu PDF thu được.

#### Câu hỏi: Aspose.PDF cho .NET có giữ nguyên các siêu liên kết và định dạng từ tệp MHT gốc trong đầu ra PDF không?

Trả lời: Có, Aspose.PDF cho .NET giữ nguyên các siêu liên kết và định dạng từ tệp MHT gốc trong đầu ra PDF. Thư viện đảm bảo rằng tệp PDF được chuyển đổi vẫn giữ nguyên bố cục và nội dung như tệp MHT nguồn.

#### Câu hỏi: Tôi có thể chuyển đổi nhiều tệp MHT thành các tài liệu PDF riêng biệt bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể chuyển đổi nhiều tệp MHT thành các tài liệu PDF riêng biệt bằng Aspose.PDF cho .NET. Chỉ cần tải từng tệp MHT và lưu dưới dạng tài liệu PDF riêng biệt với tên tệp duy nhất.