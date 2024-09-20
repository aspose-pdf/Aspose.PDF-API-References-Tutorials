---
title: Kiểu Bảng Phần Tử
linktitle: Kiểu Bảng Phần Tử
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo và định dạng phần tử bảng trong Aspose.PDF dành cho .NET với hướng dẫn từng bước, định dạng tùy chỉnh và tuân thủ PDF/UA.
type: docs
weight: 170
url: /vi/net/programming-with-tagged-pdf/style-table-element/
---
## Giới thiệu

Trong bài viết này, chúng ta sẽ tìm hiểu cách tạo và định dạng phần tử bảng bằng Aspose.PDF cho .NET. Bạn sẽ học cách cấu trúc bảng, áp dụng các kiểu tùy chỉnh và xác thực tính tuân thủ PDF/UA của tài liệu. Đến cuối hướng dẫn này, bạn sẽ có thể dễ dàng tạo các bảng trông chuyên nghiệp trong PDF của mình!

## Điều kiện tiên quyết

Trước khi bắt đầu hướng dẫn, bạn cần đảm bảo rằng mình có những điều sau:

1. Visual Studio hoặc IDE tương tự được cài đặt trên máy của bạn.
2. .NET Framework hoặc .NET Core SDK để chạy ứng dụng.
3.  Aspose.PDF cho thư viện .NET đã tải xuống và tham chiếu trong dự án của bạn. Bạn có thể lấy phiên bản mới nhất từ[đây](https://releases.aspose.com/pdf/net/).
4.  Giấy phép Aspose hợp lệ hoặc[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để mở khóa toàn bộ chức năng của thư viện.

## Nhập gói

Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án của bạn:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Các không gian tên này bao gồm các hoạt động PDF cốt lõi, nội dung được gắn thẻ, bảng và định dạng văn bản.

Bây giờ chúng ta hãy phân tích quá trình tạo và định dạng bảng trong Aspose.PDF. Chúng ta sẽ xem xét từng phần một cách chi tiết để bạn có thể theo dõi.

## Bước 1: Tạo một tài liệu PDF mới và thiết lập nội dung được gắn thẻ

Ở bước đầu tiên này, chúng ta sẽ tạo một tài liệu PDF trống và thiết lập nội dung được gắn thẻ cho tài liệu đó.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo một tài liệu PDF mới
Document document = new Document();

// Thiết lập nội dung được gắn thẻ
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Chúng tôi bắt đầu bằng cách tạo ra một cái mới`Document` đối tượng, đại diện cho PDF của chúng tôi.`TaggedContent`đối tượng được sử dụng để quản lý cấu trúc tài liệu, đảm bảo tuân thủ các tiêu chuẩn về khả năng truy cập. Chúng tôi đặt tiêu đề và ngôn ngữ của tài liệu để gắn thẻ phù hợp.

## Bước 2: Xác định phần tử gốc

Tiếp theo, chúng ta sẽ tạo phần tử cấu trúc gốc, đóng vai trò là nơi chứa toàn bộ nội dung trong tệp PDF của chúng ta.

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
```

 Các`RootElement` đóng vai trò là vùng chứa cơ sở cho tất cả các thành phần có cấu trúc, bao gồm cả bảng của chúng tôi. Nó giúp duy trì thứ bậc cấu trúc của tài liệu, điều này quan trọng đối với cả tổ chức và khả năng truy cập.

## Bước 3: Tạo và định dạng phần tử bảng

 Bây giờ phần tử gốc đã được thiết lập, chúng ta sẽ tạo một`TableElement` và áp dụng các kiểu như màu nền, đường viền và căn chỉnh.

```csharp
// Tạo phần tử cấu trúc bảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Tạo kiểu cho bảng
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Chúng tôi tạo ra một`TableElement` , xác định cấu trúc bảng của chúng tôi.`BackgroundColor`, `Border` , Và`Alignment` thuộc tính cho phép chúng ta tùy chỉnh giao diện của bảng.`Broken` Thuộc tính này đảm bảo rằng nếu bảng bị ngắt giữa các trang, nó sẽ bị ngắt theo chiều dọc.

## Bước 4: Thiết lập Kích thước Bảng và Kiểu Ô

Ở bước này, chúng ta sẽ xác định số cột, khoảng đệm ô và các thuộc tính quan trọng khác của bảng.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Chúng tôi chỉ định độ rộng cột để đảm bảo mỗi cột trong bảng được cách đều nhau.`DefaultCellBorder`, `DefaultCellPadding` , Và`DefaultCellTextState` xác định kiểu mặc định cho các ô, bao gồm đường viền, khoảng đệm, màu chữ và kích thước phông chữ.

## Bước 5: Thêm các hàng lặp lại và kiểu tùy chỉnh

Chúng ta cũng có thể xác định kiểu cho các hàng lặp lại và các thành phần bảng cụ thể khác như đầu trang và chân trang.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 Các`RepeatingRowsCount` đảm bảo rằng ba hàng đầu tiên lặp lại nếu bảng trải dài nhiều trang. Chúng tôi đặt`RepeatingRowsStyle` để áp dụng màu nền tùy chỉnh cho các hàng này.

## Bước 6: Thêm các phần tử đầu, thân và chân bảng

Bây giờ, chúng ta hãy tạo phần đầu trang, nội dung và chân trang của bảng và nhập nội dung vào đó.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Tạo hàng tiêu đề
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Điền nội dung vào thân bảng
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Bảng được chia thành ba phần: phần đầu, phần thân và phần chân. Đầu tiên chúng ta tạo hàng tiêu đề bằng cách sử dụng`TableTHElement`và thêm tiêu đề cột. Sau đó, chúng ta điền vào phần thân của bảng bằng`TableTDElement`, điền nhãn vào mỗi ô có ghi vị trí của ô đó.

## Bước 7: Lưu tài liệu

Cuối cùng, chúng ta lưu tài liệu PDF vào thư mục đã chỉ định.

```csharp
// Lưu tài liệu PDF đã gắn thẻ
document.Save(dataDir + "StyleTableElement.pdf");
```

Bước này hoàn tất quá trình tạo tài liệu bằng cách lưu tệp PDF có bảng đã định kiểu.

## Bước 8: Xác thực sự tuân thủ PDF/UA

Sau khi lưu tài liệu, điều quan trọng là phải đảm bảo rằng tài liệu đó tuân thủ các tiêu chuẩn PDF/UA (Trợ năng toàn diện).

```csharp
// Kiểm tra sự tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Tại đây, chúng tôi tải lại tài liệu và xác thực theo tiêu chuẩn PDF/UA. Tuân thủ đảm bảo rằng PDF của bạn đáp ứng các yêu cầu về khả năng truy cập, giúp nó phù hợp với nhiều người dùng.

## Phần kết luận

Với Aspose.PDF cho .NET, việc tạo và định dạng bảng trong tài liệu PDF của bạn thật đơn giản và trực quan. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể xây dựng các bảng với các kiểu tùy chỉnh và đảm bảo PDF của bạn đáp ứng các tiêu chuẩn về khả năng truy cập. Cho dù bạn đang tạo báo cáo hay tạo tài liệu có cấu trúc, bảng là một công cụ mạnh mẽ để trình bày dữ liệu rõ ràng.

## Câu hỏi thường gặp

### Tôi có thể thêm hình ảnh vào ô trong bảng không?
 Có, bạn có thể chèn hình ảnh vào các ô bảng bằng cách sử dụng`Image` yếu tố.

### Làm thế nào để điều chỉnh độ rộng cột một cách linh hoạt?
 Bạn có thể thiết lập`ColumnAdjustment` tài sản để`AutoFitToWindow` để tự động điều chỉnh độ rộng cột dựa trên nội dung.

### Có bắt buộc phải tuân thủ PDF/UA đối với tất cả tài liệu không?
Mặc dù không bắt buộc, nhưng điều này được khuyến khích đối với các tài liệu yêu cầu tiêu chuẩn khả năng truy cập cao.

### Tôi có thể áp dụng nhiều kiểu khác nhau cho các hàng cụ thể không?
 Có, bạn có thể tùy chỉnh từng hàng hoặc ô riêng lẻ bằng cách điều chỉnh chúng`TextState` hoặc`BackgroundColor`.

### Lợi ích của việc sử dụng nội dung được gắn thẻ là gì?
Nội dung được gắn thẻ cải thiện khả năng truy cập tài liệu và giúp đảm bảo tuân thủ các tiêu chuẩn như PDF/UA.