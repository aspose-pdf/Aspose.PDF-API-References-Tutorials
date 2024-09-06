---
title: Các ký hiệu có thể thay thế trong Header Footer
linktitle: Các ký hiệu có thể thay thế trong Header Footer
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng các ký hiệu có thể thay thế ở phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 320
url: /vi/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách sử dụng các ký hiệu có thể thay thế trong phần đầu trang và phần chân trang của tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn từng bước để tạo PDF, thiết lập lề, thêm phần đầu trang và phần chân trang bằng các ký hiệu có thể thay thế và lưu PDF bằng mã nguồn C# được cung cấp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục bạn mong muốn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu PDF và Trang

 Tiếp theo, chúng ta tạo một tài liệu PDF mới và thêm một trang vào đó bằng cách sử dụng`Document` lớp và`Page` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 3: Thiết lập lề

Chúng tôi thiết lập lề cho trang bằng cách sử dụng`MarginInfo` lớp. Điều chỉnh giá trị lề theo yêu cầu của bạn.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Bước 4: Thêm tiêu đề với các ký hiệu có thể thay thế

 Chúng tôi tạo ra một`HeaderFooter` đối tượng cho trang và thêm một`TextFragment` với các ký hiệu có thể thay thế được.

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

// Thêm nhiều TextFragments hoặc tùy chỉnh khi cần thiết
```

## Bước 5: Thêm Chân trang với các Ký hiệu có thể Thay thế

 Tương tự như vậy, chúng ta tạo ra một`HeaderFooter` đối tượng cho chân trang và thêm`TextFragment` các đối tượng có ký hiệu có thể thay thế.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Thêm nhiều TextFragments hoặc tùy chỉnh khi cần thiết

hfFoot.Paragraphs.Add(tab2);
```

## Bước 6: Lưu tài liệu PDF

Cuối cùng, chúng ta lưu tài liệu PDF vào tệp đầu ra đã chỉ định.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu cho Ký hiệu có thể thay thế trong Đầu trang Chân trang sử dụng Aspose.PDF cho .NET 
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
// Gán thể hiện marginInfo cho thuộc tính Margin của sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Tạo một đoạn văn bản sẽ lưu trữ nội dung để hiển thị dưới dạng tiêu đề
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
// Tạo một đối tượng HeaderFooter cho phần
HeaderFooter hfFoot = new HeaderFooter();
// Đặt đối tượng HeaderFooter thành chân trang lẻ và chẵn
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Thêm một đoạn văn bản chứa số trang hiện tại của tổng số trang
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Khởi tạo một đối tượng bảng
Table tab2 = new Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
hfFoot.Paragraphs.Add(tab2);
// Thiết lập với chiều rộng cột của bảng
tab2.ColumnWidths = "165 172 165";
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Đặt căn chỉnh theo chiều dọc của văn bản thành căn giữa
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java là biên dịch của mọi thành phần Java do Aspose cung cấp. Nó được biên dịch hàng ngày để đảm bảo chứa các phiên bản mới nhất của từng thành phần Java của chúng tôi. #$NL " + "Sử dụng Aspose.Total for Java, các nhà phát triển có thể tạo ra nhiều ứng dụng khác nhau. #$NL #$NL #$NP" + "Aspose.Total for Java là biên dịch của mọi thành phần Java do Aspose cung cấp. Nó được biên dịch hàng ngày để đảm bảo chứa các phiên bản mới nhất của từng thành phần Java của chúng tôi. #$NL " + "Sử dụng Aspose.Total for Java, các nhà phát triển có thể tạo ra nhiều ứng dụng khác nhau. #$NL #$NL #$NP" + "Aspose.Total for Java là biên dịch của mọi thành phần Java do Aspose cung cấp. Nó được biên dịch hàng ngày để đảm bảo chứa các phiên bản mới nhất của từng thành phần Java của chúng tôi. #$NL " + "Sử dụng Aspose.Total cho các nhà phát triển Java có thể tạo ra nhiều ứng dụng khác nhau. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(table);
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
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

Trong hướng dẫn này, bạn đã học cách sử dụng các ký hiệu có thể thay thế trong phần đầu trang và phần chân trang của tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tạo PDF, đặt lề, thêm phần đầu trang và phần chân trang bằng các ký hiệu có thể thay thế và lưu PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Ký hiệu có thể thay thế trong tiêu đề và chân trang" là gì?

A: Hướng dẫn "Replaceable Symbols In Header Footer" hướng dẫn bạn quy trình sử dụng thư viện Aspose.PDF cho .NET để thêm các ký hiệu có thể thay thế vào header và footer của tài liệu PDF. Các ký hiệu có thể thay thế cho phép bạn thay thế các placeholder cụ thể bằng các giá trị thực khi tạo PDF.

#### H: Ký hiệu thay thế trong phần đầu trang và chân trang của tệp PDF là gì?

A: Ký hiệu có thể thay thế là các chỗ giữ chỗ mà bạn có thể chèn vào đầu trang và chân trang của tài liệu PDF. Các ký hiệu này hoạt động như chỗ giữ chỗ động cho các giá trị có thể được điền vào khi chạy, chẳng hạn như số trang, ngày tháng và thông tin tùy chỉnh.

#### H: Tại sao tôi lại muốn sử dụng các ký hiệu có thể thay thế trong phần đầu trang và chân trang của tệp PDF?

A: Các ký hiệu có thể thay thế ở đầu trang và chân trang rất hữu ích khi bạn muốn đưa thông tin động vào tài liệu PDF, chẳng hạn như số trang, ngày tháng hoặc dữ liệu biến đổi khác có thể thay đổi khi tài liệu được tạo.

#### H: Tôi có thể thiết lập lề cho trang PDF như thế nào?

 A: Bạn có thể thiết lập lề cho trang PDF bằng cách sử dụng`MarginInfo` lớp và gán nó cho`Margin` tài sản của`PageInfo` của trang. Điều chỉnh giá trị lề khi cần thiết.

#### H: Làm thế nào để thêm các ký hiệu có thể thay thế vào đầu trang và chân trang?

 A: Bạn có thể thêm các ký hiệu có thể thay thế bằng cách tạo một`HeaderFooter` đối tượng cho phần đầu trang và phần chân trang của trang. Sau đó, bạn có thể thêm`TextFragment`các đối tượng có văn bản mong muốn, bao gồm các ký hiệu có thể thay thế, vào`Paragraphs` bộ sưu tập của`HeaderFooter` sự vật.

#### H: Tôi có thể tùy chỉnh giao diện của các ký hiệu có thể thay thế không?

 A: Có, bạn có thể tùy chỉnh giao diện của các ký hiệu có thể thay thế bằng cách sửa đổi các thuộc tính của`TextFragment` các đối tượng chứa ký hiệu. Bạn có thể thiết lập các thuộc tính như phông chữ, kích thước phông chữ, màu sắc, căn chỉnh và khoảng cách dòng.

#### H: Tôi có thể sử dụng loại ký hiệu thay thế nào?

A: Bạn có thể sử dụng nhiều ký hiệu thay thế khác nhau, chẳng hạn như:

- `$p`: Số trang hiện tại.
- `$P`: Tổng số trang.
- `$d`: Ngày hiện tại.
- `$t`: Thời gian hiện tại.
- Chỗ giữ chỗ tùy chỉnh do bạn xác định.

#### H: Tôi có thể chèn thêm văn bản và định dạng khác xung quanh các ký hiệu có thể thay thế không?

 A: Có, bạn có thể bao gồm văn bản và định dạng khác xung quanh các ký hiệu có thể thay thế trong`TextFragment` đối tượng. Điều này cho phép bạn tạo các tiêu đề và chân trang phức tạp hơn kết hợp nội dung động và tĩnh.

#### H: Tôi có thể lưu tài liệu PDF đã tạo như thế nào?

 A: Để lưu tài liệu PDF đã tạo, bạn có thể sử dụng`Save` phương pháp của`Document`lớp. Cung cấp đường dẫn và tên tệp đầu ra mong muốn làm đối số.

#### H: Có cần Giấy phép Aspose hợp lệ cho hướng dẫn này không?

A: Có, cần phải có Giấy phép Aspose hợp lệ để thực thi mã thành công trong hướng dẫn này. Bạn có thể lấy giấy phép đầy đủ hoặc giấy phép tạm thời 30 ngày từ trang web Aspose.