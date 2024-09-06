---
title: Tạo phần tử cấu trúc ghi chú
linktitle: Tạo phần tử cấu trúc ghi chú
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để tạo các mục ghi chú có cấu trúc trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-tagged-pdf/create-note-structure-element/
---
Trong hướng dẫn này, chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước về cách tạo phần tử cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Sử dụng các tính năng cấu trúc nội dung được đánh dấu của Aspose.PDF, bạn có thể thêm ghi chú có cấu trúc vào tài liệu PDF của mình.

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

## Bước 3: Tạo Tài liệu PDF và Ghi chú Các thành phần có cấu trúc

Sử dụng mã sau để tạo tài liệu PDF và thêm các thành phần có cấu trúc ghi chú:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Mã này tạo một tài liệu PDF trống và thêm các thành phần ghi chú có cấu trúc vào một đoạn văn. Mỗi ghi chú được tạo bằng các phương pháp do Aspose.PDF cung cấp.

## Bước 4: Lưu tài liệu PDF

Sử dụng mã sau để lưu tài liệu PDF:

```csharp
document. Save(outFile);
```

Mã này lưu tài liệu PDF có chứa các thành phần có cấu trúc ghi chú vào một tệp được chỉ định.

### Mã nguồn mẫu để tạo phần tử cấu trúc ghi chú bằng Aspose.PDF cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Tạo Tài Liệu PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Thêm phần tử đoạn văn
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Thêm NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Thêm NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Thêm NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Phải ném ngoại lệ - Aspose.Pdf.Tagged.TaggedException: Phần tử cấu trúc có ID='note_002' đã tồn tại
//note3.SetId("note_002");
// Tài liệu kết quả không tuân thủ PDF/UA Nếu ClearId() được sử dụng cho Phần tử Cấu trúc Ghi chú
//lưu ý3.ClearId();
// Lưu tài liệu PDF có gắn thẻ
document.Save(outFile);
// Kiểm tra sự tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET. Các thành phần ghi chú có cấu trúc cho phép bạn thêm thông tin có cấu trúc bổ sung vào tài liệu PDF của mình.

### Câu hỏi thường gặp

#### H: Mục đích của việc tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

A: Tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET cho phép bạn thêm ghi chú có cấu trúc vào nội dung của tài liệu. Các ghi chú này có thể cung cấp thêm ngữ cảnh, giải thích hoặc tham chiếu đến các phần cụ thể của nội dung.

#### H: Thư viện Aspose.PDF hỗ trợ tạo các thành phần cấu trúc ghi chú trong tài liệu PDF như thế nào?

A: Aspose.PDF for .NET là một thư viện mạnh mẽ cung cấp các chức năng để tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Trong hướng dẫn này, các tính năng cấu trúc nội dung được đánh dấu của thư viện được sử dụng để tạo các thành phần ghi chú có cấu trúc trong nội dung của tài liệu PDF.

#### H: Điều kiện tiên quyết để tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt Visual Studio với .NET framework và có thư viện Aspose.PDF cho .NET được tham chiếu trong dự án của bạn.

#### H: Mã C# được cung cấp tạo các thành phần cấu trúc ghi chú trong nội dung tài liệu PDF như thế nào?

A: Mã này trình bày cách tạo tài liệu PDF, xác định các thành phần có cấu trúc ghi chú và thêm chúng vào một đoạn văn. Mỗi ghi chú được tạo bằng các phương pháp do Aspose.PDF cung cấp, cho phép bạn kết hợp các ghi chú có cấu trúc vào nội dung.

#### H: Tôi có thể tùy chỉnh nội dung và thuộc tính của các thành phần cấu trúc ghi chú mà tôi tạo ra không?

A: Có, bạn có thể tùy chỉnh nội dung và thuộc tính của các thành phần cấu trúc ghi chú bằng cách sử dụng các phương pháp và thuộc tính do thư viện Aspose.PDF cung cấp. Mã này trình bày cách đặt văn bản và ID của các thành phần ghi chú, nhưng bạn có thể tùy chỉnh thêm nếu cần.

#### H: Mối quan hệ phân cấp giữa các thành phần cấu trúc ghi chú và nội dung của tài liệu được thiết lập như thế nào?

 A: Mối quan hệ phân cấp được thiết lập bằng cách thêm các phần tử cấu trúc ghi chú làm phần tử con của các phần tử có cấu trúc khác, chẳng hạn như đoạn văn. Trong mã, các phần tử ghi chú được thêm vào phần tử đoạn văn bằng cách sử dụng`AppendChild` phương pháp.

#### H: Tôi có thể chỉ định ID duy nhất cho các thành phần cấu trúc ghi chú không?

A: Có, bạn có thể chỉ định ID duy nhất cho các thành phần cấu trúc ghi chú bằng cách sử dụng`SetId` phương pháp. Mã này trình bày cách đặt ID của các phần tử ghi chú thành các giá trị duy nhất.

#### H: Điều gì xảy ra nếu tôi cố gắng gán một ID trùng lặp cho một phần tử cấu trúc ghi chú?

A: Cố gắng gán ID trùng lặp cho phần tử cấu trúc ghi chú sẽ dẫn đến ngoại lệ. Mã được cung cấp trong hướng dẫn bao gồm một bình luận minh họa cho tình huống này.

#### H: Làm thế nào tôi có thể đảm bảo tuân thủ PDF/UA khi tạo các thành phần cấu trúc ghi chú?

 A: Mã được cung cấp trong hướng dẫn này trình bày cách xác thực sự tuân thủ PDF/UA bằng cách sử dụng`Validate` phương pháp. Bằng cách xác thực tài liệu theo tiêu chuẩn PDF/UA, bạn có thể đảm bảo rằng các thành phần cấu trúc ghi chú được thêm vào tuân thủ các nguyên tắc về khả năng truy cập.

#### H: Tôi có thể sử dụng cách này để thêm các thành phần cấu trúc ghi chú vào tài liệu PDF hiện có không?

A: Có, bạn có thể sửa đổi cách tiếp cận được cung cấp để thêm các thành phần cấu trúc ghi chú vào tài liệu PDF hiện có. Thay vì tạo tài liệu mới, bạn sẽ tải tài liệu hiện có bằng Aspose.PDF rồi làm theo các bước tương tự để thêm các thành phần ghi chú.
