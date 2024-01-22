---
title: Tạo phần tử cấu trúc ghi chú
linktitle: Tạo phần tử cấu trúc ghi chú
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để tạo các mục ghi chú có cấu trúc trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-tagged-pdf/create-note-structure-element/
---
Trong hướng dẫn này, chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước về cách tạo thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Sử dụng các tính năng cấu trúc nội dung được đánh dấu của Aspose.PDF, bạn có thể thêm ghi chú có cấu trúc vào tài liệu PDF của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Visual Studio được cài đặt với .NET framework.
2. Thư viện Aspose.PDF cho .NET.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống thư viện từ trang web chính thức của Aspose và cài đặt nó trên máy của mình.

## Bước 2: Nhập các không gian tên cần thiết

Trong tệp mã C# của bạn, hãy nhập các vùng tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Bước 3: Tạo tài liệu PDF và các thành phần có cấu trúc ghi chú

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

Mã này tạo một tài liệu PDF trống và thêm các thành phần ghi chú có cấu trúc vào một đoạn văn. Mỗi ghi chú được tạo bằng các phương thức do Aspose.PDF cung cấp.

## Bước 4: Lưu tài liệu PDF

Sử dụng đoạn mã sau để lưu tài liệu PDF:

```csharp
document. Save(outFile);
```

Mã này lưu tài liệu PDF có các thành phần có cấu trúc ghi chú vào một tệp được chỉ định.

### Mã nguồn mẫu để Tạo phần tử cấu trúc ghi chú bằng Aspose.PDF cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Tạo tài liệu PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Thêm phần tử đoạn văn
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Thêm phần tử ghi chú
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Thêm phần tử ghi chú
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Thêm phần tử ghi chú
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Phải ném ngoại lệ - Aspose.Pdf.Tagged.TaggedException : Phần tử cấu trúc có ID='note_002' đã tồn tại
//note3.SetId("note_002");
// Tài liệu kết quả không tuân thủ PDF/UA Nếu ClearId() được sử dụng cho Thành phần cấu trúc ghi chú
//note3.ClearId();
// Lưu tài liệu PDF được gắn thẻ
document.Save(outFile);
// Kiểm tra việc tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET. Các thành phần ghi chú có cấu trúc cho phép bạn thêm thông tin có cấu trúc bổ sung vào tài liệu PDF của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của việc tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

Trả lời: Tạo các thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET cho phép bạn thêm các ghi chú có cấu trúc vào nội dung tài liệu. Những ghi chú này có thể cung cấp thêm ngữ cảnh, giải thích hoặc tài liệu tham khảo cho các phần cụ thể của nội dung.

#### Câu hỏi: Thư viện Aspose.PDF hỗ trợ tạo các thành phần cấu trúc ghi chú trong tài liệu PDF như thế nào?

Trả lời: Aspose.PDF for .NET là một thư viện mạnh mẽ cung cấp các chức năng để tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Trong hướng dẫn này, các tính năng cấu trúc nội dung được đánh dấu của thư viện được sử dụng để tạo các thành phần ghi chú có cấu trúc trong nội dung của tài liệu PDF.

#### Câu hỏi: Điều kiện tiên quyết để tạo thành phần cấu trúc ghi chú trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

Đáp: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt Visual Studio với .NET framework và có thư viện Aspose.PDF cho .NET được tham chiếu trong dự án của bạn.

#### Câu hỏi: Mã C# được cung cấp tạo ra các thành phần cấu trúc ghi chú trong nội dung tài liệu PDF như thế nào?

Đáp: Mã này trình bày cách tạo tài liệu PDF, xác định các thành phần có cấu trúc ghi chú và thêm chúng vào một đoạn văn. Mỗi ghi chú được tạo bằng các phương pháp do Aspose.PDF cung cấp, cho phép bạn kết hợp các ghi chú có cấu trúc vào nội dung.

#### Câu hỏi: Tôi có thể tùy chỉnh nội dung và thuộc tính của các thành phần cấu trúc ghi chú mà tôi tạo không?

Trả lời: Có, bạn có thể tùy chỉnh nội dung và thuộc tính của các thành phần cấu trúc ghi chú bằng cách sử dụng các phương thức và thuộc tính do thư viện Aspose.PDF cung cấp. Mã này giới thiệu cách đặt văn bản và ID của các thành phần ghi chú nhưng bạn có thể tùy chỉnh thêm nếu cần.

#### Câu hỏi: Mối quan hệ phân cấp được thiết lập giữa các thành phần cấu trúc ghi chú và nội dung tài liệu như thế nào?

 Đáp: Mối quan hệ phân cấp được thiết lập bằng cách thêm các phần tử cấu trúc ghi chú làm phần tử con của các phần tử có cấu trúc khác, chẳng hạn như đoạn văn. Trong mã, các phần tử ghi chú được thêm vào phần tử đoạn văn bằng cách sử dụng`AppendChild` phương pháp.

#### Câu hỏi: Tôi có thể gán ID duy nhất cho các thành phần cấu trúc ghi chú không?

Đáp: Có, bạn có thể gán các ID duy nhất để ghi chú các thành phần cấu trúc bằng cách sử dụng`SetId` phương pháp. Mã này trình bày cách đặt ID của các thành phần ghi chú thành các giá trị duy nhất.

#### Câu hỏi: Điều gì xảy ra nếu tôi cố gắng gán một ID trùng lặp cho thành phần cấu trúc ghi chú?

Đáp: Việc cố gắng gán một ID trùng lặp cho thành phần cấu trúc ghi chú sẽ dẫn đến một ngoại lệ. Mã được cung cấp trong hướng dẫn này bao gồm một nhận xét minh họa kịch bản này.

#### Câu hỏi: Làm cách nào tôi có thể đảm bảo tuân thủ PDF/UA khi tạo các thành phần cấu trúc ghi chú?

 Đáp: Mã được cung cấp trong hướng dẫn này trình bày cách xác thực việc tuân thủ PDF/UA bằng cách sử dụng`Validate` phương pháp. Bằng cách xác thực tài liệu theo tiêu chuẩn PDF/UA, bạn có thể đảm bảo rằng các thành phần cấu trúc ghi chú được thêm vào tuân thủ các nguyên tắc trợ năng.

#### Câu hỏi: Tôi có thể sử dụng phương pháp này để thêm các thành phần cấu trúc ghi chú vào tài liệu PDF hiện có không?

Trả lời: Có, bạn có thể sửa đổi phương pháp được cung cấp để thêm các thành phần cấu trúc ghi chú vào tài liệu PDF hiện có. Thay vì tạo tài liệu mới, bạn sẽ tải tài liệu hiện có bằng Aspose.PDF rồi làm theo các bước tương tự để nối thêm các thành phần ghi chú.
