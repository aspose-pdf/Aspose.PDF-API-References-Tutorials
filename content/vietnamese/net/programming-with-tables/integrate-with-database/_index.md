---
title: Tích hợp với cơ sở dữ liệu trong tệp PDF
linktitle: Tích hợp với cơ sở dữ liệu trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Nhúng dữ liệu từ cơ sở dữ liệu vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-tables/integrate-with-database/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách nhúng dữ liệu từ cơ sở dữ liệu vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn trong C#. Khi kết thúc hướng dẫn này, bạn sẽ biết cách nhập dữ liệu bảng từ cơ sở dữ liệu vào tài liệu PDF. Hãy bắt đầu!

## Bước 1: Thiết lập môi trường
Đảm bảo bạn đã định cấu hình môi trường phát triển C# của mình bằng Aspose.PDF cho .NET. Thêm tham chiếu vào thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tạo DataTable
Chúng tôi tạo một phiên bản DataTable để thể hiện dữ liệu mà chúng tôi muốn nhúng vào tài liệu PDF. Trong ví dụ này, chúng tôi tạo một DataTable có ba cột: Nhân viên_ID, Tên nhân viên và Giới tính. Chúng tôi cũng thêm hai hàng vào DataTable với dữ liệu giả.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Bước 3: Tạo tài liệu và bảng PDF
Chúng tôi tạo một phiên bản Tài liệu và thêm một trang vào tài liệu này. Tiếp theo, chúng ta tạo một phiên bản Bảng để thể hiện bảng của mình trong tài liệu PDF. Chúng tôi xác định độ rộng cột của bảng và kiểu đường viền.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Bước 4: Nhập dữ liệu từ DataTable vào bảng
Chúng tôi sử dụng phương thức ImportDataTable để nhập dữ liệu từ DataTable vào bảng trong tài liệu PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Bước 5: Thêm bảng vào tài liệu
Chúng tôi thêm bảng vào bộ sưu tập đoạn văn của trang tài liệu.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Bước 6: Lưu tài liệu
Chúng tôi lưu tài liệu PDF với dữ liệu từ cơ sở dữ liệu được nhúng.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Chúc mừng! Bây giờ bạn đã biết cách nhúng dữ liệu cơ sở dữ liệu vào tài liệu PDF bằng Aspose.PDF cho .NET.

### Mã nguồn ví dụ cho Tích hợp với cơ sở dữ liệu bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Thêm 2 hàng vào đối tượng DataTable theo chương trình
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Tạo phiên bản tài liệu
Document doc = new Document();
doc.Pages.Add();
// Khởi tạo một phiên bản mới của Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt độ rộng cột của bảng
table.ColumnWidths = "40 100 100 100";
// Đặt màu đường viền bảng là LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Đặt đường viền cho ô trong bảng
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Thêm đối tượng bảng vào trang đầu tiên của tài liệu đầu vào
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Lưu tài liệu cập nhật chứa đối tượng bảng
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách nhúng dữ liệu từ cơ sở dữ liệu vào tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để nhập dữ liệu từ cơ sở dữ liệu của riêng bạn và hiển thị chúng trong tài liệu PDF. Khám phá thêm tài liệu Aspose.PDF để khám phá các tính năng và khả năng khác được cung cấp bởi thư viện mạnh mẽ này.

### Câu hỏi thường gặp về tích hợp với cơ sở dữ liệu trong tệp PDF

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET với các loại cơ sở dữ liệu khác nhau như MySQL, SQL Server hoặc Oracle không?

Trả lời: Có, bạn có thể sử dụng Aspose.PDF cho .NET với các loại cơ sở dữ liệu khác nhau như MySQL, SQL Server, Oracle và các loại khác. Aspose.PDF for .NET cung cấp các chức năng để đọc dữ liệu từ nhiều nguồn dữ liệu khác nhau, bao gồm cơ sở dữ liệu, tệp XML, v.v. Bạn có thể truy xuất dữ liệu từ loại cơ sở dữ liệu mong muốn của mình và điền dữ liệu đó vào DataTable hoặc bất kỳ cấu trúc dữ liệu nào khác tương thích với Aspose.PDF cho .NET.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh giao diện của bảng trong tài liệu PDF?

Trả lời: Bạn có thể tùy chỉnh giao diện của bảng trong tài liệu PDF bằng cách sử dụng nhiều thuộc tính khác nhau do thư viện Aspose.PDF cho .NET cung cấp. Ví dụ: bạn có thể đặt các kiểu đường viền, màu nền, kiểu phông chữ và căn chỉnh khác nhau cho bảng và các ô của bảng. Tham khảo tài liệu Aspose.PDF for .NET để biết thêm chi tiết về cách tùy chỉnh giao diện bảng.

#### Câu hỏi: Có thể thêm siêu liên kết hoặc thành phần tương tác vào dữ liệu được nhập từ cơ sở dữ liệu không?

Đáp: Có, bạn có thể thêm siêu liên kết hoặc các thành phần tương tác khác vào dữ liệu được nhập từ cơ sở dữ liệu. Aspose.PDF for .NET hỗ trợ thêm siêu liên kết, dấu trang và các thành phần tương tác khác vào tài liệu PDF. Bạn có thể thao tác nội dung trong DataTable trước khi nhập nội dung đó vào bảng và bao gồm các siêu liên kết hoặc các tính năng tương tác khác.

#### Câu hỏi: Tôi có thể phân trang bảng nếu nó vượt quá một số hàng nhất định không?

 Đáp: Có, bạn có thể đánh số trang trong bảng nếu nó vượt quá một số hàng nhất định. Để đạt được điều này, bạn có thể sử dụng`IsInNewPage`thuộc tính của đối tượng Hàng để cho biết rằng một trang mới sẽ bắt đầu sau một hàng cụ thể. Bạn có thể tính toán số hàng hiển thị trên mỗi trang và đặt`IsInNewPage` tài sản tương ứng.

#### Câu hỏi: Làm cách nào tôi có thể xuất tài liệu PDF có dữ liệu cơ sở dữ liệu được nhúng sang các định dạng tệp khác nhau như DOCX hoặc XLSX?

Trả lời: Aspose.PDF for .NET cho phép bạn chuyển đổi tài liệu PDF sang nhiều định dạng tệp khác, bao gồm DOCX (Microsoft Word) và XLSX (Microsoft Excel). Bạn có thể sử dụng thư viện Aspose.PDF cho .NET kết hợp với các thư viện Aspose khác như Aspose.Words và Aspose.Cells để đạt được điều này. Trước tiên, hãy lưu tài liệu PDF có dữ liệu cơ sở dữ liệu nhúng, sau đó sử dụng thư viện Aspose tương ứng để chuyển đổi nó sang định dạng tệp bạn muốn.