---
title: Con dấu số trang trong tệp PDF
linktitle: Con dấu số trang trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm dấu số trang vào tệp PDF bằng Aspose.PDF cho .NET thông qua hướng dẫn dễ làm theo của chúng tôi, kèm theo ví dụ mã.
type: docs
weight: 160
url: /vi/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Giới thiệu

Bạn đã bao giờ thấy mình vật lộn với một tài liệu PDF, ước gì nó có số trang để dễ điều hướng hơn chưa? Cho dù bạn là sinh viên chia sẻ ghi chú, chuyên gia trình bày báo cáo hay bất kỳ ai quản lý tài liệu nhiều trang, việc thêm số trang thực sự có thể nâng cao độ rõ nét của tệp PDF của bạn. May mắn thay, với thư viện Aspose.PDF mạnh mẽ cho .NET, bạn có thể dễ dàng thêm dấu số trang vào tài liệu PDF của mình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước trong toàn bộ quy trình, đảm bảo rằng bạn được trang bị mọi kiến thức cần thiết. Hãy cùng bắt đầu!

## Điều kiện tiên quyết

Trước khi bắt đầu thêm dấu số trang vào tài liệu PDF, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. Bạn sẽ viết và thực thi mã của mình tại đây.
2. .NET Framework: Sự quen thuộc với lập trình C# và .NET framework là điều cần thiết vì Aspose.PDF được thiết kế cho các ứng dụng .NET.
3.  Thư viện Aspose.PDF: Bạn có thể tải xuống thư viện Aspose.PDF từ[Bản phát hành PDF của Aspose](https://releases.aspose.com/pdf/net/). 
4. Hiểu biết cơ bản về PDF: Mặc dù bạn không cần phải là chuyên gia, nhưng hiểu biết cơ bản về cách thức hoạt động của tệp PDF sẽ giúp bạn hiểu hướng dẫn tốt hơn.

Khi đã thiết lập xong các điều kiện tiên quyết này, bạn sẽ sẵn sàng bắt đầu đóng dấu số trang!

## Nhập gói

Trước khi bắt đầu viết mã, bạn cần đảm bảo các gói Aspose.PDF cần thiết được nhập vào dự án của bạn. Điều này rất quan trọng để tận dụng các chức năng của thư viện một cách liền mạch. Sau đây là cách thực hiện:

### Tạo một dự án mới

1. Mở Visual Studio.
2.  Nhấp vào`File` >`New` >`Project`.
3.  Chọn một mẫu phù hợp với C# (ví dụ: Ứng dụng Console), đặt tên cho mẫu đó và nhấp vào`Create`.

### Thêm tham chiếu Aspose.PDF

1. Nhấp chuột phải vào tên dự án trong Solution Explorer.
2.  Nhấp vào`Manage NuGet Packages`.
3.  Tìm kiếm`Aspose.PDF` và cài đặt phiên bản mới nhất.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Sau khi thư viện đã sẵn sàng, chúng ta hãy bắt đầu viết mã thôi!

Bây giờ môi trường của chúng ta đã được thiết lập, đã đến lúc thêm dấu số trang vào tệp PDF. Chúng tôi sẽ chia nhỏ quy trình này thành các bước rõ ràng để hiểu rõ hơn.

## Bước 1: Chỉ định thư mục tài liệu

Để bắt đầu, bạn cần chỉ định thư mục chứa tệp PDF của bạn. Đây là điểm bắt đầu của dự án.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Cập nhật đường dẫn này
```

 Giải thích: Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục chứa tệp PDF của bạn. Điều này rất quan trọng vì nó cho mã của bạn biết nơi tìm tệp bạn muốn thao tác.

## Bước 2: Mở Tài liệu

Tiếp theo, chúng ta sẽ mở tài liệu PDF hiện có mà chúng ta muốn thêm dấu số trang.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Giải thích: Ở đây, chúng ta đang sử dụng`Document` lớp do Aspose.PDF cung cấp để mở tệp PDF cụ thể của chúng tôi. Đảm bảo tên tệp khớp với tệp thực tế bạn có trong thư mục của mình.

## Bước 3: Tạo con dấu số trang

Bây giờ đến phần thú vị! Hãy tạo con dấu số trang để thêm vào PDF của chúng ta.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Giải thích:`PageNumberStamp`Lớp này sẽ cho phép chúng ta tạo một con dấu hiển thị số trang hiện tại so với tổng số trang trong tài liệu.

## Bước 4: Cấu hình Stamp

Bây giờ, bạn sẽ cần cấu hình cài đặt tem của mình. Đây là nơi bạn thiết kế giao diện và cách hoạt động của tem.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Giải thích:
- `Background = false`: Điều này có nghĩa là con tem sẽ xuất hiện ở phía trước.
- `Format`: Tại đây, bạn đang thiết lập định dạng để hiển thị "Trang X trong Y", nơi bạn sẽ lấy tổng số trang trong tài liệu một cách động.
- `BottomMargin`: Điều chỉnh khoảng cách từ cuối trang.
- `HorizontalAlignment`: Căn giữa con dấu theo chiều ngang.
- `StartingNumber`: Đặt số trang bắt đầu, thường là từ 1.

## Bước 5: Thiết lập Thuộc tính Văn bản

Tiếp theo, bạn có thể tùy chỉnh giao diện của văn bản trên tem.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Giải thích: Các thuộc tính này cấu hình kiểu phông chữ, cỡ chữ, kiểu (cả in đậm và in nghiêng) và màu sắc của văn bản trong tem để làm cho nó hấp dẫn về mặt thị giác.

## Bước 6: Thêm tem vào một trang cụ thể

Sau khi đã thiết lập xong con dấu, đã đến lúc thêm nó vào một trang cụ thể trong tài liệu của bạn.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Giải thích: Dòng này thêm dấu vào trang đầu tiên của PDF. Bạn có thể điều chỉnh`Pages[1]` lập chỉ mục cho các trang khác nếu cần.

## Bước 7: Lưu tài liệu đầu ra

Cuối cùng, hãy lưu tài liệu PDF đã chỉnh sửa để những thay đổi của bạn được lưu giữ vĩnh viễn.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Giải thích: Bạn đang xác định đường dẫn tệp đầu ra và lưu tài liệu. Bảng điều khiển sẽ cho bạn biết rằng con dấu đã được thêm thành công và tệp được lưu ở đâu.

## Phần kết luận

Thêm tem số trang vào tệp PDF của bạn bằng Aspose.PDF cho .NET không chỉ đơn giản mà còn có thể tùy chỉnh cao. Chúng tôi đã thực hiện từng bước để tạo tem số trang, đảm bảo bạn có hướng dẫn rõ ràng trong suốt quá trình. Bây giờ bạn đã có kiến thức để cải thiện tài liệu PDF của mình, giúp chúng thân thiện với người dùng và chuyên nghiệp hơn. 

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh giao diện của số trang không?  
Có! Bạn có thể thay đổi phông chữ, kích thước, màu sắc và định dạng của số trang như được trình bày trong hướng dẫn.

### Aspose.PDF có miễn phí sử dụng không?  
 Aspose.PDF cung cấp bản dùng thử miễn phí, nhưng bạn sẽ cần giấy phép để sử dụng rộng rãi. Hãy xem[mua trang](https://purchase.aspose.com/buy) để biết thêm thông tin.

### Tôi phải làm sao nếu gặp vấn đề trong khi triển khai?  
 Bạn có thể ghé thăm[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/pdf/10) để được hỗ trợ.

### Làm thế nào để tôi có thể tự động tạo số trang cho nhiều trang?  
Mã hướng dẫn sẽ tự động tính toán tổng số trang, giúp việc tùy chỉnh nhiều trang trở nên dễ dàng.

### Tôi có thể sử dụng Aspose.PDF bằng các ngôn ngữ lập trình khác không?  
Mặc dù hướng dẫn này tập trung vào .NET, Aspose cũng có các thư viện cho Java, Python, v.v.