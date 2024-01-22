---
title: Đặt chú thích nút radio
linktitle: Đặt chú thích nút radio
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để đặt chú thích cho nút radio ở dạng PDF.
type: docs
weight: 280
url: /vi/net/programming-with-forms/set-radio-button-caption/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng thư viện Aspose.PDF cho .NET để xác định chú thích của nút radio ở dạng PDF. Chúng tôi sẽ chỉ cho bạn cách truy cập trường nút radio, tạo tùy chọn nút radio mới và tùy chỉnh chú thích nút.

## Bước 1: Cấu hình thư mục tài liệu

 Bước đầu tiên là định cấu hình thư mục tài liệu chứa biểu mẫu PDF mà bạn muốn làm việc. Bạn có thể dùng`dataDir` biến để chỉ định đường dẫn thư mục.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải biểu mẫu PDF nguồn

 Trong bước này, chúng tôi sẽ tải biểu mẫu PDF nguồn bằng cách sử dụng`Aspose.Pdf.Facades.Form` lớp Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Đảm bảo rằng tệp PDF chứa biểu mẫu có trong thư mục tài liệu được chỉ định.

## Bước 3: Chỉnh sửa chú thích nút radio

Chúng tôi sẽ lặp qua tên trường biểu mẫu và tìm kiếm các trường nút radio. Nếu tìm thấy trường phù hợp, chúng tôi sẽ tạo tùy chọn nút radio mới với chú thích tùy chỉnh và thêm nó vào trường hiện có.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Tạo một đối tượng TextParagraph
TextParagraph par = new TextParagraph();
// Đặt vị trí đoạn văn
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Chỉ định chế độ ngắt dòng
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Thêm TextFragment mới vào đoạn văn
par.AppendLine(updatedFragment);
// Thêm TextParagraph bằng TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Tùy chỉnh nút radio chú thích và các cài đặt khác nếu cần.

## Bước 4: Lưu tệp PDF kết quả

 Bây giờ chúng ta đã sửa đổi xong chú thích nút radio, chúng ta có thể lưu tệp PDF thu được bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Đảm bảo chỉ định đường dẫn và tên tệp đầy đủ cho tệp PDF kết quả.

### Mã nguồn mẫu cho Đặt chú thích nút radio bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải mẫu PDF nguồn
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Tạo đối tượng TextParagraph
		TextParagraph par = new TextParagraph();
		// Đặt vị trí đoạn văn
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Chỉ định chế độ ngắt dòng
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Thêm TextFragment mới vào đoạn văn
		par.AppendLine(updatedFragment);
		// Thêm TextParagraph bằng TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã tìm hiểu cách sử dụng thư viện Aspose.PDF cho .NET để đặt chú thích cho nút radio ở dạng PDF. Bằng cách làm theo các bước được mô tả, bạn có thể tùy chỉnh các tùy chọn nút radio và thay đổi chú thích nếu cần. Vui lòng khám phá thêm các tính năng của Aspose.PDF cho .NET để mở rộng khả năng thao tác với tệp PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET để đặt chú thích cho các nút radio ở dạng PDF không?

Trả lời: Có, bạn có thể sử dụng Aspose.PDF for .NET để đặt chú thích cho các nút radio ở dạng PDF. Mã nguồn mẫu được cung cấp trình bày cách truy cập vào trường nút radio, tạo tùy chọn nút radio mới với chú thích tùy chỉnh và cập nhật trường hiện có.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh hình thức của chú thích nút radio, chẳng hạn như kích thước phông chữ và màu sắc?

 Đáp: Bạn có thể tùy chỉnh hình thức của chú thích nút radio bằng cách điều chỉnh các thuộc tính của`TextFragment` được sử dụng cho chú thích. Ví dụ: bạn có thể đặt phông chữ, cỡ chữ, màu sắc, khoảng cách dòng và các tùy chọn định dạng văn bản khác.

#### Câu hỏi: Có thể thêm nhiều tùy chọn nút radio với chú thích khác nhau vào một nhóm nút radio không?

Đáp: Có, bạn có thể thêm nhiều tùy chọn nút radio với các chú thích khác nhau vào một nhóm nút radio. Mỗi tùy chọn sẽ đại diện cho một lựa chọn khác nhau và người dùng chỉ được chọn một tùy chọn trong nhóm.

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET để sửa đổi các trường biểu mẫu khác trong tài liệu PDF không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp một bộ tính năng toàn diện để thao tác các trường biểu mẫu khác nhau trong tài liệu PDF, chẳng hạn như trường văn bản, hộp kiểm, danh sách thả xuống, v.v. Bạn có thể sử dụng thư viện để đặt giá trị, sửa đổi giao diện và thêm tính tương tác vào các trường biểu mẫu.

#### Câu hỏi: Aspose.PDF for .NET có hỗ trợ hoạt động với các tệp PDF được tạo từ các nguồn khác, chẳng hạn như tài liệu được quét không?

Trả lời: Có, Aspose.PDF for .NET hỗ trợ làm việc với các tệp PDF được tạo từ nhiều nguồn khác nhau, bao gồm cả tài liệu được quét. Thư viện cung cấp khả năng OCR (Nhận dạng ký tự quang học) để trích xuất văn bản từ các tệp PDF được quét và xử lý nội dung theo chương trình.