---
title: lnk Chiều rộng dòng chú thích
linktitle: lnk Chiều rộng dòng chú thích
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Bài viết này cung cấp hướng dẫn từng bước để thiết lập độ rộng dòng của Chú thích lnk bằng Aspose.PDF cho .NET.
type: docs
weight: 110
url: /vi/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF là một công cụ mạnh mẽ và được sử dụng rộng rãi để làm việc với các tệp PDF trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để tạo, chỉnh sửa và thao tác với tệp PDF, bao gồm khả năng thêm chú thích vào các trang. Trong hướng dẫn này, chúng tôi sẽ giải thích cách đặt độ rộng dòng của chú thích liên kết bằng Aspose.PDF cho .NET.

Khi bạn đã có những điều kiện tiên quyết này, hãy tạo một dự án ứng dụng bảng điều khiển mới trong Visual Studio. Sau đó, thêm tham chiếu đến thư viện Aspose.PDF cho .NET bằng cách nhấp chuột phải vào dự án trong Solution Explorer, chọn "Quản lý gói NuGet" và tìm kiếm "Aspose.PDF" trong Trình quản lý gói NuGet.

Để thêm chú thích lnk vào tài liệu PDF, hãy làm theo các bước sau:

##  Bước 1: Tạo mới`Document` object.
```csharp
Document doc = new Document();
```
## Bước 2: Thêm một trang mới vào tài liệu.
```csharp
doc.Pages.Add();
```
##  Bước 3: Tạo danh sách`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Bước 4: Tạo mới`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Bước 5: Tạo mới`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Bước 6: Thêm cử chỉ vào danh sách cử chỉ viết tay.
```csharp
inkList.Add(gesture);
```
##  Bước 7: Tạo mới`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Bước 8: Đặt chủ đề và tiêu đề cho chú thích.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Bước 9: Đặt màu cho chú thích.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Bước 10: Tạo mới`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Bước 11: Thêm chú thích vào trang.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Bước 12: Lưu tài liệu vào một tập tin.
```csharp
// Lưu tập tin đầu ra
doc.Save(dataDir);


```
### Ví dụ hiển thị Độ rộng dòng chú thích lnk với Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Lưu tập tin đầu ra
doc.Save(dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt độ rộng dòng của chú thích liên kết trong tài liệu PDF bằng Aspose.PDF cho .NET. Aspose.PDF for .NET cung cấp nhiều công cụ và tính năng để làm việc với tài liệu PDF, bao gồm khả năng tạo và tùy chỉnh chú thích liên kết. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng thêm các liên kết tương tác vào tài liệu PDF của họ, nâng cao trải nghiệm người dùng và tính tương tác của ứng dụng của họ. Aspose.PDF for .NET là một thư viện đa năng hỗ trợ các nhà phát triển .NET làm việc với các tệp PDF một cách hiệu quả và hiệu quả.

### Câu hỏi thường gặp

#### Hỏi: Chú thích liên kết trong tài liệu PDF là gì?

Đáp: Chú thích liên kết trong tài liệu PDF là một thành phần tương tác cho phép bạn tạo các siêu liên kết hoặc hành động hướng người dùng đến một vị trí khác trong cùng một tài liệu, một trang web bên ngoài hoặc một tài liệu PDF khác.

#### Câu hỏi: Làm cách nào tôi có thể đặt độ rộng dòng của chú thích liên kết bằng Aspose.PDF cho .NET?

Trả lời: Để đặt độ rộng dòng của chú thích liên kết bằng Aspose.PDF cho .NET, bạn có thể tạo một`InkAnnotation` đối tượng và chỉ định thuộc tính độ rộng dòng.

#### Câu hỏi: Những thuộc tính nào có thể được tùy chỉnh cho chú thích liên kết trong Aspose.PDF cho .NET?

Trả lời: Bạn có thể tùy chỉnh các thuộc tính khác nhau của chú thích liên kết trong Aspose.PDF cho .NET, chẳng hạn như vị trí, kích thước, màu sắc, thuộc tính đường viền (chiều rộng, kiểu, mẫu gạch ngang và hiệu ứng), chủ đề, tiêu đề và khả năng hiển thị.

#### Câu hỏi: Tôi có thể tạo chú thích liên kết chứa nhiều cử chỉ viết tay không?

 Đáp: Có, bạn có thể tạo chú thích liên kết chứa nhiều cử chỉ viết tay bằng cách thêm nhiều`Point` mảng để`InkAnnotation` sự vật.

#### Hỏi: Làm cách nào tôi có thể thêm chú thích liên kết vào một trang cụ thể của tài liệu PDF?

 Trả lời: Để thêm chú thích liên kết vào một trang cụ thể của tài liệu PDF, bạn cần chỉ định số trang khi tạo`InkAnnotation` sự vật. Ví dụ,`new InkAnnotation(doc.Pages[1], ...)` thêm chú thích liên kết vào trang đầu tiên.