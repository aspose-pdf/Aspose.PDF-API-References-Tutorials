---
title: Xác định ngắt bảng trong tệp PDF
linktitle: Xác định ngắt bảng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xác định ngắt bảng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-tables/determine-table-break/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách xác định ngắt bảng trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn bằng C# từng bước. Vào cuối hướng dẫn này, bạn sẽ biết cách xác định xem bảng có vượt quá lề trang hay không. Hãy bắt đầu nào!

## Bước 1: Thiết lập môi trường
Trước tiên, hãy đảm bảo bạn đã thiết lập môi trường phát triển C# của mình với Aspose.PDF cho .NET. Thêm tham chiếu đến thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tạo tài liệu PDF
 Trong bước này, chúng ta tạo một cái mới`Document` đối tượng để đại diện cho tài liệu PDF.

```csharp
pdf-Document = new Document();
```

Tài liệu này sẽ được sử dụng để thêm phần và bảng.

## Bước 3: Thêm phần và bảng
Bây giờ chúng ta sẽ thêm một phần vào tài liệu PDF và tạo một bảng bên trong phần này.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Chúng tôi cũng chỉ định lề trên là 300 điểm cho bảng. Bạn có thể điều chỉnh giá trị này theo nhu cầu của mình.

## Bước 4: Thiết lập bảng
Ở bước này, chúng ta sẽ cấu hình các thuộc tính của bảng, chẳng hạn như độ rộng cột và đường viền.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Ở đây chúng ta xác định chiều rộng của các cột bảng và đường viền ô. Bạn có thể điều chỉnh các giá trị này theo sở thích của mình.

## Bước 5: Thêm hàng và ô vào bảng
Bây giờ chúng ta sẽ tạo các hàng và ô trong bảng bằng cách sử dụng vòng lặp.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Ở đây chúng ta tạo 17 hàng trong bảng và thêm ba ô vào mỗi hàng. Bạn có thể điều chỉnh khóa theo nhu cầu của mình.

## Bước 6: Xác định ngắt bảng
Bây giờ chúng ta sẽ xác định xem bảng có vượt quá lề trang hay không bằng cách so sánh chiều cao của trang với tổng chiều cao của các đối tượng trong bảng.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Chúng tôi tính toán chiều cao của trang và tổng chiều cao của các đối tượng có tính đến lề. Nếu chênh lệch là 10 hoặc ít hơn, bảng sẽ vượt quá lề trang.

## Bước 7: Lưu tài liệu PDF
Cuối cùng, chúng ta lưu tài liệu PDF cùng với kết quả.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Hãy đảm bảo chỉ định đúng thư mục tài liệu. Tệp PDF kết quả sẽ được lưu với các ngắt bảng đã xác định.

### Mã nguồn ví dụ để Xác định ngắt bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một lớp đối tượng PDF
Document pdf = new Document();
// Thêm phần vào bộ sưu tập phần tài liệu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(table1);
// Thiết lập với chiều rộng cột của bảng
table1.ColumnWidths = "100 100 100";
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Tạo đối tượng MarginInfo và thiết lập lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Đặt khoảng đệm ô mặc định thành đối tượng MarginInfo
table1.DefaultCellPadding = margin;
// Nếu bạn tăng bộ đếm lên 17, bàn sẽ bị hỏng
// Bởi vì nó không thể được chứa thêm trên trang này nữa
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Nhận thông tin về Chiều cao trang
float PageHeight = (float)pdf.PageInfo.Height;
// Lấy thông tin tổng chiều cao của lề trên và dưới của trang,
// Lề trên cùng của bảng và chiều cao của bảng.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Hiển thị Chiều cao trang, Chiều cao bảng, Lề đầu bảng và Đầu trang
// Và thông tin lề dưới
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Kiểm tra xem chúng ta có trừ tổng của Lề trên trang + Lề dưới trang không
// + Lề đầu bảng và chiều cao bảng từ Chiều cao trang và nhỏ hơn
// Hơn 10 (một hàng trung bình có thể lớn hơn 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Nếu giá trị nhỏ hơn 10 thì hiển thị thông báo.
	//Điều đó cho thấy rằng không thể đặt một hàng khác và nếu chúng ta thêm hàng mới
	// Hàng, bảng sẽ bị hỏng. Tùy thuộc vào giá trị chiều cao của hàng.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Lưu tài liệu pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xác định ngắt bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để kiểm tra xem bảng có vượt quá lề trang trong các dự án C# của riêng bạn không.

### Câu hỏi thường gặp để xác định ngắt bảng trong tệp PDF

#### H: Mục đích của việc xác định ngắt bảng trong tài liệu PDF là gì?

A: Mục đích của việc xác định ngắt bảng trong tài liệu PDF là để kiểm tra xem bảng có vượt quá lề trang hay không. Điều này đảm bảo rằng nội dung của bảng được hiển thị chính xác trong không gian trang khả dụng. Bằng cách phát hiện ngắt bảng, bạn có thể xử lý tình trạng tràn nội dung và điều chỉnh bố cục bảng cho phù hợp.

#### H: Làm thế nào để điều chỉnh lề trên của bảng?

 A: Trong mã nguồn C# được cung cấp, bạn có thể điều chỉnh lề trên cùng của bảng bằng cách sửa đổi giá trị của`table1.Margin.Top`thuộc tính. Tăng hoặc giảm giá trị tùy ý để đặt lề trên mong muốn cho bảng.

#### H: Tôi có thể tùy chỉnh giao diện của bảng như màu ô và kích thước phông chữ không?

A: Có, bạn có thể tùy chỉnh giao diện của bảng và các ô của bảng bằng nhiều thuộc tính và phương pháp khác nhau do Aspose.PDF cung cấp cho .NET. Ví dụ, bạn có thể thay đổi màu nền ô, kích thước phông chữ, họ phông chữ, căn chỉnh văn bản, v.v. Tham khảo tài liệu chính thức để biết thêm thông tin về cách tùy chỉnh giao diện của bảng.

#### H: Điều gì xảy ra nếu bảng vượt quá lề trang?

A: Nếu bảng vượt quá lề trang, có thể dẫn đến việc cắt bớt hoặc chồng chéo nội dung, khiến tài liệu PDF khó đọc và khó sắp xếp hơn. Bằng cách phát hiện các ngắt bảng và xử lý tràn, bạn có thể đảm bảo rằng nội dung vẫn được hiển thị đúng trong phạm vi trang khả dụng.

#### H: Tôi có thể xác định ngắt bảng cho nhiều bảng trong cùng một tài liệu PDF không?

A: Có, bạn có thể xác định ngắt bảng cho nhiều bảng trong cùng một tài liệu PDF. Chỉ cần lặp lại các bước cho mỗi bảng bạn muốn phân tích và điều chỉnh bố cục bảng khi cần thiết để tránh tràn nội dung.