---
title: Thêm Bảng Vào Tệp PDF
linktitle: Thêm Bảng Vào Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng thêm bảng vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-tables/add-table/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm bảng vào tệp PDF bằng Aspose.PDF for .NET. Chúng tôi sẽ giải thích từng bước của đoạn mã được cung cấp và cung cấp hướng dẫn toàn diện để giúp bạn hiểu và triển khai chức năng trong các dự án của riêng bạn.

## Giới thiệu

Tài liệu PDF được sử dụng rộng rãi để chia sẻ và lưu trữ thông tin ở định dạng di động. Thêm bảng vào tài liệu PDF có thể cải thiện giao diện trực quan của chúng và làm cho việc trình bày dữ liệu có tổ chức và có cấu trúc hơn. Aspose.PDF for .NET cung cấp một cách thuận tiện để thêm bảng vào tài liệu PDF hiện có hoặc tạo bảng mới từ đầu.

## Aspose.PDF dành cho .NET là gì?

Aspose.PDF for .NET là một thư viện mạnh mẽ và giàu tính năng cho phép các nhà phát triển .NET tạo, thao tác và chuyển đổi các tài liệu PDF theo chương trình. Nó cung cấp nhiều chức năng, bao gồm tạo tệp PDF từ đầu, sửa đổi các tài liệu PDF hiện có, hợp nhất hoặc chia tách các tệp PDF, thêm văn bản, hình ảnh và bảng, trích xuất dữ liệu từ PDF và nhiều hơn nữa. Với Aspose.PDF for .NET, các nhà phát triển có thể tự động hóa các tác vụ phức tạp liên quan đến PDF và cung cấp các giải pháp PDF chất lượng cao.

## Thêm Bảng vào Tài liệu PDF

Để thêm bảng vào tài liệu PDF bằng Aspose.PDF cho .NET, hãy làm theo hướng dẫn từng bước dưới đây:

## Bước 1: Tải tài liệu PDF nguồn

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Đoạn mã trên sẽ tải tài liệu PDF nguồn mà bạn muốn thêm bảng vào. Đảm bảo cung cấp đúng đường dẫn đến tệp PDF của bạn.

## Bước 2: Khởi tạo một phiên bản mới của Bảng

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

Ở bước này, chúng ta tạo một phiên bản mới của lớp Table, biểu diễn một bảng trong tài liệu PDF.

## Bước 3: Thiết lập màu viền bảng

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Ở đây, chúng ta thiết lập màu đường viền cho bảng bằng lớp BorderInfo. Bạn có thể tùy chỉnh kiểu đường viền, độ rộng và màu sắc theo yêu cầu của mình.

## Bước 4: Thiết lập đường viền cho các ô của bảng

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Chúng tôi cũng thiết lập đường viền cho các ô bảng bằng cách sử dụng thuộc tính DefaultCellBorder của đối tượng bảng. Điều này đảm bảo rằng mỗi ô trong bảng có kiểu đường viền, độ rộng và màu được chỉ định.

## Bước 5: Thêm hàng và ô vào bảng

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

Trong bước này, chúng ta tạo một vòng lặp để thêm 10 hàng vào bảng. Trong mỗi hàng, chúng ta thêm ba ô có dữ liệu mẫu. Bạn có thể sửa đổi mã để thêm hàng và ô theo yêu cầu cụ thể của mình.

## Bước 6: Thêm đối tượng bảng vào tài liệu

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Lưu tài liệu cập nhật có chứa đối tượng bảng
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Cuối cùng, chúng ta thêm đối tượng bảng vào trang đầu tiên của tài liệu PDF bằng cách sử dụng bộ sưu tập Đoạn văn của trang tương ứng.

### Mã nguồn ví dụ để thêm bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Tải tài liệu PDF nguồn
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Khởi tạo một phiên bản mới của Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt màu viền bảng là LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Đặt đường viền cho các ô của bảng
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tạo một vòng lặp để thêm 10 hàng
for (int row_count = 1; row_count < 10; row_count++)
{
	// Thêm hàng vào bảng
	Aspose.Pdf.Row row = table.Rows.Add();
	// Thêm ô bảng
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Thêm đối tượng bảng vào trang đầu tiên của tài liệu đầu vào
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Lưu tài liệu cập nhật có chứa đối tượng bảng
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích quy trình từng bước để thêm bảng vào tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi đã đề cập đến việc tải tài liệu PDF nguồn, khởi tạo một phiên bản mới của lớp Table, thiết lập màu viền bảng và viền ô, thêm hàng và ô vào bảng và thêm đối tượng bảng vào tài liệu. Bằng cách làm theo hướng dẫn này, bạn có thể dễ dàng kết hợp các bảng vào tài liệu PDF của mình theo chương trình và tùy chỉnh chúng theo nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp khi thêm bảng vào tệp PDF

#### H: Tôi có thể thêm nhiều cột vào bảng không?

A: Có, bạn có thể thêm nhiều cột vào bảng bằng cách tăng số ô được thêm vào mỗi hàng. Trong ví dụ được cung cấp, mỗi hàng có ba ô đại diện cho ba cột. Bạn có thể thêm nhiều ô vào mỗi hàng để thêm các cột bổ sung.

#### H: Làm thế nào để thay đổi giao diện của bảng, chẳng hạn như kích thước phông chữ và kiểu chữ?

 A: Bạn có thể tùy chỉnh giao diện của bảng, bao gồm kích thước và kiểu phông chữ, bằng cách thiết lập các thuộc tính trên`Aspose.Pdf.Table` Và`Aspose.Pdf.TextFragment` đối tượng. Ví dụ, bạn có thể thiết lập`DefaultCellTextState` thuộc tính để thay đổi thuộc tính phông chữ của văn bản trong các ô của bảng.

#### H: Có thể nhập các ô trong bảng không?

 A: Có, bạn có thể hợp nhất các ô trong bảng bằng cách sử dụng`MergeCells` phương pháp của`Aspose.Pdf.Row` lớp. Điều này cho phép bạn tạo các ô trải dài trên nhiều hàng và cột.

#### H: Tôi có thể thêm hình ảnh hoặc nội dung khác vào ô trong bảng không?

A: Có, bạn có thể thêm nhiều loại nội dung khác nhau vào các ô của bảng, bao gồm hình ảnh, văn bản, siêu liên kết, v.v. Bạn có thể sử dụng các lớp phù hợp từ Aspose.PDF cho .NET để thêm nhiều loại nội dung khác nhau vào các ô.

#### H: Aspose.PDF cho .NET có tương thích với .NET 5.0 hoặc phiên bản mới hơn không?

A: Có, Aspose.PDF cho .NET tương thích với .NET 5.0 và các phiên bản mới hơn. Nó hỗ trợ nhiều nền tảng .NET, bao gồm .NET Framework, .NET Core và .NET 5.0+.