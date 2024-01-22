---
title: Thêm đối tượng dòng vào tệp PDF
linktitle: Thêm đối tượng dòng vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm đối tượng dòng tùy chỉnh vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-graphs/add-line-object/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# sau đây để thêm đối tượng dòng bằng Aspose.PDF cho .NET.

Đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình trước khi bắt đầu. Ngoài ra còn có kiến thức cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã nguồn được cung cấp, bạn cần chỉ định thư mục mà bạn muốn lưu tệp PDF kết quả. Thay đổi biến "dataDir" thành thư mục mong muốn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo phiên bản tài liệu và thêm trang

Chúng tôi tạo một thể hiện của lớp Tài liệu và thêm một trang vào tài liệu này.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng đồ thị và thêm nó vào trang

Chúng tôi tạo một đối tượng Biểu đồ với các kích thước được chỉ định và thêm nó vào bộ sưu tập đoạn văn của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Bước 4: Tạo đối tượng đường và thêm vào biểu đồ

Chúng ta tạo một đối tượng Line với tọa độ đã chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Bước 5: Thiết lập dòng

Chúng ta có thể chỉ định các thuộc tính cho dòng, chẳng hạn như loại dấu gạch ngang và pha gạch ngang.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Bước 6: Lưu tệp PDF

Cuối cùng, chúng tôi lưu tệp PDF kết quả có tên "AddLineObject_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Mã nguồn mẫu cho Thêm đối tượng dòng bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo phiên bản tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Tạo phiên bản đồ thị
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Thêm đối tượng biểu đồ vào bộ sưu tập đoạn văn của phiên bản trang
page.Paragraphs.Add(graph);
// Tạo phiên bản hình chữ nhật
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

Trong hướng dẫn này, chúng tôi đã giải thích từng bước cách thêm đối tượng dòng bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể sử dụng kiến thức này để tạo tài liệu PDF với các dòng tùy chỉnh trong ứng dụng của mình.

### Câu hỏi thường gặp về thêm đối tượng dòng vào tệp PDF

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này nhằm mục đích hướng dẫn bạn trong quá trình thêm đối tượng dòng bằng Aspose.PDF cho .NET để cải thiện tài liệu PDF của bạn.

#### Hỏi: Những điều kiện tiên quyết nào được yêu cầu trước khi bắt đầu?

Trả lời: Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Ngoài ra, nên có hiểu biết cơ bản về lập trình C#.

#### Hỏi: Làm cách nào để chỉ định thư mục lưu tệp PDF?

Trả lời: Trong mã nguồn được cung cấp, bạn có thể sửa đổi biến "dataDir" để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### Câu hỏi: Mục đích của đối tượng Graph là gì?

Trả lời: Đối tượng Graph đóng vai trò là nơi chứa các phần tử vẽ. Nó được tạo với các kích thước được chỉ định và được thêm vào bộ sưu tập đoạn văn của trang.

#### Câu hỏi: Làm cách nào tôi có thể thêm đối tượng dòng vào tài liệu PDF?

Đáp: Để thêm một đối tượng đường, hãy tạo một thể hiện của lớp Đường với các tọa độ được chỉ định và thêm nó vào bộ sưu tập hình dạng của biểu đồ.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của dòng không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của đường bằng cách đặt các thuộc tính như loại dấu gạch ngang và pha gạch ngang bằng cách sử dụng thuộc tính GraphInfo của đối tượng Đường.

#### Câu hỏi: Mục đích của việc chỉ định mảng gạch ngang và pha gạch ngang là gì?

Trả lời: Thuộc tính mảng gạch ngang và pha gạch ngang cho phép bạn tạo các đường đứt nét hoặc chấm với các mẫu cụ thể.

#### Câu hỏi: Làm cách nào để lưu tệp PDF sau khi thêm đối tượng dòng?

 Đáp: Sau khi thêm đối tượng dòng, bạn có thể lưu tệp PDF thu được bằng cách sử dụng`doc.Save(dataDir + "AddLineObject_out.pdf");` dòng trong mã nguồn được cung cấp.

#### Hỏi: Có sẵn mã nguồn mẫu không?

Đáp: Có, hướng dẫn này bao gồm mã nguồn mẫu mà bạn có thể tham khảo để triển khai các bước được mô tả.