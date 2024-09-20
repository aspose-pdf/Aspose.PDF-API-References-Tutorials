---
title: Kiểu Bảng Ô
linktitle: Kiểu Bảng Ô
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách định dạng ô bảng trong PDF bằng Aspose.PDF cho .NET với hướng dẫn chi tiết này. Làm theo hướng dẫn để tạo và định dạng các bảng PDF đẹp mắt.
type: docs
weight: 160
url: /vi/net/programming-with-tagged-pdf/style-table-cell/
---
## Giới thiệu

Việc tạo các bảng PDF trông chuyên nghiệp có thể rất khó khăn, nhưng với Aspose.PDF cho .NET, việc này lại trở nên đơn giản đến ngạc nhiên! Cho dù bạn đang định dạng tiêu đề, chân trang hay các ô bảng cụ thể, thư viện mạnh mẽ này cung cấp cho bạn tất cả các công cụ bạn cần để tạo các tài liệu PDF được định dạng đẹp mắt. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách định dạng các ô bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Đừng lo lắng—chúng tôi sẽ chia nhỏ mọi thứ thành các bước dễ thực hiện.

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

1. Aspose.PDF cho .NET: Tải xuống và cài đặt phiên bản mới nhất của Aspose.PDF từ[đây](https://releases.aspose.com/pdf/net/).
2. IDE (như Visual Studio): Thiết lập môi trường phát triển .NET.
3. Kiến thức cơ bản về lập trình C#: Cần có một chút quen thuộc với C#.
4.  Giấy phép Aspose.PDF: Nhận giấy phép tạm thời hoặc đầy đủ để mở khóa toàn bộ các tính năng của thư viện. Bạn có thể dùng thử miễn phí[đây](https://purchase.aspose.com/temporary-license/).

## Nhập gói

Trước khi bắt đầu, hãy đảm bảo nhập các không gian tên cần thiết. Bạn sẽ cần những thứ sau trong dự án của mình:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bây giờ mọi thứ đã được thiết lập, chúng ta hãy cùng xem hướng dẫn từng bước nhé!

Chúng ta sẽ tạo một bảng trong tài liệu PDF và định dạng các ô của bảng đó. Mỗi bước sẽ giải thích chi tiết quy trình.

## Bước 1: Tạo một tài liệu PDF mới

 Bước đầu tiên là tạo một tài liệu PDF mới. Trong Aspose.PDF, bạn có thể khởi tạo một tài liệu PDF mới`Document` đối tượng đại diện cho tệp PDF của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo một tài liệu PDF mới
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Ở đây, chúng tôi khởi tạo một tài liệu PDF và đặt tiêu đề và ngôn ngữ của nó. Điều này cung cấp cho tài liệu của bạn một cấu trúc phù hợp, điều này rất cần thiết để tuân thủ PDF/UA.

## Bước 2: Thiết lập cấu trúc bảng

Bảng trong PDF được định nghĩa trong các thành phần cấu trúc. Hãy tạo bảng và xác định các hàng và cột của bảng.

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo một phần tử cấu trúc bảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Bây giờ chúng ta đã xác định phần đầu của bảng (`TableTHeadElement`), thân hình (`TableTBodyElement`), và chân (`TableTFootElement`) các phần. Bạn có thể coi chúng như bộ khung của bảng.

## Bước 3: Định dạng các ô tiêu đề

Việc định dạng các ô tiêu đề làm cho chúng nổi bật. Ở đây, chúng tôi áp dụng màu nền, đường viền và căn chỉnh văn bản.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Trong bước này, chúng ta lặp qua từng ô tiêu đề, tạo cho nó nền màu xanh lá cây-vàng, đường viền màu xám và văn bản căn phải. Bạn có thể điều chỉnh các thuộc tính này để phù hợp với thiết kế mong muốn của mình.

## Bước 4: Điền và định dạng cho phần thân bảng

Thân bảng chứa dữ liệu thực tế. Sau đây là cách bạn có thể định dạng từng ô bằng các cài đặt lề, đường viền và văn bản cụ thể.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Trong bước này, chúng ta điền vào thân bảng với bốn hàng và định dạng mỗi ô với nền màu vàng và văn bản màu xanh đậm, được căn giữa. Chúng ta cũng sử dụng`MarginInfo`lớp để xác định khoảng đệm xung quanh văn bản.

## Bước 5: Định dạng chân trang

Để tạo cho bảng một cấu trúc hoàn chỉnh, chúng ta thêm và định dạng các ô chân trang, giống như chúng ta đã làm với ô đầu trang.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Phần chân trang được thiết kế tương tự như phần đầu trang, giúp người đọc dễ dàng theo dõi cấu trúc của bảng.

## Bước 6: Lưu và xác thực tài liệu PDF

Cuối cùng, chúng tôi lưu tài liệu PDF và kiểm tra xem nó có tương thích với PDF/UA hay không.

```csharp
// Lưu tài liệu PDF đã gắn thẻ
document.Save(dataDir + "StyleTableCell.pdf");

// Kiểm tra sự tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Chúng tôi lưu PDF và sử dụng`Validate` phương pháp đảm bảo đáp ứng các tiêu chuẩn về khả năng truy cập (tuân thủ PDF/UA).

## Phần kết luận

Tạo kiểu bảng trong PDF bằng Aspose.PDF cho .NET vừa mạnh mẽ vừa linh hoạt. Chỉ với một vài dòng mã, bạn có thể tạo các thiết kế bảng tùy chỉnh giúp tài liệu PDF của bạn nổi bật. Từ việc tùy chỉnh đường viền và nền ô đến đảm bảo tuân thủ khả năng truy cập, Aspose.PDF giúp bạn dễ dàng tạo các tệp PDF được trau chuốt.

## Câu hỏi thường gặp

### Tôi có thể áp dụng nhiều kiểu khác nhau cho từng ô trong bảng không?  
Có, bạn có thể định dạng từng ô bằng cách tùy chỉnh`TableTDElement` của cải.

### Làm thế nào để tôi có thể hợp nhất các ô trong bảng?  
 Bạn có thể sử dụng`ColSpan` Và`RowSpan` thuộc tính để hợp nhất các ô trong bảng.

### Có thể tạo bảng theo chuẩn PDF/UA không?  
 Có, như đã trình bày trong hướng dẫn này, bạn có thể đảm bảo tuân thủ PDF/UA bằng cách xác thực tài liệu của mình bằng`Validate` phương pháp.

### Tôi có thể sử dụng phông chữ khác nhau trong các ô của bảng không?  
 Chắc chắn rồi! Bạn có thể chỉ định các phông chữ khác nhau bằng cách sử dụng`TextState` đối tượng cho mỗi ô.

### Làm thế nào để tải xuống Aspose.PDF cho .NET?  
 Bạn có thể tải nó xuống từ[trang phát hành](https://releases.aspose.com/pdf/net/).