---
title: Thêm bảng vào tệp PDF
linktitle: Thêm bảng vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng thêm bảng vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-tables/add-table/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm bảng vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước của đoạn mã được cung cấp và cung cấp hướng dẫn toàn diện để giúp bạn hiểu và triển khai chức năng trong các dự án của riêng bạn.

## Giới thiệu

Tài liệu PDF được sử dụng rộng rãi để chia sẻ và lưu giữ thông tin ở định dạng di động. Việc thêm bảng vào tài liệu PDF có thể nâng cao hình thức trực quan của chúng và làm cho việc trình bày dữ liệu có tổ chức và có cấu trúc hơn. Aspose.PDF for .NET cung cấp một cách thuận tiện để thêm bảng vào tài liệu PDF hiện có hoặc tạo bảng mới từ đầu.

## Aspose.PDF cho .NET là gì?

Aspose.PDF for .NET là một thư viện mạnh mẽ và giàu tính năng cho phép các nhà phát triển .NET tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Nó cung cấp nhiều chức năng, bao gồm tạo tệp PDF từ đầu, sửa đổi tài liệu PDF hiện có, hợp nhất hoặc chia nhỏ tệp PDF, thêm văn bản, hình ảnh và bảng, trích xuất dữ liệu từ tệp PDF, v.v. Với Aspose.PDF for .NET, các nhà phát triển có thể tự động hóa các tác vụ phức tạp liên quan đến PDF và cung cấp các giải pháp PDF chất lượng cao.

## Thêm bảng vào tài liệu PDF

Để thêm bảng vào tài liệu PDF bằng Aspose.PDF cho .NET, hãy làm theo hướng dẫn từng bước bên dưới:

## Bước 1: Tải tài liệu PDF nguồn

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Đoạn mã ở trên tải tài liệu PDF nguồn mà bạn muốn thêm bảng vào. Đảm bảo cung cấp đường dẫn chính xác tới tệp PDF của bạn.

## Bước 2: Khởi tạo một phiên bản mới của Bảng

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

Trong bước này, chúng ta tạo một phiên bản mới của lớp Table, đại diện cho một bảng trong tài liệu PDF.

## Bước 3: Thiết lập màu viền bảng

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Ở đây, chúng ta đặt màu đường viền cho bảng bằng lớp BorderInfo. Bạn có thể tùy chỉnh kiểu đường viền, chiều rộng và màu sắc theo yêu cầu của mình.

## Bước 4: Thiết lập đường viền cho ô trong bảng

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Chúng tôi cũng đặt đường viền cho các ô trong bảng bằng thuộc tính DefaultCellBorder của đối tượng bảng. Điều này đảm bảo rằng mỗi ô trong bảng có kiểu đường viền, chiều rộng và màu sắc được chỉ định.

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

Ở bước này, chúng ta tạo một vòng lặp để thêm 10 hàng vào bảng. Trong mỗi hàng, chúng tôi thêm ba ô có dữ liệu mẫu. Bạn có thể sửa đổi mã để thêm hàng và ô theo yêu cầu cụ thể của mình.

## Bước 6: Thêm đối tượng bảng vào tài liệu

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Lưu tài liệu cập nhật chứa đối tượng bảng
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Cuối cùng, chúng tôi thêm đối tượng bảng vào trang đầu tiên của tài liệu PDF bằng cách sử dụng bộ sưu tập Đoạn văn của trang tương ứng.

### Mã nguồn ví dụ để thêm bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Tải tài liệu PDF nguồn
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Khởi tạo một phiên bản mới của Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Đặt màu đường viền bảng là LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Đặt đường viền cho ô trong bảng
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
// Lưu tài liệu cập nhật chứa đối tượng bảng
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích quy trình từng bước thêm bảng vào tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi đã đề cập đến việc tải tài liệu PDF nguồn, khởi tạo một phiên bản mới của lớp Bảng, đặt màu đường viền bảng và viền ô, thêm hàng và ô vào bảng cũng như thêm đối tượng bảng vào tài liệu. Bằng cách làm theo hướng dẫn này, bạn có thể dễ dàng kết hợp các bảng vào tài liệu PDF của mình theo chương trình và tùy chỉnh chúng theo nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp về thêm bảng vào tệp PDF

#### Hỏi: Tôi có thể thêm nhiều cột vào bảng không?

Đáp: Có, bạn có thể thêm nhiều cột vào bảng bằng cách tăng số lượng ô được thêm vào mỗi hàng. Trong ví dụ được cung cấp, mỗi hàng có ba ô đại diện cho ba cột. Bạn có thể thêm nhiều ô vào mỗi hàng để thêm các cột bổ sung.

#### Câu hỏi: Làm cách nào để thay đổi hình thức của bảng, chẳng hạn như cỡ chữ và kiểu chữ?

 Đáp: Bạn có thể tùy chỉnh hình thức của bảng, bao gồm cỡ chữ và kiểu phông chữ, bằng cách đặt các thuộc tính trên`Aspose.Pdf.Table` Và`Aspose.Pdf.TextFragment` các đối tượng. Ví dụ: bạn có thể đặt`DefaultCellTextState` thuộc tính để thay đổi thuộc tính phông chữ của văn bản trong các ô của bảng.

#### Hỏi: Có thể gộp các ô trong bảng được không?

 Đáp: Có, bạn có thể hợp nhất các ô trong bảng bằng cách sử dụng`MergeCells` phương pháp của`Aspose.Pdf.Row` lớp học. Điều này cho phép bạn tạo các ô trải rộng trên nhiều hàng và cột.

#### Câu hỏi: Tôi có thể thêm hình ảnh hoặc nội dung khác vào các ô của bảng không?

Đáp: Có, bạn có thể thêm nhiều loại nội dung khác nhau vào các ô của bảng, bao gồm hình ảnh, văn bản, siêu liên kết, v.v. Bạn có thể sử dụng các lớp thích hợp từ Aspose.PDF cho .NET để thêm các loại nội dung khác nhau vào ô.

#### Câu hỏi: Aspose.PDF cho .NET có tương thích với các phiên bản .NET 5.0 trở lên không?

Trả lời: Có, Aspose.PDF cho .NET tương thích với .NET 5.0 và các phiên bản mới hơn. Nó hỗ trợ nhiều nền tảng .NET khác nhau, bao gồm .NET Framework, .NET Core và .NET 5.0+.