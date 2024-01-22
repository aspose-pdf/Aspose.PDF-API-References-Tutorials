---
title: Xuất dữ liệu bảng tính Excel sang bảng
linktitle: Xuất dữ liệu bảng tính Excel sang bảng
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Xuất dữ liệu từ trang tính Excel sang bảng PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 70
url: /vi/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách xuất dữ liệu từ bảng tính Excel và tạo bảng trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn từng bước về mã nguồn và giải thích chi tiết từng phần. Đến cuối hướng dẫn này, bạn sẽ có thể tạo tệp PDF với các bảng chứa dữ liệu từ bảng tính Excel. Bắt đầu nào!

## Yêu cầu
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Visual Studio được cài đặt trên máy của bạn
- Thư viện Aspose.PDF cho .NET được thêm vào dự án của bạn

## Bước 1: Thiết lập môi trường
Để bắt đầu, hãy tạo một dự án C# mới trong Visual Studio. Thêm tham chiếu vào thư viện Aspose.PDF cho .NET bằng cách nhấp chuột phải vào dự án của bạn trong Solution Explorer, chọn "Quản lý gói NuGet" và tìm kiếm "Aspose.PDF." Cài đặt gói và bạn đã sẵn sàng.

## Bước 2: Tải bảng tính Excel
Trong bước đầu tiên của mã, chúng tôi xác định đường dẫn đến thư mục chứa tài liệu Excel. Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thư mục thực nơi chứa tệp Excel của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Ở đây, chúng tôi sử dụng thư viện Aspose.Cells để tải sổ làm việc Excel. Đảm bảo thay thế "newBook1.xlsx" bằng tên tệp Excel của bạn.

## Bước 3: Truy cập bảng tính
 Tiếp theo, chúng ta cần truy cập vào bảng tính đầu tiên trong file Excel. Chúng tôi thực hiện việc này bằng cách sử dụng`Worksheets` bộ sưu tập của`Workbook` sự vật.

```csharp
// Truy cập bảng tính đầu tiên trong tệp Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Nếu file Excel của bạn chứa nhiều bảng tính, bạn có thể thay đổi giá trị chỉ mục`[0]` để truy cập một bảng tính khác.

## Bước 4: Xuất dữ liệu sang DataTable
 Bây giờ, chúng ta sẽ xuất nội dung của bảng tính Excel sang một tập tin`DataTable` sự vật. Chúng tôi chỉ định phạm vi ô cần xuất bằng cách sử dụng`ExportDataTable` phương pháp.

```csharp
// Xuất nội dung 7 hàng và 2 cột bắt đầu từ ô đầu tiên sang DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Trong ví dụ này, chúng tôi xuất tất cả các hàng và cột bắt đầu từ ô đầu tiên (0, 0) đến ô cuối cùng trong trang tính. Đặt phạm vi thích hợp dựa trên yêu cầu của bạn.

## Bước 5: Tạo tài liệu PDF
Bây giờ, chúng tôi sẽ tạo một tài liệu PDF mới bằng thư viện Aspose.PDF.

```csharp
// Khởi tạo một phiên bản Tài liệu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Điều này tạo ra một tài liệu PDF trống để chúng ta có thể thêm nội dung.

## Bước 6: Thêm trang và bảng
Để hiển thị dữ liệu ở định dạng bảng, chúng ta cần thêm một trang và bảng vào tài liệu PDF.

```csharp
// Tạo một trang trong phiên bản tài liệu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tạo đối tượng Bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm đối tượng Table vào bộ sưu tập đoạn văn của phần
sec1.Paragraphs.Add(tab1);
```

Ở đây, chúng ta tạo một trang mới và một đối tượng bảng. Sau đó chúng tôi thêm bảng vào bộ sưu tập đoạn văn của trang.

## Bước 7: Thiết lập thuộc tính bảng
Trước khi nhập dữ liệu, chúng ta cần đặt một số thuộc tính của bảng, chẳng hạn như độ rộng cột và đường viền ô mặc định.

```csharp
// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "40 100 100";

// Đặt đường viền ô mặc định của bảng bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Trong ví dụ này, chúng tôi đặt độ rộng cột thành 40, 100 và 100 đơn vị. Điều chỉnh các giá trị dựa trên dữ liệu của bạn. Chúng tôi cũng đặt đường viền ô mặc định để hiển thị đường viền trên tất cả các cạnh của mỗi ô.

## Bước 8: Nhập dữ liệu vào bảng
 Bây giờ chúng ta sẽ nhập dữ liệu từ`DataTable` đối tượng vào bảng bằng cách sử dụng`ImportDataTable` phương pháp.

```csharp
// Nhập dữ liệu vào đối tượng Bảng từ DataTable được tạo ở trên
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Ở đây, chúng tôi chỉ định phạm vi hàng và cột cần nhập. Trong ví dụ này, chúng tôi nhập tất cả các hàng và cột từ`dataTable` sự vật.

## Bước 9: Định dạng bảng
Để nâng cao hình thức của bảng, chúng ta có thể áp dụng định dạng cho các ô hoặc hàng cụ thể. Trong bước này, chúng ta sẽ định dạng hàng đầu tiên và các hàng thay thế của bảng.

```csharp
// Lấy hàng đầu tiên từ bảng
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Định dạng hàng đầu tiên
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Đặt màu nền cho các ô ở hàng đầu tiên
     curCell.BackgroundColor = Color.Blue;// Đặt mặt cho các ô ở hàng đầu tiên
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Đặt màu phông chữ của các ô ở hàng đầu tiên
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Đặt căn chỉnh văn bản cho các ô ở hàng đầu tiên
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Định dạng hàng thay thế
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Đặt màu nền của các ô ở hàng xen kẽ
         curCell.BackgroundColor = Color.Gray;
        
         // Đặt màu văn bản của các ô trong các hàng xen kẽ
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Ở đây, chúng tôi lặp qua các ô ở hàng đầu tiên và đặt màu nền, kiểu chữ, màu phông chữ và căn chỉnh văn bản cho chúng. Sau đó, chúng tôi lặp qua tất cả các ô trong các hàng thay thế và đặt màu nền và màu văn bản cho chúng.

## Bước 10: Lưu tài liệu PDF
Cuối cùng, chúng tôi lưu tài liệu PDF vào vị trí đã chỉ định.

```csharp
// Lưu tệp PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thư mục và tên tệp mong muốn cho tệp PDF đầu ra.

### Mã nguồn ví dụ để xuất dữ liệu bảng tính Excel sang bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Truy cập bảng tính đầu tiên trong tệp Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Xuất nội dung 7 hàng và 2 cột bắt đầu từ ô đầu tiên sang DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Khởi tạo một tài liệu ngay lập tức
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Tạo một trang trong phiên bản tài liệu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Tạo đối tượng Bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Thêm đối tượng Table vào bộ sưu tập đoạn văn của phần
sec1.Paragraphs.Add(tab1);

// Đặt độ rộng cột của bảng. Chúng ta cần chỉ định ColumnCount theo cách thủ công.
// Vì bảng tính excel hiện tại có ba cột nên chúng tôi đang chỉ định cùng một số lượng
tab1.ColumnWidths = "40 100 100";

// Đặt đường viền ô mặc định của bảng bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Nhập dữ liệu vào đối tượng Bảng từ DataTable được tạo ở trên
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Lấy hàng đầu tiên từ bảng
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Lặp lại qua tất cả các ô ở hàng đầu tiên và đặt màu nền của chúng thành màu xanh lam
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Đặt nền cho tất cả các ô ở hàng đầu tiên của bảng.
	curCell.BackgroundColor = Color.Blue;
	// Đặt kiểu chữ cho các ô ở hàng đầu tiên trong bảng.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Đặt màu phông chữ của tất cả các ô ở hàng đầu tiên của bảng.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Đặt căn chỉnh văn bản cho các ô của hàng đầu tiên làm Căn giữa.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Lặp lại qua tất cả các ô ở hàng đầu tiên và đặt màu nền của chúng thành màu xanh lam
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Đặt màu nền cho tất cả các ô ngoại trừ hàng đầu tiên.
		curCell.BackgroundColor = Color.Gray;
		// Đặt màu Văn bản của tất cả các ô ngoại trừ hàng đầu tiên.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Lưu tệp PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xuất dữ liệu từ trang tính Excel sang bảng PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi đã đề cập đến quy trình từng bước tải trang tính Excel, tạo tài liệu PDF, thêm bảng, nhập dữ liệu và định dạng bảng. Bây giờ bạn có thể tạo tệp PDF với các bảng chứa dữ liệu Excel theo chương trình.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của việc xuất dữ liệu bảng tính Excel sang bảng PDF là gì?

Đáp: Việc xuất dữ liệu bảng tính Excel sang bảng PDF cho phép bạn trình bày dữ liệu ở định dạng có cấu trúc và có tổ chức. Nó cho phép bạn tạo các tệp PDF với các bảng chứa dữ liệu từ bảng tính Excel, giúp chia sẻ và lưu giữ thông tin ở định dạng tài liệu di động dễ dàng hơn.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của bảng PDF không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của bảng PDF bằng cách sử dụng nhiều thuộc tính khác nhau do Aspose.PDF cung cấp cho .NET. Trong mã nguồn C# được cung cấp, bạn có thể sửa đổi độ rộng cột, đường viền ô, căn chỉnh văn bản, kiểu phông chữ, v.v. để phù hợp với yêu cầu cụ thể của bạn.

#### Hỏi: Làm cách nào để xử lý các tệp Excel có nhiều trang tính?

 Đáp: Trong mã C# được cung cấp, chúng tôi đã truy cập trang tính đầu tiên trong tệp Excel bằng chỉ mục`[0]` . Nếu tệp Excel của bạn chứa nhiều trang tính, bạn có thể truy cập chúng bằng cách thay đổi giá trị chỉ mục tương ứng, chẳng hạn như`[1]` cho bảng tính thứ hai hoặc`[2]` cho bảng tính thứ ba.

#### Câu hỏi: Tôi có thể áp dụng định dạng khác cho các hàng hoặc ô cụ thể trong bảng PDF không?

Đáp: Có, bạn có thể áp dụng định dạng khác cho các hàng hoặc ô cụ thể trong bảng PDF. Trong mã nguồn C# được cung cấp, chúng tôi đã trình bày cách định dạng hàng đầu tiên và các hàng xen kẽ khác nhau bằng cách thay đổi màu nền, kiểu phông chữ và màu phông chữ của chúng. Bạn có thể áp dụng các kỹ thuật định dạng tương tự cho bất kỳ hàng hoặc ô cụ thể nào nếu cần.

#### Câu hỏi: Aspose.PDF cho .NET có phải là thư viện duy nhất cho phép xuất dữ liệu Excel sang bảng PDF không?

Trả lời: Aspose.PDF for .NET là một thư viện mạnh mẽ để làm việc với các tài liệu PDF trong các ứng dụng .NET. Mặc dù có thể có sẵn các thư viện khác nhưng Aspose.PDF cho .NET cung cấp nhiều tính năng và khả năng để tạo, thao tác và xuất tệp PDF với các bảng từ dữ liệu Excel, khiến nó trở thành lựa chọn phổ biến cho các tác vụ như vậy.