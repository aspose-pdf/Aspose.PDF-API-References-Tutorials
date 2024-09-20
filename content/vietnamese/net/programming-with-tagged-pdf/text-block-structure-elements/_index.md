---
title: Các thành phần cấu trúc khối văn bản
linktitle: Các thành phần cấu trúc khối văn bản
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để thêm các thành phần cấu trúc khối văn bản, chẳng hạn như tiêu đề và đoạn văn được gắn thẻ, vào tài liệu PDF hiện có.
type: docs
weight: 220
url: /vi/net/programming-with-tagged-pdf/text-block-structure-elements/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ đi sâu vào Aspose.PDF cho .NET và cách tạo tài liệu PDF có cấu trúc, được gắn thẻ với nhiều cấp độ tiêu đề khác nhau và khối văn bản được định dạng. Cho dù bạn là người mới làm quen với thao tác PDF hay đã quen thuộc với thế giới tạo tài liệu, hướng dẫn từng bước này sẽ chia nhỏ mọi thứ cho bạn theo phong cách đàm thoại đơn giản. Hãy bắt đầu nào!

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, hãy đảm bảo rằng bạn đã thiết lập mọi thứ.

-  Aspose.PDF cho .NET: Bạn sẽ cần tải xuống và cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể lấy nó từ[Trang Tải xuống Aspose.PDF](https://releases.aspose.com/pdf/net/).
- Môi trường phát triển: Bạn sẽ cần một IDE như Visual Studio để chạy và kiểm tra mã.
- .NET Framework: Đảm bảo bạn đã cài đặt .NET trên máy của mình.

 Ngoài ra, bạn sẽ cần một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) nếu bạn chỉ đang thử nghiệm phần mềm, hoặc bạn có thể[mua giấy phép đầy đủ](https://purchase.aspose.com/buy) nếu bạn đã sẵn sàng dốc toàn lực.

## Nhập gói

Bây giờ bạn đã cài đặt mọi thứ, đã đến lúc nhập các không gian tên và gói cần thiết vào dự án của bạn. Điều này cho phép chúng ta truy cập tất cả các tính năng thú vị mà Aspose.PDF cung cấp.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Hướng dẫn từng bước để tạo một tài liệu PDF có gắn thẻ

Bây giờ chúng ta đã chuẩn bị mọi thứ, hãy cùng thực hiện từng bước trong quy trình. Hãy theo dõi khi chúng tôi tạo PDF, thêm các thành phần có cấu trúc như tiêu đề và đoạn văn, rồi lưu tất cả vào một tệp.

## Bước 1: Thiết lập tài liệu

Trước tiên, chúng ta cần tạo một đối tượng Tài liệu PDF để chứa toàn bộ nội dung của chúng ta.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo một tài liệu PDF mới
Document document = new Document();
```

Chuyện gì đang xảy ra ở đây? Chúng tôi chỉ đơn giản là tạo một tài liệu mới mà cuối cùng sẽ trở thành tệp PDF được gắn thẻ của chúng tôi. Hãy đảm bảo thiết lập`dataDir` đến bất cứ nơi nào bạn muốn lưu PDF cuối cùng. Dễ phải không?

## Bước 2: Truy cập Nội dung được gắn thẻ

Bây giờ chúng ta đã có đối tượng tài liệu, hãy chuyển sang truy cập nội dung PDF được gắn thẻ. PDF được gắn thẻ rất cần thiết cho khả năng truy cập, cho phép trình đọc màn hình điều hướng tài liệu dễ dàng hơn.

```csharp
// Nhận Nội dung được gắn thẻ cho tài liệu
ITaggedContent taggedContent = document.TaggedContent;
```

Tại sao bước này lại quan trọng? Vâng, đây là điều khiến PDF của bạn không chỉ là văn bản và hình ảnh trên một trang. Các PDF được gắn thẻ được cấu trúc, giúp chúng dễ diễn giải hơn bằng công nghệ hỗ trợ và cải thiện khả năng truy cập tài liệu nói chung.

## Bước 3: Thiết lập Tiêu đề và Ngôn ngữ Tài liệu

Bây giờ, hãy đặt tiêu đề cho tài liệu và chỉ định ngôn ngữ sẽ sử dụng. Điều này rất quan trọng đối với siêu dữ liệu và giúp các công cụ tìm kiếm và người đọc biết chính xác những gì mong đợi.

```csharp
// Đặt Tiêu đề và Ngôn ngữ cho tài liệu
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Bằng cách đặt tiêu đề và ngôn ngữ, chúng ta sẽ cho cả người dùng và máy biết tài liệu nói về nội dung gì và được viết bằng ngôn ngữ nào. Giống như việc gắn thẻ tên cho tài liệu của bạn tại một bữa tiệc vậy—bây giờ mọi người đều biết đó là ai!

## Bước 4: Tạo các phần tử tiêu đề

Bây giờ chúng ta hãy thêm một số phần tử tiêu đề. Hãy nghĩ về chúng như tiêu đề phần của tài liệu của bạn. Chúng ta sẽ thêm sáu cấp tiêu đề, sẽ sắp xếp nội dung tài liệu của chúng ta theo thứ bậc rõ ràng.

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo các phần tử tiêu đề (H1 đến H6)
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// Đặt văn bản cho tiêu đề
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");

// Thêm tiêu đề vào phần tử gốc
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
```

Chúng tôi đang làm gì ở đây? Chúng tôi đang tạo các tiêu đề từ H1 đến H6, mỗi tiêu đề đại diện cho một mức độ quan trọng khác nhau trong tài liệu của bạn. Các tiêu đề này giúp cấu trúc PDF của bạn, giúp điều hướng dễ dàng hơn.

## Bước 5: Thêm đoạn văn

Bây giờ chúng ta đã có tiêu đề, đã đến lúc thêm một số nội dung văn bản. Hãy tạo một đoạn văn và đặt một số văn bản mẫu cho đoạn văn đó.

```csharp
// Tạo một phần tử đoạn văn
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
rootElement.AppendChild(p);
```

Ở đây, chúng ta thêm một đoạn văn bản bên dưới tiêu đề. Bước này thêm nội dung chính vào tài liệu và bạn có thể tùy chỉnh bằng bất kỳ văn bản nào bạn thích. Hãy nghĩ về việc điền vào khoảng trống giữa các tiêu đề bằng nội dung có ý nghĩa.

## Bước 6: Lưu PDF

Cuối cùng, chúng ta đang ở bước cuối cùng: lưu tài liệu. Bước này đơn giản như tên gọi của nó. Chúng ta sẽ lấy mọi thứ đã tạo cho đến nay và ghi vào tệp PDF.

```csharp
// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

Và chỉ như vậy, bạn đã tạo ra một tài liệu PDF có cấu trúc, được gắn thẻ! Bằng cách lưu nó, về cơ bản bạn đang nhấn nút "xuất bản" và xuất mọi thứ sang tệp PDF có thể chia sẻ hoặc sử dụng ở bất kỳ đâu.

## Phần kết luận

Xin chúc mừng! Bạn vừa tạo một tài liệu PDF có cấu trúc đầy đủ, được gắn thẻ bằng Aspose.PDF cho .NET. Chúng tôi bắt đầu từ đầu, thêm tiêu đề, đoạn văn và thậm chí đảm bảo tài liệu có thể truy cập được bằng cách gắn thẻ phù hợp. Cho dù bạn đang tạo báo cáo, sách điện tử hay hướng dẫn sử dụng, phương pháp này đảm bảo rằng các tệp PDF của bạn có cấu trúc tốt và dễ điều hướng cho cả con người và máy móc.

## Câu hỏi thường gặp

### PDF có gắn thẻ là gì?
Tệp PDF được gắn thẻ chứa siêu dữ liệu giúp trình đọc màn hình và các công nghệ hỗ trợ khác có thể truy cập, giúp người khuyết tật hiểu rõ hơn về nội dung.

### Tôi có thể tùy chỉnh văn bản trong tiêu đề và đoạn văn không?
Hoàn toàn được! Bạn có thể đặt bất kỳ văn bản nào bạn thích cho tiêu đề và đoạn văn trong PDF của mình.

### Làm thế nào để thêm hình ảnh hoặc phương tiện khác vào PDF?
Bạn có thể thêm nhiều thành phần phương tiện khác nhau như hình ảnh, bảng biểu, v.v. bằng các phương pháp khác nhau do Aspose.PDF cung cấp cho .NET.

### Aspose.PDF cho .NET có miễn phí sử dụng không?
 Bạn có thể dùng thử miễn phí bằng cách sử dụng[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) nhưng để sử dụng lâu dài, bạn sẽ cần phải[mua giấy phép đầy đủ](https://purchase.aspose.com/buy).

### Làm thế nào để cải thiện khả năng truy cập vào tệp PDF của tôi hơn nữa?
Bạn có thể tăng cường khả năng truy cập bằng cách thêm thẻ chi tiết hơn, văn bản thay thế cho hình ảnh và sử dụng các thành phần cấu trúc ngữ nghĩa để mang lại trải nghiệm phong phú hơn cho các công nghệ hỗ trợ.