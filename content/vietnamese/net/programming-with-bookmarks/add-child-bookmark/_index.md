---
title: Thêm dấu trang con vào tệp PDF
linktitle: Thêm dấu trang con vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng thêm dấu trang con vào tệp PDF để duyệt có tổ chức hơn với Aspose.PDF cho .NET.
type: docs
weight: 20
url: /vi/net/programming-with-bookmarks/add-child-bookmark/
---
Việc thêm dấu trang con vào tệp PDF cho phép tổ chức và điều hướng có cấu trúc hơn. Với Aspose.PDF cho .NET, bạn có thể dễ dàng thêm dấu trang phụ bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa file PDF muốn thêm dấu trang phụ. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Mở tài liệu PDF

Bây giờ chúng tôi sẽ mở tài liệu PDF mà chúng tôi muốn thêm dấu trang phụ bằng mã sau:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Bước 4: Tạo đối tượng bookmark gốc

 Trong bước này, chúng ta sẽ tạo một đối tượng dấu trang gốc bằng cách sử dụng`OutlineItemCollection` class và đặt các thuộc tính của nó như tiêu đề, thuộc tính in nghiêng và thuộc tính in đậm. Đây là mã tương ứng:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Bước 5: Tạo đối tượng đánh dấu con

Trong bước này, chúng ta sẽ tạo lại một đối tượng dấu trang phụ bằng cách sử dụng`OutlineItemCollection` lớp và thiết lập các thuộc tính của nó. Đây là mã tương ứng:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Bước 6: Thêm bookmark phụ vào bookmark gốc

 Cuối cùng, chúng tôi thêm dấu trang con đã tạo vào bộ sưu tập dấu trang con của dấu trang gốc bằng cách sử dụng`Add` phương thức của đối tượng cha. Đây là mã tương ứng:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Bước 7: Thêm dấu trang gốc vào bộ sưu tập dấu trang của tài liệu

 Cuối cùng, chúng tôi thêm dấu trang gốc vào bộ sưu tập dấu trang của tài liệu bằng cách sử dụng`Add` phương pháp của`Outlines` tài sản. Đây là mã tương ứng:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Mã nguồn mẫu để Thêm dấu trang con bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Tạo đối tượng đánh dấu gốc
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Tạo một đối tượng đánh dấu con
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Thêm dấu trang con vào bộ sưu tập dấu trang gốc
pdfOutline.Add(pdfChildOutline);
// Thêm dấu trang gốc vào bộ sưu tập phác thảo của tài liệu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Lưu đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để thêm dấu trang phụ bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để sắp xếp và cấu trúc dấu trang trong tài liệu PDF của mình.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng thao tác dấu trang nâng cao.

### Câu hỏi thường gặp về thêm dấu trang con vào tệp PDF

#### Câu hỏi: Dấu trang con trong tệp PDF là gì?

Đáp: Dấu trang con, còn được gọi là dấu trang phụ, là các thành phần điều hướng trong tài liệu PDF được cấu trúc phân cấp dưới dấu trang gốc. Chúng cung cấp một cách để tạo ra một mục lục có tổ chức và chi tiết hơn cho tài liệu.

#### Câu hỏi: Làm cách nào để nhập các thư viện cần thiết cho dự án C# của tôi?

Đáp: Để nhập các thư viện cần thiết cho dự án C# của bạn, bạn có thể sử dụng lệnh nhập sau:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Các thư viện này cung cấp các lớp và chức năng cần thiết để làm việc với các tài liệu PDF và các tính năng tương tác.

#### Hỏi: Làm cách nào để chỉ định đường dẫn đến thư mục tài liệu?

 Đáp: Trong mã nguồn được cung cấp, bạn cần thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tệp PDF mà bạn muốn làm việc. Điều này đảm bảo rằng mã định vị chính xác tệp PDF mục tiêu.

#### Câu hỏi: Tôi có thể tạo nhiều cấp độ dấu trang con không?

Đáp: Có, bạn có thể tạo nhiều cấp độ dấu trang con bằng cách mở rộng quy trình được nêu trong hướng dẫn. Bằng cách tạo dấu trang gốc với các dấu trang phụ và lồng chúng hơn nữa, bạn có thể tạo cấu trúc dấu trang phân cấp cho các tài liệu PDF phức tạp.

####  Hỏi: Mục đích của việc này là gì?`OutlineItemCollection` class?

 Đáp: Cái`OutlineItemCollection` lớp trong Aspose.PDF cho .NET được sử dụng để tạo và quản lý các đường viền, về cơ bản là các dấu trang trong tài liệu PDF. Lớp này cho phép bạn đặt các thuộc tính như tiêu đề, kiểu phông chữ và hành động cho dấu trang.

#### Câu hỏi: Làm cách nào để thêm dấu trang phụ vào dấu trang gốc?

 Đáp: Để thêm dấu trang phụ vào dấu trang gốc, bạn tạo một dấu trang mới`OutlineItemCollection` đối tượng cho dấu trang phụ và đặt thuộc tính của nó. Sau đó, bạn sử dụng`Add` phương pháp của dấu trang gốc`OutlineItemCollection` để thêm dấu trang phụ vào bộ sưu tập của phụ huynh.

#### Hỏi: Tôi có thể tùy chỉnh giao diện của dấu trang con không?

Trả lời: Có, tương tự như dấu trang gốc, bạn có thể tùy chỉnh giao diện của dấu trang con bằng cách đặt các thuộc tính như tiêu đề, kiểu phông chữ và các thuộc tính khác. Điều này cho phép bạn tạo các dấu trang có tính thông tin và đặc biệt trực quan.

#### Câu hỏi: Aspose.PDF cho .NET có tương thích với các ngôn ngữ lập trình khác không?

Đáp: Aspose.PDF for .NET được thiết kế đặc biệt cho môi trường C# và .NET. Tuy nhiên, Aspose cung cấp các thư viện tương tự cho các ngôn ngữ lập trình khác như Java và Android, mỗi thư viện được điều chỉnh cho phù hợp với nền tảng tương ứng của chúng.

#### Hỏi: Dấu trang con cải thiện việc điều hướng PDF như thế nào?

Đáp: Dấu trang con cải thiện việc điều hướng PDF bằng cách cung cấp mục lục có cấu trúc và tổ chức hơn. Người dùng có thể truy cập nhanh chóng các phần cụ thể của tài liệu thông qua cấu trúc dấu trang phân cấp.