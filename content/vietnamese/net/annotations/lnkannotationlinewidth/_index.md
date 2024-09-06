---
title: Chiều rộng dòng chú thích lnk
linktitle: Chiều rộng dòng chú thích lnk
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thiết lập độ rộng dòng chú thích mực trong PDF bằng Aspose.PDF cho .NET. Hướng dẫn chi tiết này hướng dẫn bạn từng bước, đảm bảo đầu ra chất lượng cao.
type: docs
weight: 110
url: /vi/net/annotations/lnkannotationlinewidth/
---
## Giới thiệu

Khi làm việc với các tài liệu PDF, việc thêm chú thích có thể là một cách hiệu quả để làm nổi bật thông tin hoặc thêm các thành phần tương tác vào tệp của bạn. Một trong những chú thích như vậy là Ink Annotation, cho phép bạn vẽ các đường tự do trên PDF của mình. Nhưng nếu bạn cần tùy chỉnh giao diện của các đường này, đặc biệt là độ rộng của đường thì sao? Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập độ rộng của đường chú thích bằng mực bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo bạn đã thiết lập mọi thứ để thực hiện theo hướng dẫn này một cách suôn sẻ:

1.  Aspose.PDF cho .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ[trang tải xuống](https://releases.aspose.com/pdf/net/) hoặc cài đặt thông qua NuGet Package Manager trong Visual Studio.
2. Môi trường phát triển: Hướng dẫn này giả định rằng bạn đang làm việc trong môi trường phát triển .NET như Visual Studio.
3. Kiến thức cơ bản về C#: Hiểu biết cơ bản về C# sẽ giúp bạn theo dõi các bước viết mã.
4. Tài liệu PDF: Sử dụng tài liệu PDF hiện có hoặc tạo tài liệu mới cho hướng dẫn này.

## Nhập các không gian tên cần thiết

Trước khi bắt đầu viết mã, hãy đảm bảo nhập các không gian tên cần thiết vào dự án của bạn:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Các không gian tên này cung cấp các lớp và phương thức cần thiết để thao tác với tài liệu PDF, làm việc với chú thích và xử lý các thành phần đồ họa.

Bây giờ chúng ta đã có đủ các điều kiện tiên quyết, hãy chia nhỏ quy trình thiết lập độ rộng dòng chú thích mực thành các bước rõ ràng, dễ quản lý.

## Bước 1: Khởi tạo Tài liệu PDF

Trước tiên, chúng ta cần tạo hoặc mở một tài liệu PDF. Đối với hướng dẫn này, chúng ta sẽ tạo một tài liệu PDF mới từ đầu.

```csharp
// Khởi tạo Tài liệu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Chỉ định thư mục tài liệu của bạn
Document doc = new Document();
doc.Pages.Add(); // Thêm một trang trống vào tài liệu
```

 Ở đây, chúng ta đang khởi tạo một cái mới`Document` đối tượng, đại diện cho tệp PDF của chúng tôi. Sau đó, chúng tôi thêm một trang trống vào tài liệu này để làm việc.

## Bước 2: Tạo chú thích mực

Tiếp theo, chúng ta sẽ tạo chú thích mực. Điều này bao gồm việc xác định các điểm tạo nên nét mực.

```csharp
// Tạo chú thích mực
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 Trong bước này, chúng tôi xác định`LineInfo` đối tượng, chứa tọa độ của các nét mực, khả năng hiển thị, màu sắc và độ rộng ban đầu của nét mực.`VerticeCoordinate` mảng chứa tọa độ X và Y của mỗi điểm trong nét vẽ.

## Bước 3: Chuyển đổi tọa độ thành điểm

Bây giờ, chúng ta cần chuyển đổi các tọa độ này thành các điểm có thể được chú thích bằng mực sử dụng.

```csharp
// Chuyển đổi tọa độ thành điểm
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Vòng lặp này xử lý mảng tọa độ, chuyển đổi từng cặp tọa độ thành một`Point` đối tượng, sau đó được thêm vào`inkList`.

## Bước 4: Thêm chú thích mực vào trang PDF

Khi các điểm đã sẵn sàng, chúng ta có thể tạo chú thích mực và thêm vào trang PDF.

```csharp
// Thêm chú thích mực vào trang PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 Trong bước này, chúng tôi khởi tạo một`InkAnnotation`đối tượng, chỉ định trang, hình chữ nhật giới hạn và danh sách các điểm của chúng tôi. Chúng tôi cũng đặt chủ đề, tiêu đề và màu sắc của chú thích.

## Bước 5: Tùy chỉnh đường viền chú thích

Để tùy chỉnh thêm giao diện chú thích, chúng ta sẽ sửa đổi thuộc tính đường viền của chú thích.

```csharp
// Tùy chỉnh đường viền chú thích
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Ở đây, chúng tôi tạo ra một`Border` đối tượng cho chú thích của chúng tôi, thiết lập chiều rộng, hiệu ứng, mẫu gạch ngang và kiểu dáng của nó. Bước này đảm bảo rằng chú thích nổi bật về mặt hình ảnh trên trang PDF.

## Bước 6: Lưu tài liệu PDF

Cuối cùng, sau khi thực hiện tất cả các thay đổi cần thiết, đã đến lúc lưu tài liệu.

```csharp
// Lưu tài liệu PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Mã này lưu tài liệu PDF đã sửa đổi với chú thích mực trong thư mục được chỉ định.`Console.WriteLine` câu lệnh xác nhận việc thực thi mã thành công.

## Phần kết luận

Xin chúc mừng! Bạn đã tạo và tùy chỉnh thành công chú thích mực trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này bao gồm toàn bộ quá trình, từ khởi tạo tài liệu đến lưu tệp cuối cùng. Với kiến thức này, bạn có thể khám phá thêm các khả năng rộng lớn của Aspose.PDF cho .NET và áp dụng các kỹ thuật tương tự cho các loại chú thích hoặc thao tác PDF khác.

## Câu hỏi thường gặp

### Tôi có thể sử dụng các màu khác nhau cho các phần chú thích bằng mực khác nhau không?  
 Có, bạn có thể tạo nhiều`InkAnnotation` các đối tượng có màu sắc khác nhau và thêm chúng vào cùng một trang hoặc các trang khác nhau trong tệp PDF của bạn.

### Làm thế nào để thay đổi độ rộng của dòng một cách linh hoạt?  
 Bạn có thể điều chỉnh`LineWidth` tài sản của`LineInfo` đối tượng trước khi chuyển đổi tọa độ thành điểm.

### Có thể làm cho chú thích mực trở nên trong suốt được không?  
 Có, bạn có thể sửa đổi`Opacity` tài sản của`InkAnnotation` đối tượng để làm cho nó trong suốt.

### Tôi có thể thêm nhiều chú thích bằng mực vào cùng một trang không?  
Chắc chắn rồi! Bạn có thể thêm bao nhiêu chú thích mực tùy thích vào một trang bằng cách lặp lại quy trình này.

### Làm thế nào để xóa chú thích mực khỏi tệp PDF?  
 Bạn có thể xóa chú thích bằng cách sử dụng`doc.Pages[1].Annotations.Delete(a1)` phương pháp, nơi`a1` là đối tượng chú thích của bạn.