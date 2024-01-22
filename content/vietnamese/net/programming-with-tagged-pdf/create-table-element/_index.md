---
title: Tạo phần tử bảng
linktitle: Tạo phần tử bảng
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước tạo phần tử mảng bằng Aspose.PDF cho .NET. Tạo các tệp PDF động với các bảng một cách dễ dàng.
type: docs
weight: 80
url: /vi/net/programming-with-tagged-pdf/create-table-element/
---
Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình tạo phần tử mảng bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn thao tác các tài liệu PDF theo chương trình. Tạo một phần tử mảng là một yêu cầu phổ biến khi tạo các tệp PDF động và Aspose.PDF cung cấp một cách dễ dàng và hiệu quả để thực hiện việc này.

Hãy đi sâu vào mã và tìm hiểu cách tạo một phần tử mảng bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Thư viện Aspose.PDF dành cho .NET được cài đặt.
2. Có kiến thức cơ bản về ngôn ngữ lập trình C#.

## Bước 1: Thiết lập môi trường

Để bắt đầu, hãy mở môi trường phát triển C# của bạn và tạo một dự án mới. Đảm bảo rằng bạn đã thêm tham chiếu đến thư viện Aspose.PDF cho .NET trong dự án của mình.

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

Ở đây chúng ta cũng đặt tiêu đề và ngôn ngữ cho nội dung được gắn thẻ.

## Bước 3: Tạo phần tử mảng

Tiếp theo, chúng ta cần tạo phần tử mảng và thêm nó vào tài liệu. Chúng ta bắt đầu bằng cách lấy phần tử cấu trúc gốc, sau đó tạo phần tử bảng mới bằng cách sử dụng`CreateTableElement` phương pháp.

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

// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "CreateTableElement.pdf");

// Kiểm tra tuân thủ PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Mã nguồn mẫu để tạo phần tử bảng bằng Aspose.PDF cho .NET 
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

// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "CreateTableElement.pdf");

// Kiểm tra việc tuân thủ PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Bạn đã học cách tạo một phần tử mảng bằng Aspose.PDF cho .NET. Bây giờ bạn có thể tạo tài liệu PDF bằng bảng động bằng phương pháp này. Vui lòng khám phá thêm các tính năng của Aspose.PDF để khám phá toàn bộ tiềm năng của nó.

### Câu hỏi thường gặp

#### Câu hỏi: Phần tử mảng trong tài liệu PDF là gì và tại sao tôi cần tạo phần tử mảng bằng Aspose.PDF cho .NET?

Đáp: Phần tử mảng trong tài liệu PDF thể hiện một tập hợp dữ liệu có cấu trúc, thường được sử dụng để tạo bảng hoặc lưới. Bạn có thể cần tạo một phần tử mảng bằng Aspose.PDF cho .NET khi tạo các tệp PDF động yêu cầu trình bày dữ liệu có cấu trúc, chẳng hạn như thông tin dạng bảng hoặc lưới.

#### Câu hỏi: Aspose.PDF cho .NET đơn giản hóa quá trình tạo phần tử mảng như thế nào?

Trả lời: Aspose.PDF for .NET cung cấp một tập hợp toàn diện các lớp và phương thức cho phép bạn tạo, tùy chỉnh và quản lý các phần tử mảng (bảng) trong tài liệu PDF theo chương trình. Điều này giúp loại bỏ nhu cầu thao tác PDF thủ công và hợp lý hóa việc tạo các biểu diễn dữ liệu có cấu trúc.

#### Câu hỏi: Các bước chính liên quan đến việc tạo phần tử mảng bằng Aspose.PDF cho .NET là gì?

Trả lời: Các bước chính bao gồm thiết lập môi trường, tạo tài liệu, lấy phần tử cấu trúc gốc, tạo phần tử bảng, xác định các hàng và ô trong bảng cũng như chỉ định định dạng và thuộc tính cho các phần tử. Ví dụ về mã được cung cấp minh họa các bước này.

####  Hỏi: Vai trò của nó là gì?`taggedContent` object play in creating an array element?

 Đáp: Cái`taggedContent` đối tượng, thu được từ tài liệu`TaggedContent`thuộc tính, cho phép bạn xác định cấu trúc của nội dung được gắn thẻ trong tài liệu PDF. Điều này bao gồm việc tạo và tổ chức các phần tử mảng và các phần tử con của chúng theo cách phân cấp.

#### Câu hỏi: Mã đảm bảo khả năng truy cập và ngữ nghĩa của phần tử mảng đã tạo bằng cách nào?

 A: Mã đặt các thuộc tính như`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Và`ColSpan` để nâng cao khả năng tiếp cận và ngữ nghĩa của phần tử mảng. Các thuộc tính này góp phần thể hiện dữ liệu có cấu trúc tốt, mang tính thông tin và hấp dẫn về mặt trực quan.

#### Câu hỏi: Tầm quan trọng của việc tuân thủ PDF/UA trong bối cảnh tạo các phần tử mảng là gì?

 Trả lời: Việc tuân thủ PDF/UA (Trợ năng truy cập toàn cầu) đảm bảo rằng người dùng khuyết tật có thể truy cập được các tài liệu PDF được tạo và đáp ứng các tiêu chuẩn trợ năng nhất định. Ví dụ về mã kiểm tra sự tuân thủ của PDF/UA bằng cách sử dụng`Validate` phương pháp giúp bạn tạo các tài liệu toàn diện và dễ tiếp cận.

#### Câu hỏi: Tôi có thể tùy chỉnh thêm định dạng và hình thức của các phần tử mảng không?

Đáp: Có, bạn có thể tùy chỉnh định dạng và hình thức của các thành phần mảng bằng cách điều chỉnh các thuộc tính như màu nền, kiểu đường viền, cỡ chữ và căn chỉnh. Aspose.PDF for .NET cung cấp nhiều thuộc tính để điều chỉnh cách trình bày trực quan theo yêu cầu của bạn.

#### Câu hỏi: Làm cách nào tôi có thể mở rộng kiến thức này để tạo các cấu trúc bảng phức tạp hơn hoặc kết hợp các phần tử mảng vào các tài liệu PDF lớn hơn?

Trả lời: Bạn có thể mở rộng kiến thức này bằng cách khám phá các tính năng bổ sung của Aspose.PDF cho .NET, chẳng hạn như hợp nhất nhiều thành phần mảng, tạo bảng lồng nhau, thêm đầu trang và chân trang cũng như tích hợp các thành phần mảng vào bố cục PDF lớn hơn. Tài liệu và ví dụ của thư viện cung cấp hướng dẫn cho các kịch bản nâng cao này.

#### Câu hỏi: Có thể nhập dữ liệu từ các nguồn bên ngoài, chẳng hạn như cơ sở dữ liệu hoặc bảng tính, để điền vào các phần tử mảng không?

Đáp: Có, bạn có thể nhập dữ liệu từ các nguồn bên ngoài để điền vào các phần tử mảng. Bạn có thể sử dụng các kỹ thuật truy xuất và chuyển đổi dữ liệu trong C# để tìm nạp dữ liệu từ cơ sở dữ liệu, bảng tính hoặc các nguồn khác, sau đó điền các phần tử mảng tương ứng.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng kiến thức thu được từ hướng dẫn này để nâng cao chất lượng và khả năng sử dụng của tài liệu PDF mà tôi tạo theo chương trình?

Đáp: Kiến thức thu được từ hướng dẫn này cho phép bạn tạo các phần tử mảng (bảng) có cấu trúc và hấp dẫn về mặt hình ảnh trong tài liệu PDF. Bằng cách kết hợp các kỹ thuật này, bạn có thể cải thiện khả năng đọc, khả năng truy cập và trải nghiệm người dùng của các tệp PDF được tạo động, làm cho chúng có nhiều thông tin hơn và thân thiện với người dùng hơn.