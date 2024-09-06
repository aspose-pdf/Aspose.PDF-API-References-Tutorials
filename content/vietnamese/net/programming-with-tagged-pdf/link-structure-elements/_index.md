---
title: Các thành phần cấu trúc liên kết
linktitle: Các thành phần cấu trúc liên kết
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước sử dụng các thành phần cấu trúc liên kết với Aspose.PDF cho .NET. Tạo siêu liên kết trong tài liệu PDF của bạn.
type: docs
weight: 120
url: /vi/net/programming-with-tagged-pdf/link-structure-elements/
---
Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách sử dụng các thành phần cấu trúc liên kết với Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo và thao tác các tài liệu PDF theo chương trình. Các thành phần cấu trúc liên kết cho phép bạn thêm siêu liên kết vào tài liệu PDF của mình, cho phép người dùng nhấp vào các liên kết và điều hướng đến các tài nguyên trực tuyến.

Hãy cùng tìm hiểu mã và cách sử dụng các thành phần cấu trúc liên kết với Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Thư viện Aspose.PDF cho .NET được cài đặt.
2. Kiến thức cơ bản về ngôn ngữ lập trình C#.

## Bước 1: Thiết lập môi trường

Để bắt đầu, hãy mở môi trường phát triển C# của bạn và tạo một dự án mới. Đảm bảo bạn đã thêm tham chiếu đến thư viện Aspose.PDF cho .NET vào dự án của bạn.

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

Sau đó, chúng ta sẽ lấy nội dung được gắn thẻ của tài liệu để làm việc.

```csharp
// Nhận nội dung được gắn thẻ của tài liệu
ITaggedContent taggedContent = document.TaggedContent;
```

## Bước 4: Đặt tiêu đề và ngôn ngữ cho tài liệu

Bây giờ chúng ta có thể đặt tiêu đề và ngôn ngữ cho tài liệu.

```csharp
// Xác định tiêu đề và ngôn ngữ của tài liệu
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Bước 5: Thêm các thành phần cấu trúc liên kết

Bây giờ chúng ta hãy thêm các thành phần cấu trúc liên kết vào tài liệu của mình. Chúng ta sẽ tạo các loại liên kết khác nhau, bao gồm liên kết văn bản đơn giản, liên kết hình ảnh và liên kết nhiều dòng.
```csharp
// Lấy phần tử cấu trúc gốc (phần tử cấu trúc tài liệu)
StructureElement rootElement = taggedContent.RootElement;

// Thêm một đoạn văn có siêu liên kết
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Thêm một đoạn văn có siêu liên kết chứa văn bản phong phú
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Thêm một đoạn văn có siêu liên kết chứa văn bản được định dạng một phần
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

// Thêm một đoạn văn có siêu liên kết nhiều dòng
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Thêm một đoạn văn có siêu liên kết chứa hình ảnh
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

## Bước 6: Lưu tài liệu PDF đã gắn thẻ

Cuối cùng, chúng ta lưu tài liệu PDF đã gắn thẻ.

```csharp
// Lưu tài liệu PDF đã gắn thẻ
document. Save(outFile);
```

## Bước 7: Kiểm tra sự tuân thủ PDF/UA

 Chúng tôi cũng có thể kiểm tra tài liệu để tuân thủ PDF/UA bằng cách sử dụng`Validate` phương pháp của`Document` lớp học.

```csharp
// Kiểm tra sự tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Mã nguồn mẫu cho các thành phần cấu trúc liên kết sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Tạo tài liệu và nhận nội dung PDF được gắn thẻ
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Thiết lập Tiêu đề và Ngôn ngữ Bản chất cho tài liệu
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

// Lưu tài liệu PDF có gắn thẻ
document.Save(outFile);

// Kiểm tra sự tuân thủ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Phần kết luận

Xin chúc mừng! Bạn đã học cách sử dụng các thành phần cấu trúc liên kết với Aspose.PDF cho .NET. Bây giờ bạn có thể tạo siêu liên kết trong tài liệu PDF của mình, cho phép người dùng điều hướng đến các tài nguyên trực tuyến. Thử nghiệm và khám phá thêm các tính năng của Aspose.PDF để tạo tài liệu PDF tương tác và phong phú.

### Câu hỏi thường gặp

#### H: Các thành phần cấu trúc liên kết trong tài liệu PDF là gì và chúng tăng cường tính tương tác của tài liệu như thế nào?

A: Các thành phần cấu trúc liên kết trong tài liệu PDF được sử dụng để tạo siêu liên kết cho phép người dùng điều hướng đến các tài nguyên trực tuyến hoặc các vị trí cụ thể trong tài liệu. Các thành phần này tăng cường tính tương tác bằng cách cung cấp các liên kết có thể nhấp cho phép người dùng truy cập nội dung liên quan hoặc các trang web bên ngoài.

#### H: Các thành phần cấu trúc liên kết có thể mang lại lợi ích gì trong tài liệu PDF?

A: Các thành phần cấu trúc liên kết nâng cao trải nghiệm của người dùng bằng cách làm cho tài liệu PDF mang tính tương tác. Chúng cung cấp quyền truy cập nhanh vào thông tin bổ sung, nội dung liên quan, trang web bên ngoài hoặc các phần cụ thể trong tài liệu, cải thiện khả năng điều hướng và tạo điều kiện thuận lợi cho việc truy xuất thông tin.

#### H: Tôi có thể tạo các loại siêu liên kết khác nhau bằng cách sử dụng các thành phần cấu trúc liên kết trong Aspose.PDF cho .NET không?

A: Có, bạn có thể tạo nhiều loại siêu liên kết khác nhau bằng các thành phần cấu trúc liên kết. Aspose.PDF cho .NET cho phép bạn tạo siêu liên kết với văn bản thuần túy, văn bản phong phú, hình ảnh và mô tả nhiều dòng, mang lại tính linh hoạt trong cách bạn liên kết đến nội dung bên ngoài hoặc các vị trí trong tài liệu.

#### H: Làm thế nào để thiết lập và khởi tạo các thành phần cấu trúc liên kết trong tài liệu PDF bằng Aspose.PDF cho .NET?

 A: Để sử dụng các thành phần cấu trúc liên kết, trước tiên bạn cần tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp. Sau đó, lấy nội dung được gắn thẻ bằng cách sử dụng`TaggedContent`thuộc tính của tài liệu. Từ đó, bạn có thể tạo và tùy chỉnh các thành phần cấu trúc liên kết và thêm chúng vào thành phần cấu trúc gốc.

#### H: Làm thế nào tôi có thể tạo siêu liên kết văn bản đơn giản bằng cách sử dụng các thành phần cấu trúc liên kết?
 A: Bạn có thể tạo một siêu liên kết văn bản đơn giản bằng cách tạo một`LinkElement` và thiết lập của nó`Hyperlink` tài sản cho một`WebHyperlink` với URL bạn muốn liên kết đến. Bạn cũng có thể thiết lập văn bản hiển thị của liên kết bằng cách sử dụng`SetText` phương pháp.

#### H: Có thể tạo siêu liên kết bằng hình ảnh bằng cách sử dụng các thành phần cấu trúc liên kết không?

 A: Có, bạn có thể tạo siêu liên kết với hình ảnh bằng cách sử dụng các thành phần cấu trúc liên kết. Bạn sẽ tạo một`LinkElement` và sau đó thêm một`FigureElement` có hình ảnh kèm theo. Điều này cho phép bạn tạo siêu liên kết dựa trên hình ảnh.

#### H: Làm sao tôi có thể đảm bảo rằng tài liệu PDF có siêu liên kết của tôi tuân thủ tiêu chuẩn PDF/UA về khả năng truy cập?

 A: Aspose.PDF cho .NET cung cấp khả năng xác thực sự tuân thủ của tài liệu PDF của bạn với tiêu chuẩn PDF/UA bằng cách sử dụng`Validate` phương pháp của`Document`lớp. Điều này đảm bảo rằng các siêu liên kết của tài liệu có thể truy cập được đối với người dùng khuyết tật.

#### H: Mô tả thay thế cho các thành phần cấu trúc liên kết là gì và tại sao chúng lại quan trọng?

A: Mô tả thay thế (văn bản thay thế) cho các thành phần cấu trúc liên kết cung cấp mô tả văn bản của siêu liên kết. Những mô tả này rất cần thiết cho khả năng truy cập, cho phép người dùng khiếm thị hiểu mục đích của liên kết và đích đến của liên kết.

#### H: Tôi có thể tùy chỉnh giao diện và hành vi của siêu liên kết được tạo bằng các thành phần cấu trúc liên kết không?

A: Trong khi các thành phần cấu trúc liên kết chủ yếu tập trung vào việc tạo siêu liên kết, bạn có thể tùy chỉnh giao diện và hành vi của siêu liên kết hơn nữa bằng các tính năng khác do Aspose.PDF cung cấp cho .NET. Điều này bao gồm chỉ định màu sắc, kiểu dáng và hành động liên kết.

#### H: Các thành phần cấu trúc liên kết góp phần làm cho tài liệu PDF trở nên tương tác và thân thiện hơn với người dùng như thế nào?

A: Các thành phần cấu trúc liên kết chuyển đổi các tài liệu PDF tĩnh thành các trải nghiệm tương tác bằng cách thêm các siêu liên kết có thể nhấp. Tính tương tác này cải thiện sự tham gia của người dùng, cho phép điều hướng liền mạch giữa các nội dung liên quan và nâng cao khả năng sử dụng chung của tài liệu.