---
title: Thêm chú thích liên kết
linktitle: Thêm chú thích liên kết
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm chú thích bằng mực vào tệp PDF bằng Aspose.PDF cho .NET trong hướng dẫn từng bước hấp dẫn này.
type: docs
weight: 20
url: /vi/net/annotations/addlnkannotation/
---
## Giới thiệu

Chào mừng đến với thế giới thao tác PDF với Aspose.PDF cho .NET! Nếu bạn đang muốn cải thiện tài liệu PDF của mình, cho dù là để sử dụng chuyên nghiệp, dự án cá nhân hay bất kỳ mục đích nào khác, thì bạn đã đến đúng nơi rồi. Hôm nay, chúng ta sẽ đi sâu vào một tính năng cụ thể nhưng thiết thực của Aspose.PDF: thêm chú thích bằng mực vào tệp PDF của bạn. Chức năng này có thể cực kỳ hữu ích khi bạn muốn thêm ghi chú hoặc chữ ký giống như viết tay vào tài liệu của mình, giúp chúng trở nên tương tác và hấp dẫn hơn.

## Điều kiện tiên quyết

Trước khi đi sâu vào phép thuật mã hóa, hãy đảm bảo rằng bạn có mọi thứ cần thiết để bắt đầu:

1. .NET Framework: Đảm bảo bạn đã cài đặt .NET trên máy của mình. Thư viện này hoạt động liền mạch với nhiều phiên bản .NET khác nhau, bao gồm .NET Core.
2.  Thư viện Aspose.PDF: Bạn sẽ cần phải tải xuống và tham chiếu thư viện Aspose.PDF cho .NET trong dự án của mình. Nếu bạn chưa thực hiện việc này, bạn có thể lấy phiên bản mới nhất từ[liên kết tải xuống](https://releases.aspose.com/pdf/net/).
3. Trình soạn thảo mã: Bạn có thể sử dụng bất kỳ trình soạn thảo mã nào bạn chọn, nhưng Visual Studio được khuyến khích sử dụng vì dễ sử dụng với các ứng dụng .NET.
4. Hiểu biết cơ bản về C#: Kiến thức cơ bản về C# sẽ giúp bạn dễ dàng xử lý các ví dụ mã hóa.
5. Thiết lập môi trường phát triển của bạn: Đảm bảo IDE của bạn được thiết lập để xử lý các dự án .NET và bạn đã tham chiếu thư viện Aspose.PDF đúng cách trong dự án của mình. 

Sau khi đáp ứng được các điều kiện tiên quyết này, bạn đã sẵn sàng để thêm chú thích bằng mực vào tệp PDF của mình!

## Nhập gói

Trước khi bắt đầu viết mã, hãy nhập các gói cần thiết. Ở đầu tệp C# của bạn, hãy thêm các câu lệnh using sau:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

Điều này sẽ cấp cho bạn quyền truy cập vào tất cả các lớp và phương thức bạn cần để làm việc với chú thích PDF.

Bây giờ chúng ta đã thiết lập xong bối cảnh, đã đến lúc xắn tay áo lên và bắt tay vào thực hiện! Chúng tôi sẽ chia nhỏ từng bước để đảm bảo bạn hiểu chính xác cách tạo và thêm chú thích mực vào tài liệu PDF của mình.

## Bước 1: Thiết lập Tài liệu và Thư mục

Điều đầu tiên bạn muốn làm là thiết lập tài liệu và đường dẫn đến nơi bạn muốn lưu tệp đầu ra. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 Chúng tôi định nghĩa một biến`dataDir` , trỏ đến thư mục nơi tệp PDF kết quả sẽ được lưu.`Document` sau đó đối tượng được khởi tạo, tạo một tài liệu PDF mới để chỉnh sửa.

## Bước 2: Thêm một trang vào tài liệu của bạn

Tiếp theo, bạn sẽ muốn thêm một trang vào tài liệu mới tạo của mình.

```csharp
Page pdfPage = doc.Pages.Add();
```
Ở đây, chúng ta đang thêm một trang mới vào tài liệu của mình. Mỗi tệp PDF cần ít nhất một trang, vì vậy bước này rất cần thiết.

## Bước 3: Xác định hình chữ nhật vẽ

Trước khi vẽ bất cứ thứ gì, bạn cần xác định vị trí bạn sẽ đặt chú thích mực trên trang.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 Ở đây, chúng tôi tạo ra một`Rectangle` đối tượng chỉ định khu vực trên trang mà chúng ta sẽ thêm chú thích mực. Chúng ta đang thiết lập kích thước của nó để phù hợp với toàn bộ trang, bắt đầu từ (0,0).

## Bước 4: Chuẩn bị các điểm mực

Bây giờ đến phần thú vị: xác định các điểm tạo nên chú thích bằng mực của bạn. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
Khối mã này tạo ra một danh sách các mảng Point, trong đó mỗi mảng biểu diễn một tập hợp các điểm cho nét mực của bạn. Ở đây, chúng tôi định nghĩa ba điểm tạo thành một hình tam giác; bạn có thể điều chỉnh tọa độ cho phù hợp với thiết kế của mình.

## Bước 5: Tạo chú thích mực

Sau khi xác định các điểm, đã đến lúc tạo chú thích mực thực tế.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 Chúng tôi thực hiện`InkAnnotation`đối tượng, truyền vào trang, hình chữ nhật và các điểm mực. Ngoài ra, chúng tôi đang thiết lập một số thuộc tính như`Title`, `Color` , Và`CapStyle`. Tùy chỉnh những điều này để phù hợp với nhu cầu của bạn!

## Bước 6: Thiết lập đường viền và độ mờ

Bạn muốn chú thích của mình nổi bật? Hãy thêm chút phong cách cho nó.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
Ở đây, chúng ta sẽ thêm đường viền vào chú thích với chiều rộng cụ thể và thiết lập độ mờ của đường viền, làm cho đường viền trở nên trong suốt một phần.

## Bước 7: Thêm chú thích vào trang

Bây giờ chú thích của bạn đã được chuẩn bị xong, đã đến lúc thêm nó vào trang PDF.

```csharp
pdfPage.Annotations.Add(ia);
```
Dòng này thêm chú thích mực mà chúng ta đã tạo trước đó vào bộ sưu tập chú thích của trang. 

## Bước 8: Lưu tài liệu

Cuối cùng, hãy lưu tài liệu đã chỉnh sửa.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 Chúng tôi sửa đổi của chúng tôi`dataDir` để bao gồm tên tệp đầu ra và lưu tài liệu. Một thông báo xác nhận được in ra bảng điều khiển để cho bạn biết mọi thứ diễn ra suôn sẻ.

## Phần kết luận

Và thế là xong! Bạn đã thêm thành công chú thích mực vào tài liệu PDF của mình bằng Aspose.PDF cho .NET. Tính năng đơn giản nhưng hiệu quả này có thể cải thiện tài liệu của bạn và khiến chúng trở nên tương tác. Cho dù bạn đang thêm chữ ký, ghi chú hay hình vẽ nguệch ngoạc, chú thích mực cung cấp một cách độc đáo để làm phong phú nội dung.

## Câu hỏi thường gặp

### Aspose.PDF là gì?
Aspose.PDF là một thư viện dùng để tạo, chỉnh sửa và chuyển đổi tài liệu PDF trong các ứng dụng .NET.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
 Có! Aspose cung cấp phiên bản dùng thử miễn phí để đánh giá sản phẩm của họ. Bạn có thể tải xuống[đây](https://releases.aspose.com/).

### Có thể thêm nhiều chú thích bằng mực không?
 Chắc chắn rồi! Bạn có thể tạo nhiều`InkAnnotation` đối tượng và thêm chúng vào trang tài liệu của bạn.

### Tôi có thể tìm thêm ví dụ ở đâu?
 Bạn có thể kiểm tra[tài liệu](https://reference.aspose.com/pdf/net/) để biết hướng dẫn chi tiết và mẫu.

### Tôi phải làm gì nếu cần hỗ trợ?
 Nếu bạn gặp bất kỳ vấn đề nào, bạn có thể tìm kiếm sự trợ giúp trên[diễn đàn hỗ trợ](https://forum.aspose.com/c/pdf/10).