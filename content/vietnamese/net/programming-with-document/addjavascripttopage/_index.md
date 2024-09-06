---
title: Thêm Java Script vào tệp PDF
linktitle: Thêm tệp PDF Java Script
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm JavaScript vào tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với hướng dẫn mã cho tập lệnh cấp tài liệu và trang.
type: docs
weight: 10
url: /vi/net/programming-with-document/addjavascripttopage/
---
## Giới thiệu

Bạn đã bao giờ tự hỏi làm thế nào để cải thiện PDF của mình bằng các thành phần tương tác như cảnh báo bật lên hoặc chức năng tự động in chưa? Vâng, tin tốt là bạn có thể! Bằng cách sử dụng Aspose.PDF cho .NET, bạn có thể dễ dàng thêm JavaScript vào tài liệu PDF của mình. Cho dù bạn đang tự động hóa các tác vụ hay tạo trải nghiệm người dùng động, việc nhúng JavaScript vào PDF sẽ cung cấp cho các tệp của bạn mức chức năng bổ sung đó.

## Điều kiện tiên quyết

Trước khi bắt đầu phần mã hóa, bạn cần thiết lập một số thứ sau:

-  Aspose.PDF cho .NET: Tải xuống thư viện từ[Aspose phát hành](https://releases.aspose.com/pdf/net/) hoặc nhận được một[dùng thử miễn phí](https://releases.aspose.com/).
- Môi trường phát triển: Bất kỳ IDE nào tương thích với .NET như Visual Studio.
- Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn đã quen thuộc với cú pháp C# cơ bản.
-  Giấy phép tạm thời (Tùy chọn): Bạn có thể nhận được[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) nếu bạn muốn tránh những hạn chế trong quá trình phát triển của mình.

## Nhập gói

Trước khi bắt đầu viết mã, bạn sẽ cần nhập các không gian tên cần thiết từ thư viện Aspose.PDF. Các không gian tên này sẽ cho phép bạn thao tác PDF và thêm các hành động JavaScript dễ dàng.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Bây giờ bạn đã nhập đúng không gian tên, bạn đã sẵn sàng để bắt đầu viết mã.

## Bước 1: Tải PDF hiện có

Trước tiên, bạn cần tải tài liệu PDF mà bạn muốn thêm JavaScript. Bước này thiết lập bối cảnh cho tất cả các sửa đổi tiếp theo. Hãy tưởng tượng bạn có một tệp PDF mà bạn muốn cải thiện bằng chức năng động, chẳng hạn như tự động in tài liệu khi mở.

Sau đây là cách bạn có thể tải tệp PDF đó:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải một tập tin PDF hiện có
Document doc = new Document(dataDir + "input.pdf");
```

 Trong đoạn mã này, chúng tôi đang sử dụng`Document` lớp để tải tệp PDF hiện có từ thư mục đã chỉ định. Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tệp PDF của bạn.

## Bước 2: Thêm JavaScript ở cấp độ tài liệu

Bây giờ, hãy thêm một số JavaScript sẽ kích hoạt khi tài liệu mở ra. Trong ví dụ này, chúng ta sẽ viết một tập lệnh mở hộp thoại in ngay khi người dùng mở PDF.

JavaScript cấp tài liệu hoàn hảo cho các hành động mà bạn muốn áp dụng cho toàn bộ PDF. Hãy nghĩ về nó như việc thiết lập một quy tắc chung cho tài liệu của bạn.

Đây là mã:

```csharp
// Thêm JavaScript ở cấp độ tài liệu
// Khởi tạo JavascriptAction với câu lệnh JavaScript mong muốn
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Gán đối tượng JavascriptAction cho OpenAction của Tài liệu
doc.OpenAction = javaScript;
```

 Trong bước này, chúng ta tạo ra một`JavascriptAction` đối tượng định nghĩa hàm JavaScript để mở hộp thoại in khi tài liệu được mở.`doc.OpenAction` sau đó thuộc tính này được gán cho hành động JavaScript này.

## Bước 3: Thêm JavaScript ở cấp độ trang

Không phải mọi hành động đều cần ảnh hưởng đến toàn bộ tài liệu. Đôi khi, bạn muốn các hành động cụ thể xảy ra khi một số trang nhất định được mở hoặc đóng. Ở đây, chúng tôi sẽ thiết lập các hành động JavaScript cho thời điểm một trang cụ thể (giả sử là trang 2) được mở và đóng.

JavaScript cấp trang hữu ích cho các tương tác có mục tiêu. Nó có thể là bất cứ thứ gì từ việc hiển thị thông báo khi người dùng điều hướng đến một trang, đến các hành động tùy chỉnh như tự động điền vào các trường biểu mẫu.

Sau đây là cách thực hiện:

```csharp
// Thêm JavaScript ở cấp độ trang
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

Trong đoạn mã này, chúng tôi thêm hai hành động JavaScript:
1. Hành động OnOpen: Hiển thị cảnh báo “Đã mở trang 2” khi người dùng mở trang 2.
2. Hành động OnClose: Hiển thị cảnh báo “Đã đóng trang 2” khi người dùng thoát khỏi trang 2.

Điều này thêm một lớp tương tác vào PDF của bạn. Hãy tưởng tượng hướng dẫn người dùng thực hiện một loạt các bước trên các trang khác nhau, với các cảnh báo bật lên khi họ vào hoặc rời khỏi một trang.

## Bước 4: Lưu tài liệu PDF

Bây giờ bạn đã thêm JavaScript vào cả tài liệu và các trang cụ thể. Bước cuối cùng là lưu PDF đã sửa đổi vào vị trí mong muốn của bạn. Phần này đơn giản nhưng rất quan trọng—đừng quên lưu công việc của bạn!

Đây là mã:

```csharp
// Chỉ định đường dẫn tệp đầu ra
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Lưu tài liệu PDF đã cập nhật
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 Trong đoạn mã này, chúng tôi lưu tài liệu đã cập nhật với JavaScript đã thêm vào một tệp mới có tên`"JavaScript-Added_out.pdf"`. Điều này đảm bảo bạn không ghi đè lên tệp gốc và cung cấp cho bạn bản sao lưu để làm việc.

## Phần kết luận

Thêm JavaScript vào tệp PDF bằng Aspose.PDF cho .NET là một cách mạnh mẽ để tạo PDF tương tác, động. Cho dù bạn đang tự động hóa các tác vụ như in ấn hay tạo cảnh báo tùy chỉnh, khả năng nhúng JavaScript vào PDF của bạn sẽ giúp tài liệu của bạn hấp dẫn và hữu ích hơn.

## Câu hỏi thường gặp

### Tôi có thể thêm nhiều hành động JavaScript vào các trang khác nhau trong một tệp PDF không?
Có, bạn có thể chỉ định các hành động JavaScript khác nhau cho từng trang hoặc toàn bộ tài liệu.

### Có thể xóa JavaScript khỏi PDF sau khi đã thêm vào không?
Có, bạn có thể xóa hoặc sửa đổi các hành động JavaScript hiện có bằng cách xóa`Actions` thuộc tính của tài liệu hoặc trang.

### Tôi có thể sử dụng loại hàm JavaScript nào trong PDF?
Bạn có thể sử dụng bất kỳ JavaScript nào được công cụ JavaScript của Adobe Acrobat hỗ trợ, chẳng hạn như in, cảnh báo và thao tác biểu mẫu.

### JavaScript có hoạt động trên tất cả các trình xem PDF không?
Hầu hết các hành động JavaScript sẽ hoạt động trong trình xem PDF hỗ trợ PDF tương tác, như Adobe Acrobat. Tuy nhiên, một số trình đọc PDF cơ bản có thể không hỗ trợ JavaScript.

### Tôi có thể kích hoạt các hành động JavaScript dựa trên thông tin người dùng nhập vào tệp PDF không?
Có, bạn có thể liên kết JavaScript với các trường biểu mẫu để kích hoạt các hành động dựa trên dữ liệu nhập của người dùng.