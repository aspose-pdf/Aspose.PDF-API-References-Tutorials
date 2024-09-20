---
title: Tạo phần tử bảng
linktitle: Tạo phần tử bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để tạo phần tử mảng bằng Aspose.PDF cho .NET. Tạo PDF động với bảng dễ dàng.
type: docs
weight: 80
url: /vi/net/programming-with-tagged-pdf/create-table-element/
---
## Giới thiệu

Bạn đã bao giờ tự hỏi làm thế nào bạn có thể dễ dàng tạo và tùy chỉnh các thành phần bảng trong PDF bằng .NET chưa? Vâng, Aspose.PDF cho .NET chính là giải pháp dành cho bạn! Cho dù bạn đang tự động tạo báo cáo hay tạo bảng động cho nhiều tài liệu khác nhau, Aspose.PDF đều cung cấp API phong phú để làm việc với các thành phần bảng. Hướng dẫn này sẽ hướng dẫn bạn từng bước cách tạo bảng, định dạng bảng và thậm chí đảm bảo bảng đáp ứng các tiêu chuẩn tuân thủ PDF/UA. Nghe có vẻ thú vị phải không? Hãy cùng tìm hiểu ngay nhé!

## Điều kiện tiên quyết

Trước khi bắt đầu, bạn cần chuẩn bị một số thứ sau:
1.  Aspose.PDF cho .NET: Tải xuống phiên bản mới nhất từ[Tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/).
2. Môi trường phát triển: Bất kỳ IDE nào hỗ trợ .NET (ví dụ: Visual Studio).
3. Kiến thức cơ bản về C#: Khuyến khích người mới bắt đầu có kiến thức về lập trình C#.

 Cuối cùng, đừng quên giấy phép Aspose.PDF của bạn. Nếu bạn không có, bạn có thể sử dụng[dùng thử miễn phí](https://releases.aspose.com/) hoặc yêu cầu một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để kiểm tra mọi thứ.

## Nhập gói

Trước tiên, hãy nhập các gói cần thiết. Điều này sẽ cho phép chúng ta làm việc với tất cả các lớp có liên quan để tạo bảng trong tài liệu PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Trong phần này, chúng tôi sẽ chia nhỏ quy trình tạo bảng thành nhiều bước. Mỗi bước tập trung vào các phần khác nhau của quy trình tạo và tùy chỉnh bảng.

## Bước 1: Tạo một tài liệu PDF mới

Điều đầu tiên chúng ta cần làm là tạo một tài liệu PDF mới. Tài liệu này sẽ đóng vai trò là vùng chứa cho bảng của chúng ta.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo một tài liệu PDF mới
Document document = new Document();
```

 Ở đây, chúng ta đang khởi tạo một phiên bản mới của`Document` class, đây sẽ là tệp PDF trống của chúng ta. Đừng quên xác định đường dẫn tệp của bạn!

## Bước 2: Thiết lập nội dung được gắn thẻ

Tiếp theo, chúng ta cần bật nội dung được gắn thẻ, đảm bảo khả năng truy cập cho bảng. Các tệp PDF được gắn thẻ là bắt buộc để tuân thủ PDF/UA (Khả năng truy cập toàn cầu).

```csharp
// Cho phép nội dung được gắn thẻ
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

Bước này thiết lập tiêu đề và ngôn ngữ của tài liệu, đảm bảo bảng tuân thủ các tiêu chuẩn về khả năng truy cập. Có tài liệu có thể truy cập được là rất quan trọng đối với trải nghiệm của người dùng và các yêu cầu pháp lý trong một số ngành.

## Bước 3: Tạo phần tử bảng

Bây giờ đến phần thú vị nhất - tạo bảng!

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Ở đây, chúng tôi đang sử dụng`RootElement` của nội dung được gắn thẻ để thêm bảng của chúng tôi. Về cơ bản, đây là việc thêm một bảng dưới dạng một nút con vào cấu trúc của tài liệu.

## Bước 4: Tùy chỉnh Đường viền và Tiêu đề Bảng

Bạn không muốn bàn của mình trông nhạt nhẽo, phải không? Hãy thêm chút phong cách!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Chúng tôi đang xác định đường viền và thêm tiêu đề, nội dung và chân trang vào bảng. Lưu ý việc sử dụng`BorderInfo` để tạo kiểu cho đường viền bảng bằng màu xanh đậm.

## Bước 5: Thêm Hàng và Ô vào Bảng

Bây giờ, hãy điền các hàng và ô vào bảng. Phần này của quy trình là nơi chúng ta xác định bố cục của bảng.

### Bước 5.1: Tạo hàng tiêu đề

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 Chúng tôi đang tạo một hàng tiêu đề với 4 cột và mỗi ô tiêu đề được định dạng bằng màu nền là`GreenYellow`. Chúng tôi cũng thiết lập đường viền và căn chỉnh cho tiêu đề.

### Bước 5.2: Thêm hàng thân

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Ở đây, chúng ta đang tạo động 50 hàng và 4 cột, điền văn bản vào và định dạng các ô. Màu nền được đặt thành màu vàng, với văn bản được căn giữa.

### Bước 5.3: Thêm hàng chân trang

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Để hoàn thành bảng, chúng ta thêm một chân trang có văn bản ở giữa và một`LightSeaGreen` lý lịch.

## Bước 6: Xác thực sự tuân thủ PDF/UA

Sau khi tạo bảng, điều quan trọng là phải đảm bảo rằng tệp PDF tuân thủ chuẩn PDF/UA.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// Xác thực sự tuân thủ PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Đoạn mã này lưu tệp PDF và kiểm tra xem tệp có đáp ứng các tiêu chuẩn tuân thủ PDF/UA hay không. Nếu tài liệu tuân thủ, người dùng khuyết tật có thể truy cập được.

## Phần kết luận

Xin chúc mừng! Bạn đã tạo thành công một bảng tùy chỉnh hoàn toàn trong PDF bằng Aspose.PDF cho .NET. Từ việc định dạng bảng đến đảm bảo tuân thủ PDF/UA, giờ đây bạn đã có nền tảng vững chắc để tạo bảng động trong tài liệu PDF của mình. Đừng quên khám phá các tính năng mở rộng của Aspose.PDF để cải thiện thêm tài liệu của bạn!

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh phông chữ và kiểu chữ của bảng không?
Có, Aspose.PDF cho phép bạn tùy chỉnh hoàn toàn phông chữ, kiểu văn bản và căn chỉnh bằng cách sử dụng`TextState` lớp học.

### Làm thế nào để thêm nhiều cột hoặc hàng một cách linh hoạt?
 Bạn có thể điều chỉnh số lượng cột hoặc hàng bằng cách sửa đổi`rowIndex` Và`colIndex` trong các vòng lặp.

### Có thể nhập các ô trong bảng không?
 Có, bạn có thể sử dụng`ColSpan` Và`RowSpan` thuộc tính để hợp nhất các ô trên các cột hoặc hàng.

### Tuân thủ PDF/UA là gì?
Việc tuân thủ PDF/UA đảm bảo rằng tài liệu có thể được người dùng khuyết tật truy cập, tuân thủ theo các tiêu chuẩn trợ năng quốc tế.

### Làm thế nào để kiểm tra tính tuân thủ PDF/UA trong Aspose.PDF?
 Bạn có thể sử dụng`Validate` phương pháp kiểm tra xem tài liệu có tuân thủ tiêu chuẩn PDF/UA hay không.