---
title: Gắn thẻ hình ảnh trong tệp PDF hiện có
linktitle: Gắn thẻ hình ảnh trong tệp PDF hiện có
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đánh dấu hình ảnh trong tệp PDF hiện có bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để thêm thẻ vào hình ảnh.
type: docs
weight: 210
url: /vi/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Trong hướng dẫn chi tiết này, chúng tôi sẽ hướng dẫn bạn từng bước về mã nguồn C# được cung cấp để đánh dấu hình ảnh trong tệp PDF hiện có bằng Aspose.PDF cho .NET. Hãy làm theo hướng dẫn bên dưới để hiểu cách thêm thẻ vào hình ảnh trong tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã định cấu hình môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này bao gồm việc cài đặt thư viện Aspose.PDF và định cấu hình dự án của bạn để tham chiếu nó.

## Bước 2: Mở tài liệu PDF hiện có

Trong bước này, chúng tôi sẽ mở một tài liệu PDF hiện có bằng Aspose.PDF.

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

Bây giờ chúng ta sẽ lấy nội dung được gắn thẻ của tài liệu PDF và thành phần cấu trúc gốc tương ứng.

```csharp
// Nhận nội dung được gắn thẻ và phần tử cấu trúc gốc
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Chúng tôi đã nhận được nội dung được gắn thẻ của tài liệu PDF và thành phần cấu trúc gốc tương ứng.

## Bước 4: Đặt tiêu đề cho tài liệu PDF được gắn thẻ

Bây giờ hãy đặt tiêu đề cho tài liệu PDF được gắn thẻ.

```csharp
// Xác định tiêu đề cho tài liệu PDF được gắn thẻ
taggedContent.SetTitle("Document with images");
```

Chúng tôi đã đặt tiêu đề cho tài liệu PDF được gắn thẻ.

## Bước 5: Gán văn bản thay thế và khung giới hạn cho hình ảnh

Bây giờ, đối với mỗi thành phần hình ảnh, chúng tôi sẽ chỉ định văn bản thay thế và hộp giới hạn.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Gán văn bản thay thế cho hình ảnh
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Tạo và gán khung giới hạn (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Chúng tôi đã chỉ định văn bản thay thế và hộp giới hạn cho từng thành phần hình ảnh trong tài liệu PDF.

## Bước 6: Di chuyển phần tử Span vào đoạn văn

Bây giờ hãy di chuyển phần tử Span vào đoạn văn.

```csharp
// Di chuyển phần tử Span vào đoạn văn (tìm khoảng và đoạn không chính xác trong TD đầu tiên)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Di chuyển phần tử Span trong đoạn văn
spanElement.ChangeParentElement(paragraph);
```

Chúng tôi đã di chuyển phần tử Span vào đoạn văn đã chỉ định.

## Bước 7: Lưu tài liệu PDF đã sửa đổi

Bây giờ chúng tôi đã thực hiện những thay đổi cần thiết, chúng tôi sẽ lưu tài liệu PDF đã sửa đổi.

```csharp
// Lưu tài liệu PDF
document. Save(outFile);
```

Chúng tôi đã lưu tài liệu PDF đã sửa đổi vào thư mục được chỉ định.

### Mã nguồn mẫu cho Hình ảnh thẻ trong tệp PDF hiện có bằng Aspose.PDF cho .NET 

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
	// Đặt văn bản thay thế cho hình
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Tạo và đặt thuộc tính BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Di chuyển phần tử Span vào đoạn văn (tìm sai nhịp và đoạn trong TD đầu tiên)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Di chuyển phần tử Span vào đoạn văn
spanElement.ChangeParentElement(paragraph);

// Lưu tài liệu
document.Save(outFile);

//Kiểm tra tuân thủ PDF/UA cho tài liệu xuất ra
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách đánh dấu hình ảnh trong tệp PDF hiện có bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng Aspose.PDF để thêm thẻ và chỉnh sửa hình ảnh trong tài liệu PDF của mình.

### Câu hỏi thường gặp

#### Hỏi: Mục tiêu chính của hướng dẫn gắn thẻ hình ảnh trong tệp PDF hiện có bằng Aspose.PDF cho .NET này là gì?

Trả lời: Mục tiêu chính của hướng dẫn này là hướng dẫn bạn quy trình đánh dấu hình ảnh trong tài liệu PDF hiện có bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước và ví dụ về mã nguồn C# để giúp bạn hiểu cách gán văn bản thay thế và hộp giới hạn cho hình ảnh, di chuyển các thành phần trong tài liệu và thêm thẻ vào hình ảnh.

#### Câu hỏi: Điều kiện tiên quyết để làm theo hướng dẫn này về gắn thẻ hình ảnh trong PDF bằng Aspose.PDF cho .NET là gì?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này liên quan đến việc cài đặt thư viện Aspose.PDF và định cấu hình dự án của bạn để tham chiếu nó.

#### Câu hỏi: Làm cách nào tôi có thể mở tài liệu PDF hiện có và truy cập nội dung được gắn thẻ của nó bằng Aspose.PDF cho .NET?

Đáp: Hướng dẫn này cung cấp các ví dụ về mã nguồn C# minh họa cách mở tài liệu PDF hiện có bằng Aspose.PDF cho .NET và truy cập nội dung được gắn thẻ của tài liệu đó để thao tác thêm.

#### Hỏi: Mục đích của việc gán văn bản thay thế và hộp giới hạn cho hình ảnh trong tài liệu PDF là gì?

Đáp: Việc gán văn bản thay thế và hộp giới hạn cho hình ảnh sẽ nâng cao khả năng truy cập bằng cách cung cấp văn bản mô tả cho hình ảnh cũng như xác định bố cục và vị trí của chúng trong tài liệu. Thông tin này rất quan trọng đối với trình đọc màn hình và các công nghệ hỗ trợ khác.

#### Câu hỏi: Làm cách nào tôi có thể đặt tiêu đề cho tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET?

Đáp: Hướng dẫn này bao gồm các ví dụ về mã nguồn C# minh họa cách đặt tiêu đề cho tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET.

#### Hỏi: Quá trình di chuyển các phần tử trong tài liệu PDF bao gồm những gì?

Đáp: Việc di chuyển các phần tử trong tài liệu PDF liên quan đến việc thay đổi phần tử gốc của một phần tử cụ thể. Trong hướng dẫn này, bạn sẽ tìm hiểu cách di chuyển phần tử Span vào phần tử Đoạn văn được chỉ định trong bảng.

#### Hỏi: Làm cách nào để lưu tài liệu PDF đã sửa đổi sau khi thêm thẻ và chỉnh sửa hình ảnh?

 Đáp: Khi bạn đã thêm thẻ, gán văn bản thay thế, đặt hộp giới hạn và thực hiện chỉnh sửa tài liệu PDF, bạn có thể sử dụng các ví dụ mã nguồn C# được cung cấp để lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save()` phương pháp.

#### Câu hỏi: Mục đích của mã nguồn mẫu được cung cấp trong hướng dẫn là gì?

Trả lời: Mã nguồn mẫu đóng vai trò là tài liệu tham khảo thực tế để triển khai gắn thẻ và thao tác hình ảnh bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này làm điểm bắt đầu và sửa đổi nó cho phù hợp với yêu cầu cụ thể của mình.

#### Hỏi: Tôi có thể áp dụng những kỹ thuật này cho các loại thành phần khác trong tài liệu PDF, không chỉ hình ảnh không?

Đáp: Có, các kỹ thuật được trình bày trong hướng dẫn này có thể được điều chỉnh để hoạt động với nhiều loại phần tử khác nhau trong tài liệu PDF. Bạn có thể áp dụng các nguyên tắc tương tự để gắn thẻ và thao tác với các thành phần khác như văn bản, bảng, v.v.

#### Câu hỏi: Làm cách nào để xác thực tính tuân thủ PDF/UA của tài liệu PDF đã sửa đổi?

 Đáp: Hướng dẫn này cung cấp các ví dụ về mã nguồn C# cho biết cách xác thực tính tuân thủ PDF/UA của tài liệu PDF đã sửa đổi bằng cách sử dụng`Validate()` phương pháp và tạo ra một báo cáo XML.

#### Câu hỏi: Aspose.PDF for .NET cung cấp những tính năng nào khác để làm việc với tài liệu PDF?

Trả lời: Aspose.PDF for .NET cung cấp nhiều tính năng để làm việc với tài liệu PDF, bao gồm thao tác văn bản, chèn hình ảnh, tạo bảng, quản lý trường biểu mẫu, chữ ký số, chú thích, v.v. Tham khảo tài liệu và tài nguyên chính thức để khám phá thêm.