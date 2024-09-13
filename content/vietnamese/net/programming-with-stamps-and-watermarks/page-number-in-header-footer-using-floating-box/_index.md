---
title: Số trang trong Header Footer sử dụng hộp nổi
linktitle: Số trang trong Header Footer sử dụng hộp nổi
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng thêm số trang vào phần đầu trang và chân trang PDF bằng Floating Box với Aspose.PDF cho .NET trong hướng dẫn từng bước này.
type: docs
weight: 150
url: /vi/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Giới thiệu

Khi nói đến việc quản lý tài liệu PDF theo chương trình, Aspose.PDF cho .NET nổi bật như một công cụ đặc biệt. Nó đơn giản hóa cách chúng ta tạo, chỉnh sửa và thao tác các tệp PDF trong các ứng dụng .NET. Cho dù bạn đang tạo hóa đơn, báo cáo hay bất kỳ loại tài liệu nào, việc thêm số trang một cách tinh tế có thể cải thiện tính chuyên nghiệp và tổ chức của các tệp PDF của bạn. Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm số trang vào đầu trang và chân trang của tệp PDF của bạn bằng cách sử dụng Floating Box. Sẵn sàng bắt đầu chưa? Bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi bắt đầu hành trình thú vị vào lĩnh vực chỉnh sửa PDF, bạn cần có một số thứ sau:

### Thiết lập môi trường .NET
Đảm bảo bạn có môi trường phát triển .NET. Bạn có thể sử dụng Visual Studio, đây là lựa chọn phổ biến trong số các nhà phát triển cho các ứng dụng .NET.

### Thư viện Aspose.PDF
Cài đặt thư viện Aspose.PDF. Bạn có thể dễ dàng tải xuống từ trang web:

- [Tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/)

### Kiến thức cơ bản về lập trình C#
Hiểu biết cơ bản về C# sẽ giúp bạn nắm bắt các khái niệm và đoạn mã được trình bày trong hướng dẫn này.

### Truy cập vào Tài liệu
 Luôn luôn có lợi khi có[Tài liệu Aspose.PDF](https://reference.aspose.com/pdf/net/) hữu ích cho việc tham khảo và khám phá sâu hơn bất kỳ chức năng bổ sung nào.

## Nhập gói

Để bắt đầu, bạn sẽ cần nhập các gói cần thiết vào dự án của mình. Điều này đảm bảo rằng Aspose.PDF có thể truy cập được để sử dụng trong mã của bạn. Sau đây là cách thực hiện:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bây giờ, chúng ta hãy chia nhỏ quy trình thêm số trang bằng Floating Box thành các bước dễ quản lý. Hãy theo dõi khi chúng tôi hướng dẫn.

## Bước 1: Thiết lập môi trường tài liệu của bạn

Hãy bắt đầu bằng cách chỉ định thư mục nơi tài liệu PDF của bạn sẽ được lưu trữ. Điều này rất quan trọng vì nó quyết định nơi tệp đầu ra của bạn được lưu.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`YOUR DOCUMENT DIRECTORY` bằng đường dẫn bạn chọn nơi bạn muốn lưu tệp PDF đầu ra.

## Bước 2: Khởi tạo tài liệu

 Tạo một tài liệu PDF mới là bước tiếp theo. Điều này liên quan đến việc sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
// Khởi tạo phiên bản Tài liệu
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Ở đây, chúng ta tạo một phiên bản mới của`Document` lớp, đóng vai trò là nền tảng để chúng ta thao tác.

## Bước 3: Thêm trang mới

Bây giờ, hãy thêm một trang vào tài liệu PDF của chúng ta. Mỗi PDF cần ít nhất một trang, đúng không?

```csharp
// Thêm một trang vào tài liệu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Đoạn mã này thêm một trang mới vào tài liệu của chúng ta, giúp tài liệu sẵn sàng nhận nội dung, bao gồm cả hộp nổi có số trang.

## Bước 4: Tạo một hộp nổi

 Tiếp theo, đã đến lúc tạo Hộp nổi của chúng ta để chứa số trang.`FloatingBox`Lớp này cho phép chúng ta định vị nội dung một cách tự do trên trang.

```csharp
// Khởi tạo một thể hiện mới của lớp FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Ở đây, các tham số`(140, 80)` chỉ định chiều rộng và chiều cao của Floating Box. Bạn có thể điều chỉnh các giá trị này dựa trên sở thích bố cục của bạn.

## Bước 5: Định vị hộp nổi

 Vị trí là chìa khóa! Bạn muốn xác định vị trí số trang sẽ xuất hiện trên trang. Bạn sẽ làm việc với`Left` Và`Top` thuộc tính để chỉ định vị trí.

```csharp
// Giá trị float chỉ ra vị trí bên trái của đoạn văn
box1.Left = 2;
// Giá trị float chỉ ra vị trí trên cùng của đoạn văn
box1.Top = 10;
```
Các giá trị này quyết định vị trí của Floating Box trên trang. Hãy thoải mái thử nghiệm chúng để xem cái nào trông đẹp nhất cho tài liệu của bạn.

## Bước 6: Thêm văn bản bằng Macro số trang

Bây giờ, chúng ta sẽ thêm một chuỗi hiển thị động số trang. Đây chính là nơi phép thuật xảy ra!

```csharp
// Thêm các macro vào bộ sưu tập đoạn văn của FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 Trong trường hợp này,`($p/ $P)`là một macro sẽ hiển thị số trang hiện tại (`$p`) và tổng số trang (`$P`). Kết quả là, nó định dạng văn bản để đọc giống như "Trang: 1/5".

## Bước 7: Thêm hộp nổi vào trang

Đã đến lúc thêm Hộp nổi cùng với văn bản số trang vào trang mới tạo của chúng ta.

```csharp
// Thêm một floatingBox vào trang
page.Paragraphs.Add(box1);
```
Dòng này về cơ bản nhúng Hộp nổi của bạn vào trang, biến nó thành một phần trong bố cục của tài liệu. 

## Bước 8: Lưu tài liệu của bạn

Cuối cùng, đừng quên lưu công việc của bạn! Bước cuối cùng là lưu tài liệu PDF của bạn với tên tệp phù hợp.

```csharp
// Lưu tài liệu
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Đảm bảo đường dẫn được chỉ định bao gồm tên tệp mong muốn của bạn. Bây giờ, tệp PDF tuyệt vời của bạn với số trang đã được tạo! 

## Phần kết luận

Và thế là xong, các bạn ạ! Thêm số trang vào phần đầu trang và phần chân trang của tệp PDF bằng Aspose.PDF cho .NET chỉ đơn giản như vậy thôi. Chỉ với một vài dòng mã, bạn đã bắt đầu hành trình làm chủ việc xử lý tài liệu trong các ứng dụng của mình. Đừng ngần ngại thử nghiệm với các bố cục và định dạng khác nhau—suy cho cùng, sự sáng tạo là vô hạn! Bạn đã sẵn sàng tạo tài liệu chuyên nghiệp chưa? Hãy đội mũ lập trình và bắt đầu thử nghiệm.

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh giao diện của số trang không?  
 Có, bạn có thể tùy chỉnh các thuộc tính văn bản, chẳng hạn như kích thước phông chữ, màu sắc và kiểu chữ bằng cách điều chỉnh`TextFragment` của cải.

### Aspose.PDF có miễn phí sử dụng không?  
 Trong khi Aspose.PDF cung cấp bản dùng thử miễn phí, thì đây là sản phẩm trả phí để sử dụng cho mục đích sản xuất. Bạn có thể[mua nó ở đây](https://purchase.aspose.com/buy).

### Tôi có thể tìm tài liệu chi tiết hơn ở đâu?  
 Bạn có thể tìm thấy tài liệu toàn diện về[Trang web tài liệu Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Làm thế nào để áp dụng tiêu đề và chân trang cho nhiều trang?  
Bạn có thể lặp qua tất cả các trang trong tài liệu của mình và áp dụng Hộp nổi cho từng trang theo cách tương tự.

### Tôi phải làm sao nếu cần hỗ trợ thêm các tính năng khác?  
Đối với bất kỳ câu hỏi hoặc hỗ trợ bổ sung nào, bạn có thể truy cập[Diễn đàn Aspose](https://forum.aspose.com/c/pdf/10).