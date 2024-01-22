---
title: Các phần tử cấu trúc liên kết
linktitle: Các phần tử cấu trúc liên kết
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước cách sử dụng các thành phần cấu trúc liên kết với Aspose.PDF cho .NET. Tạo siêu liên kết trong tài liệu PDF của bạn.
type: docs
weight: 120
url: /vi/net/programming-with-tagged-pdf/link-structure-elements/
---
Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách sử dụng các thành phần cấu trúc liên kết với Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo và thao tác các tài liệu PDF theo chương trình. Các phần tử cấu trúc liên kết cho phép bạn thêm siêu liên kết vào tài liệu PDF của mình, cho phép người dùng nhấp vào liên kết và điều hướng đến các tài nguyên trực tuyến.

Hãy đi sâu vào mã và tìm hiểu cách sử dụng các phần tử cấu trúc liên kết với Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Thư viện Aspose.PDF dành cho .NET được cài đặt.
2. Có kiến thức cơ bản về ngôn ngữ lập trình C#.

## Bước 1: Thiết lập môi trường

Để bắt đầu, hãy mở môi trường phát triển C# của bạn và tạo một dự án mới. Đảm bảo rằng bạn đã thêm tham chiếu đến thư viện Aspose.PDF cho .NET trong dự án của mình.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Bước 2: Tạo tài liệu

 Bước đầu tiên là tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp học.

```csharp
// Tạo tài liệu PDF
Document document = new Document();
```

## Bước 3: Làm việc với nội dung được gắn thẻ

Sau đó, chúng tôi lấy nội dung được gắn thẻ của tài liệu để làm việc.

```csharp
// Lấy nội dung được gắn thẻ của tài liệu
ITaggedContent taggedContent = document.TaggedContent;
```

## Bước 4: Đặt tiêu đề và ngôn ngữ tài liệu

Bây giờ chúng ta có thể đặt tiêu đề và ngôn ngữ tài liệu.

```csharp
// Xác định tiêu đề và ngôn ngữ của tài liệu
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Bước 5: Thêm các phần tử cấu trúc liên kết

Bây giờ hãy thêm các phần tử cấu trúc liên kết vào tài liệu của chúng ta. Chúng ta sẽ tạo nhiều loại liên kết khác nhau, bao gồm liên kết văn bản đơn giản, liên kết hình ảnh và liên kết nhiều dòng.
```csharp
// Lấy phần tử cấu trúc gốc (phần tử cấu trúc tài liệu)
StructureElement rootElement = taggedContent.RootElement;

// Thêm đoạn văn có siêu liên kết
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Thêm đoạn văn có siêu kết nối chứa văn bản đa dạng thức
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Thêm đoạn văn có siêu liên kết chứa văn bản được định dạng một phần
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Thêm đoạn văn có siêu liên kết nhiều dòng
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Thêm đoạn văn có siêu liên kết chứa hình ảnh
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Bước 6: Lưu tài liệu PDF được gắn thẻ

Cuối cùng, chúng tôi lưu tài liệu PDF được gắn thẻ.

```csharp
// Lưu tài liệu PDF được gắn thẻ
document. Save(outFile);
```

## Bước 7: Kiểm tra tính tuân thủ của PDF/UA

 Chúng tôi cũng có thể kiểm tra tài liệu xem có tuân thủ PDF/UA hay không bằng cách sử dụng`Validate` phương pháp của`Document` lớp học.

```csharp
// Kiểm tra tính tuân thủ của PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Mã nguồn mẫu cho Các phần tử cấu trúc liên kết bằng Aspose.PDF for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Tạo tài liệu và nhận nội dung Pdf được gắn thẻ
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Đặt tiêu đề và ngôn ngữ tự nhiên cho tài liệu
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Lấy phần tử cấu trúc gốc (Phần tử cấu trúc tài liệu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Lưu tài liệu PDF được gắn thẻ
document.Save(outFile);

// Kiểm tra việc tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Phần kết luận

Xin chúc mừng! Bạn đã học cách sử dụng các phần tử cấu trúc liên kết với Aspose.PDF cho .NET. Giờ đây, bạn có thể tạo siêu liên kết trong tài liệu PDF của mình, cho phép người dùng điều hướng đến các tài nguyên trực tuyến. Thử nghiệm và khám phá thêm các tính năng của Aspose.PDF để tạo các tài liệu PDF có tính tương tác và phong phú.

### Câu hỏi thường gặp

#### Câu hỏi: Các thành phần cấu trúc liên kết trong tài liệu PDF là gì và chúng nâng cao tính tương tác của tài liệu như thế nào?

Trả lời: Các thành phần cấu trúc liên kết trong tài liệu PDF được sử dụng để tạo siêu liên kết cho phép người dùng điều hướng đến các tài nguyên trực tuyến hoặc các vị trí cụ thể trong tài liệu. Các yếu tố này nâng cao tính tương tác bằng cách cung cấp các liên kết có thể nhấp cho phép người dùng truy cập nội dung liên quan hoặc các trang web bên ngoài.

#### Câu hỏi: Các phần tử cấu trúc liên kết có thể có lợi như thế nào trong tài liệu PDF?

Đáp: Các thành phần cấu trúc liên kết nâng cao trải nghiệm người dùng bằng cách làm cho tài liệu PDF có tính tương tác. Chúng cung cấp khả năng truy cập nhanh vào thông tin bổ sung, nội dung liên quan, trang web bên ngoài hoặc các phần cụ thể trong tài liệu, cải thiện khả năng điều hướng và tạo điều kiện thuận lợi cho việc truy xuất thông tin.

#### Câu hỏi: Tôi có thể tạo các loại siêu liên kết khác nhau bằng cách sử dụng các phần tử cấu trúc liên kết trong Aspose.PDF cho .NET không?

Đáp: Có, bạn có thể tạo nhiều loại siêu liên kết khác nhau bằng cách sử dụng các phần tử cấu trúc liên kết. Aspose.PDF for .NET cho phép bạn tạo siêu liên kết với văn bản thuần túy, văn bản đa dạng thức, hình ảnh và mô tả nhiều dòng, mang lại tính linh hoạt trong cách bạn liên kết với nội dung bên ngoài hoặc các vị trí trong tài liệu.

#### Câu hỏi: Làm cách nào để thiết lập và khởi tạo các thành phần cấu trúc liên kết trong tài liệu PDF bằng Aspose.PDF cho .NET?

 Trả lời: Để sử dụng các phần tử cấu trúc liên kết, trước tiên bạn cần tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp học. Sau đó, lấy nội dung được gắn thẻ bằng cách sử dụng`TaggedContent`thuộc tính của tài liệu. Từ đó, bạn có thể tạo và tùy chỉnh các thành phần cấu trúc liên kết và thêm chúng vào thành phần cấu trúc gốc.

#### Câu hỏi: Làm cách nào tôi có thể tạo một siêu liên kết văn bản đơn giản bằng cách sử dụng các thành phần cấu trúc liên kết?
 Đáp: Bạn có thể tạo một siêu liên kết văn bản đơn giản bằng cách tạo một`LinkElement` và thiết lập nó`Hyperlink` tài sản cho một`WebHyperlink` với URL bạn muốn liên kết tới. Bạn cũng có thể đặt văn bản hiển thị của liên kết bằng cách sử dụng`SetText` phương pháp.

#### Câu hỏi: Có thể tạo siêu liên kết bằng hình ảnh bằng cách sử dụng các phần tử cấu trúc liên kết không?

 Trả lời: Có, bạn có thể tạo siêu liên kết có hình ảnh bằng cách sử dụng các phần tử cấu trúc liên kết. Bạn sẽ tạo một`LinkElement` và sau đó nối thêm một`FigureElement` với một hình ảnh cho nó. Điều này cho phép bạn tạo siêu liên kết dựa trên hình ảnh.

#### Câu hỏi: Làm cách nào để đảm bảo rằng tài liệu PDF có siêu liên kết của tôi tuân thủ tiêu chuẩn PDF/UA về khả năng truy cập?

 Đáp: Aspose.PDF for .NET cung cấp khả năng xác thực tính tuân thủ của tài liệu PDF của bạn với tiêu chuẩn PDF/UA bằng cách sử dụng`Validate` phương pháp của`Document`lớp học. Điều này đảm bảo rằng người dùng khuyết tật có thể truy cập được các siêu liên kết của tài liệu.

#### Câu hỏi: Mô tả thay thế cho các thành phần cấu trúc liên kết là gì và tại sao chúng lại quan trọng?

Đáp: Mô tả thay thế (văn bản thay thế) cho các thành phần cấu trúc liên kết cung cấp mô tả bằng văn bản về siêu liên kết. Những mô tả này rất cần thiết cho khả năng truy cập, cho phép người dùng khiếm thị hiểu được mục đích của liên kết và đích đến của nó.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện và hoạt động của siêu liên kết được tạo bằng các phần tử cấu trúc liên kết không?

Trả lời: Mặc dù các thành phần cấu trúc liên kết chủ yếu tập trung vào việc tạo siêu liên kết, nhưng bạn có thể tùy chỉnh thêm giao diện và hoạt động của siêu liên kết bằng cách sử dụng các tính năng khác do Aspose.PDF cung cấp cho .NET. Điều này bao gồm việc chỉ định màu sắc, kiểu dáng và hành động liên kết.

#### Câu hỏi: Các phần tử cấu trúc liên kết góp phần làm cho tài liệu PDF trở nên tương tác và thân thiện hơn với người dùng như thế nào?

Đáp: Các phần tử cấu trúc liên kết chuyển đổi tài liệu PDF tĩnh thành trải nghiệm tương tác bằng cách thêm các siêu liên kết có thể nhấp vào. Tính tương tác này cải thiện mức độ tương tác của người dùng, cho phép điều hướng liền mạch giữa các nội dung liên quan và nâng cao khả năng sử dụng tổng thể của tài liệu.