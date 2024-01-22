---
title: Đặt thuộc tính chú thích trong tệp PDF
linktitle: Đặt thuộc tính chú thích trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt Thuộc tính chú thích trong tệp PDF bằng Aspose.PDF cho .NET. Tùy chỉnh chú thích bằng dòng chú thích, màu văn bản và kiểu kết thúc.
type: docs
weight: 130
url: /vi/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET là một thư viện mạnh mẽ để tạo, thao tác và chuyển đổi tài liệu PDF trong C#. Một trong những tính năng được thư viện này cung cấp là khả năng đặt thuộc tính chú thích cho chú thích văn bản miễn phí trong tài liệu PDF. Điều này có thể được thực hiện bằng cách sử dụng`FreeTextAnnotation` class, cho phép bạn tạo chú thích bằng chú thích.

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập thuộc tính chú thích cho chú thích văn bản miễn phí bằng Aspose.PDF cho .NET trong C#. Thực hiện theo các bước dưới đây để bắt đầu.

## Cài đặt Aspose.PDF cho .NET

 Nếu bạn chưa làm như vậy, bạn sẽ cần phải[Tải xuống](https://releases.aspose.com/pdf/net/) và cài đặt Aspose.PDF cho .NET từ Bản phát hành Aspose hoặc thông qua trình quản lý gói NuGet.

## Bước 1: Tạo một tài liệu PDF mới

 Tạo một tài liệu PDF mới bằng cách sử dụng`Document`lớp được cung cấp bởi Aspose.PDF cho .NET.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Bước 2: Thêm trang mới vào tài liệu

 Thêm một trang mới vào tài liệu bằng cách sử dụng`Pages` bộ sưu tập của`Document` lớp học.

```csharp
Page page = doc.Pages.Add();
```

## Bước 3: Đặt giao diện mặc định

 Đặt giao diện mặc định cho chú thích văn bản tự do bằng cách tạo mới`DefaultAppearance` đối tượng và thiết lập các thuộc tính của nó như`TextColor` Và`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Bước 4: Tạo chú thích văn bản miễn phí với chú thích

 Tạo chú thích văn bản miễn phí mới có chú thích bằng cách sử dụng`FreeTextAnnotation` lớp học. Đặt`Intent` tài sản để`FreeTextIntent.FreeTextCallout` để xác định rằng đây là chú thích chú thích. Đặt`EndingStyle` tài sản để`LineEnding.OpenArrow` để chỉ định kiểu mũi tên ở cuối chú thích. Đặt`Callout` thuộc tính cho một mảng`Point` các đối tượng đại diện cho các điểm trên trang nơi cần vẽ dòng chú thích.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Bước 5: Thêm chú thích văn bản miễn phí vào trang

 Thêm chú thích văn bản miễn phí vào trang bằng cách sử dụng`Annotations` bộ sưu tập của`Page` lớp học.

```csharp
page.Annotations.Add(fta);
```

## Bước 6: Thêm văn bản vào chú thích

 Thêm văn bản vào chú thích bằng cách đặt`RichText`thuộc tính thành một chuỗi XML được định dạng. Trong hướng dẫn này, chúng tôi đặt màu văn bản thành màu đỏ và cỡ chữ thành 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Bước 7: lưu tài liệu

Bây giờ hãy lưu tài liệu bằng cách sử dụng đoạn mã sau:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Mã nguồn mẫu cho Đặt thuộc tính chú thích bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Đây là mẫu</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách đặt thuộc tính chú thích cho chú thích văn bản miễn phí trong tài liệu PDF bằng Aspose.PDF cho .NET. Chú thích chú thích rất hữu ích trong việc cung cấp thông tin bổ sung hoặc giải thích liên quan đến các khu vực cụ thể trong tài liệu. Aspose.PDF for .NET cung cấp nhiều tính năng và khả năng hoạt động với các tệp PDF, bao gồm tạo và tùy chỉnh các chú thích, chẳng hạn như chú thích. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng triển khai chú thích chú thích trong tài liệu PDF của mình, nâng cao khả năng sử dụng và độ rõ ràng của tài liệu. Aspose.PDF for .NET là một thư viện linh hoạt và đáng tin cậy dành cho các hoạt động PDF trong các ứng dụng .NET, cung cấp các công cụ mạnh mẽ để xử lý các tác vụ liên quan đến PDF khác nhau một cách hiệu quả.

### Câu hỏi thường gặp về đặt thuộc tính chú thích trong tệp PDF

#### Câu hỏi: Chú thích chú thích trong tài liệu PDF là gì?

Đáp: Chú thích chú thích trong tài liệu PDF là một loại chú thích cho phép bạn tạo hộp văn bản có dòng dẫn đầu trỏ đến một khu vực cụ thể trong tài liệu. Nó thường được sử dụng để cung cấp thêm thông tin hoặc nhận xét liên quan đến một phần hoặc thành phần cụ thể trong tài liệu.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của chú thích chú thích bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của chú thích chú thích, chẳng hạn như màu sắc, cỡ chữ, căn chỉnh văn bản, kiểu dòng, kiểu mũi tên, v.v.

#### Câu hỏi: Làm cách nào để thêm văn bản vào chú thích chú thích?

 Đáp: Để thêm văn bản vào chú thích chú thích, bạn có thể đặt`RichText` tài sản của`FreeTextAnnotation` sự vật. Các`RichText` thuộc tính lấy một chuỗi XML được định dạng đại diện cho văn bản sẽ được hiển thị trong chú thích chú thích.

#### Câu hỏi: Tôi có thể thêm nhiều chú thích chú thích vào tài liệu PDF bằng Aspose.PDF cho .NET không?

 Đáp: Có, bạn có thể tạo nhiều chú thích chú thích trong tài liệu PDF bằng cách tạo nhiều phiên bản của`FreeTextAnnotation`đối tượng và thêm chúng vào các trang hoặc vị trí khác nhau trong tài liệu.