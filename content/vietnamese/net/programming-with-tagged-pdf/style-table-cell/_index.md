---
title: Ô bảng kiểu
linktitle: Ô bảng kiểu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tạo kiểu cho các ô trong bảng bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tạo và tùy chỉnh bảng.
type: docs
weight: 160
url: /vi/net/programming-with-tagged-pdf/style-table-cell/
---
Chào mừng bạn đến với hướng dẫn chi tiết này về định dạng ô trong bảng bằng Aspose.PDF cho .NET. Trong hướng dẫn này, chúng tôi sẽ giải thích chi tiết từng bước của mã nguồn C# được cung cấp để giúp bạn hiểu cách tạo kiểu cho các ô trong bảng. Đảm bảo bạn đã cài đặt Aspose.PDF cho .NET và thiết lập môi trường phát triển của mình trước khi bắt đầu.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Chúng tôi đã tạo một tài liệu mới và đặt tiêu đề và ngôn ngữ cho tài liệu.

## Bước 3: Lấy phần tử cấu trúc gốc

Trong bước này, chúng ta sẽ lấy phần tử cấu trúc gốc cho tài liệu của mình.

```csharp
//Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
```

Chúng ta đã có phần tử cấu trúc gốc sẽ đóng vai trò là nơi chứa các phần tử mảng.

## Bước 4: Tạo phần tử cấu trúc mảng

Bây giờ hãy tạo một thành phần cấu trúc bảng mới cho tài liệu của chúng ta.

```csharp
// Tạo phần tử cấu trúc mảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Chúng tôi đã tạo một phần tử cấu trúc mảng mới và thêm nó vào phần tử cấu trúc gốc. Chúng tôi cũng đã tạo các phần tử đầu trang, nội dung và chân trang của bảng.

## Bước 5: Thêm tiêu đề bảng

Trong bước này, chúng ta sẽ thêm các tiêu đề bảng vào bảng của mình.

```csharp
// Số hàng và cột trong bảng
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Tạo hàng tiêu đề bảng
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Chúng tôi đã tạo một hàng tiêu đề cho bảng của mình và thêm các ô tiêu đề với các thuộc tính định dạng như màu nền, đường viền, lề và căn chỉnh.

## Bước 6: Thêm các hàng nội dung bảng

Bây giờ hãy thêm các hàng nội dung bảng vào bảng của chúng ta.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

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
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
```

Chúng tôi đã thêm các hàng vào phần nội dung của bảng bằng cách sử dụng các vòng lặp để lặp qua từng ô trong bảng. Chúng ta đặt các thuộc tính định dạng cho từng ô như màu nền, đường viền, lề, căn chỉnh văn bản, v.v.

## Bước 7: Thêm chân trang

Cuối cùng, chúng ta sẽ thêm chân bảng vào bảng của mình.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Chúng tôi đã tạo chân trang cho bảng của mình và thêm các ô chân trang có văn bản.



## Bước 8: Lưu tài liệu PDF được gắn thẻ

Bây giờ chúng tôi đã tạo tài liệu của mình với bảng được tạo kiểu, chúng tôi sẽ lưu nó dưới dạng tài liệu PDF được gắn thẻ.

```csharp
// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "StyleTableCell.pdf");
```

Chúng tôi đã lưu tài liệu PDF được gắn thẻ vào thư mục được chỉ định.

## Bước 9: Xác thực tuân thủ PDF/UA

Tiếp theo, chúng tôi sẽ xác thực tính tuân thủ PDF/UA của tài liệu của chúng tôi.

```csharp
// Kiểm tra tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Chúng tôi đã tải tài liệu PDF được gắn thẻ lên và xác thực tính tuân thủ PDF/UA của tài liệu đó bằng cách tạo báo cáo XML.

### Mã nguồn mẫu cho Ô bảng kiểu bằng cách sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Tạo phần tử cấu trúc bảng
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
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
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "StyleTableCell.pdf");

// Kiểm tra việc tuân thủ PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo kiểu cho các ô trong bảng bằng Aspose.PDF cho .NET. Chúng ta đã biết cách tạo tài liệu, thêm bảng có đầu trang, hàng nội dung và chân trang cũng như tùy chỉnh kiểu ô. Cuối cùng, chúng tôi đã lưu tài liệu PDF được gắn thẻ và xác thực tính tuân thủ PDF/UA của nó. Bây giờ bạn có thể sử dụng Aspose.PDF cho .NET để tạo và định kiểu bảng trong ứng dụng .NET của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của hướng dẫn này về định dạng ô trong bảng bằng Aspose.PDF cho .NET là gì?

Đáp: Hướng dẫn này nhằm mục đích cung cấp hướng dẫn toàn diện về cách tạo kiểu cho các ô bảng trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Nó bao gồm các hướng dẫn từng bước và các ví dụ về mã nguồn C# để giúp bạn hiểu và triển khai định dạng ô trong bảng.

#### Hỏi: Điều kiện tiên quyết để làm theo hướng dẫn này là gì?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt Aspose.PDF cho .NET và đã thiết lập môi trường phát triển của mình. Điều này bao gồm việc định cấu hình dự án của bạn để tham khảo thư viện Aspose.PDF.

#### Câu hỏi: Làm cách nào để tạo tài liệu PDF mới bằng Aspose.PDF cho .NET?

Đáp: Để tạo một tài liệu PDF mới, bạn cần khởi tạo một`Document` đối tượng từ thư viện Aspose.PDF. Mã nguồn C# được cung cấp minh họa cách tạo tài liệu cũng như đặt tiêu đề và ngôn ngữ cho tài liệu đó.

#### Hỏi: Tầm quan trọng của thành phần cấu trúc gốc trong tài liệu PDF là gì?

Trả lời: Phần tử cấu trúc gốc đóng vai trò là nơi chứa các phần tử cấu trúc khác, giúp tổ chức và phân loại nội dung của tài liệu PDF. Nó đóng một vai trò quan trọng trong việc thiết lập cấu trúc logic của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tạo một thành phần cấu trúc bảng và tùy chỉnh giao diện của nó bằng Aspose.PDF cho .NET?

 Đáp: Bạn có thể tạo một phần tử cấu trúc bảng bằng cách sử dụng`CreateTableElement()` phương pháp. Mã nguồn được cung cấp trình bày cách tùy chỉnh giao diện của bảng, bao gồm đầu trang, nội dung và chân trang, bằng cách đặt các thuộc tính như màu nền, đường viền, lề và căn chỉnh.

#### Câu hỏi: Tôi có thể thêm nhiều hàng và cột vào nội dung bảng và tùy chỉnh định dạng của chúng không?

Đáp: Có, phần hướng dẫn này trình bày cách thêm nhiều hàng và cột vào nội dung bảng bằng cách sử dụng vòng lặp. Nó cũng cung cấp các ví dụ về tùy chỉnh định dạng ô, chẳng hạn như màu nền, đường viền, căn chỉnh văn bản, kiểu phông chữ, v.v.

#### Câu hỏi: Mục đích của việc xác thực tính tuân thủ PDF/UA là gì và làm cách nào tôi có thể thực hiện việc xác thực này?

 Đáp: Việc xác thực tuân thủ PDF/UA đảm bảo rằng tài liệu PDF tuân thủ các tiêu chuẩn trợ năng, giúp người dùng khuyết tật dễ tiếp cận hơn. Hướng dẫn này cho thấy cách xác thực tính tuân thủ của PDF/UA bằng cách sử dụng`Validate()` phương pháp và tạo ra một báo cáo XML.

#### Câu hỏi: Làm cách nào tôi có thể áp dụng các khái niệm này cho các ứng dụng .NET của riêng mình?

Trả lời: Bạn có thể sử dụng các ví dụ về mã nguồn C# được cung cấp làm hướng dẫn triển khai định dạng ô bảng trong các ứng dụng .NET của riêng bạn. Tùy chỉnh mã khi cần để phù hợp với yêu cầu của bạn và tích hợp nó vào các dự án của bạn.

#### Câu hỏi: Có bất kỳ phương pháp hay nhất nào được đề xuất để tạo kiểu cho các ô bảng trong tài liệu PDF không?

Đáp: Khi tạo kiểu cho các ô trong bảng, hãy xem xét nhu cầu của đối tượng, bao gồm cả các yêu cầu về khả năng truy cập. Sử dụng màu sắc tương phản, phông chữ thích hợp và căn chỉnh ô rõ ràng để nâng cao khả năng đọc. Ngoài ra, hãy xác thực việc tuân thủ PDF/UA để đảm bảo đáp ứng các tiêu chuẩn về khả năng truy cập.

#### Câu hỏi: Tôi có thể khám phá những tính năng nào khác của Aspose.PDF dành cho .NET để thao tác với tài liệu PDF?

Trả lời: Aspose.PDF for .NET cung cấp nhiều tính năng để thao tác tài liệu PDF, bao gồm trích xuất văn bản, chèn hình ảnh, quản lý trường biểu mẫu, chữ ký số, v.v. Khám phá tài liệu và tài nguyên chính thức để tìm hiểu về các chức năng bổ sung.
