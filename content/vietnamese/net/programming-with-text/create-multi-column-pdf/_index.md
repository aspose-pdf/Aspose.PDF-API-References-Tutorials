---
title: Tạo PDF nhiều cột
linktitle: Tạo PDF nhiều cột
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tạo tệp PDF nhiều cột bằng Aspose.PDF cho .NET.
type: docs
weight: 110
url: /vi/net/programming-with-text/create-multi-column-pdf/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình tạo tệp PDF nhiều cột bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã nơi bạn muốn tạo tệp PDF nhiều cột, hãy thêm các lệnh sử dụng sau ở đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Tạo phiên bản Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Đặt lề trang
 Chỉ định thông tin lề trái và lề phải cho tệp PDF bằng cách sử dụng`PageInfo.Margin` tài sản của`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Bước 6: Thêm trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = doc.Pages.Add();
```

## Bước 7: Tạo đối tượng Graph và thêm đường thẳng
 Tạo một cái mới`Graph` đối tượng có kích thước cụ thể và thêm một dòng vào nó. Sau đó, thêm`Graph` phản đối`Paragraphs` bộ sưu tập của trang.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Bước 8: Thêm văn bản tiêu đề với định dạng HTML
 Tạo ra một`HtmlFragment` đối tượng và đặt nội dung của nó thành văn bản HTML mong muốn. Sau đó, thêm đoạn này vào`Paragraphs` bộ sưu tập của trang.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Bước 9: Tạo FloatBox có nhiều cột
 Tạo một`FloatingBox` đối tượng và thiết lập số lượng cột và khoảng cách cột. Sau đó, thêm các đoạn văn bản và một dòng vào`Paragraphs` bộ sưu tập của`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Bước 10: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir);
```

### Mã nguồn mẫu để tạo Pdf nhiều cột bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Chỉ định thông tin lề trái cho tệp PDF
doc.PageInfo.Margin.Left = 40;
//Chỉ định thông tin lề phải cho tệp PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Thêm dòng vào bộ sưu tập đoạn văn của đối tượng phần
page.Paragraphs.Add(graph1);
// Xác định tọa độ cho đường
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Tạo biến chuỗi có văn bản chứa thẻ html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Tạo đoạn văn bản chứa văn bản HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Thêm bốn cột trong phần
box.ColumnInfo.ColumnCount = 2;
// Đặt khoảng cách giữa các cột
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Tạo một đối tượng đồ thị để vẽ một đường
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Xác định tọa độ cho đường
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Thêm dòng vào bộ sưu tập đoạn văn của đối tượng phần
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã tạo thành công tệp PDF nhiều cột bằng Aspose.PDF cho .NET. Bây giờ có thể tìm thấy tệp PDF kết quả tại đường dẫn tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Trọng tâm của hướng dẫn này là gì?

Hướng dẫn này tập trung vào việc hướng dẫn bạn trong quá trình tạo tệp PDF nhiều cột bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết để đạt được điều này.

#### Câu hỏi: Tôi nên nhập những không gian tên nào cho hướng dẫn này?

Đáp: Trong tệp mã nơi bạn muốn tạo tệp PDF nhiều cột, hãy nhập các vùng tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Câu hỏi: Làm cách nào để tạo một phiên bản Tài liệu mới?

 Đáp: Ở Bước 4, bạn sẽ khởi tạo một`Document` đối tượng bằng cách sử dụng mã được cung cấp.

#### Hỏi: Làm cách nào để đặt lề trang?

 Đáp: Ở Bước 5, bạn sẽ sử dụng`PageInfo.Margin` tài sản của`Document` để chỉ định thông tin lề trái và lề phải cho tệp PDF.

#### Hỏi: Làm cách nào để thêm một trang vào tài liệu?

 Đáp: Ở Bước 6, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập.

#### Câu hỏi: Làm cách nào để tạo một đối tượng Đồ thị và thêm một đường?

 Đáp: Ở Bước 7, bạn sẽ tạo một`Graph` đối tượng, thêm một dòng vào nó, rồi thêm`Graph` phản đối`Paragraphs` bộ sưu tập của trang.

#### Hỏi: Làm cách nào để thêm văn bản tiêu đề có định dạng HTML?

 Đáp: Ở Bước 8, bạn sẽ tạo một`HtmlFragment` đối tượng và đặt nội dung của nó thành văn bản HTML mong muốn, sau đó thêm đoạn vào`Paragraphs` bộ sưu tập của trang.

#### Câu hỏi: Làm cách nào để tạo một FloatBox có nhiều cột?

 Đáp: Ở Bước 9, bạn sẽ tạo một`FloatingBox` đối tượng có nhiều cột và khoảng cách cột, sau đó thêm các đoạn văn bản và một dòng vào`Paragraphs` bộ sưu tập của`FloatingBox`.

#### Hỏi: Làm cách nào để lưu tài liệu PDF?

 Đáp: Ở Bước 10, bạn sẽ lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### Hỏi: Điểm chính của hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo tài liệu PDF nhiều cột bằng Aspose.PDF cho .NET. Điều này có thể hữu ích khi hiển thị nội dung theo bố cục có cấu trúc và có tổ chức.