---
title: Các ký hiệu có thể thay thế trong Header Footer
linktitle: Các ký hiệu có thể thay thế trong Header Footer
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng các ký hiệu có thể thay thế ở phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 320
url: /vi/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## Giới thiệu

Khi làm việc với các tệp PDF, có những lúc bạn cần tùy chỉnh tiêu đề và chân trang bằng nội dung động như số trang, tên báo cáo hoặc ngày tạo. May mắn thay, Aspose.PDF cho .NET đơn giản hóa quy trình này, cho phép bạn tạo PDF với các ký hiệu được cập nhật tự động trong tiêu đề và chân trang, như số trang hoặc chi tiết tạo báo cáo. Bài viết này sẽ hướng dẫn bạn từng bước thay thế các ký hiệu trong tiêu đề và chân trang bằng Aspose.PDF cho .NET, theo cách không chỉ đơn giản mà còn cực kỳ hiệu quả.

## Điều kiện tiên quyết

Trước khi xem hướng dẫn từng bước, hãy đảm bảo bạn có những điều sau:

-  Aspose.PDF cho Thư viện .NET –[Tải về](https://releases.aspose.com/pdf/net/) hoặc nhận được một[dùng thử miễn phí](https://releases.aspose.com/).
- Visual Studio hoặc bất kỳ IDE C# nào được cài đặt trên hệ thống của bạn.
- Kiến thức cơ bản về phát triển C# và .NET.
-  Một hợp lệ[giấy phép](https://purchase.aspose.com/temporary-license/) đối với Aspose.PDF hoặc bạn có thể sử dụng phiên bản dùng thử.

## Nhập gói

Để bắt đầu, bạn cần nhập các không gian tên cần thiết để kích hoạt chức năng của Aspose.PDF cho .NET. Dưới đây là nội dung nhập cần thiết:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Đây là những điều cần thiết để xử lý việc tạo PDF, chỉnh sửa văn bản và quản lý phần đầu trang/chân trang.

Chúng ta hãy chia nhỏ mã ví dụ thành các bước dễ hiểu.

## Bước 1: Thiết lập Tài liệu và Trang

Đầu tiên, chúng ta cần khởi tạo tài liệu và thêm một trang vào đó. Điều này đặt nền tảng cho việc thêm tiêu đề và chân trang.

```csharp
// Thiết lập thư mục tài liệu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng tài liệu
Document doc = new Document();

// Thêm một trang vào tài liệu
Page page = doc.Pages.Add();
```

 Ở đây, chúng tôi đang thiết lập một tài liệu PDF bằng cách sử dụng`Document` lớp và thêm một trang với`doc.Pages.Add()`Trang này sẽ chứa phần đầu trang, phần chân trang và nội dung khác.

## Bước 2: Cấu hình lề trang

Tiếp theo, chúng ta sẽ xác định lề cho trang để đảm bảo nội dung không tràn ra mép trang.

```csharp
// Cấu hình lề
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 Ở đây, chúng tôi đã xác định lề trên, dưới, trái và phải bằng cách sử dụng`MarginInfo` lớp và áp dụng nó vào trang bằng cách sử dụng`page.PageInfo.Margin`.

## Bước 3: Tạo và cấu hình Header

Bây giờ, hãy tạo một tiêu đề và thêm vào trang. Tiêu đề sẽ bao gồm tiêu đề và tên báo cáo.

```csharp
// Tạo tiêu đề
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Đặt lề tiêu đề
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Thêm tiêu đề vào tiêu đề
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Thêm tên báo cáo vào tiêu đề
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 Chúng tôi đã thêm hai`TextFragment` đối tượng cho tiêu đề: một cho tiêu đề báo cáo và một cho tên báo cáo. Văn bản được định dạng bằng`TextState` các thuộc tính như phông chữ, kích thước và căn chỉnh.

## Bước 4: Tạo và cấu hình Footer

Bây giờ là lúc thiết lập phần chân trang, phần này sẽ chứa nội dung động như số trang và ngày tạo.

```csharp
// Tạo chân trang
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Đặt lề chân trang
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Thêm nội dung chân trang
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

Ở phần chân trang, chúng tôi bao gồm các đoạn mã cho ngày tạo, tên báo cáo và số trang động (`$p` Và`$P` lần lượt biểu thị số trang hiện tại và tổng số trang).

## Bước 5: Tạo Bảng ở Chân trang

Bạn cũng có thể thêm các thành phần phức tạp hơn như bảng vào chân trang để sắp xếp dữ liệu tốt hơn.

```csharp
// Tạo bảng cho chân trang
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Tạo hàng và ô cho bảng
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Đặt căn chỉnh cho từng ô
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Thêm nội dung vào ô bảng
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

Khối mã này tạo ra một bảng gồm 3 cột ở chân trang, trong đó mỗi cột chứa các thông tin khác nhau, chẳng hạn như ngày tạo, tên báo cáo và số trang.

## Bước 6: Thêm nội dung vào trang

Ngoài tiêu đề và chân trang, bạn có thể thêm nội dung vào phần thân của trang PDF. Ở đây, chúng tôi thêm một bảng có một số văn bản giữ chỗ.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Thêm nội dung bảng
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

Mã này thêm một bảng đơn giản có ba cột vào trang. Bạn có thể sửa đổi nó cho phù hợp với nhu cầu cụ thể của mình.

## Bước 7: Lưu PDF

Sau khi mọi thứ đã được thiết lập, bước cuối cùng là lưu tài liệu PDF vào vị trí mong muốn.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 Bạn chỉ định đường dẫn tệp và lưu tài liệu bằng cách sử dụng`doc.Save()`. Vậy là xong! Bạn đã tạo thành công tệp PDF có tiêu đề và chân trang tùy chỉnh.

## Phần kết luận

Thay thế các ký hiệu trong tiêu đề và chân trang bằng Aspose.PDF cho .NET không chỉ đơn giản mà còn mạnh mẽ. Bằng cách làm theo hướng dẫn từng bước ở trên, bạn có thể dễ dàng tùy chỉnh PDF của mình bằng nội dung động, chẳng hạn như số trang, tên báo cáo và ngày. Phương pháp này rất linh hoạt, cho phép bạn chèn bảng, điều chỉnh định dạng và kiểm soát bố cục để phù hợp với các yêu cầu cụ thể của bạn.

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh phông chữ cho đầu trang và chân trang không?  
Có, bạn có thể tùy chỉnh hoàn toàn phông chữ, kích thước, màu sắc và kiểu cho văn bản ở đầu trang và chân trang.

### Làm thế nào để thêm hình ảnh vào đầu trang và chân trang?  
 Bạn có thể sử dụng`ImageStamp` để chèn hình ảnh vào đầu trang và chân trang.

### Có thể thêm siêu liên kết vào đầu trang hoặc chân trang không?  
 Có, bạn có thể sử dụng`TextFragment` với một siêu liên kết bằng cách thiết lập`Hyperlink` tài sản.

### Tôi có thể sử dụng các tiêu đề khác nhau cho các trang lẻ và trang chẵn không?  
Có, Aspose.PDF cho phép bạn chỉ định các tiêu đề và chân trang khác nhau cho các trang lẻ và trang chẵn.

### Làm thế nào để điều chỉnh vị trí đầu trang và chân trang?  
Bạn có thể điều chỉnh lề và thuộc tính căn chỉnh để kiểm soát vị trí của đầu trang và chân trang.