---
title: Các thành phần cấu trúc liên kết
linktitle: Các thành phần cấu trúc liên kết
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo các thành phần cấu trúc liên kết trong PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để thêm liên kết có thể truy cập, hình ảnh và xác thực tuân thủ.
type: docs
weight: 120
url: /vi/net/programming-with-tagged-pdf/link-structure-elements/
---
## Giới thiệu

Việc tạo và quản lý các thành phần cấu trúc liên kết trong PDF có thể rất quan trọng đối với các tài liệu yêu cầu khả năng truy cập và điều hướng mượt mà. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thực hiện việc này bằng Aspose.PDF cho .NET. Nếu bạn mới làm quen với Aspose.PDF hoặc thao tác PDF nói chung, đừng lo lắng. Tôi sẽ giải thích chi tiết từng bước để bạn có thể dễ dàng theo dõi!

## Điều kiện tiên quyết  

Trước khi đi sâu vào mã hóa, chúng ta hãy giải quyết một số vấn đề trước. Đây là những yêu cầu cơ bản để đảm bảo trải nghiệm phát triển suôn sẻ.

1.  Aspose.PDF cho .NET: Bạn có thể tải xuống phiên bản mới nhất[đây](https://releases.aspose.com/pdf/net/).
2. Môi trường phát triển .NET: Cho dù là Visual Studio hay bất kỳ IDE nào tương thích với .NET, hãy cài đặt và sử dụng ngay.
3.  Giấy phép Aspose: Bạn có thể sử dụng phiên bản dùng thử miễn phí của Aspose.PDF[đây](https://releases.aspose.com/) hoặc có được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
4. Kiến thức cơ bản về C#: Chúng ta sẽ làm việc với một số mã C#, vì vậy hiểu được những kiến thức cơ bản sẽ giúp mọi việc dễ dàng hơn nhiều.

## Nhập gói

Bạn sẽ cần nhập một số gói trước khi viết mã cho các thành phần cấu trúc liên kết. Bắt đầu bằng cách tham chiếu các thư viện Aspose.PDF cần thiết trong dự án của bạn:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Những lệnh nhập này cho phép chúng ta làm việc với tài liệu PDF, thêm thẻ và quản lý các thành phần cấu trúc.

Bây giờ chúng ta sẽ tạo một tài liệu PDF với nhiều loại cấu trúc liên kết khác nhau và từng bước sẽ được chia nhỏ để giúp bạn hiểu rõ hơn về quy trình.

## Bước 1: Khởi tạo Tài liệu  

Hãy bắt đầu bằng cách tạo một tài liệu PDF mới và thiết lập nội dung được gắn thẻ để dễ truy cập.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Tạo một tài liệu PDF mới
Document document = new Document(); 

// Lấy lại giao diện TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Ở đây, chúng tôi đang khởi tạo`Document` đối tượng, đại diện cho tệp PDF của chúng tôi. Chúng tôi cũng lấy lại`TaggedContent` giao diện, cho phép chúng ta thêm các thành phần cấu trúc như đoạn văn, liên kết và hình ảnh.

## Bước 2: Đặt Tiêu đề và Ngôn ngữ  

Mỗi tệp PDF phải có tiêu đề và cài đặt ngôn ngữ, đặc biệt nếu bạn muốn tuân thủ các tiêu chuẩn PDF/UA.

```csharp
// Đặt tiêu đề và ngôn ngữ cho tài liệu
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Bước này đảm bảo rằng tệp PDF của bạn có tiêu đề có ý nghĩa và đặt ngôn ngữ thành tiếng Anh (`en-US`). Điều này rất quan trọng đối với khả năng truy cập và đảm bảo trình đọc màn hình hoặc các công nghệ hỗ trợ khác có thể hiểu chính xác tài liệu của bạn.

## Bước 3: Tạo và Thêm Đoạn văn  

Ở bước này, chúng ta sẽ thêm các đoạn văn để chứa các thành phần liên kết.

```csharp
// Tạo phần tử gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo một đoạn văn và thêm nó vào phần tử gốc
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Chúng tôi tạo một phần tử cấu trúc gốc, về cơ bản là vùng chứa cấp cao nhất cho tất cả các phần tử khác. Sau đó, chúng tôi tạo một đoạn văn (`p1`) và thêm nó vào phần tử gốc.

## Bước 4: Thêm một liên kết đơn giản  

Bây giờ chúng ta hãy thêm một siêu liên kết cơ bản trỏ tới Google.

```csharp
// Tạo một phần tử liên kết và thêm nó vào đoạn văn
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Đặt siêu liên kết và văn bản cho liên kết
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
Trong bước này, chúng tôi đã tạo một phần tử liên kết, đặt siêu liên kết của nó thành "http://google.com" và cung cấp văn bản ("Google") cho liên kết. Chúng tôi cũng đã thêm một mô tả thay thế để đảm bảo khả năng truy cập.

## Bước 5: Thêm liên kết với Spans  

Chúng ta cũng có thể tạo liên kết với nhiều khoảng văn bản khác nhau.

```csharp
// Tạo một đoạn văn khác
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Tạo liên kết với phần tử span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Ở đây, chúng tôi sử dụng phần tử span để bao quanh một phần văn bản trong liên kết, cho phép chúng tôi tùy chỉnh cách hiển thị một số phần nhất định của liên kết.

## Bước 6: Liên kết đa dòng  

Nếu văn bản liên kết của bạn quá dài thì sao? Đừng lo, bạn có thể chia thành nhiều dòng.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
Trong trường hợp này, chúng tôi đã tạo liên kết nhiều dòng bằng cách chỉ cần thiết lập giá trị văn bản dài và văn bản sẽ tự động ngắt dòng thành nhiều dòng.

## Bước 7: Thêm hình ảnh vào liên kết  

Cuối cùng, bạn cũng có thể thêm hình ảnh vào bên trong liên kết.

```csharp
// Tạo một đoạn văn mới và phần tử liên kết
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Thêm hình ảnh vào liên kết
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Bước này minh họa cách bạn có thể tăng cường liên kết của mình bằng hình ảnh. Trong trường hợp này, chúng tôi đã thêm biểu tượng Google bên trong liên kết. Chúng tôi cũng đảm bảo khả năng truy cập bằng cách đặt văn bản thay thế cho hình ảnh.

## Bước 8: Xác thực PDF để tuân thủ  

Nếu bạn muốn tuân thủ PDF/UA (một tiêu chuẩn về khả năng truy cập), bạn nên xác thực tài liệu của mình.

```csharp
// Lưu tài liệu PDF
document.Save(outFile);

// Xác thực tài liệu để tuân thủ PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Chúng tôi đã lưu tài liệu và xác thực theo tiêu chuẩn PDF/UA, đảm bảo PDF đáp ứng các yêu cầu về khả năng truy cập.

## Phần kết luận  

Trong hướng dẫn này, chúng tôi đã đề cập đến cách tạo tài liệu PDF có cấu trúc bằng Aspose.PDF cho .NET. Từ việc thêm siêu liên kết cơ bản đến các cấu trúc phức tạp hơn như khoảng cách, liên kết nhiều dòng và thậm chí là hình ảnh, hướng dẫn này cung cấp nền tảng vững chắc để thao tác các thành phần liên kết trong PDF của bạn. Với lợi ích bổ sung là tuân thủ PDF/UA, giờ đây bạn đã có thể tạo PDF có thể truy cập và điều hướng.

## Câu hỏi thường gặp

### Tôi có thể thêm các cấu trúc phức tạp hơn như bảng vào bên trong liên kết không?  
Không, liên kết chủ yếu dành cho văn bản và hình ảnh, nhưng bạn có thể nhúng các thành phần phức tạp ở gần đó.

### Xác thực PDF/UA có bắt buộc không?  
Không phải lúc nào cũng vậy, nhưng điều này rất được khuyến khích nếu bạn quan tâm đến khả năng truy cập.

### Điều gì xảy ra nếu đường dẫn tệp hình ảnh không đúng?  
Tài liệu sẽ không hiển thị hình ảnh và có thể báo lỗi trong quá trình kết xuất.

### Tôi có thể định dạng văn bản trong liên kết không?  
Có, bạn có thể áp dụng kiểu văn bản bằng cách sử dụng các phần tử span.

### Có thể tạo liên kết tài liệu nội bộ không?  
Hoàn toàn được! Bạn có thể liên kết đến các phần cụ thể trong cùng một tài liệu.