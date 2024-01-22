---
title: Phần tử bảng kiểu
linktitle: Phần tử bảng kiểu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách định dạng thành phần bảng bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tùy chỉnh kiểu và thuộc tính.
type: docs
weight: 170
url: /vi/net/programming-with-tagged-pdf/style-table-element/
---
Trong hướng dẫn chi tiết này, chúng tôi sẽ hướng dẫn bạn từng bước về mã nguồn C# được cung cấp để định dạng phần tử mảng bằng Aspose.PDF cho .NET. Hãy làm theo hướng dẫn bên dưới để hiểu cách tùy chỉnh kiểu và thuộc tính của phần tử mảng.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã định cấu hình môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này bao gồm việc cài đặt thư viện Aspose.PDF và định cấu hình dự án của bạn để tham chiếu nó.

## Bước 2: Tạo tài liệu

Trong bước này, chúng ta sẽ tạo một đối tượng tài liệu mới Aspose.PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Chúng tôi đã tạo một tài liệu mới và đặt tiêu đề và ngôn ngữ cho tài liệu.

## Bước 3: Lấy phần tử cấu trúc gốc

Trong bước này, chúng ta sẽ lấy phần tử cấu trúc gốc cho tài liệu của mình.

```csharp
//Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
```

Chúng ta đã có phần tử cấu trúc gốc sẽ đóng vai trò là vùng chứa cho phần tử mảng.

## Bước 4: Tạo phần tử cấu trúc mảng

Bây giờ hãy tạo một thành phần cấu trúc bảng mới cho tài liệu của chúng ta.

```csharp
// Tạo phần tử cấu trúc mảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Chúng tôi đã tạo một phần tử cấu trúc mảng mới và thêm nó vào phần tử cấu trúc gốc.

## Bước 5: Tùy chỉnh kiểu và thuộc tính phần tử mảng

Trong bước này, chúng ta sẽ tùy chỉnh kiểu và thuộc tính của phần tử mảng.

```csharp
// Tùy chỉnh kiểu và thuộc tính của phần tử mảng
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Tùy chỉnh kiểu dòng lặp lại
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Chúng tôi đã sử dụng nhiều thuộc tính khác nhau để tùy chỉnh thành phần bảng, chẳng hạn như màu nền, đường viền, căn chỉnh, kiểu ô mặc định, lề, độ rộng cột, v.v.

## Bước 6: Thêm tiêu đề, nội dung và chân trang của bảng

Bây giờ hãy thêm tiêu đề, nội dung và chân trang của bảng vào thành phần bảng.
```csharp
// Thêm tiêu đề bảng
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Số hàng và cột trong bảng
int rowCount = 10;
int colCount = 5;
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

//Thêm các hàng của nội dung bảng
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Thêm đường chân bàn
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Chúng tôi đã thêm các dòng đầu trang, hàng nội dung và hàng chân trang vào bảng bằng cách sử dụng các phần tử tương ứng.

## Bước 7: Lưu tài liệu PDF được gắn thẻ

Bây giờ chúng tôi đã tạo tài liệu của mình với thành phần bảng được tạo kiểu, chúng tôi sẽ lưu nó dưới dạng tài liệu PDF được gắn thẻ.

```csharp
// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "StyleTableElement.pdf");
```

Chúng tôi đã lưu tài liệu PDF được gắn thẻ vào thư mục được chỉ định.

## Bước 8: Xác thực tuân thủ PDF/UA

Tiếp theo, chúng tôi sẽ xác thực tính tuân thủ PDF/UA của tài liệu của chúng tôi.

```csharp
// Kiểm tra tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Chúng tôi đã tải tài liệu PDF được gắn thẻ lên và xác thực tính tuân thủ PDF/UA của tài liệu đó bằng cách tạo báo cáo XML.

### Mã nguồn mẫu cho Phần tử bảng kiểu bằng cách sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo phần tử cấu trúc bảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
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

// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "StyleTableElement.pdf");

// Kiểm tra việc tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách định dạng phần tử mảng bằng Aspose.PDF cho .NET. Chúng tôi đã tùy chỉnh kiểu và thuộc tính của thành phần bảng, thêm tiêu đề, hàng nội dung và chân trang, lưu tài liệu PDF được gắn thẻ và xác thực tính tuân thủ PDF/UA của nó.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của hướng dẫn này về định dạng phần tử mảng bằng Aspose.PDF cho .NET là gì?

Đáp: Mục tiêu của hướng dẫn này là hướng dẫn bạn quy trình định dạng phần tử mảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Nó cung cấp hướng dẫn từng bước và ví dụ về mã nguồn C# để giúp bạn tùy chỉnh kiểu và thuộc tính của thành phần mảng.

#### Hỏi: Điều kiện tiên quyết để làm theo hướng dẫn này là gì?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này liên quan đến việc cài đặt thư viện Aspose.PDF và định cấu hình dự án của bạn để tham chiếu nó.

#### Hỏi: Làm cách nào tôi có thể tạo một tài liệu PDF mới cũng như đặt tiêu đề và ngôn ngữ của nó bằng Aspose.PDF cho .NET?

 Đáp: Để tạo một tài liệu PDF mới, bạn cần tạo một`Document` đối tượng từ thư viện Aspose.PDF. Mã nguồn C# được cung cấp trong hướng dẫn này trình bày cách tạo một tài liệu và đặt các thuộc tính ngôn ngữ và tiêu đề của nó.

#### Hỏi: Tầm quan trọng của thành phần cấu trúc gốc trong tài liệu PDF là gì?

Trả lời: Phần tử cấu trúc gốc đóng vai trò là nơi chứa các phần tử cấu trúc khác, giúp tổ chức và phân loại nội dung của tài liệu PDF. Nó đóng một vai trò quan trọng trong việc thiết lập cấu trúc logic của tài liệu.

#### Câu hỏi: Làm cách nào để tạo và tùy chỉnh phần tử cấu trúc mảng bằng Aspose.PDF cho .NET?

 Đáp: Bạn có thể tạo một phần tử cấu trúc mảng bằng cách sử dụng`CreateTableElement()` phương pháp. Mã nguồn của hướng dẫn này cung cấp các ví dụ về cách tùy chỉnh các thuộc tính khác nhau của thành phần bảng, chẳng hạn như màu nền, đường viền, căn chỉnh, độ rộng cột, v.v.

#### Câu hỏi: Tôi có thể tùy chỉnh kiểu và thuộc tính của các ô bảng trong phần tử mảng không?

Đáp: Có, hướng dẫn này bao gồm cách tùy chỉnh kiểu và thuộc tính của toàn bộ thành phần bảng, bao gồm đầu trang, hàng nội dung và chân trang. Tuy nhiên, nó không đề cập cụ thể đến việc tùy chỉnh các ô trong bảng riêng lẻ.

#### Câu hỏi: Làm cách nào tôi có thể thêm đầu trang, hàng nội dung và chân trang vào thành phần bảng?

Đáp: Hướng dẫn này giải thích cách tạo và thêm tiêu đề, hàng nội dung và chân trang vào thành phần bảng bằng các phương pháp thích hợp do Aspose.PDF cung cấp cho .NET.

#### Câu hỏi: Tuân thủ PDF/UA là gì và làm cách nào để xác thực nó cho tài liệu PDF được gắn thẻ của tôi?

 Đáp: Việc tuân thủ PDF/UA đảm bảo rằng tài liệu PDF tuân thủ các tiêu chuẩn trợ năng, giúp người dùng khuyết tật dễ dàng truy cập hơn. Hướng dẫn này trình bày cách xác thực sự tuân thủ PDF/UA bằng cách sử dụng`Validate()` phương pháp và tạo ra một báo cáo tuân thủ XML.

#### Câu hỏi: Làm cách nào tôi có thể kết hợp các khái niệm này vào các ứng dụng .NET của riêng mình?

Trả lời: Bạn có thể sử dụng các ví dụ về mã nguồn C# được cung cấp làm hướng dẫn triển khai định dạng phần tử mảng trong các ứng dụng .NET của riêng bạn. Sửa đổi và điều chỉnh mã để phù hợp với yêu cầu của bạn và tích hợp nó vào các dự án của bạn.

#### Câu hỏi: Có bất kỳ phương pháp hay nhất nào được đề xuất để định dạng các phần tử mảng trong tài liệu PDF không?

Đáp: Khi định dạng các phần tử mảng (bảng), hãy xem xét khả năng đọc và khả năng truy cập của nội dung. Sử dụng phông chữ rõ ràng và dễ đọc, màu sắc phù hợp và duy trì bố cục nhất quán. Xác thực việc tuân thủ PDF/UA để đảm bảo đáp ứng các tiêu chuẩn về khả năng truy cập.

#### Câu hỏi: Tôi có thể khám phá những tính năng nào khác của Aspose.PDF dành cho .NET để tùy chỉnh tài liệu PDF?

Trả lời: Aspose.PDF for .NET cung cấp nhiều tính năng để tùy chỉnh tài liệu PDF, bao gồm thao tác văn bản, chèn hình ảnh, quản lý trường biểu mẫu, chữ ký số, chú thích, v.v. Tham khảo tài liệu và tài nguyên chính thức để khám phá các chức năng bổ sung.