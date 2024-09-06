---
title: Thiết lập thông tin tập tin trong tập tin PDF
linktitle: Thiết lập thông tin tập tin trong tập tin PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để thiết lập thông tin tệp trong tệp PDF với hướng dẫn từng bước này.
type: docs
weight: 310
url: /vi/net/programming-with-document/setfileinfo/
---
Nếu bạn đang làm việc trên một dự án yêu cầu quản lý các tệp PDF bằng Aspose.PDF cho .NET, một trong những tính năng bạn có thể muốn sử dụng là khả năng thiết lập thông tin tệp cho tài liệu PDF. Thông tin tệp bao gồm nhiều chi tiết khác nhau như tác giả, ngày tạo, từ khóa, ngày sửa đổi, chủ đề và tiêu đề. Hướng dẫn này sẽ hướng dẫn bạn quy trình thiết lập thông tin tệp cho tài liệu PDF bằng mã nguồn C# với Aspose.PDF cho .NET.

## Hướng dẫn từng bước để thiết lập thông tin tệp bằng Aspose.PDF cho .NET

1. Tạo một dự án C# mới trong IDE Visual Studio của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET vào dự án của bạn.
3. Tạo một đối tượng tài liệu PDF mới bằng cách cung cấp đường dẫn đến tệp PDF mà bạn muốn sửa đổi thông tin tệp.

## Bước 1: Đặt đường dẫn đến thư mục tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở tài liệu PDF

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Bước 3: Sử dụng đối tượng DocumentInfo để truy cập thông tin tệp của tài liệu PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Bước 4: Thiết lập các giá trị thông tin tệp mong muốn bằng cách sử dụng các thuộc tính của đối tượng DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Bước 5: Lưu tài liệu PDF đã cập nhật vào vị trí đã chỉ định.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Bước 6: Xác minh thông tin tệp đã được cập nhật thành công.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Bạn đã thiết lập thông tin tệp cho tài liệu PDF thành công bằng Aspose.PDF cho .NET.

### Mã nguồn ví dụ cho Set File Info sử dụng Aspose.PDF cho .NET


```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Chỉ định thông tin tài liệu
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Tóm lại, Aspose.PDF for .NET cung cấp một cách đơn giản và hiệu quả để thiết lập thông tin tệp cho các tài liệu PDF. Bằng cách làm theo các bước nêu trên, bạn có thể dễ dàng thiết lập các giá trị thông tin tệp mong muốn cho các tài liệu PDF của mình bằng mã nguồn C#.

### Câu hỏi thường gặp về thông tin tập tin trong tệp PDF

#### H: Tôi có thể thiết lập các thuộc tính thông tin tệp bổ sung không được đề cập trong ví dụ không?

 A: Có, bạn có thể thiết lập các thuộc tính thông tin tệp bổ sung bằng cách sử dụng`DocumentInfo` đối tượng trong Aspose.PDF cho .NET.`DocumentInfo`Lớp này cung cấp nhiều thuộc tính khác nhau cho phép bạn thiết lập thông tin bổ sung như nhà sản xuất, phiên bản và các thuộc tính tùy chỉnh.

#### H: Có thể lấy thông tin tập tin từ một tài liệu PDF hiện có không?

 A: Có, bạn có thể lấy thông tin tệp từ tài liệu PDF hiện có bằng Aspose.PDF cho .NET. Để thực hiện việc này, bạn có thể sử dụng`DocumentInfo` đối tượng để truy cập vào thuộc tính thông tin tệp và đọc thông tin được lưu trữ trong tài liệu PDF.

#### H: Việc thiết lập thông tin tệp có làm thay đổi tài liệu PDF gốc không?

A: Không, việc thiết lập thông tin tệp bằng Aspose.PDF cho .NET không sửa đổi tài liệu PDF gốc. Thay vào đó, nó tạo một tài liệu PDF mới với thông tin tệp đã cập nhật. Tài liệu PDF gốc vẫn không thay đổi.