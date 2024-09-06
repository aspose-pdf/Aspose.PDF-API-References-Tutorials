---
title: Tạo các thành phần cấu trúc
linktitle: Tạo các thành phần cấu trúc
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Trong hướng dẫn này, bạn sẽ học cách sử dụng Aspose.PDF cho .NET để tạo các thành phần cấu trúc trong tài liệu PDF được gắn thẻ.
type: docs
weight: 60
url: /vi/net/programming-with-tagged-pdf/create-structure-elements/
---
Mã nguồn C# sau đây sử dụng Aspose.PDF cho .NET để tạo các thành phần cấu trúc. Thực hiện theo các bước dưới đây để hiểu cách mã hoạt động.

## Bước 1: Nhập các thư viện cần thiết

```csharp
using Aspose.Pdf;
```

## Bước 2: Xác định thư mục tài liệu của bạn

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Hãy chắc chắn rằng bạn chỉ định đúng đường dẫn đến thư mục tài liệu của mình.

## Bước 3: Tạo tài liệu PDF

```csharp
Document document = new Document();
```

Chúng tôi tạo một đối tượng Tài liệu mới đại diện cho tài liệu PDF.

## Bước 4: Sử dụng nội dung để làm việc với TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Chúng tôi lấy lại nội dung được gắn thẻ của tài liệu PDF. Điều này sẽ cho phép chúng tôi thao tác các thành phần cấu trúc.

## Bước 5: Đặt tiêu đề và ngôn ngữ cho tài liệu

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Chúng tôi đặt tiêu đề và ngôn ngữ của tài liệu PDF được gắn thẻ. Điều này cải thiện khả năng truy cập của tài liệu.

## Bước 6: Tạo các phần tử nhóm

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Chúng tôi tạo ra các thành phần cấu trúc khác nhau để nhóm nội dung trong tài liệu PDF.

## Bước 7: Tạo các thành phần cấu trúc đoạn văn

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Chúng tôi tạo các thành phần cấu trúc cấp khối cho các đoạn văn và tiêu đề. Ví dụ trên cho thấy việc tạo tiêu đề cấp 1.

## Bước 8: Tạo các thành phần cấu trúc cấp độ nội tuyến

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Chúng tôi tạo các thành phần cấu trúc cấp độ nội tuyến cho các phần văn bản xuất hiện bên trong đoạn văn hoặc tiêu đề.

## Bước 9: Tạo các thành phần cấu trúc tác phẩm nghệ thuật

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Chúng tôi tạo ra các thành phần cấu trúc cho các hình ảnh minh họa và công thức toán học có trong tài liệu.

## Bước 10: Lưu tài liệu PDF đã gắn thẻ

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Chúng tôi lưu tài liệu PDF được gắn thẻ với các thành phần cấu trúc đã tạo.

### Mã nguồn mẫu cho Create Structure Elements sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo Tài Liệu PDF
Document document = new Document();
// Nhận nội dung cho công việc với TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Đặt Tiêu đề và Ngôn ngữ cho Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Tạo nhóm các phần tử
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Tạo các thành phần cấu trúc cấp khối văn bản
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Tạo các thành phần cấu trúc cấp độ nội tuyến văn bản
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Tạo các thành phần cấu trúc minh họa
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Các phương pháp đang được phát triển
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Lưu tài liệu PDF có gắn thẻ
document.Save(dataDir + "StructureElements.pdf");

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.PDF cho .NET để tạo các thành phần cấu trúc trong tài liệu PDF được gắn thẻ. Các thành phần cấu trúc giúp cải thiện khả năng truy cập tài liệu và sắp xếp nội dung theo cách có ý nghĩa. Bây giờ bạn có thể sử dụng kiến thức này để tạo các tài liệu PDF có cấu trúc, dễ điều hướng.

### Câu hỏi thường gặp

#### H: Mục đích của việc tạo các thành phần cấu trúc trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

A: Tạo các thành phần cấu trúc trong tài liệu PDF bằng Aspose.PDF cho .NET giúp tăng cường khả năng truy cập và tổ chức nội dung của tài liệu. Các thành phần cấu trúc cung cấp cấu trúc phân cấp giúp cải thiện điều hướng, ngữ nghĩa và khả năng tương thích với các công nghệ hỗ trợ.

#### H: Mã C# được cung cấp tạo ra các thành phần cấu trúc trong tài liệu PDF như thế nào?

A: Ví dụ mã trình bày cách tạo nhiều loại phần tử cấu trúc khác nhau, bao gồm các phần tử nhóm (như phần, mục và div), các phần tử cấp khối (như đoạn văn và tiêu đề), các phần tử cấp nội tuyến (khoảng, trích dẫn, ghi chú) và các phần tử tác phẩm nghệ thuật (như hình và công thức). Các phần tử cấu trúc này giúp sắp xếp nội dung.

####  Q: Tại sao việc thiết lập tiêu đề và ngôn ngữ của tài liệu bằng cách sử dụng`SetTitle` and `SetLanguage` methods?

 A: Thiết lập tiêu đề và ngôn ngữ của tài liệu bằng cách sử dụng`SetTitle` Và`SetLanguage`phương pháp cải thiện khả năng truy cập và ngữ nghĩa của tài liệu. Tiêu đề cung cấp mô tả ngắn gọn về mục đích của tài liệu, trong khi thuộc tính ngôn ngữ tăng cường khả năng hiển thị và khả năng truy cập theo ngôn ngữ cụ thể.

####  Q: Làm thế nào để nhóm các yếu tố, chẳng hạn như`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Việc nhóm các thành phần tạo ra một cấu trúc phân cấp trong tài liệu PDF, cho phép bạn sắp xếp và nhóm các nội dung liên quan một cách hợp lý. Điều này giúp tăng cường khả năng điều hướng và cung cấp một cấu trúc rõ ràng cho người dùng.

#### H: Các phần tử cấu trúc cấp khối và cấp nội tuyến là gì và chúng khác nhau như thế nào?

A: Các thành phần cấu trúc cấp khối biểu thị các khối nội dung lớn hơn, chẳng hạn như đoạn văn và tiêu đề, trong khi các thành phần cấp nội tuyến biểu thị các phần văn bản trong một đoạn văn hoặc tiêu đề, chẳng hạn như khoảng, trích dẫn và ghi chú. Chúng giúp xác định thứ bậc và mối quan hệ của nội dung.

####  H: Các yếu tố cấu trúc tác phẩm nghệ thuật như thế nào, chẳng hạn như`FigureElement` and `FormulaElement`, contribute to the document?

A: Các thành phần cấu trúc tác phẩm nghệ thuật cho phép bạn thêm hình minh họa, hình ảnh và công thức toán học vào tài liệu. Chúng cung cấp một cách có cấu trúc để đưa nội dung trực quan và toán học vào.

#### H: Tôi có thể sử dụng các kỹ thuật tương tự để tạo các loại thành phần cấu trúc khác như danh sách, bảng hoặc chú thích không?

A: Có, bạn có thể sử dụng các kỹ thuật tương tự để tạo các loại thành phần cấu trúc khác như danh sách, bảng, chú thích, tham chiếu, v.v. Aspose.PDF cung cấp nhiều phương pháp tạo thành phần cấu trúc.

####  Q: Làm thế nào để lưu tài liệu PDF được gắn thẻ bằng cách sử dụng`Save` method ensure the preservation of structure elements?

 A: Cái`Save` Phương pháp này lưu tài liệu PDF cùng với các thành phần cấu trúc đã tạo, đảm bảo cấu trúc phân cấp và ngữ nghĩa của tài liệu được bảo toàn để dễ truy cập và điều hướng.

#### H: Các thành phần cấu trúc mang lại lợi ích gì cho tài liệu PDF về mặt khả năng truy cập và khả năng tương thích với các công nghệ hỗ trợ?

A: Các thành phần cấu trúc tăng cường khả năng truy cập bằng cách cung cấp cấu trúc và ngữ nghĩa có ý nghĩa cho tài liệu. Điều này cho phép các công nghệ hỗ trợ như trình đọc màn hình diễn giải và truyền tải nội dung tài liệu hiệu quả hơn cho người dùng khuyết tật.

#### H: Tôi có thể tùy chỉnh và kết hợp nhiều loại thành phần cấu trúc khác nhau trong tài liệu PDF của mình như thế nào?

A: Bạn có thể kết hợp và tùy chỉnh các thành phần cấu trúc bằng cách sử dụng các phương pháp tạo phù hợp do Aspose.PDF cung cấp. Thử nghiệm với các thành phần khác nhau và các thuộc tính của chúng để tạo ra một tài liệu PDF có cấu trúc và tổ chức tốt.