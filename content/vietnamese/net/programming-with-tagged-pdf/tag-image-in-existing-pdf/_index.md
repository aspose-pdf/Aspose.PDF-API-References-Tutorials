---
title: Gắn thẻ hình ảnh trong PDF hiện có
linktitle: Gắn thẻ hình ảnh trong PDF hiện có
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách gắn thẻ hình ảnh trong các tệp PDF hiện có bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tăng cường khả năng truy cập với sự tuân thủ PDF/UA.
type: docs
weight: 210
url: /vi/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Giới thiệu

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách gắn thẻ hình ảnh trong PDF hiện có bằng Aspose.PDF cho .NET. Đến cuối hướng dẫn này, bạn sẽ có thể đặt văn bản thay thế cho hình ảnh, điều chỉnh thuộc tính bố cục và đảm bảo PDF của bạn tuân thủ các tiêu chuẩn về khả năng truy cập.

## Điều kiện tiên quyết

Trước khi bắt đầu, chúng ta hãy xem qua những gì bạn cần để bắt đầu:

-  Aspose.PDF cho .NET: Đảm bảo bạn đã tải xuống và cài đặt phiên bản mới nhất của Aspose.PDF cho .NET.[Tải xuống tại đây](https://releases.aspose.com/pdf/net/).
- .NET Framework: Đảm bảo rằng bạn đã thiết lập môi trường phát triển .NET như Visual Studio.
- Hiểu biết cơ bản về cấu trúc PDF: Làm quen với các thành phần cấu trúc PDF như đoạn văn, khoảng, bảng và hình ảnh.
-  Giấy phép hợp lệ: Bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy) hoặc sử dụng tạm thời[đây](https://purchase.aspose.com/temporary-license/).

## Nhập gói

Để bắt đầu mã hóa, bạn cần nhập các không gian tên cần thiết từ Aspose.PDF cho .NET. Chúng sẽ cung cấp cho bạn quyền truy cập vào các lớp và phương thức cần thiết để thao tác với tài liệu PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bây giờ chúng ta đã thiết lập xong bối cảnh, hãy chia nhỏ quy trình gắn thẻ hình ảnh thành nhiều bước.

## Bước 1: Tải tài liệu PDF hiện có

Bước đầu tiên là tải tệp PDF mà bạn muốn làm việc. Đây có thể là bất kỳ tệp PDF nào có hình ảnh mà bạn muốn gắn thẻ.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Mở tài liệu
Document document = new Document(inFile);
```

-  Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tập tin của bạn.
-  Các`Document` lớp cho phép bạn tải PDF hiện có. Bạn sẽ sửa đổi PDF này để gắn thẻ hình ảnh.

## Bước 2: Truy cập Nội dung được gắn thẻ và Phần tử cấu trúc gốc

Sau khi bạn mở PDF, bước tiếp theo là truy cập nội dung được gắn thẻ và xác định phần tử cấu trúc gốc. Điều này rất quan trọng vì nó cho phép bạn điều hướng qua các phần tử trong PDF và thực hiện các sửa đổi.

```csharp
// Nhận nội dung được gắn thẻ và phần tử cấu trúc gốc
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` cung cấp quyền truy cập vào các thành phần có cấu trúc trong PDF.
-  Các`RootElement` là phần tử cấu trúc trên cùng, từ đó bạn có thể di chuyển xuống các phần tử khác như đoạn văn, bảng và hình ảnh.

## Bước 3: Đặt Tiêu đề cho Tài liệu PDF được gắn thẻ

Việc thêm tiêu đề vào tài liệu PDF được gắn thẻ sẽ đảm bảo rằng tài liệu của bạn được gắn nhãn chính xác, điều này hữu ích cho khả năng truy cập và tuân thủ PDF/UA.

```csharp
// Đặt tiêu đề cho tài liệu PDF được gắn thẻ
taggedContent.SetTitle("Document with images");
```

- Đặt tiêu đề cho tệp PDF được gắn thẻ của bạn sẽ tăng cường khả năng truy cập và cải thiện độ rõ ràng của tài liệu đối với trình đọc màn hình và công nghệ hỗ trợ.

## Bước 4: Tìm và gắn thẻ hình ảnh

 Bây giờ, chúng ta hãy tìm phần tử hình ảnh (được gọi là`FigureElement` trong Aspose.PDF), đặt văn bản thay thế cho nó và cấu hình các thuộc tính bố cục của nó.

```csharp
// Lặp qua tất cả các phần tử Hình (hình ảnh) và đặt văn bản thay thế và các thuộc tính bố cục
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Đặt văn bản thay thế cho hình ảnh
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Tạo và thiết lập thuộc tính BBox (hộp giới hạn)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Đặt thuộc tính bố cục cho hình
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Mã này lặp qua tất cả`FigureElement` các đối tượng trong cấu trúc gốc, biểu diễn hình ảnh.
- Thiết lập văn bản thay thế để dễ truy cập (trình đọc màn hình sẽ sử dụng văn bản này để mô tả hình ảnh).
- Hộp giới hạn (`BBox`chỉ định tọa độ cho bố cục của hình ảnh, đảm bảo hình ảnh được hiển thị chính xác trong tài liệu.

## Bước 5: Sửa đổi các phần tử Span trong Bảng

 Trong một số trường hợp, bạn có thể cần phải sửa đổi các phần tử span trong một bảng. Ở đây, chúng tôi sẽ trình bày cách tìm một`SpanElement` và chuyển nó vào một đoạn văn.

```csharp
// Tìm các thành phần bảng, khoảng và đoạn văn
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Di chuyển phần tử span vào đoạn văn
spanElement.ChangeParentElement(paragraph);
```

-  Ở đây, chúng tôi xác định vị trí`TableElement`, `SpanElement` , Và`ParagraphElement` trong PDF.
-  Sử dụng`ChangeParentElement` phương pháp này, chúng ta di chuyển khoảng vào trong đoạn văn để đảm bảo gắn thẻ và cấu trúc phù hợp.

## Bước 6: Lưu tài liệu và xác thực sự tuân thủ PDF/UA

Khi tất cả các thay đổi đã được thực hiện, bước cuối cùng là lưu tệp PDF đã cập nhật và kiểm tra xem nó có tuân thủ các tiêu chuẩn PDF/UA hay không.

```csharp
// Lưu tài liệu PDF đã cập nhật
document.Save(outFile);

// Xác thực sự tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  Các`Validate` Phương pháp này kiểm tra tài liệu PDF theo các tiêu chuẩn PDF/UA và ghi lại kết quả.
- Đảm bảo tuân thủ giúp cải thiện khả năng truy cập và đáp ứng các yêu cầu quy định về xuất bản tài liệu.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã chỉ cho bạn cách gắn thẻ hình ảnh trong PDF hiện có bằng Aspose.PDF cho .NET. Bằng cách thiết lập văn bản thay thế, điều chỉnh các thuộc tính bố cục và xác thực tài liệu để tuân thủ PDF/UA, bạn có thể đảm bảo rằng PDF của mình có thể truy cập được và đáp ứng các tiêu chuẩn hiện đại. Aspose.PDF giúp bạn dễ dàng làm việc với các thành phần có cấu trúc, giúp bạn kiểm soát bố cục và khả năng truy cập của tài liệu.

## Câu hỏi thường gặp

### Aspose.PDF for .NET được sử dụng để làm gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ được sử dụng để tạo, chỉnh sửa và thao tác các tài liệu PDF theo chương trình trong môi trường .NET.

### Làm thế nào để đảm bảo tuân thủ PDF/UA?
 Bạn có thể sử dụng Aspose.PDF`Validate` phương pháp kiểm tra sự tuân thủ PDF/UA sau khi thực hiện sửa đổi đối với tài liệu.

### Văn bản thay thế trong PDF là gì?
Văn bản thay thế là mô tả được thêm vào hình ảnh trong tệp PDF để cải thiện khả năng truy cập, đặc biệt đối với người dùng sử dụng trình đọc màn hình.

### Tôi có thể thao tác các bảng và khoảng trong PDF bằng Aspose.PDF không?
Có, Aspose.PDF cho phép bạn thao tác các bảng, khoảng và các thành phần có cấu trúc khác trong tài liệu PDF.

### Tôi có thể tải xuống Aspose.PDF cho .NET ở đâu?
 Bạn có thể tải xuống phiên bản mới nhất của Aspose.PDF cho .NET[đây](https://releases.aspose.com/pdf/net/).