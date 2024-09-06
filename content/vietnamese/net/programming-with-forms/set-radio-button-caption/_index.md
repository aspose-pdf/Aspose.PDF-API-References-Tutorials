---
title: Đặt tiêu đề nút radio
linktitle: Đặt tiêu đề nút radio
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để đặt tiêu đề cho nút radio trong biểu mẫu PDF.
type: docs
weight: 280
url: /vi/net/programming-with-forms/set-radio-button-caption/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng thư viện Aspose.PDF cho .NET để xác định chú thích của nút radio trong biểu mẫu PDF. Chúng tôi sẽ chỉ cho bạn cách truy cập trường nút radio, tạo tùy chọn nút radio mới và tùy chỉnh chú thích nút.

## Bước 1: Cấu hình thư mục tài liệu

 Bước đầu tiên là cấu hình thư mục tài liệu nơi chứa biểu mẫu PDF mà bạn muốn làm việc. Bạn có thể sử dụng`dataDir` biến để chỉ định đường dẫn thư mục.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải biểu mẫu PDF nguồn

 Trong bước này, chúng tôi sẽ tải biểu mẫu PDF nguồn bằng cách sử dụng`Aspose.Pdf.Facades.Form` lớp Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Đảm bảo rằng tệp PDF chứa biểu mẫu có trong thư mục tài liệu đã chỉ định.

## Bước 3: Chỉnh sửa tiêu đề nút radio

Chúng tôi sẽ lặp qua các tên trường biểu mẫu và tìm kiếm các trường nút radio. Nếu tìm thấy trường phù hợp, chúng tôi sẽ tạo tùy chọn nút radio mới với chú thích tùy chỉnh và thêm vào trường hiện có.

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

Tùy chỉnh nút tùy chọn chú thích và các cài đặt khác khi cần thiết.

## Bước 4: Lưu PDF kết quả

 Bây giờ chúng ta đã hoàn tất việc sửa đổi tiêu đề nút radio, chúng ta có thể lưu tệp PDF kết quả bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Hãy chắc chắn chỉ định đường dẫn đầy đủ và tên tệp cho tệp PDF kết quả.

### Mã nguồn mẫu cho Đặt tiêu đề nút radio bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải biểu mẫu PDF nguồn
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
		// Chỉ định chế độ ngắt dòng từ
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

Trong hướng dẫn này, chúng ta đã học cách sử dụng thư viện Aspose.PDF cho .NET để đặt chú thích cho nút radio trong biểu mẫu PDF. Bằng cách làm theo các bước được mô tả, bạn có thể tùy chỉnh các tùy chọn nút radio và thay đổi chú thích khi cần. Hãy thoải mái khám phá thêm các tính năng của Aspose.PDF cho .NET để mở rộng khả năng thao tác các tệp PDF.

### Câu hỏi thường gặp

#### H: Tôi có thể sử dụng Aspose.PDF cho .NET để đặt chú thích cho các nút radio trong biểu mẫu PDF không?

A: Có, bạn có thể sử dụng Aspose.PDF cho .NET để đặt chú thích cho các nút radio trong biểu mẫu PDF. Mã nguồn mẫu được cung cấp sẽ trình bày cách truy cập trường nút radio, tạo tùy chọn nút radio mới với chú thích tùy chỉnh và cập nhật trường hiện có.

#### H: Làm thế nào tôi có thể tùy chỉnh giao diện của chú thích nút radio, chẳng hạn như kích thước phông chữ và màu sắc?

 A: Bạn có thể tùy chỉnh giao diện của tiêu đề nút radio bằng cách điều chỉnh các thuộc tính của`TextFragment` được sử dụng cho chú thích. Ví dụ, bạn có thể thiết lập phông chữ, cỡ chữ, màu sắc, khoảng cách dòng và các tùy chọn định dạng văn bản khác.

#### H: Có thể thêm nhiều tùy chọn nút radio có chú thích khác nhau vào một nhóm nút radio không?

A: Có, bạn có thể thêm nhiều tùy chọn nút radio có chú thích khác nhau vào một nhóm nút radio. Mỗi tùy chọn sẽ đại diện cho một lựa chọn khác nhau và người dùng chỉ có thể chọn một tùy chọn từ nhóm.

#### H: Tôi có thể sử dụng Aspose.PDF cho .NET để sửa đổi các trường biểu mẫu khác trong tài liệu PDF không?

A: Có, Aspose.PDF for .NET cung cấp một bộ tính năng toàn diện để thao tác nhiều trường biểu mẫu khác nhau trong tài liệu PDF, chẳng hạn như trường văn bản, hộp kiểm, danh sách thả xuống, v.v. Bạn có thể sử dụng thư viện để đặt giá trị, sửa đổi giao diện và thêm tính tương tác vào các trường biểu mẫu.

#### H: Aspose.PDF cho .NET có hỗ trợ làm việc với các tệp PDF được tạo từ các nguồn khác, chẳng hạn như tài liệu được quét không?

A: Có, Aspose.PDF for .NET hỗ trợ làm việc với các tệp PDF được tạo từ nhiều nguồn khác nhau, bao gồm cả tài liệu được quét. Thư viện cung cấp khả năng OCR (Nhận dạng ký tự quang học) để trích xuất văn bản từ các tệp PDF được quét và xử lý nội dung theo chương trình.