---
title: Tạo hình chữ nhật đã tô
linktitle: Tạo hình chữ nhật đã tô
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo hình chữ nhật tô màu trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này. Hoàn hảo cho các nhà phát triển ở mọi cấp độ.
type: docs
weight: 50
url: /vi/net/programming-with-graphs/create-filled-rectangle/
---
## Giới thiệu

Bạn đã bao giờ muốn tạo PDF hấp dẫn về mặt hình ảnh theo chương trình chưa? Nếu có, bạn đã đến đúng nơi rồi! Trong hướng dẫn này, chúng ta sẽ khám phá thế giới của Aspose.PDF cho .NET, một thư viện mạnh mẽ cho phép bạn dễ dàng thao tác các tài liệu PDF. Hôm nay, chúng ta sẽ tập trung vào việc tạo một hình chữ nhật được tô đầy trong tệp PDF. Cho dù bạn là một nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn từng bước một cách thân thiện và hấp dẫn. Vì vậy, hãy đội mũ lập trình của bạn và bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, bạn cần chuẩn bị một số thứ sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Đây là IDE tuyệt vời cho phát triển .NET.
2.  Aspose.PDF cho .NET: Bạn sẽ cần tải xuống và cài đặt thư viện Aspose.PDF. Bạn có thể tìm thấy nó[đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Một chút quen thuộc với lập trình C# sẽ giúp bạn hiểu các đoạn mã tốt hơn.

## Nhập gói

Để bắt đầu, bạn cần nhập các gói cần thiết vào dự án C# của mình. Sau đây là cách bạn có thể thực hiện:

### Tạo một dự án mới

Mở Visual Studio và tạo một dự án C# mới. Bạn có thể chọn Ứng dụng Console để đơn giản hơn.

### Thêm tham chiếu Aspose.PDF

1. Nhấp chuột phải vào dự án của bạn trong Solution Explorer.
2. Chọn "Quản lý gói NuGet".
3. Tìm kiếm "Aspose.PDF" và cài đặt phiên bản mới nhất.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bây giờ chúng ta đã thiết lập xong mọi thứ, hãy cùng tìm hiểu về mã lệnh nhé!

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, bạn cần chỉ định đường dẫn nơi tệp PDF của bạn sẽ được lưu. Điều này rất quan trọng vì nó cho chương trình biết nơi tạo tệp.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế trên máy của bạn nơi bạn muốn lưu tệp PDF.

## Bước 2: Tạo một phiên bản tài liệu

 Tiếp theo, chúng ta sẽ tạo một phiên bản của`Document`lớp. Lớp này đại diện cho tài liệu PDF mà bạn sẽ làm việc.

```csharp
// Tạo phiên bản Tài liệu
Document doc = new Document();
```

Dòng này khởi tạo một tài liệu PDF mới mà chúng ta có thể thao tác.

## Bước 3: Thêm Trang vào Tài liệu

Bây giờ, hãy thêm một trang vào tài liệu của chúng ta. Mỗi tệp PDF cần ít nhất một trang, đúng không?

```csharp
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
```

Đoạn mã này thêm một trang mới vào tài liệu, cho phép chúng ta vẽ hình dạng trên đó.

## Bước 4: Tạo một thể hiện đồ thị

 Để vẽ các hình dạng, chúng ta cần tạo một`Graph` Ví dụ. Hãy nghĩ về biểu đồ như một tấm vải mà bạn có thể vẽ nhiều hình dạng khác nhau.

```csharp
// Tạo phiên bản đồ thị
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Ở đây, chúng ta sẽ tạo một biểu đồ có chiều rộng là 100 và chiều cao là 400.

## Bước 5: Thêm biểu đồ vào trang

Bây giờ chúng ta đã có biểu đồ, hãy thêm nó vào trang mà chúng ta đã tạo trước đó.

```csharp
// Thêm đối tượng đồ thị vào tập hợp đoạn văn của trang
page.Paragraphs.Add(graph);
```

Dòng này gắn biểu đồ vào trang giấy, giúp bạn sẵn sàng vẽ biểu đồ.

## Bước 6: Tạo một thể hiện hình chữ nhật

Tiếp theo, chúng ta sẽ tạo một hình chữ nhật mà chúng ta muốn tô màu.

```csharp
// Tạo thể hiện hình chữ nhật
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

Trong mã này, chúng ta xác định vị trí và kích thước của hình chữ nhật. Các tham số biểu diễn tọa độ x và y, chiều rộng và chiều cao.

## Bước 7: Chỉ định màu tô

Bây giờ, hãy chọn màu cho hình chữ nhật của chúng ta. Chúng ta sẽ tô màu đỏ cho ví dụ này.

```csharp
// Chỉ định màu tô cho đối tượng Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Dòng này thiết lập màu tô của hình chữ nhật thành màu đỏ. Bạn có thể chọn bất kỳ màu nào bạn thích!

## Bước 8: Thêm hình chữ nhật vào biểu đồ

Sau khi đã có hình chữ nhật, đã đến lúc thêm nó vào biểu đồ.

```csharp
// Thêm đối tượng hình chữ nhật vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(rect);
```

Đoạn mã này thêm hình chữ nhật vào biểu đồ, biến nó thành một phần trong bản vẽ của chúng ta.

## Bước 9: Lưu tài liệu PDF

Cuối cùng, chúng ta cần lưu tài liệu vào thư mục đã chỉ định.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
```

 Mã này lưu tệp PDF với tên`CreateFilledRectangle_out.pdf` trong thư mục bạn đã chỉ định trước đó.

## Bước 10: Tin nhắn xác nhận

Để cho chúng tôi biết mọi việc diễn ra suôn sẻ, chúng tôi có thể in tin nhắn xác nhận.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Dòng này sẽ đưa ra thông báo trong bảng điều khiển, xác nhận rằng hình chữ nhật đã tô màu đã được tạo thành công.

## Phần kết luận

Và bạn đã có nó! Bạn đã tạo thành công một hình chữ nhật được tô đầy trong một tài liệu PDF bằng Aspose.PDF cho .NET. Thư viện mạnh mẽ này mở ra một thế giới khả năng để thao tác PDF, cho phép bạn tạo các tài liệu tuyệt đẹp theo chương trình. Cho dù bạn đang tạo báo cáo, hóa đơn hay bất kỳ loại PDF nào khác, Aspose.PDF đều có thể đáp ứng nhu cầu của bạn.

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF theo cách lập trình.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
 Có, Aspose cung cấp phiên bản dùng thử miễn phí mà bạn có thể sử dụng để khám phá các tính năng của thư viện. Bạn có thể tải xuống[đây](https://releases.aspose.com/).

### Có cách nào để nhận được hỗ trợ cho Aspose.PDF không?
 Chắc chắn rồi! Bạn có thể nhận được hỗ trợ thông qua diễn đàn Aspose[đây](https://forum.aspose.com/c/pdf/10).

### Tôi có thể mua Aspose.PDF như thế nào?
 Bạn có thể mua Aspose.PDF bằng cách truy cập trang mua hàng[đây](https://purchase.aspose.com/buy).

### Tôi có thể tạo những loại hình dạng nào bằng Aspose.PDF?
Bạn có thể tạo nhiều hình dạng khác nhau, bao gồm hình chữ nhật, hình tròn, đường thẳng, v.v. bằng thư viện Aspose.PDF.