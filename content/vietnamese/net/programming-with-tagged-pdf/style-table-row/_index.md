---
title: Hàng của bảng kiểu
linktitle: Hàng của bảng kiểu
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tùy chỉnh các hàng trong bảng bằng Aspose.PDF cho hướng dẫn từng bước về cách tạo kiểu và định dạng các hàng.
type: docs
weight: 180
url: /vi/net/programming-with-tagged-pdf/style-table-row/
---
Trong hướng dẫn chi tiết này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# được cung cấp để định dạng hàng bảng bằng Aspose.PDF cho .NET. Làm theo hướng dẫn bên dưới để hiểu cách tùy chỉnh kiểu và thuộc tính hàng bảng.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã cấu hình môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này bao gồm cài đặt thư viện Aspose.PDF và cấu hình dự án của bạn để tham chiếu đến nó.

## Bước 2: Tạo tài liệu

Ở bước này, chúng ta sẽ tạo một đối tượng tài liệu mới Aspose.PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Chúng tôi đã tạo một tài liệu mới và đặt tiêu đề và ngôn ngữ cho tài liệu.

## Bước 3: Lấy phần tử cấu trúc gốc

Ở bước này, chúng ta sẽ lấy phần tử cấu trúc gốc cho tài liệu của mình.

```csharp
//Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
```

Chúng ta có phần tử cấu trúc gốc sẽ đóng vai trò là vùng chứa cho phần tử mảng.

## Bước 4: Tạo phần tử cấu trúc mảng

Bây giờ chúng ta hãy tạo một phần tử cấu trúc bảng mới cho tài liệu của mình.

```csharp
// Tạo phần tử cấu trúc mảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Chúng tôi đã tạo một phần tử cấu trúc mảng mới và thêm nó vào phần tử cấu trúc gốc.

## Bước 5: Tùy chỉnh kiểu dáng và thuộc tính của hàng bảng

Ở bước này, chúng ta sẽ tùy chỉnh kiểu dáng và thuộc tính của hàng trong bảng.

```csharp
// Tùy chỉnh kiểu dáng và thuộc tính của hàng bảng
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

// Tạo hàng tiêu đề bảng
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// Tùy chỉnh các hàng của phần thân bảng
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Tạo dòng chân trang của bảng
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Chúng tôi đã tùy chỉnh nhiều khía cạnh khác nhau của hàng trong bảng, chẳng hạn như màu nền, đường viền, chiều cao hàng, phân trang, kiểu ô mặc định, v.v.

## Bước 6: Lưu tài liệu PDF đã gắn thẻ

Bây giờ chúng ta đã tạo xong tài liệu với hàng bảng được tạo kiểu, chúng ta sẽ lưu nó dưới dạng tài liệu PDF có gắn thẻ.
```csharp
// Lưu tài liệu PDF đã gắn thẻ
document.Save(dataDir + "StyleTableRow.pdf");
```

Chúng tôi đã lưu tài liệu PDF được gắn thẻ vào thư mục đã chỉ định.

## Bước 7: Xác thực sự tuân thủ PDF/UA

Tiếp theo, chúng tôi sẽ xác thực tính phù hợp PDF/UA của tài liệu.

```csharp
// Kiểm tra sự tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Chúng tôi đã tải lên tài liệu PDF được gắn thẻ và xác thực tính tuân thủ PDF/UA của tài liệu này bằng cách tạo báo cáo XML.


### Mã nguồn mẫu cho Style Table Row sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo phần tử cấu trúc bảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Lưu tài liệu PDF có gắn thẻ
document.Save(dataDir + "StyleTableRow.pdf");

// Kiểm tra sự tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách định dạng hàng bảng bằng Aspose.PDF cho .NET. Chúng ta đã tùy chỉnh các kiểu và thuộc tính của hàng bảng, thêm tiêu đề, hàng nội dung và chân trang, lưu tài liệu PDF được gắn thẻ và xác thực sự tuân thủ PDF/UA của nó.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn định dạng hàng bảng bằng Aspose.PDF cho .NET này là gì?

A: Mục đích của hướng dẫn này là hướng dẫn bạn quy trình định dạng hàng bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước và ví dụ mã nguồn C# để giúp bạn tùy chỉnh kiểu và thuộc tính hàng bảng.

#### H: Cần có những điều kiện tiên quyết nào để thực hiện hướng dẫn này?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập môi trường phát triển để sử dụng Aspose.PDF cho .NET. Điều này bao gồm cài đặt thư viện Aspose.PDF và cấu hình dự án của bạn để tham chiếu đến nó.

#### H: Làm thế nào để tạo một tài liệu PDF mới và đặt tiêu đề cũng như ngôn ngữ cho nó bằng Aspose.PDF cho .NET?

 A: Để tạo một tài liệu PDF mới, bạn cần tạo một`Document` đối tượng từ thư viện Aspose.PDF. Mã nguồn C# được cung cấp trong hướng dẫn này sẽ trình bày cách tạo tài liệu và thiết lập tiêu đề cũng như thuộc tính ngôn ngữ của tài liệu đó.

#### H: Tầm quan trọng của phần tử cấu trúc gốc trong tài liệu PDF là gì?

A: Phần tử cấu trúc gốc đóng vai trò như một container cho các phần tử cấu trúc khác, giúp sắp xếp và phân loại nội dung của tài liệu PDF. Nó đóng vai trò quan trọng trong việc thiết lập cấu trúc logic của tài liệu.

#### H: Làm thế nào để tạo và tùy chỉnh phần tử cấu trúc bảng để định dạng các hàng bảng bằng Aspose.PDF cho .NET?

A: Hướng dẫn giải thích cách tạo thành phần cấu trúc bảng và tùy chỉnh các thuộc tính của thành phần đó để định dạng các hàng bảng. Nó bao gồm các khía cạnh như màu nền, đường viền, chiều cao hàng, phân trang, kiểu ô mặc định, v.v.

#### H: Tôi có thể tùy chỉnh kiểu dáng và thuộc tính của từng ô trong một hàng của bảng không?

A: Có, bạn có thể tùy chỉnh kiểu và thuộc tính của từng ô trong một hàng bảng. Hướng dẫn này sẽ trình bày cách thiết lập các thuộc tính như màu nền, đường viền, màu văn bản, phần đệm và nhiều thuộc tính khác cho các ô bảng trong hàng bảng được định dạng.

#### H: Làm thế nào tôi có thể thêm tiêu đề, hàng nội dung và chân trang vào hàng bảng đã định dạng?

A: Hướng dẫn cung cấp các ví dụ về cách tạo và thêm tiêu đề, hàng nội dung và chân trang vào phần tử cấu trúc bảng. Các phần tử này có thể được tùy chỉnh thêm bằng các thuộc tính được mô tả trong hướng dẫn.

#### H: Tuân thủ PDF/UA là gì và tôi có thể xác thực nó cho tài liệu PDF được gắn thẻ của mình như thế nào?

 A: Tuân thủ PDF/UA đảm bảo rằng tài liệu PDF tuân thủ các tiêu chuẩn về khả năng truy cập, giúp người dùng khuyết tật dễ truy cập hơn. Hướng dẫn này trình bày cách xác thực tính tuân thủ PDF/UA bằng cách sử dụng`Validate()` phương pháp và tạo báo cáo tuân thủ XML.

#### H: Làm thế nào tôi có thể kết hợp những khái niệm này vào ứng dụng .NET của riêng mình?

A: Bạn có thể sử dụng các ví dụ mã nguồn C# được cung cấp làm hướng dẫn để triển khai định dạng hàng bảng trong các ứng dụng .NET của riêng bạn. Sửa đổi và điều chỉnh mã để phù hợp với yêu cầu của bạn và tích hợp vào các dự án của bạn.

#### H: Có khuyến nghị nào về cách định dạng hàng bảng trong tài liệu PDF không?

A: Khi định dạng các hàng trong bảng, hãy cân nhắc đến khả năng đọc và khả năng truy cập của nội dung. Đảm bảo rằng màu sắc có đủ độ tương phản, sử dụng phông chữ rõ ràng và dễ đọc, và duy trì bố cục nhất quán. Xác thực sự tuân thủ PDF/UA để đảm bảo đáp ứng các tiêu chuẩn về khả năng truy cập.

#### H: Tôi có thể khám phá những tính năng nào khác của Aspose.PDF cho .NET để tùy chỉnh tài liệu PDF?

A: Aspose.PDF for .NET cung cấp nhiều tính năng để tùy chỉnh tài liệu PDF, bao gồm thao tác văn bản, chèn hình ảnh, quản lý trường biểu mẫu, chữ ký số, chú thích, v.v. Tham khảo tài liệu và tài nguyên chính thức để khám phá các chức năng bổ sung.