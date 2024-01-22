---
title: Đường vẽ
linktitle: Đường vẽ
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách vẽ một đường trên một trang bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tạo dòng tùy chỉnh.
type: docs
weight: 80
url: /vi/net/programming-with-graphs/drawing-line/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về mã nguồn C# sau đây để vẽ một đường bằng Aspose.PDF cho .NET.

Đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình trước khi bắt đầu. Ngoài ra còn có kiến thức cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã nguồn được cung cấp, bạn cần chỉ định thư mục mà bạn muốn lưu tệp PDF kết quả. Thay đổi biến "dataDir" thành thư mục mong muốn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo phiên bản tài liệu và thêm trang

Chúng tôi tạo một thể hiện của lớp Tài liệu và thêm một trang vào tài liệu này.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Bước 3: Đặt lề trang

Chúng tôi đặt lề trang thành 0 ở tất cả các bên.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Bước 4: Tạo đối tượng đồ thị và dòng đầu tiên

Chúng ta tạo một đối tượng Graph có kích thước bằng kích thước của trang và vẽ đường đầu tiên đi từ góc dưới bên trái đến góc trên bên phải của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Bước 5: Vẽ đường thứ hai

Chúng ta vẽ đường thứ hai đi từ góc trên bên trái đến góc dưới bên phải của trang.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Bước 6: Thêm đối tượng đồ thị vào trang

Chúng tôi thêm đối tượng Biểu đồ vào bộ sưu tập đoạn văn của trang.

```csharp
pg.Paragraphs.Add(graph);
```

## Bước 7: Lưu tệp PDF kết quả

Cuối cùng, chúng tôi lưu tệp PDF kết quả có tên "drawLine_out.pdf" trong thư mục đã chỉ định.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Mã nguồn mẫu cho Đường vẽ bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo phiên bản tài liệu
Document pDoc = new Document();
// Thêm trang vào bộ sưu tập trang của tài liệu PDF
Page pg = pDoc.Pages.Add();
// Đặt lề trang ở tất cả các bên là 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Tạo đối tượng Graph có Chiều rộng và Chiều cao bằng kích thước trang
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Tạo đối tượng dòng đầu tiên bắt đầu từ góc dưới bên trái đến góc trên bên phải của trang
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Thêm dòng vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(line);
// Vẽ đường từ góc trên bên trái của trang đến góc dưới bên phải của trang
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Thêm dòng vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(line2);
// Thêm đối tượng Graph vào bộ sưu tập đoạn văn của trang
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Lưu tệp PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách vẽ một đường bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để tạo các hình dạng hình học với các đường tùy chỉnh trong tệp PDF của mình.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Mục đích của hướng dẫn này là hướng dẫn bạn trong quá trình vẽ đường bằng Aspose.PDF cho .NET. Bạn sẽ tìm hiểu cách tạo dòng trên trang PDF và tùy chỉnh giao diện của chúng.

#### Hỏi: Những điều kiện tiên quyết nào được yêu cầu trước khi bắt đầu?

Trả lời: Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Kiến thức cơ bản về lập trình C# cũng được khuyến khích.

#### Hỏi: Làm cách nào để chỉ định thư mục lưu tệp PDF?

Đáp: Sửa đổi biến "dataDir" trong mã nguồn được cung cấp để cho biết thư mục mà bạn muốn lưu tệp PDF kết quả.

#### Hỏi: Làm cách nào để tạo dòng trên trang PDF?

Đáp: Hướng dẫn này trình bày cách tạo một đối tượng Đồ thị với các kích thước của trang và sau đó thêm các đối tượng Đường vào đó. Sửa đổi tọa độ và thuộc tính của đối tượng Line để tạo các đường mong muốn.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của các đường kẻ không?

Đáp: Có, bạn có thể tùy chỉnh hình thức của các đường bằng cách sửa đổi các thuộc tính của đối tượng Đường. Điều này bao gồm việc thay đổi tọa độ, màu sắc, độ dày và các thuộc tính đồ họa khác của chúng.

#### Hỏi: Làm cách nào để lưu tài liệu PDF sau khi vẽ các đường?

Đáp: Sau khi thêm đối tượng Graph với các đối tượng Line vào trang, bạn có thể lưu tài liệu PDF thu được bằng cách sử dụng`pDoc.Save(dataDir + "DrawingLine_out.pdf");` dòng trong mã nguồn được cung cấp.

#### Hỏi: Tôi có thể vẽ các đường có góc và hướng khác nhau không?

Đáp: Có, bạn có thể vẽ các đường có các góc và hướng khác nhau bằng cách điều chỉnh tọa độ và thuộc tính của các đối tượng Đường trong Biểu đồ.