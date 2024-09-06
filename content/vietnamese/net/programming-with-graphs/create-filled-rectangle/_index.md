---
title: Tạo hình chữ nhật đã tô
linktitle: Tạo hình chữ nhật đã tô
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo hình chữ nhật tô màu bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tùy chỉnh màu tô.
type: docs
weight: 50
url: /vi/net/programming-with-graphs/create-filled-rectangle/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước sử dụng mã nguồn C# sau để tạo hình chữ nhật tô màu bằng Aspose.PDF cho .NET.

Đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển trước khi bắt đầu. Ngoài ra, bạn cũng cần có kiến thức cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã nguồn được cung cấp, bạn cần chỉ định thư mục mà bạn muốn lưu tệp PDF kết quả. Thay đổi biến "dataDir" thành thư mục mong muốn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo một phiên bản tài liệu và thêm một trang

Chúng tôi tạo một thể hiện của lớp Document và thêm một trang vào tài liệu này.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng đồ thị và thêm vào trang

Chúng tôi tạo một đối tượng Graph với các kích thước được chỉ định và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Bước 4: Tạo đối tượng hình chữ nhật và thêm vào biểu đồ

Chúng ta tạo một đối tượng Hình chữ nhật có kích thước được chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Bước 5: Thiết lập màu tô

Chúng ta có thể chỉ định màu tô cho hình chữ nhật bằng cách sử dụng thuộc tính FillColor của đối tượng GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Bước 6: Lưu tệp PDF kết quả

Cuối cùng, chúng ta lưu tệp PDF kết quả với tên "CreateFilledRectangle_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Mã nguồn mẫu cho Tạo hình chữ nhật đã tô bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo phiên bản Tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Tạo phiên bản đồ thị
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Thêm đối tượng đồ thị vào tập hợp đoạn văn của trang
page.Paragraphs.Add(graph);
// Tạo thể hiện hình chữ nhật
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Chỉ định màu tô cho đối tượng Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Thêm đối tượng hình chữ nhật vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách tạo hình chữ nhật được tô màu bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để tạo các hình dạng hình học với màu tô tùy chỉnh trong tệp PDF của mình.

## Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Mục đích của hướng dẫn này là hướng dẫn bạn quy trình tạo hình chữ nhật tô màu bằng Aspose.PDF cho .NET, cho phép bạn thêm các hình dạng hình học tùy chỉnh với màu tô vào tệp PDF của mình.

#### H: Cần có những điều kiện tiên quyết nào trước khi bắt đầu?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Ngoài ra, nên có hiểu biết cơ bản về lập trình C#.

#### H: Làm thế nào để chỉ định thư mục lưu tệp PDF?

A: Trong mã nguồn được cung cấp, bạn có thể sửa đổi biến "dataDir" để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### H: Mục đích của đối tượng Graph là gì?

A: Đối tượng Graph hoạt động như một container để vẽ các thành phần. Nó được tạo ra với các kích thước được chỉ định và được thêm vào bộ sưu tập đoạn văn của trang.

#### H: Làm thế nào để thêm hình chữ nhật tô màu vào tài liệu PDF?

A: Để thêm một hình chữ nhật được tô màu, hãy tạo một thể hiện của lớp Rectangle với các kích thước và màu tô được chỉ định, sau đó thêm nó vào bộ sưu tập hình dạng của biểu đồ.

#### H: Tôi có thể tùy chỉnh kích thước và màu nền của hình chữ nhật không?

 A: Có, bạn có thể tùy chỉnh kích thước và màu tô của hình chữ nhật bằng cách sửa đổi các tham số được truyền cho`Aspose.Pdf.Drawing.Rectangle` hàm tạo và thiết lập thuộc tính FillColor.

#### H: Làm thế nào để lưu tệp PDF kết quả sau khi tạo hình chữ nhật đã tô màu?

 A: Sau khi tạo hình chữ nhật đã tô màu, bạn có thể lưu tệp PDF kết quả bằng cách sử dụng`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` dòng trong mã nguồn được cung cấp.