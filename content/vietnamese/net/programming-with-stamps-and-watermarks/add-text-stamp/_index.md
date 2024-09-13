---
title: Thêm Dấu Văn Bản Vào Tệp PDF
linktitle: Thêm Dấu Văn Bản Vào Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước của chúng tôi và nâng cao khả năng trình bày tài liệu của bạn.
type: docs
weight: 50
url: /vi/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Giới thiệu

Trong thời đại kỹ thuật số ngày nay, PDF là định dạng phổ biến để chia sẻ và phân phối tài liệu. Cho dù bạn là nhà phát triển, người tạo nội dung hay chỉ là người muốn cải thiện tệp PDF của mình, thì việc biết cách thao tác PDF theo chương trình có thể là một bước ngoặt. Một tính năng tiện lợi mà bạn có thể muốn sử dụng là khả năng thêm tem văn bản vào tệp PDF của mình. Thêm tem văn bản có thể mang lại cho tài liệu của bạn nét chuyên nghiệp hoặc truyền tải thông tin quan trọng, chẳng hạn như "Mẫu", "Bí mật" hoặc thậm chí là hình mờ.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, có một vài điều kiện tiên quyết để đảm bảo bạn đã thiết lập mọi thứ đúng cách. Sau đây là những gì bạn cần:

1.  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF trong dự án của mình. Nếu bạn chưa thực hiện việc này, bạn có thể tải xuống từ[Trang web Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio hoặc IDE tương thích: Bạn sẽ cần một môi trường phát triển để viết và chạy mã .NET của mình. Visual Studio là lựa chọn phổ biến nhất trong số các nhà phát triển.
3. Kiến thức cơ bản về C#: Sự quen thuộc với C# và các nguyên tắc lập trình hướng đối tượng sẽ giúp bạn hiểu các ví dụ tốt hơn.
4. Tệp PDF mẫu: Bạn phải có tệp PDF sẵn sàng để sử dụng. Bạn có thể tạo tệp PDF cơ bản hoặc sử dụng bất kỳ tệp PDF hiện có nào để kiểm tra chức năng.

Sau khi đã giải quyết xong những điều kiện tiên quyết này, chúng ta có thể chuyển sang viết mã!

## Nhập gói

Bây giờ, hãy nhập các gói cần thiết. Bước này rất quan trọng vì nó giúp các lớp và phương thức từ thư viện Aspose có sẵn trong dự án của bạn.

### Nhập Aspose.PDF Assembly

Để bắt đầu, bạn cần nhập không gian tên Aspose.PDF. Ở đầu tệp C# của bạn, hãy thêm chỉ thị using sau:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Điều này sẽ cho phép bạn truy cập vào các lớp học cần thiết để tạo và xử lý tài liệu PDF.

Bây giờ, chúng ta hãy đi vào phần chính của hướng dẫn. Chúng tôi sẽ chia nhỏ quy trình thành các bước rõ ràng và súc tích. Mỗi bước sẽ hướng dẫn bạn qua mã để thêm dấu văn bản vào tệp PDF.

## Bước 1: Thiết lập thư mục tài liệu

Đầu tiên, bạn cần thiết lập thư mục lưu trữ tài liệu PDF của mình. Điều này có nghĩa là mã của bạn cần biết nơi tìm tệp PDF bạn muốn chỉnh sửa.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Giải thích: Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tệp PDF của bạn (`AddTextStamp.pdf`) được lưu trữ. Đường dẫn này được sử dụng sau đó để mở và lưu tệp PDF đã sửa đổi.

## Bước 2: Mở Tài liệu PDF

 Tiếp theo, chúng ta sẽ mở tài liệu PDF bằng cách sử dụng`Document` lớp từ không gian tên Aspose.PDF.

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Giải thích: Ở đây, chúng ta đang tạo một phiên bản của`Document` lớp và truyền đường dẫn đến tệp PDF của chúng ta. Điều này sẽ tải tệp PDF để chúng ta có thể thao tác.

## Bước 3: Tạo một con dấu văn bản

Bây giờ, chúng ta sẽ tạo một con dấu văn bản để áp dụng sau này vào tài liệu PDF của mình.

```csharp
// Tạo con dấu văn bản
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Giải thích:`TextStamp` đối tượng được tạo bằng văn bản bạn muốn hiển thị. Trong trường hợp này, chúng tôi sử dụng "Mẫu tem" làm văn bản cho tem của chúng tôi.

## Bước 4: Thiết lập Thuộc tính tem

Để tùy chỉnh con dấu của bạn, chúng ta có thể thiết lập nhiều thuộc tính khác nhau như màu nền, vị trí và xoay. Hãy thực hiện ngay bây giờ:

```csharp
// Thiết lập tem có phải là nền không
textStamp.Background = true;

// Đặt nguồn gốc
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Xoay tem
textStamp.Rotate = Rotation.on90;
```

Giải thích:
- Bối cảnh: Thiết lập điều này thành`true` có nghĩa là con dấu sẽ xuất hiện phía sau nội dung của tệp PDF.
- XIndent & YIndent: Các thuộc tính này xác định vị trí của con dấu trên trang. Trong ví dụ này, con dấu sẽ được đặt cách mép trái và mép trên của trang 100 đơn vị.
- Xoay: Xoay tem 90 độ. Bạn có thể chọn các tùy chọn xoay khác nhau dựa trên yêu cầu thiết kế của mình.

## Bước 5: Tùy chỉnh Thuộc tính Văn bản

Tiếp theo, chúng ta hãy sáng tạo bằng cách tùy chỉnh giao diện của văn bản trong tem của mình:

```csharp
// Đặt thuộc tính văn bản
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Giải thích:
- Phông chữ: Chúng tôi sử dụng phông chữ Arial và in đậm và in nghiêng.
- FontSize: Được đặt ở mức 14.
- ForegroundColor: Sử dụng RGB để đặt màu chữ thành Aqua. Hãy thoải mái thay đổi màu sắc để phù hợp với nhu cầu về thương hiệu hoặc thiết kế của bạn!

## Bước 6: Thêm tem vào trang PDF

Bây giờ là lúc thêm dấu vào một trang cụ thể của tài liệu PDF.

```csharp
// Thêm tem vào trang cụ thể
pdfDocument.Pages[1].AddStamp(textStamp);
```

Giải thích: Trong ví dụ này, con dấu được thêm vào trang đầu tiên của PDF (các trang được lập chỉ mục 1). Điều chỉnh số trang theo nhu cầu cho tài liệu của bạn.

## Bước 7: Lưu PDF đã sửa đổi

Cuối cùng, hãy lưu tài liệu với dấu văn bản mới được thêm vào.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Giải thích: Chúng tôi xác định một đường dẫn mới cho tệp đầu ra và sau đó lưu tài liệu đã sửa đổi. Sau khi lưu, đường dẫn được in ra bảng điều khiển, xác nhận thao tác thành công.

## Phần kết luận

Xin chúc mừng! Bạn đã thêm thành công một con dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET. Phương pháp này cho phép bạn chú thích tài liệu của mình một cách hiệu quả, nâng cao cả tính chuyên nghiệp và khả năng sử dụng của chúng. Cho dù bạn đang thêm hình mờ, chữ ký hay ghi chú đơn giản, thư viện Aspose cung cấp các công cụ mạnh mẽ để thao tác PDF của bạn một cách dễ dàng.

## Câu hỏi thường gặp

### Con dấu văn bản trong PDF là gì?
Con dấu văn bản là lớp phủ đồ họa chứa văn bản có thể được đặt trên tài liệu PDF, thường được sử dụng để chú thích hoặc thêm hình mờ.

### Tôi có thể tùy chỉnh con dấu bằng hình ảnh không?
Có, Aspose.PDF cũng hỗ trợ thêm tem hình ảnh, mang lại tính linh hoạt hơn trong thiết kế.

### Tôi có thể sử dụng ngôn ngữ lập trình nào với Aspose.PDF?
Aspose.PDF chủ yếu tập trung vào .NET, nhưng cũng có phiên bản dành cho các ngôn ngữ khác như Java và Python.

### Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.PDF?
 Bạn có thể nộp đơn xin giấy phép tạm thời bằng cách truy cập[liên kết mua hàng](https://purchase.aspose.com/temporary-license/) trên trang web của họ.

### Tôi có thể tìm thấy hỗ trợ cho Aspose.PDF ở đâu?
 Hỗ trợ cho Aspose.PDF có sẵn trên[diễn đàn hỗ trợ](https://forum.aspose.com/c/pdf/10).