---
title: Đặt ngày hết hạn trong tệp PDF
linktitle: Đặt ngày hết hạn trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách đặt ngày hết hạn trong tệp PDF bằng Aspose.PDF cho .NET. Tăng cường bảo mật tài liệu với hướng dẫn từng bước này.
type: docs
weight: 300
url: /vi/net/programming-with-document/setexpirydate/
---
## Giới thiệu

Trong thời đại kỹ thuật số ngày nay, việc quản lý và bảo mật tài liệu trở nên quan trọng hơn bao giờ hết. Hãy tưởng tượng việc gửi một tệp PDF tự động trở nên không thể truy cập sau một ngày nhất định. Nghe có vẻ kỳ diệu phải không? Vâng, với Aspose.PDF cho .NET, bạn có thể dễ dàng đặt ngày hết hạn cho các tệp PDF của mình. Tính năng này đặc biệt hữu ích đối với các tài liệu nhạy cảm cần được hạn chế sau một khoảng thời gian nhất định. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước trong quy trình đặt ngày hết hạn trong tệp PDF. Vì vậy, hãy đội mũ lập trình của bạn và bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi bắt đầu, bạn cần chuẩn bị một số thứ sau:

1. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET. Có thể là Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ .NET.
2.  Aspose.PDF cho .NET: Bạn cần cài đặt thư viện Aspose.PDF. Nếu bạn chưa thực hiện việc này, bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình C#. Nếu bạn mới làm quen với C#, đừng lo lắng! Chúng tôi sẽ hướng dẫn bạn một cách đơn giản và dễ hiểu.

## Nhập gói

Để bắt đầu với Aspose.PDF, bạn cần nhập các không gian tên cần thiết vào dự án C# của mình. Đây là cách bạn có thể thực hiện:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Các không gian tên này cung cấp cho bạn quyền truy cập vào các chức năng cốt lõi cần thiết để làm việc với tài liệu PDF trong Aspose.PDF.

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, bạn cần chỉ định đường dẫn đến thư mục tài liệu của mình. Đây là nơi tệp PDF đầu ra của bạn sẽ được lưu. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế mà bạn muốn lưu tệp PDF của mình. Giống như nói với chương trình của bạn, "Này, đây là nơi tôi lưu trữ các tệp của mình!"

## Bước 2: Khởi tạo đối tượng tài liệu

 Tiếp theo, bạn cần tạo một phiên bản mới của`Document` lớp. Đây là nơi bạn sẽ tạo tệp PDF của mình.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Nghĩ về`Document` đối tượng như một tờ giấy trắng. Bạn có thể thêm nội dung vào đó theo ý thích!

## Bước 3: Thêm một trang vào PDF

Bây giờ bạn đã thiết lập xong tài liệu, đã đến lúc thêm trang vào đó. Đây là nơi nội dung của bạn sẽ xuất hiện.

```csharp
doc.Pages.Add();
```

Bạn vừa tạo một trang mới trong PDF của mình. Giống như thêm một trang mới vào sổ tay nơi bạn có thể ghi lại suy nghĩ của mình.

## Bước 4: Thêm văn bản vào trang

Hãy làm cho trang này thú vị hơn một chút bằng cách thêm một số văn bản. Chúng ta sẽ thêm một thông báo đơn giản "Hello World".

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Dòng mã này thêm một đoạn văn bản vào trang đầu tiên của tệp PDF. Giống như viết tiêu đề ở đầu trang vậy!

## Bước 5: Tạo JavaScript cho Ngày hết hạn

Bây giờ đến phần thú vị! Bạn sẽ tạo một hành động JavaScript để kiểm tra ngày hết hạn của PDF. Nếu ngày hiện tại vượt quá ngày hết hạn, một thông báo sẽ cảnh báo người dùng.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Sau đây là những gì đang xảy ra:
- Bạn xác định năm và tháng hết hạn.
- Bạn có ngày hôm nay.
- Bạn so sánh ngày hôm nay với ngày hết hạn.
- Nếu ngày hôm nay đã quá ngày hết hạn, một thông báo sẽ hiện ra!

## Bước 6: Đặt JavaScript làm Hành động mở PDF

Bây giờ, bạn cần thiết lập hành động JavaScript làm hành động mở cho tài liệu PDF của bạn. Điều này có nghĩa là JavaScript sẽ chạy ngay khi PDF được mở.

```csharp
doc.OpenAction = javaScript;
```

Dòng này yêu cầu PDF thực thi JavaScript khi ai đó mở nó. Giống như việc đặt lời nhắc sẽ kêu ngay khi bạn mở lịch!

## Bước 7: Lưu tài liệu PDF

Cuối cùng, đã đến lúc lưu tài liệu PDF của bạn với tính năng ngày hết hạn. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Dòng này sẽ lưu tệp PDF của bạn vào thư mục được chỉ định với tên "SetExpiryDate_out.pdf". Giống như việc bạn đặt tác phẩm nghệ thuật đã hoàn thành vào trong khung vậy!

## Phần kết luận

Và bạn đã có nó! Bạn đã tạo thành công một tệp PDF có ngày hết hạn bằng Aspose.PDF cho .NET. Tính năng này không chỉ tăng cường bảo mật mà còn đảm bảo thông tin nhạy cảm được kiểm soát. Cho dù bạn đang gửi hợp đồng, báo cáo hay bất kỳ tài liệu quan trọng nào khác, việc đặt ngày hết hạn có thể là một bước ngoặt.

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF trong các ứng dụng .NET.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
 Có, bạn có thể sử dụng phiên bản dùng thử miễn phí của Aspose.PDF. Bạn có thể tải xuống[đây](https://releases.aspose.com/).

### Làm thế nào để tôi mua Aspose.PDF?
Bạn có thể mua Aspose.PDF bằng cách truy cập[trang mua hàng](https://purchase.aspose.com/buy).

### Tôi phải làm sao nếu cần hỗ trợ?
Nếu bạn có bất kỳ câu hỏi hoặc cần hỗ trợ, bạn có thể truy cập[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/pdf/10).

### Tôi có thể nhận được giấy phép tạm thời cho Aspose.PDF không?
 Có, bạn có thể yêu cầu giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).