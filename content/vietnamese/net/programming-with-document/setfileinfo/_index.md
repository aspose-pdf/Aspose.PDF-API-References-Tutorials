---
title: Đặt thông tin tệp trong tệp PDF
linktitle: Đặt thông tin tệp trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để đặt thông tin tệp trong tệp PDF bằng hướng dẫn từng bước này.
type: docs
weight: 310
url: /vi/net/programming-with-document/setfileinfo/
---
Nếu bạn đang làm việc trong một dự án yêu cầu quản lý tệp PDF bằng Aspose.PDF cho .NET, một trong những tính năng bạn có thể muốn sử dụng là khả năng đặt thông tin tệp cho tài liệu PDF. Thông tin tệp bao gồm nhiều chi tiết khác nhau như tác giả, ngày tạo, từ khóa, ngày sửa đổi, chủ đề và tiêu đề. Hướng dẫn này sẽ hướng dẫn bạn quy trình thiết lập thông tin tệp cho tài liệu PDF bằng mã nguồn C# với Aspose.PDF cho .NET.

## Hướng dẫn từng bước để thiết lập thông tin tệp bằng Aspose.PDF cho .NET

1. Tạo một dự án C# mới trong Visual Studio IDE của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET trong dự án của bạn.
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

## Bước 3: Sử dụng đối tượng DocumentInfo để truy cập thông tin file của tài liệu PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Bước 4: Đặt các giá trị thông tin tệp mong muốn bằng cách sử dụng các thuộc tính của đối tượng DocumentInfo.

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

## Bước 6: Xác minh thông tin file đã được cập nhật thành công.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Bạn đã đặt thành công thông tin tệp cho tài liệu PDF bằng Aspose.PDF cho .NET.

### Mã nguồn ví dụ cho Đặt thông tin tệp bằng Aspose.PDF cho .NET


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

Tóm lại, Aspose.PDF for .NET cung cấp một cách đơn giản và hiệu quả để thiết lập thông tin tệp cho tài liệu PDF. Bằng cách làm theo các bước được đề cập ở trên, bạn có thể dễ dàng đặt các giá trị thông tin tệp mong muốn cho tài liệu PDF của mình bằng mã nguồn C#.

### Câu hỏi thường gặp về thông tin tập tin được đặt trong tệp PDF

#### Câu hỏi: Tôi có thể đặt các thuộc tính thông tin tệp bổ sung không được đề cập trong ví dụ không?

 Trả lời: Có, bạn có thể đặt các thuộc tính thông tin tệp bổ sung bằng cách sử dụng`DocumentInfo` đối tượng trong Aspose.PDF cho .NET. Các`DocumentInfo`class cung cấp nhiều thuộc tính khác nhau cho phép bạn đặt thông tin bổ sung như nhà sản xuất, phiên bản và thuộc tính tùy chỉnh.

#### Hỏi: Có thể truy xuất thông tin tệp từ tài liệu PDF hiện có không?

 Trả lời: Có, bạn có thể truy xuất thông tin tệp từ tài liệu PDF hiện có bằng Aspose.PDF cho .NET. Để làm điều này, bạn có thể sử dụng`DocumentInfo` đối tượng để truy cập các thuộc tính thông tin tệp và đọc thông tin được lưu trữ trong tài liệu PDF.

#### Hỏi: Việc cài đặt thông tin tệp có làm thay đổi tài liệu PDF gốc không?

Trả lời: Không, việc đặt thông tin tệp bằng Aspose.PDF cho .NET không sửa đổi tài liệu PDF gốc. Thay vào đó, nó tạo một tài liệu PDF mới với thông tin tệp được cập nhật. Tài liệu PDF gốc vẫn không thay đổi.