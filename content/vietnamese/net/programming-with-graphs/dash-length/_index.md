---
title: Chiều dài dấu gạch ngang
linktitle: Chiều dài dấu gạch ngang
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tùy chỉnh các mẫu gạch ngang trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước của chúng tôi. Hoàn hảo để thêm kiểu cho tài liệu của bạn.
type: docs
weight: 70
url: /vi/net/programming-with-graphs/dash-length/
---
## Giới thiệu

Bạn có muốn thêm một chút sáng tạo vào tài liệu PDF của mình bằng cách tùy chỉnh các dòng với nhiều mẫu gạch ngang khác nhau không? Với Aspose.PDF cho .NET, bạn có thể dễ dàng sửa đổi các kiểu dòng để phù hợp với nhu cầu của tài liệu. Trong hướng dẫn này, chúng ta sẽ khám phá cách điều chỉnh độ dài gạch ngang của các dòng trong tài liệu PDF bằng Aspose.PDF cho .NET. Cho dù bạn đang hướng đến một dòng gạch ngang hay một mẫu chấm bi, hướng dẫn này sẽ cung cấp cho bạn các công cụ và các bước cần thiết để đạt được kết quả mong muốn.

## Điều kiện tiên quyết

Trước khi bắt đầu hướng dẫn, bạn cần chuẩn bị một số thứ sau:

1. Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt Aspose.PDF cho .NET. Nếu bạn chưa cài đặt, bạn có thể tải xuống từ[Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/).
2. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình C#. Nếu bạn mới làm quen với C#, bạn có thể muốn ôn lại những kiến thức cơ bản trước.
3. Visual Studio: Mặc dù bạn có thể sử dụng bất kỳ IDE nào, nhưng hướng dẫn này giả định rằng bạn đang sử dụng Visual Studio để viết và chạy mã C#.
4.  Tài khoản Aspose: Để có thêm tài nguyên và hỗ trợ, hãy đảm bảo bạn có tài khoản với Aspose. Bạn có thể đăng ký[dùng thử miễn phí](https://releases.aspose.com/) hoặc mua giấy phép[đây](https://purchase.aspose.com/buy).

## Nhập gói

Để bắt đầu làm việc với Aspose.PDF cho .NET, bạn sẽ cần nhập các không gian tên có liên quan. Sau đây là cách bạn có thể thực hiện:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Các không gian tên này bao gồm các lớp và phương thức cần thiết để làm việc với tài liệu PDF, bản vẽ và đường thẳng.

## Bước 1: Thiết lập dự án của bạn

Trước khi bắt đầu viết mã, hãy thiết lập một dự án C# mới trong Visual Studio. Thêm thư viện Aspose.PDF cho .NET vào dự án của bạn thông qua NuGet hoặc bằng cách tham chiếu DLL theo cách thủ công. 

## Bước 2: Khởi tạo Tài liệu

Bắt đầu bằng cách tạo một tài liệu PDF mới và thêm một trang vào đó. Đây là khung vẽ mà bạn sẽ vẽ các đường nét của mình.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo phiên bản Tài liệu
Document doc = new Document();

// Thêm trang vào bộ sưu tập trang của đối tượng Tài liệu
Page page = doc.Pages.Add();
```

 Ở đây, chúng tôi tạo ra một`Document` đối tượng và thêm một cái mới`Page` với nó. Điều này thiết lập nền tảng để bạn vẽ đường.

## Bước 3: Tạo đối tượng vẽ

 Tiếp theo, tạo một`Graph` đối tượng đại diện cho khu vực bạn sẽ vẽ. Xác định kích thước của nó theo yêu cầu của bạn.

```csharp
// Tạo đối tượng bản vẽ có kích thước nhất định
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// Thêm đối tượng vẽ vào tập hợp đoạn văn của trang
page.Paragraphs.Add(canvas);
```

 Các`Graph` Đối tượng đóng vai trò là nơi chứa các thành phần bản vẽ của bạn. Ở đây, nó được đặt thành chiều rộng 100 đơn vị và chiều cao 400 đơn vị.

## Bước 4: Xác định đường thẳng

 Bây giờ là lúc tạo ra`Line`đối tượng. Chỉ định điểm bắt đầu và kết thúc của đường thẳng và tùy chỉnh kiểu của nó.

```csharp
// Tạo đối tượng Line
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

Dòng này bắt đầu tại tọa độ (100, 100) và kết thúc tại (200, 100). Bạn có thể điều chỉnh các tọa độ này để phù hợp với nhu cầu cụ thể của mình.

## Bước 5: Tùy chỉnh Kiểu Đường

Thiết lập màu sắc và kiểu nét đứt của đường kẻ. Đây là nơi bạn có thể làm cho đường kẻ của mình nổi bật.

```csharp
// Đặt màu cho đối tượng Line
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// Chỉ định mảng gạch ngang cho đối tượng đường thẳng
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Đặt pha gạch ngang cho thể hiện Line
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: Thiết lập màu của đường. Trong trường hợp này là màu đỏ.
- `line.GraphInfo.DashArray` : Xác định mẫu gạch ngang. Ở đây,`{ 0, 1, 0 }` thể hiện một mẫu nét đứt.
- `line.GraphInfo.DashPhase`: Điều chỉnh điểm bắt đầu của mẫu nét gạch ngang.

## Bước 6: Thêm đường vào bản vẽ

 Với dòng của bạn được tạo kiểu, hãy thêm nó vào`Graph` sự vật.

```csharp
// Thêm đường thẳng vào bộ sưu tập hình dạng của đối tượng vẽ
canvas.Shapes.Add(line);
```

Thao tác này sẽ tích hợp đường nét vào khung vẽ của bạn.

## Bước 7: Lưu tài liệu

Cuối cùng, lưu tài liệu của bạn vào đường dẫn đã chỉ định. Đây là nơi tệp PDF sẽ được tạo.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// Lưu tài liệu PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

Dòng mã này lưu tài liệu PDF và cung cấp thông báo xác nhận cho biết vị trí tệp đã được lưu.

## Phần kết luận

Tùy chỉnh kiểu đường nét trong tài liệu PDF có thể thêm nét chuyên nghiệp vào báo cáo, bài thuyết trình và các tài liệu khác của bạn. Bằng cách làm theo hướng dẫn này, bạn đã học cách điều chỉnh độ dài nét gạch ngang của các đường bằng Aspose.PDF cho .NET. Cho dù bạn đang tạo các đường gạch ngang đơn giản hay các mẫu phức tạp hơn, Aspose.PDF đều cung cấp tính linh hoạt mà bạn cần để làm cho tài liệu của mình nổi bật. Thử nghiệm với các mẫu và màu gạch ngang khác nhau để tìm kiểu phù hợp nhất với nhu cầu của bạn.

## Câu hỏi thường gặp

### Làm thế nào để cài đặt Aspose.PDF cho .NET?
 Bạn có thể cài đặt nó thông qua NuGet trong Visual Studio hoặc tải xuống từ[Trang web của Aspose](https://releases.aspose.com/pdf/net/).

### Tôi có thể sử dụng Aspose.PDF cho .NET miễn phí không?
 Có, Aspose cung cấp một[dùng thử miễn phí](https://releases.aspose.com/) vì vậy bạn có thể kiểm tra các tính năng trước khi mua giấy phép.

### Tôi có thể tùy chỉnh những dòng nào khác trong tệp PDF?
 Bạn có thể điều chỉnh độ dày của đường, màu sắc và kiểu nét gạch ngang. Tham khảo[tài liệu](https://reference.aspose.com/pdf/net/) để biết thêm chi tiết.

### Tôi có thể nhận được hỗ trợ như thế nào nếu gặp vấn đề?
 Bạn có thể truy cập hỗ trợ thông qua[Diễn đàn Aspose](https://forum.aspose.com/c/pdf/10).

### Tôi có thể mua giấy phép Aspose.PDF cho .NET ở đâu?
Bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy).