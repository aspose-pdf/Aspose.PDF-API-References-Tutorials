---
title: Thêm đối tượng đường thẳng vào tệp PDF
linktitle: Thêm đối tượng đường thẳng vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm đối tượng đường tùy chỉnh vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-graphs/add-line-object/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước sử dụng mã nguồn C# sau để thêm đối tượng đường thẳng bằng Aspose.PDF cho .NET.

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

## Bước 3: Tạo Đối tượng đồ thị và thêm nó vào trang

Chúng tôi tạo một đối tượng Graph với các kích thước được chỉ định và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Bước 4: Tạo đối tượng đường và thêm vào biểu đồ

Chúng tôi tạo một đối tượng Đường thẳng có tọa độ được chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Bước 5: Thiết lập đường dây

Chúng ta có thể chỉ định các thuộc tính cho đường thẳng, chẳng hạn như kiểu nét gạch ngang và pha nét gạch ngang.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Bước 6: Lưu tệp PDF

Cuối cùng, chúng ta lưu tệp PDF kết quả với tên "AddLineObject_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Mã nguồn mẫu cho Thêm đối tượng dòng bằng Aspose.PDF cho .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Chỉ định màu tô cho đối tượng Graph
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Thêm đối tượng hình chữ nhật vào bộ sưu tập hình dạng của đối tượng Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích từng bước cách thêm đối tượng đường kẻ bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để tạo tài liệu PDF với các đường kẻ tùy chỉnh trong ứng dụng của mình.

### Câu hỏi thường gặp để thêm đối tượng đường thẳng vào tệp PDF

#### H: Mục đích của hướng dẫn này là gì?

A: Mục đích của hướng dẫn này là hướng dẫn bạn quy trình thêm đối tượng đường thẳng bằng Aspose.PDF cho .NET để cải thiện tài liệu PDF của bạn.

#### H: Cần có những điều kiện tiên quyết nào trước khi bắt đầu?

A: Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Ngoài ra, nên có hiểu biết cơ bản về lập trình C#.

#### H: Làm thế nào để chỉ định thư mục lưu tệp PDF?

A: Trong mã nguồn được cung cấp, bạn có thể sửa đổi biến "dataDir" để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### H: Mục đích của đối tượng Graph là gì?

A: Đối tượng Graph đóng vai trò là một container để vẽ các thành phần. Nó được tạo ra với các kích thước được chỉ định và được thêm vào bộ sưu tập đoạn văn của trang.

#### H: Làm thế nào để thêm đối tượng đường thẳng vào tài liệu PDF?

A: Để thêm đối tượng đường thẳng, hãy tạo một thể hiện của lớp Line với tọa độ được chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

#### H: Tôi có thể tùy chỉnh giao diện của dòng không?

A: Có, bạn có thể tùy chỉnh giao diện của đường bằng cách thiết lập các thuộc tính như kiểu nét gạch ngang và pha nét gạch ngang bằng cách sử dụng thuộc tính GraphInfo của đối tượng Đường thẳng.

#### H: Mục đích của việc chỉ định mảng gạch ngang và pha gạch ngang là gì?

A: Thuộc tính mảng gạch ngang và pha gạch ngang cho phép bạn tạo các đường nét đứt hoặc chấm với các mẫu cụ thể.

#### H: Làm thế nào để lưu tệp PDF sau khi thêm đối tượng đường thẳng?

 A: Sau khi thêm đối tượng đường thẳng, bạn có thể lưu tệp PDF kết quả bằng cách sử dụng`doc.Save(dataDir + "AddLineObject_out.pdf");` dòng trong mã nguồn được cung cấp.

#### H: Có mã nguồn mẫu nào có sẵn không?

A: Có, hướng dẫn này bao gồm mã nguồn mẫu mà bạn có thể tham khảo để thực hiện các bước được mô tả.