---
title: Thẻ HTML bên trong bảng trong tệp PDF
linktitle: Thẻ HTML bên trong bảng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng thẻ HTML bên trong bảng trong tệp PDF với Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-tables/html-tags-inside-table/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng các thẻ HTML bên trong bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn trong C#. Khi kết thúc hướng dẫn này, bạn sẽ biết cách chèn nội dung HTML vào bảng trong tài liệu PDF. Hãy bắt đầu!

## Bước 1: Thiết lập môi trường
Đảm bảo bạn đã định cấu hình môi trường phát triển C# của mình bằng Aspose.PDF cho .NET. Thêm tham chiếu vào thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tạo dữ liệu bảng
Chúng tôi tạo một DataTable chứa cột "dữ liệu" kiểu Chuỗi. Sau đó, chúng tôi thêm các hàng vào DataTable này bằng nội dung HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Bước 3: Tạo tài liệu và bảng
Chúng tôi tạo một tài liệu PDF mới và thêm một trang trong tài liệu này. Tiếp theo, chúng ta khởi tạo một thể hiện của lớp Table và thiết lập các thuộc tính của bảng.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Bước 4: Nhập dữ liệu vào bảng
Chúng tôi nhập dữ liệu từ DataTable vào bảng bằng phương thức "ImportDataTable". Chúng tôi chỉ định các tham số phương thức để cho biết phạm vi hàng và cột nào của DataTable sẽ được nhập.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Bước 5: Thêm bảng vào tài liệu
Chúng tôi thêm bảng vào trang tài liệu.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Bước 6: Lưu tài liệu
Chúng ta lưu tài liệu PDF kèm theo bảng chứa nội dung HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Mã nguồn mẫu cho Thẻ HTML Bên trong Bảng sử dụng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Khởi tạo một phiên bản mới của Bảng
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Đặt độ rộng cột của bảng
tableProvider.ColumnWidths = "400 50 ";
// Đặt màu đường viền bảng là LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Đặt đường viền cho ô trong bảng
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng thẻ HTML bên trong bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để chèn nội dung HTML vào ô bảng trong tài liệu PDF bằng C#.

### Câu hỏi thường gặp về thẻ HTML bên trong bảng trong tệp PDF

#### Câu hỏi: Tôi có thể sử dụng các thẻ và thuộc tính HTML khác bên trong các ô của bảng không?

 Đáp: Có, bạn có thể sử dụng nhiều thẻ HTML và thuộc tính khác nhau bên trong các ô của bảng, chẳng hạn như`<b>`, `<i>`, `<a>`và nhiều cái khác. Aspose.PDF for .NET hỗ trợ nhiều thành phần và kiểu HTML mà bạn có thể sử dụng để định dạng nội dung trong các ô bảng.

#### Câu hỏi: Tôi có thể áp dụng các kiểu CSS cho nội dung HTML bên trong các ô của bảng không?

Đáp: Có, bạn có thể áp dụng các kiểu CSS cho nội dung HTML bên trong các ô của bảng. Aspose.PDF for .NET cung cấp hỗ trợ cho các kiểu CSS cơ bản có thể áp dụng cho các thành phần HTML.

#### Câu hỏi: Có thể thêm hình ảnh cùng với nội dung HTML bên trong các ô của bảng không?

 Đáp: Có, bạn có thể thêm hình ảnh cùng với nội dung HTML bên trong các ô của bảng. Bạn có thể sử dụng HTML`<img>` thẻ để bao gồm hình ảnh từ nhiều nguồn khác nhau, chẳng hạn như tệp cục bộ hoặc URL.

#### Câu hỏi: Làm cách nào tôi có thể chỉ định các độ rộng cột khác nhau cho bảng?

 Đáp: Bạn có thể chỉ định độ rộng cột khác nhau cho bảng bằng cách sử dụng`ColumnWidths` thuộc tính của bảng. Thuộc tính này lấy một chuỗi chứa các giá trị được phân tách bằng dấu cách, trong đó mỗi giá trị biểu thị chiều rộng của một cột tính bằng điểm.

#### Câu hỏi: Tôi có thể sử dụng các bảng lồng nhau bên trong một ô có nội dung HTML không?

Đáp: Có, bạn có thể sử dụng các bảng lồng nhau bên trong một ô có nội dung HTML. Bạn có thể tạo các phiên bản bảng riêng biệt và thêm chúng như một phần của nội dung HTML bên trong một ô để đạt được hiệu ứng lồng nhau.