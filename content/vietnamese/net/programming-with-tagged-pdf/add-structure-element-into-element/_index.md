---
title: Thêm phần tử cấu trúc vào phần tử
linktitle: Thêm phần tử cấu trúc vào phần tử
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để thêm phần tử cấu trúc vào phần tử trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 20
url: /vi/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Trong hướng dẫn này, chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước về cách thêm phần tử cấu trúc vào phần tử trong tài liệu PDF bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Sử dụng các tính năng cấu trúc nội dung được đánh dấu của Aspose.PDF, bạn có thể tạo cấu trúc phân cấp trong tài liệu PDF của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Visual Studio được cài đặt với .NET framework.
2. Thư viện Aspose.PDF dành cho .NET.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống thư viện từ trang web chính thức của Aspose và cài đặt trên máy của mình.

## Bước 2: Nhập các không gian tên cần thiết

Trong tệp mã C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Bước 3: Tạo tài liệu PDF và xác định các thành phần có cấu trúc

Sử dụng mã sau để tạo tài liệu PDF và xác định các thành phần có cấu trúc:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Mã này tạo một tài liệu PDF trống và thêm các thành phần có cấu trúc như đoạn văn và khoảng. Mỗi thành phần cấu trúc được tạo bằng các phương pháp do Aspose.PDF cung cấp.

## Bước 4: Lưu tài liệu PDF

Sử dụng mã sau để lưu tài liệu PDF:

```csharp
document. Save(outFile);
```

Mã này lưu tài liệu PDF có các thành phần có cấu trúc vào một tệp được chỉ định.

### Mã nguồn mẫu cho Thêm phần tử cấu trúc vào phần tử bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Tạo tài liệu và nhận nội dung PDF được gắn thẻ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Thiết lập Tiêu đề và Ngôn ngữ Bản chất cho tài liệu
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Lấy phần tử cấu trúc gốc (Phần tử cấu trúc tài liệu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Lưu tài liệu PDF có gắn thẻ
document.Save(outFile);
// Kiểm tra sự tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách thêm phần tử cấu trúc vào phần tử trong tài liệu PDF bằng Aspose.PDF cho .NET. Sử dụng các tính năng cấu trúc nội dung được đánh dấu của Aspose.PDF, bạn có thể tạo cấu trúc phân cấp trong tài liệu PDF của mình, giúp quản lý và điều hướng nội dung dễ dàng hơn.

### Câu hỏi thường gặp

#### H: Mục đích của việc thêm phần tử cấu trúc vào một phần tử trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

A: Thêm một phần tử cấu trúc vào một phần tử trong tài liệu PDF bằng Aspose.PDF cho .NET cho phép bạn tạo một cấu trúc phân cấp trong nội dung của tài liệu. Cấu trúc phân cấp này tăng cường tổ chức và điều hướng nội dung, giúp quản lý và truy cập các phần tử cụ thể dễ dàng hơn.

#### H: Thư viện Aspose.PDF hỗ trợ thêm các thành phần cấu trúc vào tài liệu PDF như thế nào?

A: Aspose.PDF for .NET là một thư viện mạnh mẽ cung cấp khả năng tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Trong hướng dẫn này, các tính năng cấu trúc nội dung được đánh dấu của thư viện được tận dụng để tạo và thêm các thành phần cấu trúc vào nội dung của tài liệu PDF.

#### H: Cần có những điều kiện tiên quyết nào để thêm các thành phần cấu trúc vào tài liệu PDF bằng Aspose.PDF cho .NET?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt Visual Studio với .NET framework và có thư viện Aspose.PDF cho .NET được tham chiếu trong dự án của bạn.

#### H: Mã C# được cung cấp tạo và thêm các thành phần cấu trúc vào nội dung tài liệu PDF như thế nào?

A: Mã này trình bày cách tạo tài liệu PDF, xác định phần tử cấu trúc gốc và thêm nhiều phần tử có cấu trúc khác nhau như đoạn văn và khoảng vào đó. Mỗi phần tử có cấu trúc được tạo bằng các phương pháp do Aspose.PDF cung cấp, cho phép bạn xây dựng cấu trúc phân cấp.

#### H: Tôi có thể tùy chỉnh loại thành phần cấu trúc mà tôi thêm vào tài liệu PDF không?

A: Có, bạn có thể tùy chỉnh các loại phần tử cấu trúc bằng cách khám phá các phương pháp khác nhau do thư viện Aspose.PDF cung cấp. Mã này trình bày các đoạn văn và khoảng cách làm ví dụ, nhưng bạn có thể tạo và thêm các loại phần tử có cấu trúc khác khi cần.

#### H: Làm thế nào để xác định mối quan hệ phân cấp giữa các thành phần cấu trúc được thêm vào?

 A: Mối quan hệ phân cấp giữa các phần tử cấu trúc được xác định theo thứ tự mà bạn thêm chúng vào các phần tử cha của chúng. Trong mã, mối quan hệ cha-con được thiết lập bằng cách sử dụng`AppendChild` phương pháp.

#### H: Lợi ích của việc tạo cấu trúc phân cấp trong tài liệu PDF là gì?

A: Việc tạo cấu trúc phân cấp trong tài liệu PDF giúp tăng khả năng truy cập, điều hướng và tổ chức. Nó cho phép các công nghệ hỗ trợ diễn giải và truyền tải nội dung tài liệu tốt hơn, giúp người khuyết tật dễ sử dụng hơn.

#### H: Làm thế nào tôi có thể xác thực tính tuân thủ PDF/UA sau khi thêm các thành phần cấu trúc?

 A: Mã được cung cấp trong hướng dẫn này trình bày cách xác thực sự tuân thủ PDF/UA bằng cách sử dụng`Validate` phương pháp. Bằng cách xác thực tài liệu theo tiêu chuẩn PDF/UA, bạn có thể đảm bảo rằng các thành phần cấu trúc được thêm vào tuân thủ các nguyên tắc về khả năng truy cập.

#### H: Tôi có thể sử dụng cách tiếp cận này để thêm các thành phần cấu trúc vào tài liệu PDF hiện có không?

A: Có, bạn có thể sửa đổi cách tiếp cận được cung cấp để thêm các thành phần cấu trúc vào tài liệu PDF hiện có. Thay vì tạo tài liệu mới, bạn sẽ tải tài liệu hiện có bằng Aspose.PDF rồi làm theo các bước tương tự để thêm các thành phần cấu trúc.