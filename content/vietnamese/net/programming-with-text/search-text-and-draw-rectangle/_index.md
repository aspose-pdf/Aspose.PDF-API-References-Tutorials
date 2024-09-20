---
title: Tìm kiếm văn bản và vẽ hình chữ nhật
linktitle: Tìm kiếm văn bản và vẽ hình chữ nhật
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Học cách tìm kiếm văn bản trong PDF và tô sáng bằng hình chữ nhật bằng Aspose.PDF cho .NET! Hướng dẫn từng bước dễ dàng để nâng cao kỹ năng thao tác PDF.
type: docs
weight: 460
url: /vi/net/programming-with-text/search-text-and-draw-rectangle/
---
## Giới thiệu

Bạn đang muốn nâng cao kỹ năng thao tác PDF của mình? Bạn có muốn tìm hiểu cách tìm kiếm văn bản cụ thể trong các tệp PDF và tô sáng nó bằng hình chữ nhật không? Bạn đã tìm đúng hướng dẫn rồi! Hôm nay, tôi sẽ hướng dẫn bạn cách sử dụng Aspose.PDF cho .NET để tìm kiếm văn bản trong tài liệu PDF và vẽ hình chữ nhật xung quanh nó. Bài viết này sẽ cung cấp hướng dẫn từng bước được thiết kế rõ ràng và hữu ích, đảm bảo bạn có thể làm theo và áp dụng các kỹ thuật này vào các dự án của mình. 

## Điều kiện tiên quyết

Trước khi bắt đầu hướng dẫn, hãy chuẩn bị những gì bạn cần để đảm bảo quy trình làm việc diễn ra suôn sẻ:

1. Hiểu biết cơ bản về .NET: Bạn nên quen thuộc với lập trình C# và .NET framework để thực hiện hướng dẫn này một cách hiệu quả.
   
2. Đã cài Visual Studio: Bạn sẽ cần một môi trường phát triển tích hợp (IDE) để viết và kiểm tra mã của mình. Visual Studio Community là một lựa chọn tuyệt vời và miễn phí.
   
3. Aspose.PDF cho .NET: Bạn cần cài đặt thư viện Aspose.PDF trong dự án của mình. Bạn có thể tải xuống[đây](https://releases.aspose.com/pdf/net/) hoặc xem xét một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để có các tính năng mở rộng.
   
4.  Tài liệu PDF mẫu: Đối với hướng dẫn này, bạn sẽ cần một tệp PDF mẫu có tên`SearchAndGetTextFromAll.pdf` được lưu trữ trong thư mục dự án của bạn. 

## Nhập gói

Để bắt đầu, trước tiên bạn cần nhập các gói cần thiết vào dự án .NET của mình. Thực hiện theo các bước sau:

### Mở Visual Studio

Khởi chạy Visual Studio và tạo một Ứng dụng Console mới hoặc sử dụng ứng dụng hiện có khi bạn muốn triển khai các chức năng PDF.

### Thêm Aspose.PDF vào Dự án của bạn

1. Nhấp chuột phải vào dự án của bạn trong Solution Explorer.
2. Chọn "Quản lý gói NuGet".
3.  Tìm kiếm`Aspose.PDF` và cài đặt phiên bản mới nhất.

Bằng cách này, bạn đang đặt nền tảng cho tất cả các thao tác PDF tuyệt vời mà bạn sắp thực hiện.

## Nhập không gian tên

Ở đầu tệp chương trình, bạn sẽ muốn nhập các không gian tên có liên quan từ thư viện Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Điều này giúp bạn dễ dàng truy cập các lớp và phương thức trong thư viện Aspose.PDF cho các tác vụ của mình hơn.


Bây giờ bạn đã thiết lập mọi thứ, hãy cùng chia nhỏ quy trình tìm kiếm văn bản trong tệp PDF và vẽ hình chữ nhật xung quanh nó thành các bước dễ quản lý.

## Bước 1: Thiết lập Đường dẫn cho Tài liệu của bạn

 Đầu tiên, hãy thiết lập đường dẫn đến tệp PDF của bạn. Hãy đảm bảo thay thế`YOUR DOCUMENT DIRECTORY` với con đường thực tế nơi bạn`SearchAndGetTextFromAll.pdf` được lưu trữ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở Tài liệu PDF

 Tiếp theo, tạo một phiên bản của`Document` lớp để tải PDF của bạn:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Dòng mã này sẽ mở tệp PDF bạn chỉ định, cho phép bạn tiếp tục chỉnh sửa tệp đó.

## Bước 3: Tạo một trình hấp thụ văn bản

 Bây giờ, bạn sẽ cần một cách để tìm kiếm văn bản trong tài liệu đó. Đối với điều này, chúng tôi sử dụng`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Biểu thức chính quy`@"[\S]+"` được thiết kế để phù hợp với bất kỳ chuỗi ký tự không phải khoảng trắng nào trong PDF. 

## Bước 4: Cấu hình Tùy chọn Tìm kiếm Văn bản

Tiếp theo, bạn nên thiết lập các tùy chọn tìm kiếm văn bản:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Ở đây,`true` tham số có nghĩa là tìm kiếm sẽ phân biệt chữ hoa chữ thường. Bạn có thể đặt nó thành`false` nếu bạn muốn tìm kiếm không phân biệt chữ hoa chữ thường.

## Bước 5: Chấp nhận Text Absorber trong Tài liệu

 Với bạn`TextFragmentAbsorber` và các tùy chọn tìm kiếm đã sẵn sàng, đã đến lúc lấy văn bản từ tài liệu:

```csharp
document.Pages.Accept(textAbsorber);
```

Phương pháp này kiểm tra từng trang trong tệp PDF của bạn để tìm các đoạn văn bản khớp với mẫu đã chỉ định.

## Bước 6: Tạo một PdfContentEditor

 Để vẽ hình dạng trên tài liệu, bạn sẽ cần`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Trình chỉnh sửa này cho phép bạn thao tác và chỉnh sửa nội dung PDF dễ dàng.

## Bước 7: Lặp qua các đoạn văn bản đã tìm thấy

Bây giờ, bạn sẽ muốn lặp qua các đoạn văn bản đã tìm thấy để vẽ các hình chữ nhật xung quanh chúng:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Vòng lặp này lặp lại qua từng đoạn văn bản và các phân đoạn của chúng, gọi một`DrawBox` phương pháp vẽ hình chữ nhật.

## Bước 8: Xác định phương thức DrawBox

 Bạn cần phải xác định`DrawBox` phương pháp này sẽ xử lý logic vẽ hình chữ nhật. Sau đây là một triển khai đơn giản:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Tính kích thước hình chữ nhật dựa trên đoạn văn bản
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Vẽ một hình chữ nhật sử dụng các giá trị đã tính toán
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Phương pháp này xác định vị trí và kích thước của hình chữ nhật dựa trên hình chữ nhật giới hạn của đoạn thẳng và sử dụng trình chỉnh sửa để vẽ hình chữ nhật đó.

## Bước 9: Lưu tài liệu đã sửa đổi

Sau khi vẽ các hình chữ nhật xung quanh văn bản tìm thấy, bạn có thể lưu tài liệu đã sửa đổi:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Hãy đảm bảo tệp mới của bạn được lưu dưới tên riêng để tránh ghi đè lên tài liệu gốc.

## Bước 10: Tin nhắn xác nhận

Cuối cùng, in thông báo xác nhận tới bảng điều khiển để cho bạn biết rằng thao tác đã thành công:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Và thế là xong! Bạn đã tạo thành công một tập lệnh để tìm kiếm văn bản trong PDF và tô sáng nó bằng hình chữ nhật.

## Phần kết luận

Xin chúc mừng! Bạn vừa mở khóa một kỹ năng mạnh mẽ có thể cải thiện đáng kể khả năng thao tác PDF của bạn bằng Aspose.PDF cho .NET. Chỉ với một vài bước đơn giản, bạn có thể tìm kiếm bất kỳ văn bản nào trong tài liệu của mình và tô sáng trực quan, giúp tài liệu PDF của bạn tương tác và dễ quản lý hơn. Đừng ngần ngại thử nghiệm các mẫu biểu thức chính quy và tùy chọn màu khác nhau để thực sự biến công cụ này thành của riêng bạn!

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là thư viện cung cấp giải pháp toàn diện để tạo, chỉnh sửa và chuyển đổi tài liệu PDF theo chương trình.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
Có, Aspose cung cấp bản dùng thử miễn phí mà bạn có thể sử dụng để kiểm tra các chức năng của thư viện. Hãy xem thử[đây](https://releases.aspose.com/).

### Tôi cần sử dụng ngôn ngữ lập trình nào với Aspose.PDF cho .NET?
Aspose.PDF cho .NET được thiết kế để sử dụng với C# và các ngôn ngữ .NET khác.

### Làm thế nào để tôi nhận được trợ giúp về Aspose.PDF?
 Bạn có thể truy cập diễn đàn hỗ trợ Aspose để được trợ giúp về bất kỳ vấn đề hoặc thắc mắc nào bạn có thể có. Tìm hỗ trợ[đây](https://forum.aspose.com/c/pdf/10).

### Tôi có thể tải Aspose.PDF cho .NET ở đâu?
 Bạn có thể tải xuống thư viện từ trang web Aspose,[đây](https://releases.aspose.com/pdf/net/).