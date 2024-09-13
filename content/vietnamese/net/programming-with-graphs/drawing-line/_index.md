---
title: Đường vẽ
linktitle: Đường vẽ
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách vẽ các đường trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này bao gồm thiết lập tài liệu, thêm đường và lưu tệp.
type: docs
weight: 80
url: /vi/net/programming-with-graphs/drawing-line/
---
## Giới thiệu

Vẽ các đường trong tài liệu PDF có vẻ như là một nhiệm vụ đơn giản, nhưng nó có thể là một công cụ mạnh mẽ để tạo các phương tiện hỗ trợ trực quan, sơ đồ và nhấn mạnh các khu vực chính. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình vẽ các đường trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này sẽ đề cập đến mọi thứ từ thiết lập môi trường của bạn đến thực thi mã để tạo PDF có các đường kẻ ngang qua.

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, bạn cần chuẩn bị một số thứ sau:

1.  Aspose.PDF cho .NET: Bạn cần cài đặt Aspose.PDF cho .NET. Bạn có thể tải xuống từ[Trang web Aspose](https://releases.aspose.com/pdf/net/).
2. Môi trường phát triển .NET: Đảm bảo bạn đã thiết lập môi trường phát triển cho các ứng dụng .NET. Visual Studio là lựa chọn tốt cho việc này.
3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ hữu ích cho việc hiểu các đoạn mã và ví dụ trong hướng dẫn này.

## Nhập gói

Để làm việc với Aspose.PDF cho .NET, bạn cần nhập các không gian tên có liên quan. Thêm chỉ thị using sau vào đầu tệp C# của bạn:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để thao tác với tài liệu PDF và vẽ hình dạng.

Hãy chia nhỏ quá trình vẽ đường thành một loạt các bước. Mỗi bước sẽ hướng dẫn bạn qua một phần cụ thể của mã để giúp bạn hiểu cách đạt được kết quả mong muốn.

## Bước 1: Thiết lập tài liệu và trang của bạn

Bước đầu tiên là tạo một tài liệu PDF mới và thêm một trang vào đó. Sau đây là cách bạn có thể thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo phiên bản Tài liệu
Document pDoc = new Document();

// Thêm trang vào bộ sưu tập trang của tài liệu PDF
Page pg = pDoc.Pages.Add();
```

 Đây,`dataDir` là đường dẫn nơi tệp PDF đầu ra của bạn sẽ được lưu.`Document` là lớp chính để xử lý PDF và`Page` đại diện cho một trang duy nhất trong tài liệu PDF.

## Bước 2: Cấu hình lề trang

Để đảm bảo các dòng của bạn kéo dài từ mép này sang mép kia, bạn sẽ cần đặt lề trang thành 0:

```csharp
// Đặt lề trang ở tất cả các mặt là 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

Thao tác này sẽ xóa mọi lề mặc định, cung cấp cho bạn một trang đầy đủ để vẽ.

## Bước 3: Tạo đối tượng đồ thị

 Tiếp theo, tạo một`Graph` đối tượng phù hợp với kích thước của trang. Đối tượng này sẽ đóng vai trò là nơi chứa các hình dạng của bạn:

```csharp
// Tạo đối tượng đồ thị có chiều rộng và chiều cao bằng kích thước trang
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

 Các`Graph` Đối tượng cho phép bạn thêm và thao tác các hình dạng trên trang.

## Bước 4: Vẽ đường đầu tiên

Bây giờ là lúc vẽ dòng đầu tiên của bạn. Ví dụ này sẽ vẽ một dòng từ góc dưới bên trái đến góc trên bên phải của trang:

```csharp
// Tạo đối tượng dòng đầu tiên bắt đầu từ góc dưới bên trái đến góc trên bên phải của trang
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Thêm đường thẳng vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(line);
```

 Các`Line` lớp lấy tọa độ cho điểm bắt đầu và kết thúc của đường thẳng. Ở đây,`pg.Rect.LLX` Và`pg.Rect.URY` lần lượt biểu thị góc dưới bên trái và góc trên bên phải của trang.

## Bước 5: Vẽ đường thứ hai

Đối với dòng thứ hai, chúng ta sẽ vẽ từ góc trên bên trái xuống góc dưới bên phải:

```csharp
// Vẽ đường thẳng từ góc trên bên trái của trang đến góc dưới bên phải của trang
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Thêm đường thẳng vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(line2);
```

Dòng này sẽ cắt ngang trang theo đường chéo theo hướng ngược lại.

## Bước 6: Thêm biểu đồ vào trang

 Với các đường đã vẽ, bây giờ bạn cần thêm`Graph` phản đối việc thu thập đoạn văn của trang:

```csharp
// Thêm đối tượng Graph vào bộ sưu tập đoạn văn của trang
pg.Paragraphs.Add(graph);
```

 Bước này tích hợp`Graph` đối tượng (bằng các dòng của bạn) vào trang PDF.

## Bước 7: Lưu tài liệu

Cuối cùng, lưu tài liệu của bạn vào một tập tin:

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// Lưu tệp PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

 Thao tác này sẽ lưu tệp PDF với các đường bạn đã vẽ và`Console.WriteLine` tuyên bố xác nhận rằng hoạt động đã thành công.

## Phần kết luận

Vẽ các đường trong tài liệu PDF bằng Aspose.PDF cho .NET là một quá trình đơn giản khi bạn chia nhỏ thành các bước dễ quản lý. Bằng cách làm theo hướng dẫn này, bạn đã học cách thiết lập tài liệu PDF, vẽ các đường trên đó và lưu sản phẩm cuối cùng. Cho dù bạn đang tạo sơ đồ, nhấn mạnh văn bản hay chỉ đơn giản là thử nghiệm thao tác PDF, hướng dẫn này cung cấp nền tảng vững chắc để làm việc với các đường trong PDF.

 Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ thêm, vui lòng tham khảo[Tài liệu Aspose.PDF](https://reference.aspose.com/pdf/net/) hoặc ghé thăm[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/pdf/10).

## Câu hỏi thường gặp

### Tôi có thể vẽ các hình dạng khác ngoài đường thẳng không?
 Có, bạn có thể vẽ nhiều hình dạng khác nhau như hình chữ nhật, hình elip và hình đa giác bằng cách sử dụng`Aspose.Pdf.Drawing` không gian tên.

### Làm thế nào để điều chỉnh màu sắc và độ dày của các đường?
 Bạn có thể thiết lập`Line` đối tượng của`StrokeColor` Và`LineWidth` thuộc tính để tùy chỉnh giao diện của các dòng.

### Có thể vẽ đường ở những khu vực cụ thể trên trang không?
 Chắc chắn rồi! Chỉ cần điều chỉnh tọa độ của`Line` đối tượng để định vị các đường theo nhu cầu.

### Tôi có thể thêm văn bản vào các dòng không?
 Có, bạn có thể thêm văn bản bằng cách tạo`TextFragment` các đối tượng và đặt chúng vào`Paragraphs` bộ sưu tập của trang.

### Tôi phải làm sao nếu muốn thêm dòng vào tệp PDF hiện có thay vì tạo tệp PDF mới?
 Bạn có thể tải một tệp PDF hiện có bằng cách sử dụng`Document` và sau đó sử dụng các phương pháp tương tự để thêm dòng vào các trang hiện có.