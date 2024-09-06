---
title: Xuất dữ liệu bảng tính Excel sang bảng
linktitle: Xuất dữ liệu bảng tính Excel sang bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Xuất dữ liệu từ bảng tính Excel sang bảng PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 70
url: /vi/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Trong hướng dẫn này, chúng ta sẽ học cách xuất dữ liệu từ bảng tính Excel và tạo bảng trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng ta sẽ hướng dẫn từng bước mã nguồn và giải thích chi tiết từng phần. Đến cuối hướng dẫn này, bạn sẽ có thể tạo tệp PDF với các bảng chứa dữ liệu từ bảng tính Excel. Hãy bắt đầu nào!

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Visual Studio được cài đặt trên máy của bạn
- Thư viện Aspose.PDF cho .NET đã được thêm vào dự án của bạn

## Bước 1: Thiết lập môi trường
Để bắt đầu, hãy tạo một dự án C# mới trong Visual Studio. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET bằng cách nhấp chuột phải vào dự án của bạn trong Solution Explorer, chọn "Manage NuGet Packages" và tìm kiếm "Aspose.PDF". Cài đặt gói và bạn đã sẵn sàng.

## Bước 2: Tải bảng tính Excel
Trong bước đầu tiên của mã, chúng ta định nghĩa đường dẫn đến thư mục chứa tài liệu Excel. Thay thế "YOUR DOCUMENT DIRECTORY" bằng đường dẫn thư mục thực tế nơi tệp Excel của bạn nằm.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Ở đây, chúng tôi sử dụng thư viện Aspose.Cells để tải sổ làm việc Excel. Đảm bảo thay thế "newBook1.xlsx" bằng tên tệp Excel của bạn.

## Bước 3: Truy cập vào Bảng tính
 Tiếp theo, chúng ta cần truy cập vào bảng tính đầu tiên trong tệp Excel. Chúng ta thực hiện việc này bằng cách sử dụng`Worksheets` bộ sưu tập của`Workbook` sự vật.

```csharp
// Truy cập vào trang tính đầu tiên trong tệp Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Nếu tệp Excel của bạn chứa nhiều bảng tính, bạn có thể thay đổi giá trị chỉ mục`[0]` để truy cập vào một bảng tính khác.

## Bước 4: Xuất dữ liệu vào DataTable
 Bây giờ, chúng ta sẽ xuất nội dung của bảng tính Excel sang`DataTable` đối tượng. Chúng tôi chỉ định phạm vi ô để xuất bằng cách sử dụng`ExportDataTable` phương pháp.

```csharp
// Xuất nội dung của 7 hàng và 2 cột bắt đầu từ ô thứ 1 đến DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Trong ví dụ này, chúng tôi xuất tất cả các hàng và cột bắt đầu từ ô đầu tiên (0, 0) đến ô cuối cùng trong bảng tính. Đặt phạm vi phù hợp dựa trên yêu cầu của bạn.

## Bước 5: Tạo tài liệu PDF
Bây giờ, chúng ta sẽ tạo một tài liệu PDF mới bằng thư viện Aspose.PDF.

```csharp
// Khởi tạo một phiên bản Tài liệu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Thao tác này sẽ tạo ra một tài liệu PDF trống để chúng ta có thể thêm nội dung.

## Bước 6: Thêm Trang và Bảng
Để hiển thị dữ liệu dưới dạng bảng, chúng ta cần thêm một trang và một bảng vào tài liệu PDF.

```csharp
// Tạo một trang trong phiên bản tài liệu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tạo một đối tượng Bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm đối tượng Bảng vào bộ sưu tập đoạn văn của phần
sec1.Paragraphs.Add(tab1);
```

Ở đây, chúng ta tạo một trang mới và một đối tượng bảng. Sau đó, chúng ta thêm bảng vào bộ sưu tập đoạn văn của trang.

## Bước 7: Thiết lập Thuộc tính Bảng
Trước khi nhập dữ liệu, chúng ta cần thiết lập một số thuộc tính của bảng, chẳng hạn như độ rộng cột và đường viền ô mặc định.

```csharp
// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "40 100 100";

// Đặt đường viền ô mặc định của bảng bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Trong ví dụ này, chúng tôi đặt độ rộng cột thành 40, 100 và 100 đơn vị. Điều chỉnh các giá trị dựa trên dữ liệu của bạn. Chúng tôi cũng đặt đường viền ô mặc định để hiển thị đường viền ở tất cả các cạnh của mỗi ô.

## Bước 8: Nhập dữ liệu vào bảng
 Bây giờ, chúng ta sẽ nhập dữ liệu từ`DataTable` đối tượng vào bảng bằng cách sử dụng`ImportDataTable` phương pháp.

```csharp
// Nhập dữ liệu vào đối tượng Bảng từ DataTable được tạo ở trên
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Ở đây, chúng tôi chỉ định phạm vi các hàng và cột để nhập. Trong ví dụ này, chúng tôi nhập tất cả các hàng và cột từ`dataTable` sự vật.

## Bước 9: Định dạng bảng
Để cải thiện giao diện của bảng, chúng ta có thể áp dụng định dạng cho các ô hoặc hàng cụ thể. Trong bước này, chúng ta sẽ định dạng hàng đầu tiên và các hàng xen kẽ của bảng.

```csharp
// Lấy hàng đầu tiên từ bảng
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Định dạng hàng đầu tiên
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Đặt màu nền của các ô ở hàng đầu tiên
     curCell.BackgroundColor = Color.Blue;// Đặt mặt cho các ô ở hàng đầu tiên
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Đặt màu chữ của các ô ở hàng đầu tiên
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Đặt căn chỉnh văn bản cho các ô ở hàng đầu tiên
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Định dạng hàng thay thế
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Đặt màu nền của các ô trong các hàng xen kẽ
         curCell.BackgroundColor = Color.Gray;
        
         // Đặt màu văn bản của các ô trong các hàng xen kẽ
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Ở đây, chúng ta lặp lại qua các ô ở hàng đầu tiên và thiết lập màu nền, kiểu chữ, màu chữ và căn chỉnh văn bản. Sau đó, chúng ta lặp lại qua tất cả các ô ở các hàng xen kẽ và thiết lập màu nền và màu văn bản.

## Bước 10: Lưu tài liệu PDF
Cuối cùng, chúng ta lưu tài liệu PDF vào vị trí đã chỉ định.

```csharp
// Lưu PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Đảm bảo thay thế "YOUR DOCUMENT DIRECTORY" bằng đường dẫn thư mục và tên tệp mong muốn cho tệp PDF đầu ra.

### Mã nguồn ví dụ để Xuất dữ liệu bảng tính Excel sang bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Truy cập vào trang tính đầu tiên trong tệp Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Xuất nội dung của 7 hàng và 2 cột bắt đầu từ ô thứ 1 đến DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Khởi tạo một phiên bản Tài liệu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Tạo một trang trong phiên bản tài liệu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tạo một đối tượng Bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm đối tượng Bảng vào bộ sưu tập đoạn văn của phần
sec1.Paragraphs.Add(tab1);

// Thiết lập độ rộng cột của bảng. Chúng ta cần chỉ định ColumnCount theo cách thủ công.
// Vì bảng tính excel hiện tại có ba cột, nên chúng tôi đang chỉ định cùng một số lượng
tab1.ColumnWidths = "40 100 100";

// Đặt đường viền ô mặc định của bảng bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Nhập dữ liệu vào đối tượng Bảng từ DataTable được tạo ở trên
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Lấy hàng đầu tiên từ bảng
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Lặp lại tất cả các ô ở hàng thứ nhất và đặt màu nền của chúng thành màu xanh lam
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Đặt nền cho tất cả các ô ở hàng đầu tiên của bảng.
	curCell.BackgroundColor = Color.Blue;
	// Đặt mặt phông chữ cho các ô của hàng đầu tiên trong bảng.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Thiết lập màu phông chữ cho tất cả các ô ở hàng đầu tiên của bảng.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Đặt căn chỉnh văn bản cho các ô của hàng đầu tiên thành Trung tâm.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Lặp lại tất cả các ô ở hàng thứ nhất và đặt màu nền của chúng thành màu xanh lam
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Đặt màu nền cho tất cả các ô ngoại trừ hàng đầu tiên.
		curCell.BackgroundColor = Color.Gray;
		// Đặt màu Văn bản cho tất cả các ô ngoại trừ hàng đầu tiên.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Lưu tệp PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xuất dữ liệu từ bảng tính Excel sang bảng PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi đã trình bày từng bước về quy trình tải bảng tính Excel, tạo tài liệu PDF, thêm bảng, nhập dữ liệu và định dạng bảng. Bây giờ bạn có thể tạo tệp PDF với các bảng chứa dữ liệu Excel theo chương trình.

### Câu hỏi thường gặp

#### H: Mục đích của việc xuất dữ liệu bảng tính Excel sang bảng PDF là gì?

A: Xuất dữ liệu bảng tính Excel sang bảng PDF cho phép bạn trình bày dữ liệu theo định dạng có cấu trúc và được sắp xếp. Nó cho phép bạn tạo tệp PDF với các bảng chứa dữ liệu từ bảng tính Excel, giúp chia sẻ và lưu giữ thông tin dễ dàng hơn ở định dạng tài liệu di động.

#### H: Tôi có thể tùy chỉnh giao diện của bảng PDF không?

A: Có, bạn có thể tùy chỉnh giao diện của bảng PDF bằng nhiều thuộc tính khác nhau do Aspose.PDF cung cấp cho .NET. Trong mã nguồn C# được cung cấp, bạn có thể sửa đổi độ rộng cột, đường viền ô, căn chỉnh văn bản, kiểu phông chữ, v.v. để phù hợp với yêu cầu cụ thể của bạn.

#### H: Tôi phải xử lý các tệp Excel có nhiều bảng tính như thế nào?

 A: Trong mã C# được cung cấp, chúng tôi đã truy cập vào bảng tính đầu tiên trong tệp Excel bằng cách sử dụng chỉ mục`[0]` . Nếu tệp Excel của bạn chứa nhiều bảng tính, bạn có thể truy cập chúng bằng cách thay đổi giá trị chỉ mục cho phù hợp, chẳng hạn như`[1]` cho bài tập thứ hai hoặc`[2]` cho bài tập thứ ba.

#### H: Tôi có thể áp dụng định dạng khác nhau cho các hàng hoặc ô cụ thể trong bảng PDF không?

A: Có, bạn có thể áp dụng định dạng khác nhau cho các hàng hoặc ô cụ thể trong bảng PDF. Trong mã nguồn C# được cung cấp, chúng tôi đã trình bày cách định dạng hàng đầu tiên và các hàng xen kẽ khác nhau bằng cách thay đổi màu nền, kiểu phông chữ và màu phông chữ của chúng. Bạn có thể áp dụng các kỹ thuật định dạng tương tự cho bất kỳ hàng hoặc ô cụ thể nào khi cần.

#### H: Aspose.PDF cho .NET có phải là thư viện duy nhất cho phép xuất dữ liệu Excel sang bảng PDF không?

A: Aspose.PDF for .NET là một thư viện mạnh mẽ để làm việc với các tài liệu PDF trong các ứng dụng .NET. Mặc dù có thể có các thư viện khác, Aspose.PDF for .NET cung cấp nhiều tính năng và khả năng để tạo, thao tác và xuất các tệp PDF có bảng từ dữ liệu Excel, khiến nó trở thành lựa chọn phổ biến cho các tác vụ như vậy.