---
title: Gắn thẻ hình ảnh trong PDF hiện có
linktitle: Gắn thẻ hình ảnh trong PDF hiện có
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách đánh dấu hình ảnh trong PDF hiện có bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để thêm thẻ vào hình ảnh.
type: docs
weight: 210
url: /vi/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Trong hướng dẫn chi tiết này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# được cung cấp để đánh dấu hình ảnh trong PDF hiện có bằng Aspose.PDF cho .NET. Làm theo hướng dẫn bên dưới để hiểu cách thêm thẻ vào hình ảnh trong PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã cấu hình môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này bao gồm cài đặt thư viện Aspose.PDF và cấu hình dự án của bạn để tham chiếu đến nó.

## Bước 2: Mở tài liệu PDF hiện có

Ở bước này, chúng ta sẽ mở một tài liệu PDF hiện có bằng Aspose.PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Đường dẫn tập tin đầu vào và đầu ra
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Mở tài liệu
Document document = new Document(inFile);
```

Chúng tôi đã mở tài liệu PDF hiện có bằng Aspose.PDF.

## Bước 3: Lấy nội dung được gắn thẻ và phần tử cấu trúc gốc

Bây giờ chúng ta sẽ lấy nội dung được gắn thẻ của tài liệu PDF và phần tử cấu trúc gốc tương ứng.

```csharp
// Nhận nội dung được gắn thẻ và phần tử cấu trúc gốc
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Chúng tôi đã có nội dung được gắn thẻ của tài liệu PDF và phần tử cấu trúc gốc tương ứng.

## Bước 4: Đặt tiêu đề cho tài liệu PDF được gắn thẻ

Bây giờ chúng ta hãy đặt tiêu đề cho tài liệu PDF được gắn thẻ.

```csharp
// Xác định tiêu đề cho tài liệu PDF được gắn thẻ
taggedContent.SetTitle("Document with images");
```

Chúng tôi đã đặt tiêu đề cho tài liệu PDF được gắn thẻ.

## Bước 5: Gán văn bản thay thế và hộp giới hạn cho hình ảnh

Bây giờ, đối với mỗi phần tử hình ảnh, chúng ta sẽ gán văn bản thay thế và hộp giới hạn.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Gán văn bản thay thế cho hình ảnh
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Tạo và chỉ định hộp giới hạn (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Chúng tôi đã chỉ định văn bản thay thế và hộp giới hạn cho mỗi phần tử hình ảnh trong tài liệu PDF.

## Bước 6: Di chuyển phần tử Span vào đoạn văn

Bây giờ chúng ta hãy di chuyển phần tử Span vào trong đoạn văn.

```csharp
// Di chuyển phần tử Span vào đoạn văn (tìm khoảng cách và đoạn văn không chính xác trong TD đầu tiên)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Di chuyển phần tử Span trong đoạn văn
spanElement.ChangeParentElement(paragraph);
```

Chúng tôi đã di chuyển phần tử Span vào đoạn văn đã chỉ định.

## Bước 7: Lưu tài liệu PDF đã sửa đổi

Bây giờ chúng ta đã thực hiện những thay đổi cần thiết, chúng ta sẽ lưu tài liệu PDF đã sửa đổi.

```csharp
// Lưu tài liệu PDF
document. Save(outFile);
```

Chúng tôi đã lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu cho Thẻ hình ảnh trong PDF hiện có bằng cách sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Mở tài liệu
Document document = new Document(inFile);

// Nhận nội dung được gắn thẻ và phần tử cấu trúc gốc
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Đặt tiêu đề cho tài liệu pdf được gắn thẻ
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Đặt Văn bản thay thế cho Hình
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Tạo và thiết lập thuộc tính BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Di chuyển phần tử Span vào đoạn văn (tìm khoảng cách và đoạn văn sai trong TD đầu tiên)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Di chuyển phần tử Span vào đoạn văn
spanElement.ChangeParentElement(paragraph);

// Lưu tài liệu
document.Save(outFile);

//Kiểm tra sự tuân thủ PDF/UA cho tài liệu của chúng tôi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách đánh dấu hình ảnh trong PDF hiện có bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng Aspose.PDF để thêm thẻ và chỉnh sửa hình ảnh trong tài liệu PDF của mình.

### Câu hỏi thường gặp

#### H: Mục tiêu chính của hướng dẫn này về gắn thẻ hình ảnh trong tệp PDF hiện có bằng Aspose.PDF cho .NET là gì?

A: Mục tiêu chính của hướng dẫn này là hướng dẫn bạn quy trình đánh dấu hình ảnh trong tài liệu PDF hiện có bằng Aspose.PDF cho .NET. Hướng dẫn cung cấp hướng dẫn từng bước và ví dụ mã nguồn C# để giúp bạn hiểu cách gán văn bản thay thế và hộp giới hạn cho hình ảnh, di chuyển các thành phần trong tài liệu và thêm thẻ vào hình ảnh.

#### H: Cần có những điều kiện tiên quyết nào để thực hiện theo hướng dẫn này về cách gắn thẻ hình ảnh trong PDF bằng Aspose.PDF cho .NET?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập môi trường phát triển để sử dụng Aspose.PDF cho .NET. Điều này bao gồm cài đặt thư viện Aspose.PDF và cấu hình dự án của bạn để tham chiếu đến nó.

#### H: Làm thế nào tôi có thể mở một tài liệu PDF hiện có và truy cập vào nội dung được gắn thẻ của nó bằng Aspose.PDF cho .NET?

A: Bài hướng dẫn cung cấp các ví dụ về mã nguồn C# để chứng minh cách mở tài liệu PDF hiện có bằng Aspose.PDF cho .NET và truy cập nội dung được gắn thẻ của tài liệu đó để thao tác thêm.

#### H: Mục đích của việc gán văn bản thay thế và hộp giới hạn cho hình ảnh trong tài liệu PDF là gì?

A: Việc gán văn bản thay thế và hộp giới hạn cho hình ảnh giúp tăng khả năng truy cập bằng cách cung cấp văn bản mô tả cho hình ảnh và xác định bố cục và vị trí của chúng trong tài liệu. Thông tin này rất quan trọng đối với trình đọc màn hình và các công nghệ hỗ trợ khác.

#### H: Làm thế nào tôi có thể đặt tiêu đề cho tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET?

A: Bài hướng dẫn bao gồm các ví dụ về mã nguồn C# minh họa cách đặt tiêu đề cho tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET.

#### H: Quá trình di chuyển các thành phần trong tài liệu PDF bao gồm những gì?

A: Di chuyển các phần tử trong tài liệu PDF liên quan đến việc thay đổi phần tử cha của một phần tử cụ thể. Trong hướng dẫn này, bạn sẽ học cách di chuyển phần tử Span vào phần tử Paragraph được chỉ định trong bảng.

#### H: Làm thế nào để lưu tài liệu PDF đã chỉnh sửa sau khi thêm thẻ và chỉnh sửa hình ảnh?

 A: Sau khi bạn đã thêm thẻ, chỉ định văn bản thay thế, đặt hộp giới hạn và chỉnh sửa tài liệu PDF, bạn có thể sử dụng các ví dụ mã nguồn C# được cung cấp để lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save()` phương pháp.

#### H: Mục đích của mã nguồn mẫu được cung cấp trong hướng dẫn là gì?

A: Mã nguồn mẫu đóng vai trò là tài liệu tham khảo thực tế để triển khai gắn thẻ và thao tác hình ảnh bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này làm điểm khởi đầu và sửa đổi cho phù hợp với yêu cầu cụ thể của mình.

#### H: Tôi có thể áp dụng những kỹ thuật này cho các loại thành phần khác trong tài liệu PDF, không chỉ hình ảnh không?

A: Có, các kỹ thuật được trình bày trong hướng dẫn này có thể được điều chỉnh để làm việc với nhiều loại thành phần khác nhau trong tài liệu PDF. Bạn có thể áp dụng các nguyên tắc tương tự để gắn thẻ và thao tác các thành phần khác như văn bản, bảng, v.v.

#### H: Làm thế nào tôi có thể xác thực tính tuân thủ PDF/UA của tài liệu PDF đã sửa đổi?

 A: Hướng dẫn cung cấp các ví dụ về mã nguồn C# cho thấy cách xác thực tính tuân thủ PDF/UA của tài liệu PDF đã sửa đổi bằng cách sử dụng`Validate()` phương pháp và tạo báo cáo XML.

#### H: Aspose.PDF for .NET còn cung cấp những tính năng nào khác để làm việc với tài liệu PDF?

A: Aspose.PDF for .NET cung cấp nhiều tính năng để làm việc với tài liệu PDF, bao gồm thao tác văn bản, chèn hình ảnh, tạo bảng, quản lý trường biểu mẫu, chữ ký số, chú thích, v.v. Tham khảo tài liệu và tài nguyên chính thức để khám phá thêm.