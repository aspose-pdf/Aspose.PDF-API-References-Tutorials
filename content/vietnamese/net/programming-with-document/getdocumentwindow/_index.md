---
title: Nhận cửa sổ tài liệu
linktitle: Nhận cửa sổ tài liệu
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng tính năng GetDocumentWindow của Aspose.PDF cho .NET để lấy thông tin về thuộc tính cửa sổ của tài liệu PDF.
type: docs
weight: 170
url: /vi/net/programming-with-document/getdocumentwindow/
---
# Giới thiệu

Bạn đang làm việc với PDF và muốn kiểm soát nhiều hơn cách chúng xuất hiện khi mở? Cho dù đó là ẩn thanh menu hay thay đổi kích thước cửa sổ để vừa với trang đầu tiên, Aspose.PDF for .NET cung cấp cho bạn tất cả các công cụ bạn cần để tùy chỉnh cách PDF hoạt động khi mở trong trình xem. Trong hướng dẫn này, chúng tôi sẽ phân tích cách truy xuất và thao tác cài đặt cửa sổ tài liệu trong Aspose.PDF for .NET.


# Điều kiện tiên quyết

Trước khi bắt đầu hướng dẫn, hãy đảm bảo rằng bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

- Aspose.PDF cho .NET được cài đặt trên môi trường phát triển của bạn.
  - [Tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/)
-  Giấy phép hợp lệ cho Aspose.PDF hoặc bạn có thể nhận được[dùng thử miễn phí](https://releases.aspose.com/) hoặc[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
- Hiểu biết cơ bản về .NET và C#.
- Visual Studio hoặc IDE phù hợp khác.

# Nhập gói

Trước khi bắt đầu viết bất kỳ mã nào, bạn sẽ cần nhập các gói cần thiết. Mở dự án của bạn và ở đầu tệp C#, thêm không gian tên sau:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Điều này sẽ giúp bạn truy cập vào tất cả các lớp và phương thức cần thiết để thao tác với tài liệu PDF bằng Aspose.PDF cho .NET.

 Bây giờ chúng ta hãy phân tích quá trình lấy các thiết lập cửa sổ tài liệu khác nhau. Đối với ví dụ này, chúng ta sẽ sử dụng một tệp PDF mẫu có tên`GetDocumentWindow.pdf`.

## Bước 1: Đặt Đường dẫn Thư mục Tài liệu

Trước tiên, chúng ta cần xác định đường dẫn đến tệp PDF của mình. Điều quan trọng là bạn phải có đường dẫn tệp chính xác để tránh mọi lỗi trong quá trình thực hiện.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ở đây, thay thế`"YOUR DOCUMENT DIRECTORY"` với thư mục thực tế nơi tệp PDF của bạn nằm. Đây là thư mục làm việc của bạn, nơi bạn sẽ tải tài liệu PDF.

## Bước 2: Mở Tài liệu PDF

Bây giờ đường dẫn tệp đã được thiết lập, bước tiếp theo là mở tài liệu PDF bằng Aspose.PDF. Thao tác này sẽ tải tài liệu vào bộ nhớ, cho phép bạn truy xuất các thuộc tính của tài liệu.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Với dòng mã đơn giản này, bạn đã tải thành công tệp PDF của mình vào`pdfDocument` đối tượng, cho phép bạn truy cập tất cả các thuộc tính của đối tượng đó.

## Bước 3: Lấy lại trạng thái căn giữa cửa sổ

 Tiếp theo, hãy kiểm tra xem cửa sổ tài liệu có được căn giữa khi mở hay không. Giá trị mặc định cho việc này là`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Nếu đầu ra là`true`, cửa sổ tài liệu sẽ mở ở giữa màn hình. Nếu không, nó sẽ mở ở vị trí mặc định.

## Bước 4: Kiểm tra hướng văn bản

Một khía cạnh quan trọng khác của giao diện PDF là hướng văn bản, xác định xem văn bản được đọc từ trái sang phải (L2R) hay từ phải sang trái (R2L). Bạn có thể lấy thông tin này bằng cách sử dụng mã sau:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Đầu ra sẽ là`L2R` cho văn bản từ trái sang phải và`R2L` cho văn bản từ phải sang trái. Thiết lập này đặc biệt hữu ích cho các tài liệu bằng các ngôn ngữ như tiếng Ả Rập hoặc tiếng Do Thái.

## Bước 5: Hiển thị Tiêu đề Tài liệu trong Cửa sổ

Thuộc tính tiếp theo cho phép bạn kiểm soát xem tiêu đề tài liệu hay tên tệp sẽ được hiển thị trên thanh tiêu đề của cửa sổ. Theo mặc định, điều này được đặt thành`false`, nghĩa là tên tệp sẽ được hiển thị.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Nếu bạn muốn hiển thị tiêu đề của tài liệu thay vì tên tệp, bạn phải bật cài đặt này.

## Bước 6: Thay đổi kích thước cửa sổ để vừa với trang đầu tiên

Đôi khi, bạn có thể muốn cửa sổ tài liệu tự động thay đổi kích thước để vừa với trang đầu tiên của PDF khi mở. Sau đây là cách kiểm tra xem tính năng đó có được bật hay không:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Theo mặc định, điều này được thiết lập thành`false`, nghĩa là kích thước cửa sổ sẽ vẫn giữ nguyên bất kể kích thước của trang đầu tiên.

## Bước 7: Ẩn thanh Menu

Để có trải nghiệm đọc tập trung hơn, bạn có thể muốn ẩn thanh menu của ứng dụng trình xem. Bạn có thể lấy lại cài đặt này bằng cách sử dụng dòng sau:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Điều này sẽ trở lại`true` nếu thanh menu bị ẩn và`false` nếu không thì.

## Bước 8: Ẩn thanh công cụ

Tương tự, bạn cũng có thể muốn ẩn thanh công cụ trong trình xem PDF để có giao diện người dùng sạch hơn. Cài đặt này có thể được lấy lại như sau:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Nếu bật cài đặt này, thanh công cụ sẽ bị ẩn khi mở tệp PDF.

## Bước 9: Ẩn thanh cuộn và các thành phần UI

Nếu bạn chỉ muốn hiển thị nội dung trang mà không có bất kỳ thành phần UI bổ sung nào như thanh cuộn, thiết lập này sẽ kiểm soát hành vi đó:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Khi thiết lập thành`true`, trình xem PDF sẽ ẩn thanh cuộn và các thành phần giao diện người dùng khác, chỉ để lại nội dung tài liệu.

## Bước 10: Đặt chế độ trang không toàn màn hình

 Bạn có thể kiểm soát cách tài liệu xuất hiện khi thoát khỏi chế độ toàn màn hình bằng cách sử dụng`NonFullScreenPageMode` thuộc tính. Thiết lập này hữu ích để xác định cách người dùng tương tác với tài liệu ở chế độ không toàn màn hình.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Đầu ra có thể được thiết lập ở nhiều chế độ khác nhau như hình thu nhỏ, phác thảo hoặc bảng tệp đính kèm.

## Bước 11: Xác định Bố cục Trang

Thiết lập này cho phép bạn kiểm soát cách bố trí các trang tài liệu. Ví dụ, bạn có thể chọn chế độ xem một trang hoặc chế độ xem cột liên tục:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Điều này mang lại cho người dùng sự linh hoạt trong cách họ đọc hoặc xem nội dung tài liệu.

## Bước 12: Chỉ định chế độ trang

 Cuối cùng,`PageMode` thuộc tính xác định cách tài liệu sẽ được hiển thị khi mở. Các tùy chọn bao gồm hiển thị hình thu nhỏ, vào chế độ toàn màn hình hoặc hiển thị bảng đính kèm.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Tùy thuộc vào nhu cầu của mình, bạn có thể cài đặt chế độ này phù hợp với mục đích của tệp PDF.

## Phần kết luận

Như bạn có thể thấy, Aspose.PDF for .NET cung cấp các công cụ toàn diện để thao tác cách hiển thị tài liệu PDF của bạn trong nhiều trình xem PDF khác nhau. Cho dù bạn muốn ẩn thanh công cụ, căn giữa cửa sổ hay kiểm soát hướng văn bản, Aspose.PDF đều cung cấp tính linh hoạt để nâng cao trải nghiệm xem của người dùng.

# Câu hỏi thường gặp

### Tôi có thể tùy chỉnh mức thu phóng ban đầu của tệp PDF không?
Có, Aspose.PDF cho phép bạn cài đặt mức thu phóng khi mở tài liệu.

### Làm thế nào để khóa kích thước cửa sổ của tệp PDF?
 Bạn có thể thiết lập`FitWindow` thuộc tính để ngăn cửa sổ thay đổi kích thước.

### Aspose.PDF có hỗ trợ các chế độ đọc khác nhau không?
Có, nó hỗ trợ nhiều chế độ khác nhau như toàn màn hình, hình thu nhỏ và tệp đính kèm.

### Có thể ẩn thanh cuộn trong trình xem PDF không?
 Hoàn toàn có thể ẩn thanh cuộn bằng cách thiết lập`HideWindowUI` tài sản để`true`.

### Tôi có thể căn giữa cửa sổ tài liệu khi mở không?
 Có, bạn có thể kiểm soát điều này bằng cách thiết lập`CenterWindow` tài sản.