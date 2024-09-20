---
title: Tìm kiếm biểu thức chính quy trong tệp PDF
linktitle: Tìm kiếm biểu thức chính quy trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm biểu thức chính quy trong tệp PDF bằng Aspose.PDF cho .NET trong hướng dẫn từng bước này. Tăng năng suất của bạn với regex.
type: docs
weight: 440
url: /vi/net/programming-with-text/search-regular-expression/
---
## Giới thiệu

Khi xử lý các tài liệu PDF lớn, bạn có thể thấy mình đang tìm kiếm các mẫu hoặc định dạng cụ thể như ngày tháng, số điện thoại hoặc dữ liệu có cấu trúc khác. Việc duyệt thủ công PDF có thể rất nhàm chán, phải không? Đây là lúc sử dụng biểu thức chính quy (regex) trở nên hữu ích. Trong hướng dẫn này, chúng ta sẽ khám phá cách tìm kiếm mẫu biểu thức chính quy trong tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này sẽ hướng dẫn bạn từng bước để bạn có thể dễ dàng triển khai trong ứng dụng .NET của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn từng bước, chúng ta hãy xem qua những gì bạn cần chuẩn bị:

-  Aspose.PDF cho .NET: Bạn cần cài đặt thư viện này. Nếu bạn chưa cài đặt, bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio hoặc bất kỳ IDE nào khác tương thích với C#.
- .NET Framework: Đảm bảo dự án của bạn được thiết lập với phiên bản .NET Framework phù hợp.
- Kiến thức cơ bản về C#: Mặc dù hướng dẫn này khá chi tiết, nhưng hiểu biết cơ bản về C# sẽ rất hữu ích.

### Nhập gói

Để bắt đầu, bạn sẽ cần nhập các không gian tên cần thiết từ Aspose.PDF cho .NET vào dự án của mình. Các gói này rất cần thiết để làm việc với PDF và thực hiện các hoạt động tìm kiếm bằng regex.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Chúng ta hãy chia nhỏ quá trình tìm kiếm biểu thức chính quy trong tệp PDF bằng Aspose.PDF thành nhiều bước.

## Bước 1: Thiết lập thư mục tài liệu

 Mỗi thao tác PDF đều bắt đầu bằng việc chỉ định vị trí tài liệu của bạn. Bạn sẽ cần phải xác định đường dẫn đến tệp PDF của mình, được lưu trữ trong`dataDir` biến đổi.

### Bước 1.1: Xác định đường dẫn tài liệu của bạn

```csharp
// Xác định đường dẫn đến tài liệu PDF của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tệp PDF của bạn. Bước này rất quan trọng vì nó trỏ mã của bạn đến tệp bạn muốn làm việc.

### Bước 1.2: Mở Tài liệu PDF

 Tiếp theo, bạn cần mở tài liệu PDF bằng cách sử dụng`Document` lớp từ Aspose.PDF.

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Đây,`"SearchRegularExpressionAll.pdf"` là tệp PDF mẫu mà chúng ta sẽ thực hiện tìm kiếm biểu thức chính quy.

## Bước 2: Thiết lập TextFragmentAbsorber

 Đây là nơi phép thuật xảy ra!`TextFragmentAbsorber` Lớp này giúp nắm bắt các đoạn văn bản khớp với một mẫu cụ thể hoặc biểu thức chính quy.

Hãy thiết lập bộ hấp thụ để tìm mẫu bằng regex. Trong trường hợp này, chúng ta đang tìm kiếm mẫu của những năm như "1999-2000".

```csharp
// Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Giống như 1999-2000
```

 Biểu thức chính quy`\\d{4}-\\d{4}` tìm kiếm một mẫu gồm bốn chữ số theo sau là dấu gạch nối và bốn chữ số khác, đây là mẫu điển hình cho phạm vi năm.

## Bước 3: Bật Tìm kiếm biểu thức chính quy

 Để đảm bảo rằng hoạt động tìm kiếm diễn giải mẫu như một biểu thức chính quy, bạn cần cấu hình các tùy chọn tìm kiếm bằng cách sử dụng`TextSearchOptions` lớp học.

```csharp
// Đặt tùy chọn tìm kiếm văn bản để chỉ định cách sử dụng biểu thức chính quy
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 Thiết lập`TextSearchOptions` ĐẾN`true` đảm bảo rằng trình hấp thụ sử dụng tìm kiếm dựa trên biểu thức chính quy thay vì văn bản thuần túy.

## Bước 4: Chấp nhận Text Absorber

 Ở giai đoạn này, bạn áp dụng trình hấp thụ văn bản vào tài liệu PDF để nó có thể thực hiện thao tác tìm kiếm. Điều này được thực hiện bằng cách gọi`Accept` phương pháp trên`Pages` đối tượng của tài liệu PDF.

```csharp
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

Lệnh này xử lý tất cả các trang của tệp PDF, tìm kiếm bất kỳ văn bản nào khớp với biểu thức chính quy.

## Bước 5: Trích xuất và hiển thị kết quả

 Sau khi tìm kiếm hoàn tất, bạn cần trích xuất kết quả.`TextFragmentAbsorber` lưu trữ những kết quả này trong một`TextFragmentCollection`. Bạn có thể lặp qua bộ sưu tập này để truy cập và hiển thị từng đoạn văn bản phù hợp.

### Bước 5.1: Lấy lại các đoạn văn bản đã trích xuất

```csharp
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

Bây giờ bạn đã thu thập được các đoạn văn bản, đã đến lúc lặp lại chúng và hiển thị các chi tiết có liên quan như văn bản, vị trí, chi tiết phông chữ, v.v.

### Bước 5.2: Lặp qua các đoạn

```csharp
// Lặp lại các đoạn
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

 Đối với mỗi`TextFragment`, các chi tiết như kích thước phông chữ, tên phông chữ và vị trí được in ra. Điều này không chỉ giúp tìm văn bản mà còn cung cấp cho bạn định dạng và vị trí chính xác của văn bản.

## Phần kết luận

Vậy là xong! Tìm kiếm các mẫu trong tệp PDF bằng biểu thức chính quy cực kỳ hiệu quả, đặc biệt là đối với văn bản có cấu trúc như ngày tháng, số điện thoại và các mẫu tương tự. Aspose.PDF cho .NET cung cấp một cách liền mạch để thực hiện các thao tác như vậy một cách dễ dàng. Bây giờ bạn có thể tận dụng sức mạnh của biểu thức chính quy để tự động tìm kiếm văn bản PDF, giúp quy trình làm việc của bạn hiệu quả hơn.

## Câu hỏi thường gặp

### Tôi có thể tìm kiếm nhiều mẫu trong một tệp PDF không?
 Có, bạn có thể chạy nhiều`TextFragmentAbsorber` các đối tượng, mỗi đối tượng có các mẫu biểu thức chính quy khác nhau, trên cùng một tệp PDF.

### Aspose.PDF có hỗ trợ tìm kiếm các mẫu không phân biệt chữ hoa chữ thường không?
 Chắc chắn rồi! Bạn có thể cấu hình`TextSearchOptions` để tìm kiếm không phân biệt chữ hoa chữ thường.

### Có giới hạn về kích thước tệp PDF mà tôi có thể tìm kiếm không?
Không có giới hạn nghiêm ngặt, nhưng hiệu suất có thể thay đổi tùy thuộc vào kích thước của tệp PDF và độ phức tạp của mẫu biểu thức chính quy.

### Tôi có thể đánh dấu văn bản tìm thấy trong tệp PDF không?
Có, Aspose.PDF cho phép bạn đánh dấu hoặc thậm chí thay thế văn bản sau khi tìm thấy bằng cách sử dụng trình hấp thụ.

### Tôi phải xử lý lỗi như thế nào nếu không tìm thấy mẫu?
 Nếu không tìm thấy kết quả khớp,`TextFragmentCollection` sẽ trống. Bạn có thể xử lý tình huống này bằng cách kiểm tra đơn giản trước khi lặp qua các kết quả.