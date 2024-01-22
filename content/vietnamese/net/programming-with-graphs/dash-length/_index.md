---
title: Độ dài dấu gạch ngang
linktitle: Độ dài dấu gạch ngang
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt độ dài dấu gạch ngang bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tùy chỉnh các mẫu dấu gạch ngang.
type: docs
weight: 70
url: /vi/net/programming-with-graphs/dash-length/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# sau đây để đặt độ dài dấu gạch ngang bằng Aspose.PDF cho .NET.

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
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Bước 4: Tạo đối tượng đường và cấu hình

Chúng tôi tạo một đối tượng Line với tọa độ được chỉ định và định cấu hình màu sắc cũng như độ dài của dấu gạch ngang.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Bước 5: Thêm dòng vào đối tượng đồ thị

Chúng ta thêm đường thẳng vào bộ sưu tập hình dạng của đối tượng Graph.

```csharp
canvas.Shapes.Add(line);
```

## Bước 6: Lưu tệp PDF kết quả

Cuối cùng, chúng tôi lưu tệp PDF kết quả có tên "DashLength_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Mã nguồn mẫu cho Độ dài dấu gạch ngang bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo phiên bản tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của đối tượng Document
Page page = doc.Pages.Add();
// Tạo đối tượng Vẽ với kích thước nhất định
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Thêm đối tượng vẽ vào bộ sưu tập đoạn văn của phiên bản trang
page.Paragraphs.Add(canvas);
// Tạo đối tượng Line
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Đặt màu cho đối tượng Line
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Chỉ định mảng gạch ngang cho đối tượng dòng
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Đặt pha gạch ngang cho phiên bản Line
line.GraphInfo.DashPhase = 1;
// Thêm dòng vào bộ sưu tập hình dạng của đối tượng vẽ
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách đặt độ dài dấu gạch ngang bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể sử dụng kiến thức này để tạo các dòng có mẫu gạch ngang tùy chỉnh trong tệp PDF của mình.

## Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Mục đích của hướng dẫn này là hướng dẫn bạn qua quá trình thiết lập độ dài dấu gạch ngang cho các dòng bằng Aspose.PDF cho .NET. Bạn sẽ tìm hiểu cách tạo dòng với các mẫu gạch ngang tùy chỉnh trong tệp PDF của mình.

#### Hỏi: Những điều kiện tiên quyết nào được yêu cầu trước khi bắt đầu?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Hiểu biết cơ bản về lập trình C# cũng được khuyến khích.

#### Hỏi: Làm cách nào để chỉ định thư mục lưu tệp PDF?

Đáp: Sửa đổi biến "dataDir" trong mã nguồn được cung cấp để cho biết thư mục mà bạn muốn lưu tệp PDF kết quả.

#### Câu hỏi: Làm cách nào để tạo một đường có mẫu gạch ngang tùy chỉnh?

 Đáp: Hướng dẫn này trình bày cách tạo một đối tượng Đường và định cấu hình màu sắc, mảng gạch ngang và pha gạch ngang của nó bằng cách sử dụng`GraphInfo` sự vật. Sửa đổi các cài đặt này để đạt được mẫu gạch ngang mong muốn.

#### Hỏi: Tôi có thể tùy chỉnh màu của đường kẻ không?

 Trả lời: Có, bạn có thể tùy chỉnh màu của đường bằng cách đặt`Color` tài sản của`GraphInfo` đối tượng được liên kết với Line.

#### Hỏi: Làm cách nào để lưu tài liệu PDF sau khi đặt độ dài dấu gạch ngang?

 Đáp: Sau khi định cấu hình đối tượng Line với mẫu gạch ngang mong muốn, bạn có thể lưu tài liệu PDF thu được bằng cách sử dụng`doc.Save(dataDir + "DashLength_out.pdf");` dòng trong mã nguồn được cung cấp.