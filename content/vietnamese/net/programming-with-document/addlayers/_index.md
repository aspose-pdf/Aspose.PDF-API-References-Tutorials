---
title: Thêm lớp vào tệp PDF
linktitle: Thêm lớp vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm lớp vào tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với hướng dẫn mã để tạo và lưu các tệp PDF xếp lớp.
type: docs
weight: 20
url: /vi/net/programming-with-document/addlayers/
---
Để thêm lớp vào tệp PDF, chúng tôi sẽ sử dụng Aspose.PDF cho .NET. Thư viện này cho phép chúng ta làm việc với các tệp PDF trong ứng dụng .NET một cách hiệu quả. Thực hiện theo hướng dẫn từng bước bên dưới để thêm lớp bằng Aspose.PDF cho .NET.

## Bước 1: Tạo một tài liệu PDF mới

 Bắt đầu bằng cách tạo một phiên bản mới của`Document` lớp được cung cấp bởi Aspose.PDF cho .NET. Đây sẽ đóng vai trò là tài liệu PDF nơi chúng tôi sẽ thêm các lớp.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Bước 2: Thêm trang vào tài liệu

 Tiếp theo, thêm một trang vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập ở`Document` lớp học.

```csharp
Page page = doc.Pages.Add();
```

## Bước 3: Tạo và thêm lớp vào trang

 Tạo các thể hiện của`Layer` class cho mỗi lớp bạn muốn thêm vào tệp PDF. Chỉ định một mã định danh duy nhất và tên cho mỗi lớp.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

Trong hướng dẫn này, chúng tôi đã thêm ba lớp với màu sắc và tên khác nhau vào trang.

## Bước 4: Lưu tệp PDF

 Lưu tệp PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Mã này sẽ lưu tệp PDF đã sửa đổi vào thư mục được chỉ định.

### Mã nguồn ví dụ về Thêm lớp vào trang PDF bằng Aspose.PDF cho .NET

```csharp            
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Phần kết luận

Trong bài viết này, chúng tôi đã cung cấp hướng dẫn từng bước để thêm lớp vào tệp PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn và sử dụng các hướng dẫn về mã được cung cấp, bạn có thể dễ dàng kết hợp các lớp vào tài liệu PDF của mình. Lớp cho phép bạn sắp xếp và kiểm soát khả năng hiển thị của nội dung, cung cấp trải nghiệm tương tác và tùy chỉnh hơn cho người dùng của bạn.


### Câu hỏi thường gặp về thêm lớp vào tệp PDF

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Trả lời: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PDF một cách hiệu quả trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để tạo, sửa đổi và thao tác các tài liệu PDF.

#### Câu hỏi: Lớp PDF là gì?

Trả lời: Các lớp PDF, còn được gọi là Nhóm nội dung tùy chọn (OCG), cho phép bạn kiểm soát khả năng hiển thị và hình thức của nội dung cụ thể trong tệp PDF. Chúng rất hữu ích cho việc tổ chức nội dung và tạo tài liệu tương tác.

#### Câu hỏi: Tôi có thể thêm nhiều lớp vào tệp PDF bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể thêm nhiều lớp vào tệp PDF bằng Aspose.PDF cho .NET. Mỗi lớp có thể có mã định danh và tên riêng, như được minh họa trong hướng dẫn.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh giao diện của các lớp?

Trả lời: Bạn có thể tùy chỉnh giao diện của các lớp bằng cách chỉ định các thuộc tính khác nhau, chẳng hạn như màu sắc, độ mờ và khả năng hiển thị. Aspose.PDF for .NET cung cấp nhiều tùy chọn khác nhau để đạt được điều này.

#### Câu hỏi: Aspose.PDF cho .NET có phù hợp với các dự án chuyên nghiệp không?

Trả lời: Có, Aspose.PDF for .NET là một thư viện đáng tin cậy và được sử dụng rộng rãi để thao tác PDF trong các dự án chuyên nghiệp. Nó cung cấp chức năng mở rộng và hiệu suất tuyệt vời để làm việc với các tệp PDF trong các ứng dụng .NET.