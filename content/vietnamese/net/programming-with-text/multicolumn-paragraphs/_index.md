---
title: Đoạn văn nhiều cột trong tệp PDF
linktitle: Đoạn văn nhiều cột trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách làm việc với các đoạn văn nhiều cột trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 250
url: /vi/net/programming-with-text/multicolumn-paragraphs/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách làm việc với các đoạn văn nhiều cột trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ thực hiện từng bước để thao tác và truy cập các đoạn văn nhiều cột bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục chứa tệp PDF đầu vào của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải Tài liệu PDF

 Tiếp theo, chúng tôi tải tài liệu PDF đầu vào bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Bước 3: Truy cập đoạn văn nhiều cột

 Chúng tôi sử dụng`ParagraphAbsorber` lớp để hấp thụ và truy cập các đoạn văn trong tài liệu PDF. Sau đó, chúng tôi lấy các đánh dấu trang và truy cập các đoạn văn nhiều cột.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Bước 4: Làm việc với các đoạn văn nhiều cột

Chúng tôi truy cập các phần và đoạn văn cụ thể trong cấu trúc nhiều cột và in văn bản của chúng.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Truy cập đoạn văn cuối cùng trong một phần
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Truy cập đoạn văn đầu tiên trong một phần
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Cho phép các đoạn văn nhiều cột
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Truy cập đoạn văn cuối cùng trong một phần sau khi bật đoạn văn nhiều cột
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Truy cập đoạn văn đầu tiên trong một phần sau khi bật đoạn văn nhiều cột
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Mã nguồn mẫu cho Đoạn văn nhiều cột sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách làm việc với các đoạn văn nhiều cột trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể truy cập và thao tác các đoạn văn nhiều cột trong tài liệu PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Đoạn văn nhiều cột trong tệp PDF" là gì?

A: Hướng dẫn "Đoạn văn nhiều cột trong tệp PDF" trình bày cách làm việc với các đoạn văn nhiều cột trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Hướng dẫn cung cấp hướng dẫn từng bước và mã nguồn C# để giúp bạn truy cập và thao tác các đoạn văn nhiều cột.

#### H: Tại sao tôi lại muốn làm việc với các đoạn văn nhiều cột trong tài liệu PDF?

A: Làm việc với các đoạn văn nhiều cột cho phép bạn tạo ra các bố cục tinh vi và hấp dẫn hơn về mặt thị giác cho các tài liệu PDF của mình. Các đoạn văn nhiều cột thường được sử dụng để cải thiện khả năng đọc và nâng cao khả năng trình bày nội dung tổng thể.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục chứa tệp PDF đầu vào của bạn.

#### H: Làm thế nào để tải tài liệu PDF và truy cập các đoạn văn nhiều cột?

 A: Trong hướng dẫn,`Document` lớp được sử dụng để tải tài liệu PDF đầu vào.`ParagraphAbsorber` lớp sau đó được sử dụng để hấp thụ và truy cập các đoạn văn trong tài liệu PDF.`PageMarkup` lớp được sử dụng để truy cập các đoạn văn nhiều cột.

#### H: Tôi phải làm việc với các đoạn văn nhiều cột cụ thể như thế nào?

 A: Hướng dẫn này hướng dẫn bạn quy trình truy cập các phần và đoạn văn cụ thể trong cấu trúc nhiều cột bằng cách sử dụng`MarkupSection` Và`MarkupParagraph` lớp. Nó trình bày cách in văn bản của các đoạn văn này.

#### H: Làm thế nào để bật đoạn văn nhiều cột?

 A: Để bật đoạn văn nhiều cột, bạn có thể thiết lập`IsMulticolumnParagraphsAllowed` tài sản của`PageMarkup` phản đối`true`.

#### H: Kết quả mong đợi của hướng dẫn này là gì?

A: Sau khi làm theo hướng dẫn và thực thi mã C# được cung cấp, bạn sẽ có thể truy cập và thao tác các đoạn văn nhiều cột trong tài liệu PDF. Hướng dẫn này trình bày cách làm việc với các phần và đoạn văn khác nhau trong cấu trúc nhiều cột.

#### H: Tôi có thể tùy chỉnh giao diện của đoạn văn nhiều cột không?

A: Hướng dẫn này tập trung vào việc truy cập và thao tác nội dung của các đoạn văn nhiều cột thay vì giao diện của chúng. Tuy nhiên, bạn có thể sử dụng các tính năng khác của thư viện Aspose.PDF để tùy chỉnh giao diện của tài liệu PDF, chẳng hạn như cài đặt phông chữ, màu sắc và kiểu.