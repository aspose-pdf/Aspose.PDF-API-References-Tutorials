---
title: Thêm đối tượng SVG vào tệp PDF
linktitle: Thêm đối tượng SVG vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng thêm các đối tượng SVG vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-tables/add-svg-object/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm đối tượng SVG vào tệp PDF bằng thư viện Aspose.PDF cho .NET. SVG (Scalable Vector Graphics) là định dạng phổ biến cho đồ họa vector có thể dễ dàng thu nhỏ mà không làm giảm chất lượng. Với Aspose.PDF, bạn có thể thêm đối tượng SVG vào tài liệu PDF của mình theo chương trình.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt Visual Studio
- Đã cài đặt thư viện Aspose.PDF cho .NET

## Bước 1: Thiết lập Môi trường

Đầu tiên, hãy thiết lập môi trường bằng cách tạo một dự án C# mới trong Visual Studio. Mở Visual Studio và làm theo các bước sau:

1. Nhấp vào "Tệp" > "Mới" > "Dự án" để tạo một dự án mới.
2. Chọn mẫu "Console App (.NET Framework)" hoặc "Console App (.NET Core)", tùy thuộc vào thiết lập của bạn.
3. Chọn tên và vị trí phù hợp cho dự án của bạn, sau đó nhấp vào "Tạo".

## Bước 2: Tạo đối tượng tài liệu và hình ảnh

Trong bước này, chúng ta sẽ tạo các đối tượng cần thiết cho tài liệu PDF và hình ảnh SVG của mình. Mở tệp C# của dự án và thêm mã sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Đối tượng Tài liệu tức thời
Document doc = new Document();
// Tạo một phiên bản hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Bước 3: Thiết lập Thuộc tính Hình ảnh

Tiếp theo, chúng ta sẽ thiết lập các thuộc tính cho hình ảnh SVG của mình. Chúng ta sẽ chỉ định loại tệp là SVG, đường dẫn đến tệp SVG và kích thước của hình ảnh. Thêm mã sau vào sau bước trước:

```csharp
// Đặt loại hình ảnh là SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Đường dẫn đến tệp nguồn
img.File = dataDir + "SVGToPDF.svg";
// Đặt chiều rộng cho trường hợp hình ảnh
img. FixWidth = 50;
// Đặt chiều cao cho phiên bản hình ảnh
img.FixHeight = 50;
```

## Bước 4: Tạo và cấu hình bảng

Bây giờ, hãy tạo một đối tượng bảng và thiết lập độ rộng cột. Chúng ta sẽ tạo một bảng có hai cột, mỗi cột có độ rộng là 100 đơn vị. Thêm mã sau:

```csharp
// Tạo bảng thể hiện
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt chiều rộng cho các ô của bảng
table. ColumnWidths = "100 100";
```

## Bước 5: Thêm ô vào bảng

Trong bước này, chúng ta sẽ thêm một hàng và các ô vào bảng. Mỗi hàng đại diện cho một hàng ngang trong bảng và các ô được thêm vào các hàng. Thêm mã sau:

```csharp
//Tạo đối tượng hàng và thêm nó vào thể hiện bảng
Aspose.Pdf.Row row = table.Rows.Add();
// Tạo đối tượng ô và thêm nó vào thể hiện hàng
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Bước 6: Thêm văn bản và hình ảnh vào ô

Tiếp theo, chúng ta hãy thêm văn bản và hình ảnh SVG vào các ô của bảng. Chúng ta sẽ thêm văn bản "First cell" vào ô đầu tiên và hình ảnh SVG vào ô thứ hai. Thêm mã sau:

```csharp
// Thêm đoạn văn bản vào bộ sưu tập đoạn văn của đối tượng ô
cell.Paragraphs.Add(new TextFragment("First cell"));
// Thêm một ô khác vào đối tượng hàng
cell = row. Cells. Add();
// Thêm hình ảnh SVG vào bộ sưu tập đoạn văn của trường hợp ô được thêm gần đây
cell.Paragraphs.Add(img);
```

## Bước 7: Tạo và Thêm Trang vào Tài liệu

Bây giờ, hãy tạo một đối tượng trang và thêm nó vào tài liệu. Bảng sẽ được thêm vào bộ sưu tập đoạn văn của trang. Thêm mã sau:

```csharp
// Tạo đối tượng trang và thêm nó vào bộ sưu tập trang của phiên bản tài liệu
Page page = doc.Pages.Add();
// Thêm bảng vào bộ sưu tập đoạn văn của đối tượng trang
page.Paragraphs.Add(table);
```

## Bước 8: Lưu tệp PDF

Cuối cùng, chúng ta sẽ lưu tệp PDF vào vị trí đã chỉ định. Thêm mã sau:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Mã nguồn ví dụ để thêm đối tượng SVG bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Tạo một phiên bản hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Đặt loại hình ảnh là SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Đường dẫn đến tệp nguồn
img.File = dataDir + "SVGToPDF.svg";
// Đặt chiều rộng cho trường hợp hình ảnh
img.FixWidth = 50;
// Đặt chiều cao cho phiên bản hình ảnh
img.FixHeight = 50;
// Tạo phiên bản bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt chiều rộng cho các ô của bảng
table.ColumnWidths = "100 100";
//Tạo đối tượng hàng và thêm nó vào thể hiện bảng
Aspose.Pdf.Row row = table.Rows.Add();
// Tạo đối tượng ô và thêm nó vào thể hiện hàng
Aspose.Pdf.Cell cell = row.Cells.Add();
// Thêm đoạn văn bản vào bộ sưu tập đoạn văn của đối tượng ô
cell.Paragraphs.Add(new TextFragment("First cell"));
// Thêm một ô khác vào đối tượng hàng
cell = row.Cells.Add();
// Thêm hình ảnh SVG vào bộ sưu tập đoạn văn của trường hợp ô được thêm gần đây
cell.Paragraphs.Add(img);
// Tạo đối tượng trang và thêm nó vào bộ sưu tập trang của phiên bản tài liệu
Page page = doc.Pages.Add();
// Thêm bảng vào bộ sưu tập đoạn văn của đối tượng trang
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thêm đối tượng SVG vào tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi đã trình bày từng bước về quy trình tạo tài liệu, thiết lập môi trường, thêm hình ảnh SVG vào ô bảng và lưu tệp PDF. Bây giờ bạn có thể kết hợp các đối tượng SVG vào tài liệu PDF của mình theo chương trình.

### Câu hỏi thường gặp để thêm đối tượng SVG vào tệp PDF

#### H: Tôi có thể thêm nhiều đối tượng SVG vào tài liệu PDF không?

 A: Có, bạn có thể thêm nhiều đối tượng SVG vào tài liệu PDF. Chỉ cần tạo và cấu hình thêm`Aspose.Pdf.Image` các trường hợp cho mỗi hình ảnh SVG mà bạn muốn thêm, sau đó thêm chúng vào các ô bảng hoặc đoạn văn mong muốn trong tài liệu PDF.

#### H: Làm thế nào để điều chỉnh kích thước và vị trí của hình ảnh SVG trong ô bảng?

 A: Để điều chỉnh kích thước và vị trí của hình ảnh SVG trong ô bảng, bạn có thể sửa đổi`FixWidth` Và`FixHeight` tính chất của`Aspose.Pdf.Image`Ví dụ. Bạn cũng có thể sử dụng các thuộc tính khác như`HorizontalAlignment` Và`VerticalAlignment` của ô bảng để kiểm soát vị trí.

#### H: Có thể thêm văn bản bên cạnh hình ảnh SVG trong cùng một ô của bảng không?

 A: Có, có thể thêm văn bản bên cạnh hình ảnh SVG trong cùng một ô bảng. Bạn có thể sử dụng`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` phương pháp thêm văn bản vào ô cùng với hình ảnh SVG.

#### H: Tôi có thể thêm siêu liên kết vào hình ảnh SVG không?

 A: Có, bạn có thể thêm siêu liên kết vào hình ảnh SVG bằng cách sử dụng`Hyperlink` tài sản của`Aspose.Pdf.Image` Ví dụ. Đặt URL siêu liên kết hoặc hành động để làm cho hình ảnh có thể nhấp được.

#### H: Aspose.PDF cho .NET có tương thích với .NET Core 3.1 hoặc phiên bản mới hơn không?

A: Có, Aspose.PDF cho .NET tương thích với .NET Core 3.1 và các phiên bản mới hơn. Bạn có thể sử dụng nó trong cả ứng dụng .NET Framework và .NET Core.