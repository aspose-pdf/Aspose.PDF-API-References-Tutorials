---
title: Thêm Bản Vẽ Với Gradient Fill
linktitle: Thêm Bản Vẽ Với Gradient Fill
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm bản vẽ có tô màu chuyển sắc bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tạo tài liệu PDF hấp dẫn.
type: docs
weight: 20
url: /vi/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước sử dụng mã nguồn C# sau để thêm bản vẽ có hiệu ứng tô màu chuyển màu vào lập trình đồ họa bằng Aspose.PDF cho .NET.

Đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển trước khi bắt đầu. Ngoài ra, bạn cũng cần có kiến thức cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã nguồn được cung cấp, bạn cần chỉ định thư mục mà bạn muốn lưu tệp PDF kết quả. Thay đổi biến "dataDir" thành thư mục mong muốn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Khởi tạo một đối tượng tài liệu và thêm một trang

Chúng tôi tạo một thể hiện của lớp Document và thêm một trang vào tài liệu này.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng đồ thị và thêm vào trang

Chúng tôi tạo một đối tượng Graph với các kích thước được chỉ định và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Bước 4: Tạo đối tượng hình chữ nhật và thêm vào biểu đồ

Chúng tôi tạo một đối tượng Hình chữ nhật có kích thước được chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Bước 5: Cấu hình Gradient Fill

Chúng tôi cấu hình màu tô chuyển màu cho hình chữ nhật bằng cách sử dụng lớp GradientAxialShading.

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

Thao tác này tạo ra một hiệu ứng tô màu chuyển màu từ đỏ sang xanh, từ điểm (0, 0) đến điểm (300, 300).

## Bước 6: Lưu tệp PDF

Cuối cùng, chúng ta lưu tệp PDF kết quả với tên "AddDrawingWithGradientFill_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Mã nguồn mẫu để Thêm bản vẽ với tô màu chuyển sắc bằng Aspose.PDF cho .NET 

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

Trong hướng dẫn này, chúng tôi đã giải thích từng bước cách thêm bản vẽ có tô màu gradient vào lập trình đồ họa bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để tạo các tài liệu PDF hấp dẫn với thiết kế tùy chỉnh và tô màu gradient.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Mục đích của hướng dẫn này là hướng dẫn bạn quy trình thêm bản vẽ có hiệu ứng tô màu chuyển màu vào lập trình đồ họa bằng Aspose.PDF cho .NET.

#### H: Cần có những điều kiện tiên quyết nào trước khi bắt đầu?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Ngoài ra, nên có hiểu biết cơ bản về lập trình C#.

#### H: Làm thế nào để chỉ định thư mục lưu tệp PDF?

A: Trong mã nguồn được cung cấp, bạn có thể thay đổi giá trị của biến "dataDir" để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### H: Mục đích của đối tượng Graph là gì?

A: Đối tượng Graph đóng vai trò là một container cho các thành phần bản vẽ. Nó được tạo ra với các kích thước được chỉ định và được thêm vào bộ sưu tập đoạn văn của trang.

#### H: Làm thế nào để cấu hình tô màu chuyển sắc cho một hình dạng?

A: Để cấu hình tô màu gradient, bạn có thể đặt thuộc tính FillColor của GraphInfo của hình dạng bằng cách sử dụng lớp GradientAxialShading. Điều này cho phép bạn xác định điểm bắt đầu và kết thúc của gradient và màu sắc để chuyển tiếp giữa chúng.

#### H: Tôi có thể tùy chỉnh màu sắc và hướng của hiệu ứng đổ màu gradient không?

A: Có, bạn có thể tùy chỉnh màu sắc và hướng của hiệu ứng tô màu chuyển màu bằng cách điều chỉnh các đối tượng Màu và chỉ định điểm bắt đầu và kết thúc của GradientAxialShading.

#### H: Bước cuối cùng của hướng dẫn là gì?

A: Bước cuối cùng là lưu tệp PDF kết quả với tên "AddDrawingWithGradientFill_out.pdf" vào thư mục đã chỉ định.

#### H: Có mã nguồn mẫu nào có sẵn không?

A: Có, phần hướng dẫn cung cấp mã nguồn mẫu mà bạn có thể sử dụng làm tài liệu tham khảo để thực hiện các bước được mô tả.

#### H: Tôi có thể áp dụng hiệu ứng tô chuyển màu cho các hình dạng khác ngoài hình chữ nhật không?

A: Có, bạn cũng có thể áp dụng tô màu chuyển sắc cho các hình dạng khác. Quá trình này bao gồm việc cấu hình thuộc tính FillColor của GraphInfo của hình dạng bằng cách sử dụng lớp GradientAxialShading.