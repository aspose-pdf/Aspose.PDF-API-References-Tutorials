---
title: Các ký hiệu có thể thay thế ở chân trang đầu trang
linktitle: Các ký hiệu có thể thay thế ở chân trang đầu trang
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng các ký hiệu có thể thay thế trong đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 320
url: /vi/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách sử dụng các ký hiệu có thể thay thế trong đầu trang và chân trang của tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng ta sẽ thực hiện quy trình từng bước tạo tệp PDF, đặt lề, thêm đầu trang và chân trang bằng các ký hiệu có thể thay thế và lưu tệp PDF bằng mã nguồn C# được cung cấp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Trước tiên, bạn cần đặt đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir`biến có đường dẫn đến thư mục bạn muốn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo tài liệu và trang PDF

 Tiếp theo, chúng tôi tạo một tài liệu PDF mới và thêm một trang vào đó bằng cách sử dụng`Document` lớp học và`Page` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 3: Đặt lề

 Chúng tôi đặt lề cho trang bằng cách sử dụng`MarginInfo`lớp học. Điều chỉnh giá trị lề theo yêu cầu của bạn.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Bước 4: Thêm tiêu đề với các ký hiệu có thể thay thế

 Chúng tôi tạo ra một`HeaderFooter` đối tượng cho trang và thêm một`TextFragment` với các ký hiệu có thể thay thế cho nó.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Đặt thuộc tính văn bản nếu muốn
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Thêm nhiều TextFragment hơn hoặc tùy chỉnh nếu cần
```

## Bước 5: Thêm chân trang với các ký hiệu có thể thay thế

 Tương tự, chúng ta tạo một`HeaderFooter` đối tượng cho chân trang và thêm`TextFragment` các đối tượng có ký hiệu có thể thay thế cho nó.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Thêm nhiều TextFragment hơn hoặc tùy chỉnh nếu cần

hfFoot.Paragraphs.Add(tab2);
```

## Bước 6: Lưu tài liệu PDF

Cuối cùng, chúng tôi lưu tài liệu PDF vào tệp đầu ra được chỉ định.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu cho các Biểu tượng có thể thay thế trong Chân trang đầu trang bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Gán phiên bản MarginInfo cho thuộc tính Margin của sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Khởi tạo một đoạn Văn bản sẽ lưu trữ nội dung để hiển thị dưới dạng tiêu đề
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Tạo đối tượng HeaderFooter cho phần này
HeaderFooter hfFoot = new HeaderFooter();
// Đặt đối tượng HeaderFooter thành chân trang lẻ và chẵn
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Thêm một đoạn văn bản chứa số trang hiện tại trên tổng số trang
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Khởi tạo một đối tượng bảng
Table tab2 = new Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
hfFoot.Paragraphs.Add(tab2);
// Đặt độ rộng cột của bảng
tab2.ColumnWidths = "165 172 165";
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Đặt căn chỉnh theo chiều dọc của văn bản là căn giữa
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java là một bản tổng hợp của mọi thành phần Java do Aspose cung cấp. Nó được biên dịch trên cơ sở #$NL" + "hàng ngày để đảm bảo nó chứa các phiên bản cập nhật nhất của mỗi thành phần của các thành phần Java của chúng tôi. #$NL " + "Sử dụng Aspose.Total cho Java các nhà phát triển có thể tạo ra nhiều loại ứng dụng. #$NL #$NL #$NP" + "Aspose.Total cho Java là một bản tổng hợp của mọi thành phần Java được cung cấp bởi Aspose. Nó được biên soạn hàng ngày #$NL" + "để đảm bảo nó chứa các phiên bản cập nhật nhất của từng thành phần Java của chúng tôi. #$NL " + "Sử dụng Aspose.Total dành cho các nhà phát triển Java có thể tạo ra một phạm vi rộng #$NL #$NL #$NP" + "Aspose.Total for Java là sự tổng hợp của mọi thành phần Java do Aspose cung cấp. Nó được biên dịch trên cơ sở #$NL" + "hàng ngày để đảm bảo nó chứa nhiều nhất phiên bản cập nhật của từng thành phần Java của chúng tôi. #$NL " + "Sử dụng Aspose.Total dành cho các nhà phát triển Java có thể tạo ra nhiều loại ứng dụng. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(table);
// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách sử dụng các ký hiệu có thể thay thế trong đầu trang và chân trang của tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tạo tệp PDF, đặt lề, thêm đầu trang và chân trang bằng các ký hiệu có thể thay thế và lưu tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Các ký hiệu có thể thay thế trong chân trang đầu trang" là gì?

Đáp: Hướng dẫn "Các ký hiệu có thể thay thế trong chân trang đầu trang" nhằm hướng dẫn bạn qua quá trình sử dụng thư viện Aspose.PDF cho .NET để thêm các ký hiệu có thể thay thế vào đầu trang và chân trang của tài liệu PDF. Các ký hiệu có thể thay thế cho phép bạn tự động thay thế các phần giữ chỗ cụ thể bằng các giá trị thực tế khi tạo tệp PDF.

#### Câu hỏi: Các ký hiệu có thể thay thế trong ngữ cảnh của đầu trang và chân trang PDF là gì?

Đáp: Các ký hiệu có thể thay thế là các phần giữ chỗ mà bạn có thể chèn vào đầu trang và chân trang của tài liệu PDF. Các ký hiệu này đóng vai trò là phần giữ chỗ động cho các giá trị có thể được điền vào trong thời gian chạy, chẳng hạn như số trang, ngày tháng và thông tin tùy chỉnh.

#### Hỏi: Tại sao tôi muốn sử dụng các ký hiệu có thể thay thế trong đầu trang và chân trang PDF?

Đáp: Các ký hiệu có thể thay thế ở đầu trang và chân trang rất hữu ích khi bạn muốn đưa thông tin động vào tài liệu PDF của mình, chẳng hạn như số trang, ngày tháng hoặc dữ liệu biến đổi khác có thể thay đổi khi tài liệu được tạo.

#### Hỏi: Làm cách nào tôi có thể đặt lề cho trang PDF?

 Đáp: Bạn có thể đặt lề cho trang PDF bằng cách sử dụng`MarginInfo` lớp và gán nó cho`Margin` tài sản của`PageInfo` của trang. Điều chỉnh giá trị lề nếu cần.

#### Câu hỏi: Làm cách nào để thêm các ký hiệu có thể thay thế vào đầu trang và chân trang?

 Đáp: Bạn có thể thêm các biểu tượng có thể thay thế được bằng cách tạo một`HeaderFooter` đối tượng cho đầu trang và chân trang của trang. Sau đó, bạn có thể thêm`TextFragment`các đối tượng có văn bản mong muốn, bao gồm các ký hiệu có thể thay thế, vào`Paragraphs` bộ sưu tập của`HeaderFooter` sự vật.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của các biểu tượng có thể thay thế được không?

 Trả lời: Có, bạn có thể tùy chỉnh giao diện của các ký hiệu có thể thay thế bằng cách sửa đổi các thuộc tính của`TextFragment` các đối tượng có chứa các ký hiệu. Bạn có thể đặt các thuộc tính như phông chữ, cỡ chữ, màu sắc, căn chỉnh và khoảng cách dòng.

#### Câu hỏi: Tôi có thể sử dụng loại biểu tượng có thể thay thế nào?

Đáp: Bạn có thể sử dụng nhiều biểu tượng có thể thay thế được, chẳng hạn như:

- `$p`: Số trang hiện tại.
- `$P`: Tổng số trang.
- `$d`: Ngay hiện tại.
- `$t`: Thời điểm hiện tại.
- Trình giữ chỗ tùy chỉnh mà bạn xác định.

#### Câu hỏi: Tôi có thể bao gồm văn bản và định dạng khác xung quanh các ký hiệu có thể thay thế được không?

 Đáp: Có, bạn có thể bao gồm văn bản và định dạng khác xung quanh các ký hiệu có thể thay thế được trong`TextFragment` các đối tượng. Điều này cho phép bạn tạo các đầu trang và chân trang phức tạp hơn kết hợp nội dung động và tĩnh.

#### Hỏi: Làm cách nào tôi có thể lưu tài liệu PDF đã tạo?

 Đáp: Để lưu tài liệu PDF đã tạo, bạn có thể sử dụng`Save` phương pháp của`Document`lớp học. Cung cấp đường dẫn và tên tệp đầu ra mong muốn làm đối số.

#### Câu hỏi: Có cần phải có Giấy phép Aspose hợp lệ cho hướng dẫn này không?

Trả lời: Có, cần có Giấy phép Aspose hợp lệ để thực thi mã thành công trong hướng dẫn này. Bạn có thể nhận được giấy phép đầy đủ hoặc giấy phép tạm thời 30 ngày từ trang web Aspose.