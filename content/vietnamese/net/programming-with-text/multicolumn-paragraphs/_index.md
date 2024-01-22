---
title: Đoạn văn nhiều cột trong tệp PDF
linktitle: Đoạn văn nhiều cột trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách làm việc với các đoạn văn nhiều cột trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 250
url: /vi/net/programming-with-text/multicolumn-paragraphs/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách làm việc với các đoạn văn nhiều cột trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng ta sẽ thực hiện quy trình từng bước thao tác và truy cập các đoạn văn có nhiều cột bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Trước tiên, bạn cần đặt đường dẫn đến thư mục chứa tệp PDF đầu vào của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến bằng đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu PDF

 Tiếp theo, chúng tôi tải tài liệu PDF đầu vào bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Bước 3: Truy cập các đoạn văn có nhiều cột

 Chúng tôi sử dụng`ParagraphAbsorber` lớp để tiếp thu và tham quan các đoạn văn trong tài liệu PDF. Sau đó chúng tôi truy xuất các đánh dấu trang và truy cập các đoạn văn có nhiều cột.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Bước 4: Làm việc với các đoạn văn có nhiều cột

Chúng tôi truy cập các phần và đoạn văn cụ thể trong cấu trúc nhiều cột và in văn bản của chúng.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Truy cập đoạn cuối cùng trong một phần
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Truy cập đoạn đầu tiên trong một phần
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Kích hoạt các đoạn văn nhiều cột
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Truy cập đoạn cuối cùng trong một phần sau khi bật đoạn văn nhiều cột
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

//Truy cập đoạn đầu tiên trong một phần sau khi bật đoạn văn nhiều cột
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Mã nguồn mẫu cho Đoạn văn có nhiều cột sử dụng Aspose.PDF for .NET 
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

Trong hướng dẫn này, bạn đã học cách làm việc với các đoạn văn nhiều cột trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể truy cập và thao tác các đoạn văn có nhiều cột trong tài liệu PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Đoạn nhiều cột trong tệp PDF" là gì?

Đáp: Hướng dẫn "Đoạn nhiều cột trong tệp PDF" trình bày cách làm việc với các đoạn văn nhiều cột trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước và mã nguồn C# để giúp bạn truy cập và thao tác với các đoạn văn có nhiều cột.

#### Hỏi: Tại sao tôi muốn làm việc với các đoạn văn có nhiều cột trong tài liệu PDF?

Đáp: Làm việc với các đoạn văn nhiều cột cho phép bạn tạo các bố cục phức tạp và hấp dẫn trực quan hơn cho tài liệu PDF của mình. Các đoạn văn nhiều cột thường được sử dụng để cải thiện khả năng đọc và nâng cao cách trình bày nội dung tổng thể.

#### Hỏi: Làm cách nào để thiết lập thư mục tài liệu?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến có đường dẫn đến thư mục chứa tệp PDF đầu vào của bạn.

#### Hỏi: Làm cách nào để tải tài liệu PDF và truy cập các đoạn văn có nhiều cột?

 A: Trong phần hướng dẫn,`Document` lớp được sử dụng để tải tài liệu PDF đầu vào. Các`ParagraphAbsorber` Sau đó, lớp này được sử dụng để tiếp thu và truy cập các đoạn văn trong tài liệu PDF. Các`PageMarkup` lớp được sử dụng để truy cập các đoạn văn nhiều cột.

#### Hỏi: Làm cách nào để làm việc với các đoạn văn có nhiều cột cụ thể?

 Đáp: Hướng dẫn này sẽ hướng dẫn bạn quy trình truy cập các phần và đoạn văn cụ thể trong cấu trúc nhiều cột bằng cách sử dụng`MarkupSection` Và`MarkupParagraph` các lớp học. Nó trình bày cách in văn bản của các đoạn văn này.

#### Hỏi: Làm cách nào để kích hoạt các đoạn văn có nhiều cột?

 Đáp: Để kích hoạt các đoạn văn có nhiều cột, bạn có thể đặt`IsMulticolumnParagraphsAllowed` tài sản của`PageMarkup` chủ đề`true`.

#### Hỏi: Kết quả mong đợi của hướng dẫn này là gì?

Đáp: Sau khi làm theo hướng dẫn và thực thi mã C# được cung cấp, bạn sẽ có thể truy cập và thao tác các đoạn văn có nhiều cột trong tài liệu PDF. Hướng dẫn này trình bày cách làm việc với các phần và đoạn văn khác nhau trong cấu trúc nhiều cột.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của các đoạn văn có nhiều cột không?

Đáp: Hướng dẫn này tập trung vào việc truy cập và thao tác với nội dung của các đoạn văn nhiều cột hơn là hình thức của chúng. Tuy nhiên, bạn có thể sử dụng các tính năng khác của thư viện Aspose.PDF để tùy chỉnh giao diện tài liệu PDF của mình, chẳng hạn như cài đặt phông chữ, màu sắc và kiểu.