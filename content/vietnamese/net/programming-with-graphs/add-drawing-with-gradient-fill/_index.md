---
title: Thêm bản vẽ với màu tô chuyển màu
linktitle: Thêm bản vẽ với màu tô chuyển màu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm bản vẽ có màu tô chuyển màu bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tạo tài liệu PDF hấp dẫn.
type: docs
weight: 20
url: /vi/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# sau đây để thêm bản vẽ có tô màu gradient vào lập trình bằng đồ họa bằng Aspose.PDF cho .NET.

Đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình trước khi bắt đầu. Ngoài ra còn có kiến thức cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã nguồn được cung cấp, bạn cần chỉ định thư mục mà bạn muốn lưu tệp PDF kết quả. Thay đổi biến "dataDir" thành thư mục mong muốn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo đối tượng tài liệu và thêm trang

Chúng tôi tạo một thể hiện của lớp Tài liệu và thêm một trang vào tài liệu này.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng đồ thị và thêm nó vào trang

Chúng tôi tạo một đối tượng Biểu đồ với các kích thước được chỉ định và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Bước 4: Tạo đối tượng hình chữ nhật và thêm vào biểu đồ

Chúng ta tạo một đối tượng Hình chữ nhật với các kích thước được chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Bước 5: Định cấu hình tô màu gradient

Chúng tôi định cấu hình tô màu gradient cho hình chữ nhật bằng cách sử dụng lớp gradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Điều này tạo ra một dải màu tô chuyển màu từ đỏ sang xanh lam, từ điểm (0, 0) đến điểm (300, 300).

## Bước 6: Lưu tệp PDF

Cuối cùng, chúng tôi lưu tệp PDF kết quả với tên "AdddrawWithGradientFill_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Mã nguồn mẫu cho Thêm bản vẽ bằng tô chuyển màu bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích từng bước cách thêm bản vẽ có tô chuyển màu vào lập trình bằng đồ họa bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể sử dụng kiến thức này để tạo các tài liệu PDF hấp dẫn với các thiết kế tùy chỉnh và màu tô chuyển màu.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này nhằm mục đích hướng dẫn bạn trong quá trình thêm bản vẽ có tô màu chuyển màu vào lập trình bằng đồ họa bằng Aspose.PDF cho .NET.

#### Hỏi: Những điều kiện tiên quyết nào được yêu cầu trước khi bắt đầu?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Ngoài ra, nên có hiểu biết cơ bản về lập trình C#.

#### Hỏi: Làm cách nào để chỉ định thư mục lưu tệp PDF?

Trả lời: Trong mã nguồn được cung cấp, bạn có thể thay đổi giá trị của biến "dataDir" để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### Câu hỏi: Mục đích của đối tượng Graph là gì?

Trả lời: Đối tượng Graph đóng vai trò là nơi chứa các phần tử vẽ. Nó được tạo với các kích thước được chỉ định và được thêm vào bộ sưu tập đoạn văn của trang.

#### Câu hỏi: Làm cách nào tôi có thể định cấu hình tô chuyển màu cho hình dạng?

Trả lời: Để định cấu hình tô màu chuyển màu, bạn có thể đặt thuộc tính FillColor của GraphInfo của hình bằng cách sử dụng lớp gradientAxialShading. Điều này cho phép bạn xác định điểm bắt đầu và điểm kết thúc của dải màu cũng như màu sắc để chuyển tiếp giữa chúng.

#### Câu hỏi: Tôi có thể tùy chỉnh màu sắc và hướng tô chuyển màu không?

Trả lời: Có, bạn có thể tùy chỉnh màu sắc và hướng của màu tô chuyển màu bằng cách điều chỉnh các đối tượng Màu và chỉ định điểm bắt đầu và điểm kết thúc của gradientAxialShading.

#### Hỏi: Bước cuối cùng của hướng dẫn là gì?

Trả lời: Bước cuối cùng bao gồm việc lưu tệp PDF thu được có tên "AdddrawWithGradientFill_out.pdf" trong thư mục được chỉ định.

#### Hỏi: Có sẵn mã nguồn mẫu không?

Đáp: Có, hướng dẫn này cung cấp mã nguồn mẫu mà bạn có thể sử dụng làm tài liệu tham khảo để triển khai các bước được mô tả.

#### Câu hỏi: Tôi có thể áp dụng màu tô chuyển màu cho các hình dạng khác ngoài hình chữ nhật không?

Đáp: Có, bạn cũng có thể áp dụng màu tô chuyển màu cho các hình dạng khác. Quá trình này bao gồm việc định cấu hình thuộc tính FillColor của GraphInfo của hình bằng cách sử dụng lớp gradientAxialShading.