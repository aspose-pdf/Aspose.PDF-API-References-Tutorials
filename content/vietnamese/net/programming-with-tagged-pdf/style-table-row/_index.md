---
title: Hàng của bảng kiểu
linktitle: Hàng của bảng kiểu
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách định dạng hàng bảng trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước để cải thiện định dạng tài liệu của bạn một cách dễ dàng.
type: docs
weight: 180
url: /vi/net/programming-with-tagged-pdf/style-table-row/
---
## Giới thiệu

Khi nói đến việc tạo các tài liệu PDF có cấu trúc tốt và định dạng đẹp, Aspose.PDF cho .NET là giải pháp phù hợp. Cho dù bạn đang tự động hóa báo cáo, hóa đơn hay tạo bảng động, định dạng bảng với nhiều kiểu khác nhau là chìa khóa để có một tài liệu hoàn thiện. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc tạo kiểu cho một hàng bảng bằng Aspose.PDF cho .NET. Và đừng lo lắng, tôi sẽ hướng dẫn bạn từng bước, giống như một cuộc trò chuyện vui vẻ bên tách cà phê!

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết, hãy đảm bảo rằng bạn đã chuẩn bị mọi thứ chu đáo. Bạn sẽ cần:

1. Aspose.PDF cho Thư viện .NET  
    Nếu bạn chưa có nó, bạn có thể lấy nó từ[đây](https://releases.aspose.com/pdf/net/) . Bạn cũng có thể nhận được một[dùng thử miễn phí](https://releases.aspose.com/) để bắt đầu.
2. Môi trường phát triển  
   Thiết lập Visual Studio hoặc bất kỳ IDE C# nào bạn chọn. Bạn cũng cần cài đặt .NET, nhưng tôi đoán là bạn đã quen với điều đó rồi.
3. Kiến thức cơ bản về C# và .NET  
   Hiểu rõ về C# sẽ giúp bạn thực hiện hướng dẫn này dễ dàng. Nhưng đừng lo, tôi sẽ giải thích chi tiết từng bước!

## Nhập gói

Trước khi chúng ta có thể bắt đầu làm việc với Aspose.PDF, chúng ta cần nhập các không gian tên cần thiết. Trong dự án C# của bạn, hãy đảm bảo bạn bao gồm những điều sau:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Những điều này rất cần thiết để tạo và định dạng bảng, và tất nhiên, để làm việc với nội dung được gắn thẻ nhằm đảm bảo tuân thủ.

Bây giờ chúng ta hãy phân tích từng bước thực hiện để bạn có thể tạo kiểu cho các hàng trong bảng một cách chuyên nghiệp!

## Bước 1: Tạo một tài liệu PDF mới

Trước tiên: hãy tạo một tài liệu PDF hoàn toàn mới. Tài liệu này sẽ chứa tất cả các hàng bảng được định dạng.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu
Document document = new Document();
```

 Ở đây, chúng tôi chỉ đơn giản là khởi tạo một cái mới`Document` đối tượng sẽ đại diện cho tệp PDF của chúng ta. Hãy đảm bảo thiết lập đường dẫn thư mục nơi bạn sẽ lưu các tệp đầu ra.

## Bước 2: Làm việc với Nội dung được gắn thẻ

Để cấu trúc PDF của bạn cho khả năng truy cập, chúng tôi sẽ làm việc với nội dung được gắn thẻ. Điều này giúp tạo các thành phần có cấu trúc như bảng, đảm bảo chúng tuân thủ các tiêu chuẩn về khả năng truy cập như PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Ở đây, chúng ta sẽ thiết lập tiêu đề và ngôn ngữ cho nội dung được gắn thẻ của PDF. Giống như đặt tên cho PDF và cho nó biết ngôn ngữ nào nó nên nói!

## Bước 3: Xác định cấu trúc bảng

Tiếp theo, hãy xác định cấu trúc của bảng mà chúng ta sắp tạo. Mỗi bảng cần có tiêu đề, nội dung và chân trang – giống như một bài đăng trên blog được tổ chức tốt!

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo phần tử cấu trúc bảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Những gì chúng ta đang làm ở đây là tạo một bảng có tiêu đề (`THead`), thân hình (`TBody`), và chân trang (`TFoot`). Các yếu tố này sẽ giữ các hàng của chúng ta.

## Bước 4: Thêm hàng tiêu đề bảng

Bảng không có tiêu đề giống như sách không có tiêu đề. Trước tiên, hãy tạo hàng tiêu đề để cung cấp ngữ cảnh cho dữ liệu.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Ở đây, chúng ta lặp lại và thêm ba ô tiêu đề (`TableTHElement`), cung cấp cho mỗi người một văn bản mô tả. Đơn giản, phải không?

## Bước 5: Thêm các hàng thân được tạo kiểu

Bây giờ đến phần thú vị – tạo kiểu cho các hàng! Hãy tạo bảy hàng với các kiểu tùy chỉnh. Chúng ta sẽ thiết lập màu nền, đường viền, khoảng đệm và căn chỉnh văn bản.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Màu nền: Chúng tôi sử dụng màu vàng kim nhạt để tạo cảm giác chuyên nghiệp nhưng ấm áp.
- Đường viền: Mỗi hàng có đường viền ngoài màu xám đậm và đường viền ô màu xanh lam để có giao diện sắc nét.
- Chiều cao và khoảng đệm: Chiều cao của hàng được thiết lập và khoảng đệm được thêm vào để có giao diện gọn gàng.
- Ngắt trang: Để bảng dễ đọc hơn, mỗi hàng thứ hai sẽ bắt đầu ở một trang mới.

## Bước 6: Thêm Hàng Chân Trang

Giống như tiêu đề, chân trang neo bảng. Hãy cùng tạo một chân trang.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Chúng tôi chỉ cần lặp qua ba ô chân trang và thêm một chút văn bản. Văn bản thay thế cho chân trang là “Hàng chân trang” để có thể truy cập được.

## Bước 7: Lưu tài liệu PDF

Bây giờ khi bàn đã sẵn sàng, đã đến lúc lưu lại kiệt tác của bạn!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Chỉ cần như vậy, tệp PDF của bạn đã được lưu với tất cả các hàng bảng đẹp mắt mà chúng ta vừa tạo kiểu.

## Bước 8: Xác thực sự tuân thủ PDF/UA

Để đảm bảo tệp PDF của chúng tôi tuân thủ các tiêu chuẩn về khả năng truy cập, chúng tôi sẽ xác thực tệp PDF đó để đảm bảo tuân thủ PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Điều này đảm bảo rằng PDF của bạn đáp ứng tiêu chuẩn PDF/UA, giúp mọi người đều có thể truy cập. Khả năng truy cập chính là mục tiêu của trò chơi!

## Phần kết luận

Và bạn đã có nó! Chỉ với một vài dòng mã, bạn đã tạo một bảng được định dạng đầy đủ trong PDF bằng Aspose.PDF cho .NET. Từ tiêu đề đến chân trang, chúng tôi đã định dạng từng hàng, thêm các thành phần trợ năng và thậm chí xác thực tài liệu để tuân thủ. Cho dù bạn đang làm việc trên các báo cáo của công ty, bản trình bày hay chỉ đang giải trí với PDF, hướng dẫn này sẽ giúp bạn. Bây giờ, hãy tiếp tục và bắt đầu định dạng bảng của bạn như một chuyên gia!

## Câu hỏi thường gặp

### Tôi có thể thay đổi kiểu phông chữ của bảng không?  
 Có! Bạn có thể sửa đổi kiểu phông chữ bằng cách sử dụng`TextState` đối tượng cho mỗi ô, cho phép tùy chỉnh đầy đủ.

### Làm thế nào để thêm nhiều cột vào bảng của tôi?  
 Chỉ cần điều chỉnh`colCount`biến và thêm nhiều ô hơn vào vòng lặp cho phần đầu trang, phần thân và phần chân trang.

### Điều gì xảy ra nếu tôi không thiết lập chiều cao hàng?  
Nếu bạn không thiết lập chiều cao hàng, bảng sẽ tự động điều chỉnh dựa trên nội dung.

### Tôi có thể sử dụng tùy chọn này cho số lượng hàng động không?  
Hoàn toàn có thể! Bạn có thể lấy dữ liệu từ cơ sở dữ liệu hoặc bất kỳ nguồn nào khác và điều chỉnh số lượng hàng và cột một cách linh hoạt.

### Aspose.PDF cho .NET có miễn phí sử dụng không?  
 Aspose.PDF cho .NET là một sản phẩm được cấp phép, nhưng bạn có thể dùng thử với[dùng thử miễn phí](https://releases.aspose.com/) hoặc nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).