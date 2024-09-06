---
title: Tạo phần tử bảng
linktitle: Tạo phần tử bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để tạo phần tử mảng bằng Aspose.PDF cho .NET. Tạo PDF động với bảng dễ dàng.
type: docs
weight: 80
url: /vi/net/programming-with-tagged-pdf/create-table-element/
---
Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình tạo phần tử mảng bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn thao tác các tài liệu PDF theo chương trình. Tạo phần tử mảng là yêu cầu chung khi tạo PDF động và Aspose.PDF cung cấp một cách dễ dàng và hiệu quả để thực hiện việc này.

Hãy cùng tìm hiểu mã và cách tạo phần tử mảng bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Thư viện Aspose.PDF cho .NET được cài đặt.
2. Kiến thức cơ bản về ngôn ngữ lập trình C#.

## Bước 1: Thiết lập môi trường

Để bắt đầu, hãy mở môi trường phát triển C# của bạn và tạo một dự án mới. Đảm bảo bạn đã thêm tham chiếu đến thư viện Aspose.PDF cho .NET vào dự án của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu

 Bước đầu tiên là tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp học.

```csharp
// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Ở đây chúng ta cũng thiết lập tiêu đề và ngôn ngữ cho nội dung được gắn thẻ.

## Bước 3: Tạo phần tử mảng

Tiếp theo, chúng ta cần tạo phần tử mảng và thêm nó vào tài liệu. Chúng ta bắt đầu bằng cách lấy phần tử cấu trúc gốc, sau đó chúng ta tạo một phần tử bảng mới bằng cách sử dụng`CreateTableElement` phương pháp.

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Lưu tài liệu PDF đã gắn thẻ
document.Save(dataDir + "CreateTableElement.pdf");

// Kiểm tra sự tuân thủ PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Mã nguồn mẫu cho Create Table Element sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Lưu tài liệu PDF có gắn thẻ
document.Save(dataDir + "CreateTableElement.pdf");

// Kiểm tra sự tuân thủ PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Bạn đã học cách tạo phần tử mảng bằng Aspose.PDF cho .NET. Bây giờ bạn có thể tạo tài liệu PDF với các bảng động bằng phương pháp này. Hãy thoải mái khám phá thêm các tính năng của Aspose.PDF để khám phá hết tiềm năng của nó.

### Câu hỏi thường gặp

#### H: Phần tử mảng trong tài liệu PDF là gì và tại sao tôi cần phải tạo một phần tử mảng bằng Aspose.PDF cho .NET?

A: Một phần tử mảng trong tài liệu PDF biểu diễn một tập hợp dữ liệu có cấu trúc, thường được sử dụng để tạo bảng hoặc lưới. Bạn có thể cần tạo một phần tử mảng bằng Aspose.PDF cho .NET khi tạo PDF động yêu cầu trình bày dữ liệu có cấu trúc, chẳng hạn như thông tin dạng bảng hoặc lưới.

#### H: Aspose.PDF cho .NET đơn giản hóa quá trình tạo phần tử mảng như thế nào?

A: Aspose.PDF cho .NET cung cấp một bộ lớp và phương thức toàn diện cho phép bạn tạo, tùy chỉnh và quản lý các phần tử mảng (bảng) trong tài liệu PDF theo chương trình. Điều này loại bỏ nhu cầu thao tác PDF thủ công và hợp lý hóa việc tạo biểu diễn dữ liệu có cấu trúc.

#### H: Các bước chính liên quan đến việc tạo phần tử mảng bằng Aspose.PDF cho .NET là gì?

A: Các bước chính bao gồm thiết lập môi trường, tạo tài liệu, lấy phần tử cấu trúc gốc, tạo phần tử bảng, xác định hàng và ô trong bảng và chỉ định định dạng và thuộc tính cho các phần tử. Ví dụ mã được cung cấp minh họa các bước này.

####  Q: Vai trò của`taggedContent` object play in creating an array element?

 A: Cái`taggedContent` đối tượng, thu được từ tài liệu`TaggedContent`thuộc tính, cho phép bạn xác định cấu trúc của nội dung được gắn thẻ trong tài liệu PDF. Điều này bao gồm việc tạo và sắp xếp các phần tử mảng và các phần tử con của chúng theo cách phân cấp.

#### H: Mã đảm bảo khả năng truy cập và ngữ nghĩa của phần tử mảng được tạo như thế nào?

 A: Mã thiết lập các thuộc tính như`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Và`ColSpan` để tăng cường khả năng truy cập và ngữ nghĩa của phần tử mảng. Các thuộc tính này góp phần tạo nên một biểu diễn dữ liệu có cấu trúc tốt, nhiều thông tin và hấp dẫn về mặt trực quan.

#### H: Việc tuân thủ PDF/UA có ý nghĩa gì trong bối cảnh tạo các phần tử mảng?

 A: Tuân thủ PDF/UA (Khả năng truy cập phổ quát) đảm bảo rằng các tài liệu PDF được tạo ra có thể truy cập được đối với người dùng khuyết tật và đáp ứng các tiêu chuẩn khả năng truy cập nhất định. Ví dụ mã kiểm tra sự tuân thủ PDF/UA bằng cách sử dụng`Validate` phương pháp giúp bạn tạo ra các tài liệu có tính bao hàm và dễ tiếp cận.

#### H: Tôi có thể tùy chỉnh định dạng và giao diện của các phần tử mảng hơn nữa không?

A: Có, bạn có thể tùy chỉnh định dạng và giao diện của các phần tử mảng bằng cách điều chỉnh các thuộc tính như màu nền, kiểu đường viền, kích thước phông chữ và căn chỉnh. Aspose.PDF cho .NET cung cấp nhiều thuộc tính để tùy chỉnh bản trình bày trực quan theo yêu cầu của bạn.

#### H: Làm thế nào tôi có thể mở rộng kiến thức này để tạo ra các cấu trúc bảng phức tạp hơn hoặc kết hợp các phần tử mảng vào các tài liệu PDF lớn hơn?

A: Bạn có thể mở rộng kiến thức này bằng cách khám phá các tính năng bổ sung của Aspose.PDF cho .NET, chẳng hạn như hợp nhất nhiều phần tử mảng, tạo bảng lồng nhau, thêm tiêu đề và chân trang và tích hợp các phần tử mảng vào các bố cục PDF lớn hơn. Tài liệu và ví dụ của thư viện cung cấp hướng dẫn cho các tình huống nâng cao này.

#### H: Có thể nhập dữ liệu từ các nguồn bên ngoài, chẳng hạn như cơ sở dữ liệu hoặc bảng tính, để điền vào các phần tử mảng không?

A: Có, bạn có thể nhập dữ liệu từ các nguồn bên ngoài để điền vào các phần tử mảng. Bạn có thể sử dụng các kỹ thuật truy xuất và chuyển đổi dữ liệu trong C# để lấy dữ liệu từ cơ sở dữ liệu, bảng tính hoặc các nguồn khác rồi điền vào các phần tử mảng cho phù hợp.

#### H: Tôi có thể sử dụng kiến thức thu được từ hướng dẫn này như thế nào để nâng cao chất lượng và khả năng sử dụng của các tài liệu PDF mà tôi tạo theo chương trình?

A: Kiến thức thu được từ hướng dẫn này cho phép bạn tạo các phần tử mảng (bảng) có cấu trúc và hấp dẫn về mặt thị giác trong các tài liệu PDF. Bằng cách kết hợp các kỹ thuật này, bạn có thể cải thiện khả năng đọc, khả năng truy cập và trải nghiệm người dùng của các tệp PDF được tạo động, giúp chúng mang tính thông tin hơn và thân thiện với người dùng hơn.