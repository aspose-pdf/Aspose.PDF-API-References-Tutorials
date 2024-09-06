---
title: Thêm văn bản trong suốt vào tệp PDF
linktitle: Thêm văn bản trong suốt vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm văn bản trong suốt vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-text/add-transparent-text/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm văn bản trong suốt vào tài liệu PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn thêm văn bản trong suốt, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Tạo một phiên bản Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Thêm một trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Bước 6: Tạo đối tượng Graph
 Tạo một cái mới`Graph` đối tượng có chiều rộng và chiều cao cụ thể.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Bước 7: Tạo một hình chữ nhật có độ trong suốt
 Tạo một hình chữ nhật có kích thước cụ thể và đặt màu tô của nó thành màu trong suốt bằng cách sử dụng`Color.FromRgb` phương pháp.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Bước 8: Thêm đối tượng Graph vào trang
 Thêm vào`Graph` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(canvas);
```

## Bước 9: Đặt vị trí cho đối tượng Graph
 Đặt`IsChangePosition` tài sản của`Graph` phản đối`false` để ngăn không cho nó thay đổi vị trí.

```csharp
canvas. IsChangePosition = false;
```

## Bước 10: Tạo TextFragment có độ trong suốt
 Tạo một`TextFragment` đối tượng và đặt nội dung của nó thành văn bản mong muốn. Đặt`ForegroundColor` tài sản của`TextState` đến một màu sắc có độ trong suốt bằng cách sử dụng`Color.FromArgb` phương pháp.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Bước 11: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để Thêm Văn bản Trong suốt bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo phiên bản Tài liệu
Document doc = new Document();
// Tạo bộ sưu tập trang thành trang của tệp PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Tạo đối tượng Graph
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tạo phiên bản hình chữ nhật có kích thước nhất định
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Tạo đối tượng màu từ kênh màu Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Thêm hình chữ nhật vào bộ sưu tập hình dạng của đối tượng Graph
canvas.Shapes.Add(rect);
//Thêm đối tượng đồ thị vào tập hợp đoạn văn của đối tượng trang
page.Paragraphs.Add(canvas);
// Đặt giá trị không thay đổi vị trí cho đối tượng đồ thị
canvas.IsChangePosition = false;
// Tạo phiên bản TextFragment với giá trị mẫu
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Tạo đối tượng màu từ kênh Alpha
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Đặt thông tin màu cho trường hợp văn bản
text.TextState.ForegroundColor = color;
// Thêm văn bản vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Phần kết luận
Bạn đã thêm thành công văn bản trong suốt vào tài liệu PDF của mình bằng Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Trọng tâm của hướng dẫn này là gì?

A: Hướng dẫn này tập trung vào việc thêm văn bản trong suốt vào tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết để đạt được hiệu ứng này.

#### H: Những không gian tên nào cần được nhập cho hướng dẫn này?

A: Trong tệp mã mà bạn muốn thêm văn bản trong suốt, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để tạo một phiên bản Tài liệu mới?

 A: Ở Bước 4, bạn sẽ tạo một phiên bản mới`Document` đối tượng sử dụng mã được cung cấp.

#### H: Làm thế nào để thêm trang vào tài liệu?

 A: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập.

#### H: Làm thế nào để tạo một đối tượng Graph?

 A: Ở Bước 6, bạn sẽ tạo một`Graph` đối tượng có chiều rộng và chiều cao cụ thể.

#### H: Làm thế nào để tạo hình chữ nhật có độ trong suốt?

A: Ở Bước 7, bạn sẽ tạo một hình chữ nhật có kích thước cụ thể và đặt màu tô của nó thành màu trong suốt bằng cách sử dụng`Color.FromRgb` phương pháp.

#### H: Làm thế nào để thêm đối tượng Graph vào trang?

 A: Ở Bước 8, bạn sẽ thêm`Graph` phản đối việc thu thập đoạn văn của trang.

#### H: Làm thế nào để thiết lập vị trí cho đối tượng Đồ thị?

 A: Ở Bước 9, bạn sẽ thiết lập`IsChangePosition` tài sản của`Graph` phản đối`false` để ngăn không cho nó thay đổi vị trí.

#### H: Làm thế nào để tạo một TextFragment có tính trong suốt?

 A: Ở Bước 10, bạn sẽ tạo một`TextFragment` đối tượng và thiết lập nội dung của nó và`ForegroundColor` thuộc tính để đạt được văn bản trong suốt.

#### H: Làm thế nào để lưu tài liệu PDF?

 A: Ở Bước 11, bạn sẽ lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### H: Nội dung chính rút ra từ hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học cách thêm văn bản trong suốt vào tài liệu PDF bằng Aspose.PDF cho .NET. Điều này có thể hữu ích để tạo tài liệu PDF hấp dẫn và sáng tạo.