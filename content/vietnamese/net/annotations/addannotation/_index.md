---
title: Thêm chú thích PDF
linktitle: Thêm chú thích
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng thêm chú thích tùy chỉnh vào PDF của bạn bằng Aspose.PDF cho .NET với hướng dẫn từng bước này. Tùy chỉnh chú thích của bạn với các chi tiết và biểu tượng cụ thể.
type: docs
weight: 10
url: /vi/net/annotations/addannotation/
---
## Giới thiệu

Chú thích là một cách tuyệt vời để làm phong phú thêm tài liệu PDF, khiến chúng trở nên tương tác và nhiều thông tin. Cho dù bạn đang để lại ghi chú cho cộng tác viên hay thêm thông tin bổ sung cho người đọc, chú thích có thể là điều cần thiết. Trong hướng dẫn này, chúng tôi sẽ đi sâu vào quy trình thêm chú thích PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chia nhỏ từng bước để đến cuối hướng dẫn này, bạn sẽ trở thành chuyên gia nhúng chú thích vào tệp PDF của mình. Hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo rằng bạn có mọi thứ cần thiết:

-  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF. Bạn có thể tải xuống từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE C# nào khác mà bạn chọn.
- Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn đã thành thạo lập trình C#.
- Tài liệu PDF: Một tệp PDF mẫu mà bạn sẽ thêm chú thích vào.

 Nếu bạn chưa có thư viện Aspose.PDF, bạn có thể lấy nó từ liên kết ở trên và bắt đầu[dùng thử miễn phí](https://releases.aspose.com/) hoặc mua một[giấy phép](https://purchase.aspose.com/buy). 

## Nhập gói

Trước khi bắt đầu viết mã, hãy đảm bảo bạn đã nhập các không gian tên cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức bạn cần để thao tác và chú thích PDF.

## Bước 1: Tải tài liệu PDF của bạn

Trước tiên, bạn cần tải tài liệu PDF mà bạn định thêm chú thích.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DATA DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

 Đây là những gì đang xảy ra: bạn đang chỉ định thư mục nơi tệp PDF của bạn được lưu trữ, sau đó tải nó bằng cách sử dụng`Document` lớp do Aspose.PDF cung cấp. Bước này rất quan trọng vì nếu không tải tài liệu, bạn không thể thực hiện bất kỳ thay đổi nào đối với tài liệu đó.

## Bước 2: Tạo chú thích

### Xác định các thuộc tính chú thích
 Bây giờ, chúng ta hãy tạo chú thích đó. Chúng ta sẽ sử dụng`TextAnnotation`, rất phù hợp để thêm bình luận hoặc ghi chú vào tệp PDF của bạn.

```csharp
// Tạo chú thích
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Trong đoạn trích này:
-  Vị trí và kích thước:`Rectangle` lớp xác định vị trí chú thích của bạn sẽ xuất hiện trên trang và kích thước của nó.
- Tiêu đề, Chủ đề và Nội dung: Các thuộc tính này cho phép bạn chỉ định chú thích của mình nói về điều gì và chú thích sẽ chứa những gì.
-  Biểu tượng:`TextIcon.Key` đặt biểu tượng cho chú thích, làm cho chú thích hấp dẫn hơn về mặt trực quan.

## Bước 3: Tùy chỉnh giao diện của chú thích

Tiếp theo, hãy làm nổi bật chú thích này bằng cách thêm đường viền và thay đổi giao diện của nó.

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

Sau đây là thông tin chi tiết về những gì đang diễn ra:
-  Đường viền: Chúng tôi tạo ra một`Border` đối tượng và đặt chiều rộng của nó thành 5, giúp chú thích của chúng ta có một phác thảo nổi bật.
-  Mẫu gạch ngang:`Dash` Thuộc tính này cho phép bạn tạo đường viền đứt nét, thêm một chút phong cách cho chú thích.

## Bước 4: Thêm chú thích vào trang PDF

Sau khi tạo và tùy chỉnh chú thích, đã đến lúc thêm chú thích vào trang PDF của bạn.

```csharp
// Thêm chú thích vào bộ sưu tập chú thích của trang
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

 Mã này thêm chú thích vào trang đầu tiên của tệp PDF của bạn.`Annotations` bộ sưu tập chứa tất cả chú thích cho một trang cụ thể và bước này đảm bảo chú thích mới của bạn là một phần của bộ sưu tập đó.

## Bước 5: Lưu tài liệu PDF đã cập nhật

Cuối cùng, hãy lưu tài liệu để chú thích của bạn được thêm vĩnh viễn.

```csharp
// Lưu tập tin đầu ra
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nAnnotation added successfully.\nFile saved at " + dataDir);
```

Bằng cách lưu tài liệu với tên mới (`AddAnnotation_out.pdf`), bạn giữ nguyên tệp gốc và tạo tệp mới có chú thích được thêm vào. Thông báo trên bảng điều khiển xác nhận mọi thứ đã thành công và giờ bạn có thể tìm thấy tệp PDF có chú thích của mình trong thư mục đã chỉ định.

## Phần kết luận

Thêm chú thích vào PDF không chỉ là một tính năng mạnh mẽ; mà còn cực kỳ đơn giản với Aspose.PDF for .NET. Cho dù bạn đang đánh dấu một tài liệu để xem lại hay thêm ghi chú để tham khảo trong tương lai, hướng dẫn này đã đề cập đến mọi thứ bạn cần biết. Bằng cách làm theo các bước này, bạn có thể tạo chú thích tùy chỉnh làm phong phú thêm PDF của mình, giúp chúng hữu ích và tương tác hơn.

## Câu hỏi thường gặp

### Tôi có thể thêm những loại chú thích nào khi sử dụng Aspose.PDF cho .NET?
Bạn có thể thêm nhiều loại chú thích khác nhau, bao gồm chú thích văn bản, liên kết, đánh dấu và đóng dấu, cùng nhiều loại chú thích khác.

### Tôi có thể tùy chỉnh giao diện của chú thích không?
Chắc chắn rồi! Bạn có thể tùy chỉnh kích thước, màu sắc, đường viền và thậm chí cả biểu tượng của chú thích.

### Có thể thêm nhiều chú thích vào một trang không?
Có, bạn có thể thêm bao nhiêu chú thích tùy thích vào bất kỳ trang nào trong tệp PDF của mình.

### Tôi có thể xóa chú thích sau khi đã thêm chúng không?
 Có, chú thích có thể được xóa bằng cách sử dụng`Annotations.Delete` phương pháp được cung cấp bởi Aspose.PDF.

### Tôi có cần giấy phép để sử dụng Aspose.PDF cho .NET không?
 Có, để mở khóa tất cả các tính năng và tránh mọi hạn chế, bạn sẽ cần một[giấy phép](https://purchase.aspose.com/buy) . Bạn cũng có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.