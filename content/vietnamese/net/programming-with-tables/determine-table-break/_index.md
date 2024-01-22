---
title: Xác định ngắt bảng trong tệp PDF
linktitle: Xác định ngắt bảng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách xác định ngắt bảng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-tables/determine-table-break/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách xác định ngắt bảng trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn trong C#. Ở cuối hướng dẫn này, bạn sẽ biết cách xác định xem một bảng có vượt quá lề trang hay không. Hãy bắt đầu!

## Bước 1: Thiết lập môi trường
Trước tiên, hãy đảm bảo bạn đã thiết lập môi trường phát triển C# của mình với Aspose.PDF cho .NET. Thêm tham chiếu vào thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tạo tài liệu PDF
 Ở bước này chúng ta tạo mới`Document` đối tượng đại diện cho tài liệu PDF.

```csharp
pdf-Document = new Document();
```

Tài liệu này sẽ được sử dụng để thêm các phần và bảng.

## Bước 3: Thêm phần và bảng
Bây giờ chúng ta sẽ thêm một phần vào tài liệu PDF của mình và tạo một bảng bên trong phần này.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Chúng tôi cũng chỉ định mức chênh lệch cao nhất là 300 điểm cho bảng. Bạn có thể điều chỉnh giá trị này theo nhu cầu của bạn.

## Bước 4: Thiết lập bảng
Trong bước này, chúng ta định cấu hình các thuộc tính của bảng, chẳng hạn như độ rộng và đường viền của cột.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Ở đây chúng ta xác định độ rộng của các cột trong bảng và đường viền ô. Bạn có thể điều chỉnh các giá trị này theo sở thích của mình.

## Bước 5: Thêm hàng và ô vào bảng
Bây giờ chúng ta sẽ tạo các hàng và ô trong bảng bằng vòng lặp.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Ở đây chúng tôi tạo 17 hàng trong bảng và thêm ba ô vào mỗi hàng. Bạn có thể điều chỉnh khóa theo nhu cầu của bạn.

## Bước 6: Xác định ngắt bảng
Bây giờ chúng ta sẽ xác định xem bảng có vượt quá lề trang hay không bằng cách so sánh chiều cao của trang với tổng chiều cao của các đối tượng trong bảng.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Chúng tôi tính toán chiều cao của trang và tổng chiều cao của các đối tượng có tính đến lề. Nếu chênh lệch từ 10 trở xuống, bảng sẽ vượt quá lề trang.

## Bước 7: Lưu tài liệu PDF
Cuối cùng, chúng tôi lưu tài liệu PDF cùng với kết quả.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Đảm bảo chỉ định đúng thư mục tài liệu. Tệp PDF kết quả sẽ được lưu với các ngắt bảng được xác định.

### Mã nguồn ví dụ cho Xác định ngắt bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một lớp PDF đối tượng
Document pdf = new Document();
// Thêm phần vào bộ sưu tập phần tài liệu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(table1);
// Đặt độ rộng cột của bảng
table1.ColumnWidths = "100 100 100";
// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Tạo đối tượng MarginInfo và đặt lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Đặt phần đệm ô mặc định cho đối tượng MarginInfo
table1.DefaultCellPadding = margin;
// Nếu bạn tăng bộ đếm lên 17, bàn sẽ bị hỏng
// Bởi vì nó không thể được cung cấp thêm nữa trên trang này
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Nhận thông tin Chiều cao trang
float PageHeight = (float)pdf.PageInfo.Height;
// Nhận thông tin tổng chiều cao của lề Trên & Dưới Trang,
// Lề trên của bảng và chiều cao của bảng.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Hiển thị chiều cao trang, chiều cao bảng, lề đầu bảng và đầu trang
// Và thông tin lề dưới
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Kiểm tra xem chúng tôi có khấu trừ tổng Lề trên của trang + Lề dưới của trang hay không
// + Lề trên cùng của bảng và chiều cao của bảng từ Chiều cao của trang trở xuống
// Hơn 10 (một hàng trung bình có thể lớn hơn 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Nếu giá trị nhỏ hơn 10 thì hiển thị thông báo.
	//Điều này cho thấy không thể đặt một hàng khác và nếu chúng ta thêm hàng mới
	// Hàng, bảng sẽ bị gãy. Nó phụ thuộc vào giá trị chiều cao của hàng.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Lưu tài liệu pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách xác định ngắt bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để kiểm tra xem bảng có vượt quá lề trang trong dự án C# của riêng bạn hay không.

### Câu hỏi thường gặp để xác định ngắt bảng trong tệp PDF

#### Câu hỏi: Mục đích của việc xác định ngắt bảng trong tài liệu PDF là gì?

Đáp: Mục đích của việc xác định ngắt bảng trong tài liệu PDF là để kiểm tra xem bảng có vượt quá lề trang hay không. Điều này đảm bảo rằng nội dung của bảng được hiển thị chính xác trong không gian trang có sẵn. Bằng cách phát hiện dấu ngắt bảng, bạn có thể xử lý tình trạng tràn nội dung và điều chỉnh bố cục bảng cho phù hợp.

#### Hỏi: Làm cách nào để điều chỉnh lề trên của bảng?

 Đáp: Trong mã nguồn C# được cung cấp, bạn có thể điều chỉnh lề trên của bảng bằng cách sửa đổi giá trị của`table1.Margin.Top`tài sản. Tăng hoặc giảm giá trị nếu cần để đặt lề trên mong muốn cho bảng.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của bảng, chẳng hạn như màu ô và cỡ chữ không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của bảng và các ô của bảng bằng cách sử dụng các thuộc tính và phương thức khác nhau do Aspose.PDF cung cấp cho .NET. Ví dụ: bạn có thể thay đổi màu nền ô, cỡ chữ, họ phông chữ, căn chỉnh văn bản, v.v. Tham khảo tài liệu chính thức để biết thêm thông tin về cách tùy chỉnh giao diện bảng.

#### Câu hỏi: Điều gì xảy ra nếu bảng vượt quá lề trang?

Đáp: Nếu bảng vượt quá lề trang, điều đó có thể dẫn đến việc cắt ngắn hoặc chồng chéo nội dung, khiến tài liệu PDF khó đọc và khó sắp xếp hơn. Bằng cách phát hiện ngắt bảng và xử lý tràn bảng, bạn có thể đảm bảo rằng nội dung vẫn được hiển thị chính xác trong vùng trang có sẵn.

#### Câu hỏi: Tôi có thể xác định ngắt bảng cho nhiều bảng trong cùng một tài liệu PDF không?

Đáp: Có, bạn có thể xác định ngắt bảng cho nhiều bảng trong cùng một tài liệu PDF. Chỉ cần lặp lại các bước cho mỗi bảng bạn muốn phân tích và điều chỉnh bố cục bảng nếu cần để tránh tràn nội dung.