---
title: Trích xuất đường viền trong tệp PDF
linktitle: Trích xuất đường viền trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất đường viền từ tệp PDF và lưu chúng dưới dạng hình ảnh bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với các mẫu mã và mẹo để thành công.
type: docs
weight: 80
url: /vi/net/programming-with-tables/extract-border/
---
## Giới thiệu

Khi làm việc với PDF, việc trích xuất các thành phần cụ thể như đường viền hoặc đường dẫn đồ họa có vẻ là một nhiệm vụ khó khăn. Nhưng với Aspose.PDF cho .NET, bạn có thể dễ dàng trích xuất đường viền hoặc hình dạng từ tệp PDF và lưu chúng dưới dạng hình ảnh. Trong hướng dẫn này, chúng ta sẽ tìm hiểu sâu hơn về quy trình trích xuất đường viền từ PDF và lưu dưới dạng hình ảnh PNG. Hãy sẵn sàng để kiểm soát nội dung đồ họa của PDF!

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo bạn đã thiết lập mọi thứ:

1.  Aspose.PDF cho .NET: Nếu bạn chưa cài đặt thư viện Aspose.PDF, bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/). Bạn cũng cần phải áp dụng giấy phép, thông qua bản dùng thử miễn phí hoặc giấy phép đã mua.
2. Thiết lập IDE: Thiết lập dự án C# trong Visual Studio hoặc bất kỳ IDE .NET nào khác. Đảm bảo bạn đã thêm các tham chiếu cần thiết vào thư viện Aspose.PDF.
3. Đầu vào tệp PDF: Chuẩn bị tệp PDF mà bạn sẽ trích xuất các đường viền. Hướng dẫn này sẽ tham chiếu đến tệp có tên`input.pdf`.

## Nhập các gói cần thiết

Hãy bắt đầu bằng cách nhập các không gian tên cần thiết. Các gói này cung cấp các công cụ cần thiết để thao tác nội dung PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Bây giờ chúng ta đã nắm được những kiến thức cơ bản, hãy cùng chuyển sang hướng dẫn từng bước, trong đó chúng tôi sẽ phân tích từng phần của mã để giải thích chi tiết.


## Bước 1: Tải tài liệu PDF

Bước đầu tiên là tải tài liệu PDF có chứa đường viền bạn muốn trích xuất. Hãy nghĩ về việc này giống như việc mở một cuốn sách trước khi bạn bắt đầu đọc — bạn cần truy cập vào nội dung!

 Chúng tôi sẽ bắt đầu bằng cách chỉ định thư mục lưu trữ tệp PDF của bạn và tải tài liệu bằng cách sử dụng`Aspose.Pdf.Document` lớp học.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Mã này tải`input.pdf` tệp từ thư mục bạn chỉ định. Đảm bảo đường dẫn tệp là chính xác, nếu không bạn có thể gặp lỗi không tìm thấy tệp.

## Bước 2: Thiết lập đồ họa và Bitmap

Trước khi bắt đầu trích xuất, chúng ta cần tạo một canvas để vẽ. Trong thế giới .NET, điều này có nghĩa là thiết lập các đối tượng Bitmap và Graphics. Bitmap biểu diễn hình ảnh và đối tượng Graphics sẽ cho phép chúng ta vẽ các hình dạng, chẳng hạn như đường viền, được trích xuất từ PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Sau đây là thông tin chi tiết:
- Chúng tôi tạo một hình ảnh bitmap có kích thước bằng trang đầu tiên của tệp PDF.
- GraphicsPath được sử dụng để xác định hình dạng (trong trường hợp này là đường viền).
- Ma trận xác định cách đồ họa sẽ được chuyển đổi; chúng ta cần một ma trận đảo ngược vì PDF và .NET có hệ tọa độ khác nhau.

## Bước 3: Xử lý nội dung PDF


Tệp PDF là một chuỗi các lệnh vẽ và chúng ta cần xử lý từng lệnh này để xác định và trích xuất thông tin đường viền.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Xử lý các lệnh như lưu/khôi phục trạng thái, vẽ đường, tô hình, v.v.
}
```

Mã lặp qua mọi toán tử vẽ trong luồng nội dung của PDF. Mỗi toán tử có thể biểu diễn một đường thẳng, hình chữ nhật hoặc hướng dẫn đồ họa khác.

## Bước 4: Xử lý các toán tử PDF

Mỗi toán tử trong tệp PDF điều khiển một hành động. Để trích xuất đường viền, chúng ta cần xác định các lệnh như "di chuyển đến", "đường thẳng đến" và "vẽ hình chữ nhật". Các toán tử sau xử lý các hành động này:

- MoveTo: Di chuyển con trỏ đến điểm bắt đầu.
- LineTo: Vẽ một đường thẳng từ điểm hiện tại đến một điểm mới.
- Trả lời: Vẽ một hình chữ nhật (đây có thể là một phần của đường viền).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

Ở bước này:
- Chúng tôi ghi lại các điểm cho mỗi đường thẳng hoặc hình dạng được vẽ.
- Đối với hình chữ nhật (`opRe` ), chúng tôi thêm chúng trực tiếp vào`graphicsPath`, chúng ta sẽ sử dụng sau để vẽ đường viền.

## Bước 5: Vẽ đường viền

Sau khi xác định được các đường thẳng và hình chữ nhật tạo thành đường viền, chúng ta cần thực sự vẽ chúng vào đối tượng Bitmap. Đây chính là lúc đối tượng Graphics xuất hiện.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Chúng ta tạo một đối tượng Đồ họa dựa trên bitmap.
- SmoothingMode.HighQuality đảm bảo chúng ta có được hình ảnh mịn đẹp.
- Cuối cùng, chúng ta sử dụng DrawPath để vẽ đường viền.

## Bước 6: Lưu đường viền đã trích xuất

Bây giờ chúng ta đã trích xuất đường viền, đã đến lúc lưu nó dưới dạng tệp hình ảnh. Thao tác này sẽ lưu đường viền dưới dạng PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Ảnh bitmap được lưu dưới dạng ảnh PNG.
- Bây giờ bạn có thể mở hình ảnh này để xem đường viền đã trích xuất.

## Phần kết luận

Trích xuất đường viền từ tệp PDF bằng Aspose.PDF cho .NET có vẻ khó khăn lúc đầu, nhưng khi bạn phân tích kỹ, nó trở nên đơn giản. Bằng cách hiểu các toán tử vẽ trong PDF và sử dụng các thư viện .NET mạnh mẽ, bạn có thể thao tác và trích xuất nội dung đồ họa một cách hiệu quả. Hướng dẫn này cung cấp cho bạn nền tảng vững chắc để bắt đầu thao tác PDF!

## Câu hỏi thường gặp

### Tôi phải xử lý nhiều trang trong tệp PDF như thế nào?  
 Bạn có thể lặp qua từng trang trong tài liệu bằng cách lặp lại`doc.Pages` thay vì mã hóa cứng`doc.Pages[1]`.

### Tôi có thể trích xuất các thành phần khác, như văn bản, bằng cách sử dụng phương pháp tương tự không?  
Có, Aspose.PDF cung cấp các API phong phú để trích xuất văn bản, hình ảnh và nội dung khác từ tệp PDF.

### Tôi phải áp dụng giấy phép như thế nào để tránh bị hạn chế?  
 Bạn có thể[áp dụng giấy phép](https://purchase.aspose.com/temporary-license/) bằng cách tải nó thông qua`License` lớp học do Aspose cung cấp.

### Nếu tệp PDF của tôi không có đường viền thì sao?  
Nếu PDF của bạn không có đường viền nào có thể nhìn thấy, quá trình trích xuất đồ họa có thể không mang lại kết quả nào. Đảm bảo rằng nội dung PDF bao gồm đường viền có thể vẽ được.

### Tôi có thể lưu đầu ra ở định dạng khác ngoài PNG không?  
 Vâng, chỉ cần thay đổi`ImageFormat.Png` sang một định dạng được hỗ trợ khác như`ImageFormat.Jpeg`.