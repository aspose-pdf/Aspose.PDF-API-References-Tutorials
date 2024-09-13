---
title: Hình ảnh và Số trang trong Phần Đầu trang Chân trang Nội tuyến
linktitle: Hình ảnh và Số trang trong Phần Đầu trang Chân trang Nội tuyến
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm hình ảnh và số trang trực tiếp vào phần tiêu đề của tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 120
url: /vi/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Giới thiệu

Aspose.PDF for .NET là một công cụ mạnh mẽ cung cấp các khả năng mở rộng để thao tác và tạo tệp PDF. Cho dù bạn cần thêm hình ảnh, tùy chỉnh tiêu đề và chân trang hay quản lý văn bản, Aspose.PDF đều có thể đáp ứng nhu cầu của bạn. Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm hình ảnh và số trang trực tuyến vào tiêu đề hoặc chân trang của tài liệu PDF. Hãy cùng tìm hiểu và phân tích từng bước trong quy trình này.

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn đã chuẩn bị mọi thứ để làm theo:

-  Aspose.PDF cho .NET: Tải xuống phiên bản mới nhất từ[Trang Tải Xuống PDF Aspose](https://releases.aspose.com/pdf/net/).
- Môi trường phát triển: Bạn sẽ cần một IDE C# như Visual Studio.
-  Giấy phép: Nếu bạn chưa có giấy phép, bạn có thể xin[giấy phép tạm thời ở đây](https://purchase.aspose.com/temporary-license/) hoặc mua một cái đầy đủ từ[Cửa hàng Aspose](https://purchase.aspose.com/buy).

Bây giờ bạn đã chuẩn bị đủ các điều kiện tiên quyết, chúng ta hãy bắt đầu nhé.

## Nhập gói

Trước khi bắt đầu viết mã, hãy đảm bảo nhập các không gian tên cần thiết:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Các gói này cho phép bạn làm việc với các tệp PDF và chỉnh sửa văn bản.

## Bước 1: Thiết lập thư mục tài liệu

Điều đầu tiên chúng ta cần làm là xác định đường dẫn đến thư mục nơi tệp PDF của chúng ta sẽ được lưu. Đường dẫn này có thể được tùy chỉnh theo thư mục dự án của bạn hoặc bất kỳ vị trí nào trên máy của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Biến này giữ vị trí nơi tài liệu của bạn sẽ được lưu trữ. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế.

## Bước 2: Khởi tạo tài liệu PDF

 Trong bước này, chúng ta tạo một phiên bản mới của`Aspose.Pdf.Document` đối tượng. Đối tượng này sẽ đóng vai trò là xương sống của tệp PDF của bạn.

```csharp
// Khởi tạo một đối tượng Document bằng cách gọi hàm tạo rỗng của nó
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Ở đây, chúng ta sẽ tạo một tệp PDF trống để có thể điền nội dung vào sau.

## Bước 3: Thêm một trang vào PDF

Tệp PDF của bạn cần ít nhất một trang để bạn có thể thêm tiêu đề, chân trang và nội dung. Hãy thêm một trang trống vào tài liệu của chúng ta.

```csharp
// Tạo một trang trong đối tượng Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Bằng cách gọi`pdf1.Pages.Add()`một trang mới sẽ được thêm vào tài liệu, sẵn sàng để tùy chỉnh đầu trang và chân trang.

## Bước 4: Tạo và thiết lập Header

Bây giờ là lúc tạo tiêu đề cho tài liệu. Đây là nơi chúng ta sẽ thêm văn bản, hình ảnh và số trang.

```csharp
// Tạo phần Tiêu đề của tài liệu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Đặt tiêu đề cho tệp PDF
page.Header = header;
```

 Chúng tôi tạo ra một`HeaderFooter` đối tượng và gán nó cho`Header` thuộc tính của trang, đảm bảo rằng bất cứ thứ gì chúng ta thêm vào tiêu đề sẽ xuất hiện ở đầu trang.

## Bước 5: Thêm văn bản nội tuyến vào tiêu đề

 Thêm văn bản cũng đơn giản như việc tạo một`TextFragment` và chỉ định các thuộc tính của nó. Hãy thêm một số văn bản có màu vào tiêu đề của chúng ta.

```csharp
// Tạo một đối tượng Văn bản
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Chỉ định màu sắc
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 Trong bước này, chúng ta tạo ra một`TextFragment` với nội dung "Aspose.Pdf là một thành phần mạnh mẽ của" và đặt màu của nó thành màu xanh lam.`IsInLineParagraph` thuộc tính này đảm bảo rằng văn bản nằm trong dòng, nghĩa là nó sẽ xuất hiện trên cùng một dòng với các phần tử khác (như hình ảnh và văn bản bổ sung).

## Bước 6: Chèn một hình ảnh nội tuyến vào tiêu đề

Để làm cho tiêu đề của bạn hấp dẫn về mặt thị giác, bạn có thể thêm hình ảnh vào dòng văn bản. Đây có thể là logo công ty của bạn hoặc bất kỳ đồ họa nào khác.

```csharp
// Tạo một đối tượng hình ảnh trong phần
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Thiết lập đường dẫn của tập tin hình ảnh
image1.File = dataDir + "aspose-logo.jpg";
// Thiết lập chiều rộng hình ảnh Thông tin
image1.FixWidth = 50;
image1.FixHeight = 20;
// Chỉ ra InlineParagraph của seg1 là một hình ảnh.
image1.IsInLineParagraph = true;
```

 Ở đây, chúng ta thêm một hình ảnh vào tiêu đề bằng cách tạo một`Image` đối tượng, thiết lập đường dẫn của nó và điều chỉnh chiều rộng và chiều cao.`IsInLineParagraph` đảm bảo hình ảnh được căn chỉnh với văn bản.

## Bước 7: Thêm văn bản nội tuyến bổ sung để hoàn thiện tiêu đề

Hãy thêm một số văn bản để hoàn thiện tiêu đề nội tuyến.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 Trong phần này, chúng ta tạo ra một phần khác`TextFragment` với nội dung "Pty Ltd." và đặt màu thành màu hạt dẻ. Cả đoạn văn bản và hình ảnh đều được thêm vào tiêu đề.

## Bước 8: Lưu PDF

Sau khi thiết lập tiêu đề, đã đến lúc lưu tệp PDF.

```csharp
// Lưu tệp PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 Các`Save` phương pháp này ghi tệp PDF cuối cùng vào vị trí đã chỉ định.

## Phần kết luận

Xin chúc mừng! Bạn đã thêm thành công hình ảnh và văn bản vào tiêu đề của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này hướng dẫn bạn các bước cần thiết, bao gồm tạo tài liệu, thêm trang, chèn tiêu đề và đặt nội dung nội tuyến như văn bản và hình ảnh. Aspose.PDF cung cấp cho bạn sự linh hoạt đáng kinh ngạc để quản lý PDF của mình, cho dù đó là thao tác tiêu đề, chân trang hay nội dung phức tạp. 

## Câu hỏi thường gặp

### Tôi có thể thêm số trang vào tiêu đề không?
 Có! Bạn có thể dễ dàng thêm số trang bằng cách sử dụng`TextFragment` lớp và định dạng theo nhu cầu. Chỉ cần chèn nó vào phần tiêu đề dưới dạng nội dung nội tuyến.

### Làm thế nào để đặt hình nền ở phần đầu trang?
 Bạn có thể sử dụng`BackgroundImage` tài sản của`HeaderFooter` lớp để đặt hình nền. Tuy nhiên, đây không phải là nội dung nội tuyến và nó sẽ bao phủ toàn bộ vùng tiêu đề.

### Có thể sử dụng định dạng hình ảnh nào khác ngoài JPEG không?
Hoàn toàn có thể! Aspose.PDF hỗ trợ nhiều định dạng hình ảnh như PNG, BMP và GIF.

### Tôi có thể tùy chỉnh phông chữ của văn bản ở tiêu đề không?
 Có, bạn có thể sử dụng`TextState`đối tượng để thay đổi phông chữ, kích thước và kiểu của văn bản.

### Tôi có cần giấy phép để sử dụng Aspose.PDF cho .NET không?
 Có, Aspose.PDF yêu cầu giấy phép để sử dụng sản xuất, nhưng bạn có thể bắt đầu bằng[dùng thử miễn phí tại đây](https://releases.aspose.com/).