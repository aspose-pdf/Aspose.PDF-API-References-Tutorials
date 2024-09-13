---
title: Áp dụng Kiểu Số Trong Tệp PDF
linktitle: Áp dụng Kiểu Số Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách áp dụng các kiểu số khác nhau (số La Mã, chữ cái) cho tiêu đề trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-headings/apply-number-style/
---
## Giới thiệu

Bạn đã bao giờ thấy mình cần thêm danh sách được đánh số đẹp mắt vào tài liệu PDF của mình chưa? Cho dù bạn đang định dạng tài liệu pháp lý, báo cáo hay bài thuyết trình, thì các kiểu đánh số phù hợp là điều cần thiết để sắp xếp thông tin. Với Aspose.PDF for .NET, bạn có thể áp dụng nhiều kiểu đánh số khác nhau vào tiêu đề tệp PDF của mình, tạo ra các tài liệu có cấu trúc tốt và chuyên nghiệp. 

## Điều kiện tiên quyết

Trước khi bắt đầu viết mã, chúng ta hãy xem qua những gì bạn cần:

1. Aspose.PDF cho .NET: Tải xuống phiên bản mới nhất của Aspose.PDF từ[đây](https://releases.aspose.com/pdf/net/).
2. Môi trường phát triển: Đảm bảo bạn có Visual Studio hoặc bất kỳ IDE nào khác tương thích với .NET.
3. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework 4.0 trở lên.
4.  Giấy phép: Bạn có thể sử dụng giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/) hoặc khám phá[dùng thử miễn phí](https://releases.aspose.com/) tùy chọn.

## Nhập gói

Để bắt đầu, hãy đảm bảo bạn đã nhập các không gian tên sau vào dự án của mình:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 1: Thiết lập tài liệu

Hãy bắt đầu bằng cách tạo một tài liệu PDF mới và cấu hình cài đặt trang của nó. Chúng ta sẽ thiết lập kích thước trang và lề để kiểm soát bố cục nội dung của chúng ta.

Giải thích: Ở bước này, chúng ta sẽ thiết lập cấu trúc cơ bản của PDF, bao gồm xác định kích thước trang, chiều cao và lề để định dạng thống nhất.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Đặt kích thước và lề trang
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Bằng cách này, tài liệu của bạn sẽ có kích thước trang chuẩn, tương đương với trang có kích thước 8,5 x 11 inch và lề là 72 điểm (hoặc 1 inch) ở tất cả các cạnh.

## Bước 2: Thêm trang vào PDF

Tiếp theo, chúng ta sẽ thêm một trang mới vào tài liệu PDF, tại đó chúng ta sẽ áp dụng kiểu đánh số.

Giải thích: Mỗi tệp PDF đều yêu cầu số trang! Bước này thêm một trang trống vào tệp PDF và đặt lề của tệp PDF cho phù hợp với cài đặt cấp độ tài liệu.

```csharp
// Thêm một trang mới vào tài liệu PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Bước 3: Tạo một hộp nổi

FloatingBox cho phép bạn đặt nội dung (như văn bản hoặc tiêu đề) bên trong một hộp hoạt động độc lập với luồng của trang. Điều này hữu ích khi bạn muốn kiểm soát hoàn toàn bố cục nội dung của mình.

Giải thích: Ở đây, chúng ta thiết lập FloatingBox để chứa các tiêu đề sẽ được áp dụng kiểu số.

```csharp
// Tạo FloatingBox cho nội dung có cấu trúc
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Bước 4: Thêm Tiêu đề đầu tiên bằng Số La Mã

Bây giờ đến phần thú vị! Chúng ta hãy thêm tiêu đề đầu tiên bằng số La Mã viết thường.

Giải thích: Chúng tôi đang áp dụng kiểu NumberingStyle.NumeralsRomanLowercase cho tiêu đề, kiểu này sẽ hiển thị số theo chữ số La Mã (i, ii, iii, v.v.).

```csharp
// Tạo tiêu đề đầu tiên bằng số La Mã
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Bước 5: Thêm Tiêu đề số La Mã thứ hai

Để minh họa, chúng ta hãy thêm tiêu đề số La Mã thứ hai, nhưng lần này chúng ta sẽ bắt đầu từ số 13.

Giải thích: Thuộc tính StartNumber cho phép bạn bắt đầu đánh số từ một số tùy chỉnh—trong trường hợp này, chúng ta bắt đầu từ 13.

```csharp
// Tạo tiêu đề thứ hai bắt đầu bằng số La Mã 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Bước 6: Thêm Tiêu đề với Số thứ tự chữ cái

Để đa dạng hơn, chúng ta hãy thêm tiêu đề thứ ba, nhưng lần này chúng ta sẽ đánh số theo chữ cái thường (a, b, c, v.v.).

Giải thích: Thay đổi NumberingStyle thành LettersLowercase cho phép chúng ta áp dụng cách đánh số theo chữ cái cho các tiêu đề.

```csharp
// Tạo tiêu đề với số thứ tự chữ cái
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Bước 7: Lưu PDF

Cuối cùng, sau khi áp dụng tất cả các tiêu đề và kiểu số, hãy lưu tệp PDF vào thư mục mong muốn.

Giải thích: Bước này lưu tệp PDF chứa tất cả các tiêu đề được định dạng với các kiểu đánh số được áp dụng.

```csharp
// Lưu tài liệu PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Phần kết luận

Và bạn đã có nó! Bạn đã áp dụng thành công các kiểu đánh số—chữ số La Mã và chữ cái—cho các tiêu đề trong tệp PDF bằng Aspose.PDF cho .NET. Tính linh hoạt do Aspose.PDF cung cấp để kiểm soát bố cục trang, kiểu đánh số và định vị nội dung mang đến cho bạn một bộ công cụ mạnh mẽ để tạo các tài liệu PDF chuyên nghiệp, được tổ chức tốt.

## Câu hỏi thường gặp

### Tôi có thể áp dụng nhiều kiểu số khác nhau cho cùng một tài liệu PDF không?  
Có, Aspose.PDF cho .NET cho phép bạn kết hợp nhiều kiểu đánh số khác nhau như số La Mã, số Ả Rập và đánh số theo chữ cái trong cùng một tài liệu.

### Làm thế nào tôi có thể tùy chỉnh số bắt đầu cho tiêu đề?  
 Bạn có thể thiết lập số bắt đầu cho bất kỳ tiêu đề nào bằng cách sử dụng`StartNumber` tài sản.

### Có cách nào để thiết lập lại trình tự đánh số không?  
Có, bạn có thể thiết lập lại số bằng cách điều chỉnh`StartNumber` thuộc tính cho mỗi tiêu đề.

### Tôi có thể áp dụng kiểu in đậm hoặc in nghiêng cho tiêu đề ngoài việc đánh số không?  
 Chắc chắn rồi! Bạn có thể tùy chỉnh kiểu tiêu đề bằng cách sửa đổi các thuộc tính như phông chữ, kích thước, in đậm và in nghiêng bằng cách sử dụng`TextState` sự vật.

### Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.PDF?  
 Bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/) để thử nghiệm Aspose.PDF mà không có hạn chế.