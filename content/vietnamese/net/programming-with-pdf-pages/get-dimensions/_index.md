---
title: Nhận Kích thước Trang PDF
linktitle: Nhận Kích thước Trang PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Trong hướng dẫn này, chúng tôi giải thích cách lấy kích thước trang PDF và thực hiện thao tác bằng Aspose.PDF cho .NET. Các bước chi tiết được cung cấp để hướng dẫn bạn thực hiện quy trình.
type: docs
weight: 60
url: /vi/net/programming-with-pdf-pages/get-dimensions/
---
## Giới thiệu

Bạn đã bao giờ cần thao tác kích thước trang của một tài liệu PDF chưa? Có thể bạn muốn thay đổi kích thước trang hoặc xoay trang để phù hợp với nhu cầu của mình? Nếu vậy, bạn đã đến đúng nơi rồi! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách lấy và sửa đổi kích thước trang PDF bằng Aspose.PDF cho .NET. Cho dù bạn là người mới bắt đầu hay là nhà phát triển dày dạn kinh nghiệm, bạn sẽ thấy hướng dẫn này đơn giản và dễ làm theo.

Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi các tệp PDF một cách dễ dàng. Giống như có một con dao quân đội Thụy Sĩ cho PDF – bạn có thể điều chỉnh mọi chi tiết nhỏ để phù hợp với yêu cầu chính xác của mình. Vì vậy, hãy cùng tìm hiểu cách lấy và cập nhật kích thước trang PDF bằng công cụ tuyệt vời này!

## Điều kiện tiên quyết

Trước khi bắt đầu, bạn cần chuẩn bị một số thứ để thực hiện hướng dẫn này một cách suôn sẻ:

1.  Aspose.PDF cho .NET: Bạn có thể[tải phiên bản mới nhất tại đây](https://releases.aspose.com/pdf/net/) . Nếu bạn không có giấy phép, đừng lo lắng! Bạn có thể yêu cầu[dùng thử miễn phí](https://releases.aspose.com/) , hoặc lựa chọn một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: Môi trường phát triển bạn sẽ sử dụng để viết và thực thi mã.
3. Kiến thức cơ bản về C#: Mặc dù chúng tôi sẽ đơn giản hóa mọi thứ, nhưng một chút quen thuộc với C# sẽ giúp quá trình này trở nên dễ dàng hơn.
4. Tệp PDF để làm việc: Lấy bất kỳ tệp PDF mẫu nào hoặc tạo một tệp PDF mới để kiểm tra.

## Nhập gói

Để làm việc với Aspose.PDF cho .NET, bạn cần nhập một số không gian tên thiết yếu. Điều này thiết lập giai đoạn tương tác với các tài liệu PDF. Sau đây là cách thực hiện:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Các lần nhập này đảm bảo rằng bạn có quyền truy cập vào các lớp cốt lõi cần thiết để thao tác với các tệp PDF, đặc biệt là để quản lý các trang và lấy kích thước của chúng.

Bây giờ chúng ta đã có mọi thứ, hãy chia nhỏ quy trình thành các bước dễ thực hiện.

## Bước 1: Xác định Đường dẫn Tệp và Tải Tài liệu

Bước đầu tiên là chỉ định đường dẫn đến tài liệu PDF của bạn và tải nó bằng Aspose.PDF. Điều này sẽ cho phép bạn tương tác với các trang trong tệp PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

Ở bước này, về cơ bản bạn đang mở tệp PDF mà bạn muốn làm việc. Nếu bạn đã từng mở một cuốn sách đến một trang cụ thể, thì điều này khá giống nhau – nhưng thay vào đó, bạn đang mở một tài liệu PDF để truy cập các trang của nó.

## Bước 2: Thêm một trang trống nếu không có trang nào tồn tại

Nếu tài liệu của bạn không có trang thì sao? Đừng lo! Chúng tôi có thể thêm một trang trống vào tài liệu và làm việc với trang đó. Sau đây là cách kiểm tra xem một trang có tồn tại hay không và thêm một trang mới nếu cần:

```csharp
// Thêm một trang trống vào tài liệu pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Dòng mã này kiểm tra xem đã có trang nào trong tài liệu chưa. Nếu có, nó sẽ chọn trang đầu tiên (`Pages[1]`). Nếu không, nó sẽ tạo một trang trống và thêm vào PDF.

Hãy nghĩ đến việc mở một cuốn sổ tay trống và viết lên trang đầu tiên nếu không có gì ở đó – dễ phải không?

## Bước 3: Lấy thông tin về chiều cao và chiều rộng của trang

 Bây giờ chúng ta đã có một trang để làm việc, hãy lấy kích thước của trang. Chúng ta sẽ sử dụng`GetPageRect()` phương pháp để lấy chiều cao và chiều rộng.

```csharp
// Nhận thông tin chiều cao và chiều rộng của trang
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Đây,`GetPageRect(true)` trả về một hình chữ nhật bao gồm chiều cao và chiều rộng của trang. Giống như việc đo một tờ giấy bằng thước kẻ. Đầu ra sẽ được hiển thị trong bảng điều khiển, cung cấp cho bạn kích thước trang hiện tại.

## Bước 4: Xoay trang 90 độ

Bạn có muốn xoay trang không? Không vấn đề gì! Với một thuộc tính đơn giản, bạn có thể xoay trang 90 độ.

```csharp
// Xoay trang ở góc 90 độ
page.Rotate = Rotation.on90;
```

Bước này xoay trang theo chiều kim đồng hồ 90 độ. Hãy tưởng tượng bạn đang xoay một tờ giấy đã in trên bàn làm việc của mình – giờ thì nó ở chế độ ngang!

## Bước 5: Kiểm tra lại Kích thước trang sau khi xoay

Sau khi xoay trang, bạn nên kiểm tra lại kích thước. Tại sao? Bởi vì việc xoay có thể ảnh hưởng đến cách bạn diễn giải chiều cao và chiều rộng.

```csharp
// Nhận thông tin chiều cao và chiều rộng của trang
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Bây giờ, kích thước trang sẽ được cập nhật dựa trên hướng mới. Giống như xoay ảnh trên điện thoại của bạn – đột nhiên, chiều rộng trở thành chiều cao và ngược lại.


## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách lấy và sửa đổi kích thước của trang PDF bằng Aspose.PDF cho .NET. Bây giờ, bạn có thể tải PDF, kiểm tra kích thước trang và thậm chí xoay trang nếu cần.

Việc xử lý PDF không nhất thiết phải phức tạp. Với Aspose.PDF, chỉ cần làm theo một vài bước và sử dụng các phương pháp trực quan là đủ. Vì vậy, lần tới khi bạn cần xử lý kích thước trang PDF, bạn sẽ biết chính xác phải làm gì!

## Câu hỏi thường gặp

### Tôi có thể xoay trang theo góc khác ngoài góc 90 độ không?
 Có, Aspose.PDF cho phép bạn xoay các trang theo góc 0, 90, 180 hoặc 270 độ bằng cách sử dụng`Rotation` tài sản.

### Điều gì xảy ra nếu tệp PDF của tôi không có trang?
 Nếu tệp PDF của bạn không có trang nào, bạn có thể thêm một trang trống bằng cách sử dụng`Pages.Add()` phương pháp như được trình bày trong hướng dẫn này.

### Tôi có thể thao tác nhiều trang cùng lúc không?
Có, bạn có thể lặp qua nhiều trang và áp dụng các phép biến đổi, như thay đổi kích thước hoặc xoay, cho tất cả các trang đó.

### Kích thước trang có ảnh hưởng tới nội dung bên trong tệp PDF không?
Kích thước trang chỉ thay đổi kích thước của canvas, không phải nội dung. Tuy nhiên, việc thay đổi kích thước có thể thay đổi cách nội dung hiển thị trên trang.

### Tôi có thể tìm thêm thông tin về Aspose.PDF cho .NET ở đâu?
 Bạn có thể ghé thăm[tài liệu ở đây](https://reference.aspose.com/pdf/net/) để biết thông tin chi tiết hơn và các trường hợp sử dụng nâng cao.