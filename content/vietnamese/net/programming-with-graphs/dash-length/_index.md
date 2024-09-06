---
title: Chiều dài dấu gạch ngang
linktitle: Chiều dài dấu gạch ngang
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thiết lập độ dài của dấu gạch ngang bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tùy chỉnh mẫu dấu gạch ngang.
type: docs
weight: 70
url: /vi/net/programming-with-graphs/dash-length/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước sử dụng mã nguồn C# sau để thiết lập độ dài của dấu gạch ngang bằng Aspose.PDF cho .NET.

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

## Bước 3: Tạo Đối tượng đồ thị và thêm nó vào trang

Chúng tôi tạo một đối tượng Graph với các kích thước được chỉ định và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Bước 4: Tạo đối tượng đường thẳng và cấu hình

Chúng ta tạo một đối tượng Line với tọa độ được chỉ định và cấu hình màu sắc và độ dài của các nét gạch ngang.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Bước 5: Thêm Đường vào Đối tượng Đồ thị

Chúng ta thêm đường thẳng vào bộ sưu tập hình dạng của đối tượng Graph.

```csharp
canvas.Shapes.Add(line);
```

## Bước 6: Lưu tệp PDF kết quả

Cuối cùng, chúng ta lưu tệp PDF kết quả với tên "DashLength_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Mã nguồn mẫu cho Dash Length sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo phiên bản Tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của đối tượng Tài liệu
Page page = doc.Pages.Add();
// Tạo đối tượng bản vẽ có kích thước nhất định
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Thêm đối tượng vẽ vào tập hợp đoạn văn của trang
page.Paragraphs.Add(canvas);
// Tạo đối tượng Line
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Đặt màu cho đối tượng Line
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Chỉ định mảng gạch ngang cho đối tượng đường thẳng
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Đặt pha gạch ngang cho thể hiện Line
line.GraphInfo.DashPhase = 1;
// Thêm đường thẳng vào bộ sưu tập hình dạng của đối tượng vẽ
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách thiết lập độ dài của dấu gạch ngang bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để tạo các dòng có mẫu dấu gạch ngang tùy chỉnh trong tệp PDF của mình.

## Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Mục đích của hướng dẫn này là hướng dẫn bạn quy trình thiết lập độ dài của dấu gạch ngang cho các dòng bằng Aspose.PDF cho .NET. Bạn sẽ học cách tạo các dòng với các mẫu dấu gạch ngang tùy chỉnh trong các tệp PDF của mình.

#### H: Cần có những điều kiện tiên quyết nào trước khi bắt đầu?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Bạn cũng nên có hiểu biết cơ bản về lập trình C#.

#### H: Làm thế nào để chỉ định thư mục lưu tệp PDF?

A: Sửa đổi biến "dataDir" trong mã nguồn được cung cấp để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### H: Làm thế nào để tạo một đường thẳng có mẫu gạch ngang tùy chỉnh?

 A: Hướng dẫn này trình bày cách tạo đối tượng Line và cấu hình màu, mảng gạch ngang và pha gạch ngang của đối tượng đó bằng cách sử dụng`GraphInfo` đối tượng. Sửa đổi các thiết lập này để đạt được mẫu gạch ngang mong muốn.

#### Q: Tôi có thể tùy chỉnh màu của đường kẻ không?

 A: Có, bạn có thể tùy chỉnh màu của đường bằng cách thiết lập`Color` tài sản của`GraphInfo` đối tượng liên quan đến Đường thẳng.

#### H: Làm thế nào để lưu tài liệu PDF sau khi thiết lập độ dài dấu gạch ngang?

 A: Sau khi cấu hình đối tượng Line với mẫu gạch ngang mong muốn, bạn có thể lưu tài liệu PDF kết quả bằng cách sử dụng`doc.Save(dataDir + "DashLength_out.pdf");` dòng trong mã nguồn được cung cấp.