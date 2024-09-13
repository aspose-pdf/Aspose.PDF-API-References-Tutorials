---
title: Thay đổi hướng
linktitle: Thay đổi hướng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để thay đổi hướng trang của PDF bằng Aspose.PDF cho .NET. Dễ dàng thực hiện và triển khai trong các dự án của bạn.
type: docs
weight: 10
url: /vi/net/programming-with-pdf-pages/change-orientation/
---
## Giới thiệu

Bạn đã bao giờ thấy mình vật lộn với một tệp PDF mà hướng trang chỉ... lệch? Có thể bạn đang xử lý một tài liệu được quét hoặc tạo không đúng cách và các trang cần phải xoay để có ý nghĩa. Thật may mắn cho chúng ta, Aspose.PDF cho .NET cung cấp một cách dễ dàng và mạnh mẽ để thao tác các tệp PDF theo hầu hết mọi cách có thể tưởng tượng được—bao gồm cả việc thay đổi hướng của các trang. Cho dù bạn muốn chuyển từ chế độ dọc sang chế độ ngang hoặc ngược lại, hướng dẫn này sẽ hướng dẫn bạn từng bước trong quy trình.

Vì vậy, nếu bạn đã sẵn sàng để bắt đầu và xoay các trang PDF một cách dễ dàng, hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết về cách thay đổi hướng trang trong tệp PDF, chúng ta hãy cùng xem nhanh những gì bạn cần chuẩn bị:

-  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF cho .NET. Nếu chưa, bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/).
- Môi trường phát triển .NET: Bạn có thể sử dụng Visual Studio, JetBrains Rider hoặc bất kỳ IDE nào bạn thích để làm việc với .NET.
- Kiến thức cơ bản về C#: Mặc dù hướng dẫn này khá đơn giản, nhưng một số hiểu biết cơ bản về C# sẽ giúp bạn dễ hiểu hơn.
- Tệp PDF: Ví dụ bên dưới giả định bạn có tệp PDF có nhiều trang. Nếu bạn không có tệp nào tiện dụng, hãy tạo hoặc tải xuống tệp PDF mẫu để làm việc.

 Ngoài ra, nếu bạn mới bắt đầu, bạn có thể thử Aspose.PDF với[giấy phép tạm thời miễn phí](https://purchase.aspose.com/temporary-license/) trước khi quyết định[mua phiên bản đầy đủ](https://purchase.aspose.com/buy).

## Nhập không gian tên

Trước khi bạn có thể thao tác hướng của các trang trong PDF, bạn sẽ cần nhập các không gian tên cần thiết vào dự án C# của mình. Đảm bảo bạn có các mục sau:

```csharp
using System.IO;
using Aspose.Pdf;
```

Sau khi nhập xong, chúng ta hãy cùng đi vào phần chính của hướng dẫn.

## Bước 1: Tải Tài liệu PDF

 Điều đầu tiên chúng ta cần làm là tải tệp PDF mà bạn muốn sửa đổi. Bạn có thể sử dụng`Document` lớp từ không gian tên Aspose.PDF để mở tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Dòng này tải PDF từ thư mục bạn chỉ định. Hãy đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tệp của bạn.`"input.pdf"` là tệp PDF bạn muốn thay đổi hướng.

## Bước 2: Lặp qua từng trang

 Bây giờ chúng ta đã tải xong tài liệu, hãy lặp qua từng trang trong PDF. Chúng ta sẽ sử dụng`foreach` vòng lặp để duyệt qua mọi trang, cho phép chúng ta áp dụng thay đổi hướng cho tất cả các trang.

```csharp
foreach (Page page in doc.Pages)
{
    // Thao tác từng trang
}
```

Vòng lặp này sẽ lặp lại tất cả các trang trong tài liệu.

## Bước 3: Lấy MediaBox của Trang

 Mỗi trang trong PDF có một`MediaBox` xác định ranh giới của trang. Chúng ta cần truy cập vào đây để xác định hướng hiện tại và sửa đổi nó.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 Các`MediaBox` cung cấp cho chúng ta kích thước của trang, chẳng hạn như chiều rộng, chiều cao và vị trí của trang.

## Bước 4: Hoán đổi chiều rộng và chiều cao

Để thay đổi hướng trang từ dọc sang ngang hoặc từ ngang sang dọc, chúng ta chỉ cần hoán đổi giá trị chiều rộng và chiều cao. Bước này sẽ điều chỉnh kích thước của trang.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Mã này hoán đổi chiều cao và chiều rộng và định vị lại góc dưới bên trái (`LLY`) để nội dung vừa khít sau khi xoay.

## Bước 5: Cập nhật MediaBox và CropBox

Bây giờ chúng ta đã có chiều cao và chiều rộng mới, hãy áp dụng các thay đổi vào trang.`MediaBox` Và`CropBox` . Các`CropBox` là điều cần thiết nếu tài liệu gốc có một bộ, đảm bảo toàn bộ trang hiển thị chính xác.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Bước này sẽ thay đổi kích thước trang dựa trên kích thước mới mà chúng ta vừa tính toán.

## Bước 6: Xoay trang

Cuối cùng, chúng ta thiết lập góc xoay của trang. Aspose.PDF giúp việc này cực kỳ đơn giản. Chúng ta có thể xoay trang 90 độ để chuyển từ chế độ dọc sang chế độ ngang hoặc ngược lại.

```csharp
page.Rotate = Rotation.on90;
```

Mã này xoay trang 90 độ, lật trang theo hướng mong muốn.

## Bước 7: Lưu PDF đầu ra

Sau khi áp dụng thay đổi hướng cho tất cả các trang, chúng ta lưu tài liệu đã sửa đổi vào một tệp mới. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Hãy đảm bảo bạn cung cấp tên tệp mới (trong trường hợp này,`ChangeOrientation_out.pdf`) để lưu đầu ra. Bằng cách này, bạn không ghi đè lên tệp gốc.

### Phần kết luận

Và bạn đã có nó! Thay đổi hướng trang của tệp PDF bằng Aspose.PDF cho .NET đơn giản như tải tài liệu, lặp qua các trang, điều chỉnh MediaBox và lưu tệp đã cập nhật. Cho dù bạn đang xử lý tài liệu được quét kém hay cần xoay các trang để phù hợp với nhu cầu định dạng của mình, hướng dẫn từng bước này sẽ giúp bạn.

## Câu hỏi thường gặp

### Tôi có thể xoay các trang cụ thể thay vì tất cả các trang trong tệp PDF không?  
Có, bạn có thể sửa đổi vòng lặp để nhắm mục tiêu vào các trang cụ thể bằng cách sử dụng chỉ mục của chúng thay vì lặp qua tất cả các trang.

###  Cái gì là`MediaBox`?  
 Các`MediaBox` xác định kích thước và hình dạng của trang trong tệp PDF. Đây là nơi đặt nội dung của trang.

### Aspose.PDF cho .NET có hoạt động với các định dạng tệp khác không?  
Có, Aspose.PDF có thể xử lý nhiều định dạng tệp khác nhau như HTML, XML, XPS, v.v.

### Có phiên bản miễn phí của Aspose.PDF dành cho .NET không?  
 Vâng, bạn có thể bắt đầu với một[dùng thử miễn phí](https://releases.aspose.com/) hoặc yêu cầu một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

### Tôi có thể hoàn tác những thay đổi sau khi đã lưu không?  
Sau khi bạn lưu tài liệu, các thay đổi sẽ có hiệu lực vĩnh viễn. Hãy đảm bảo làm việc trên một bản sao hoặc giữ bản sao lưu của tệp gốc.