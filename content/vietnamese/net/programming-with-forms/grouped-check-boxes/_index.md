---
title: Nhóm các hộp kiểm trong tài liệu PDF
linktitle: Nhóm các hộp kiểm trong tài liệu PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng tạo các hộp kiểm được nhóm trong tài liệu PDF với Aspose.PDF cho .NET.
type: docs
weight: 170
url: /vi/net/programming-with-forms/grouped-check-boxes/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách tạo nhóm hộp kiểm trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# từng bước để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Khởi tạo một đối tượng tài liệu

Khởi tạo một đối tượng Tài liệu:

```csharp
Document pdfDocument = new Document();
```

## Bước 3: Thêm trang vào tài liệu PDF

Thêm một trang vào tài liệu PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Bước 4: Khởi tạo đối tượng RadioButtonField

Khởi tạo đối tượng RadioButtonField với số trang làm đối số:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Bước 5: Thêm tùy chọn nút radio

Thêm tùy chọn nút radio bằng cách sử dụng đối tượng RadioButtonOptionField và chỉ định vị trí của chúng bằng cách sử dụng đối tượng Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Bước 6: Tùy chỉnh tùy chọn nút radio

Tùy chỉnh các tùy chọn nút radio bằng cách thiết lập kiểu dáng, đường viền và giao diện của chúng:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Bước 7: Thêm các nút radio vào biểu mẫu

Thêm các nút radio vào đối tượng biểu mẫu tài liệu:

```csharp
pdfDocument.Form.Add(radio);
```

## Bước 8: Lưu tài liệu

Lưu tài liệu PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu cho Hộp kiểm nhóm sử dụng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Khởi tạo đối tượng Tài liệu
	Document pdfDocument = new Document();
	// Thêm một trang vào tệp PDF
	Page page = pdfDocument.Pages.Add();
	// Khởi tạo đối tượng RadioButtonField với số trang làm đối số
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Thêm tùy chọn nút radio đầu tiên và cũng chỉ định nguồn gốc của nó bằng cách sử dụng đối tượng Rectangle
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Thêm nút radio vào đối tượng biểu mẫu của đối tượng Tài liệu
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Lưu tài liệu PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo các hộp kiểm nhóm trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng thêm các tùy chọn nút radio tùy chỉnh và đóng gói chúng trong tài liệu PDF của mình bằng Aspose.PDF.

### Câu hỏi thường gặp

#### H: Các hộp kiểm được nhóm trong tài liệu PDF là gì?

A: Các hộp kiểm nhóm trong tài liệu PDF đề cập đến một tập hợp các tùy chọn nút radio được nhóm lại với nhau. Các nút radio cho phép người dùng chỉ chọn một tùy chọn từ một nhóm các lựa chọn loại trừ lẫn nhau. Khi một nút radio được chọn, các nút radio khác trong cùng nhóm sẽ tự động bị bỏ chọn. Hành vi nhóm này hữu ích khi bạn muốn cung cấp cho người dùng nhiều tùy chọn nhưng giới hạn lựa chọn của họ chỉ ở một lựa chọn.

#### H: Tôi có thể tùy chỉnh giao diện của các hộp kiểm được nhóm trong Aspose.PDF cho .NET không?

A: Có, bạn có thể tùy chỉnh giao diện của các hộp kiểm được nhóm trong Aspose.PDF cho .NET. API cung cấp nhiều tùy chọn khác nhau để thiết lập kiểu, đường viền và giao diện của các tùy chọn nút radio. Bạn có thể xác định vị trí của từng tùy chọn, chọn giữa các kiểu hộp khác nhau (ví dụ: hình vuông, hình tròn, hình chữ thập) và điều chỉnh các thuộc tính đường viền để đạt được hình ảnh mong muốn.

#### H: Làm thế nào để thêm các hộp kiểm được nhóm vào một trang cụ thể trong tài liệu PDF?

A: Để thêm các hộp kiểm được nhóm vào một trang cụ thể trong tài liệu PDF, bạn cần khởi tạo một`RadioButtonField` đối tượng với số trang mong muốn làm đối số. Sau đó, tạo`RadioButtonOptionField` các đối tượng đại diện cho mỗi tùy chọn nút radio và chỉ định vị trí của chúng bằng cách sử dụng`Rectangle` đối tượng. Cuối cùng, thêm các tùy chọn này vào`RadioButtonField` và tùy chỉnh giao diện của chúng khi cần thiết trước khi thêm`RadioButtonField` vào mẫu tài liệu.

#### H: Tôi có thể thêm nhiều nhóm hộp kiểm vào một tài liệu PDF không?

 A: Có, bạn có thể thêm nhiều nhóm hộp kiểm vào một tài liệu PDF. Mỗi nhóm phải có một`RadioButtonField` đối tượng, và`RadioButtonOptionField` các đối tượng trong mỗi nhóm phải chia sẻ cùng một trang và tên duy nhất cho các tùy chọn của chúng. Điều này đảm bảo rằng các nút radio trong mỗi nhóm hoạt động chính xác và các lựa chọn loại trừ lẫn nhau.

#### H: Có phải tất cả các ứng dụng và trình xem PDF đều hỗ trợ hộp kiểm nhóm không?

A: Có, các hộp kiểm nhóm được hỗ trợ trong tất cả các trình xem PDF và ứng dụng tuân thủ chuẩn. Đặc tả PDF định nghĩa các nút radio và hành vi nhóm của chúng, giúp chúng được nhận dạng chung trong định dạng PDF. Tuy nhiên, điều cần thiết là phải kiểm tra chức năng trong các trình xem PDF khác nhau để đảm bảo hành vi nhất quán trên nhiều nền tảng khác nhau.