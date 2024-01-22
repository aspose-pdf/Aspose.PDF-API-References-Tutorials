---
title: Các hộp kiểm được nhóm trong tài liệu PDF
linktitle: Các hộp kiểm được nhóm trong tài liệu PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng tạo các hộp kiểm được nhóm trong tài liệu PDF với Aspose.PDF cho .NET.
type: docs
weight: 170
url: /vi/net/programming-with-forms/grouped-check-boxes/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách tạo các hộp kiểm được nhóm trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của mình:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Khởi tạo đối tượng tài liệu

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

Khởi tạo một đối tượng RadioButtonField với số trang làm đối số:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Bước 5: Thêm tùy chọn nút radio

Thêm các tùy chọn nút radio bằng đối tượng RadioButtonOptionField và chỉ định vị trí của chúng bằng đối tượng Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Bước 6: Tùy chỉnh tùy chọn nút radio

Tùy chỉnh các tùy chọn nút radio bằng cách đặt kiểu, đường viền và giao diện của chúng:

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

### Mã nguồn mẫu cho Hộp kiểm được nhóm bằng Aspose.PDF cho .NET 
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
	// Thêm tùy chọn nút radio đầu tiên và cũng chỉ định nguồn gốc của nó bằng đối tượng Hình chữ nhật
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
	// Thêm nút radio để tạo đối tượng của đối tượng Document
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

Trong hướng dẫn này, chúng ta đã tìm hiểu cách tạo các hộp kiểm được nhóm trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng thêm các tùy chọn nút radio tùy chỉnh và gói chúng vào tài liệu PDF của mình bằng Aspose.PDF.

### Câu hỏi thường gặp

#### Hỏi: Các hộp kiểm được nhóm trong tài liệu PDF là gì?

Đáp: Các hộp kiểm được nhóm trong tài liệu PDF đề cập đến một tập hợp các tùy chọn nút radio được nhóm lại với nhau. Nút radio cho phép người dùng chỉ chọn một tùy chọn từ một nhóm các lựa chọn loại trừ lẫn nhau. Khi một nút radio được chọn, các nút khác trong cùng nhóm sẽ tự động được bỏ chọn. Hành vi nhóm này hữu ích khi bạn muốn cung cấp cho người dùng nhiều tùy chọn nhưng chỉ giới hạn lựa chọn của họ ở một lựa chọn.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của các hộp kiểm được nhóm trong Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của các hộp kiểm được nhóm trong Aspose.PDF cho .NET. API cung cấp nhiều tùy chọn khác nhau để đặt kiểu, đường viền và giao diện của các tùy chọn nút radio. Bạn có thể xác định vị trí của từng tùy chọn, chọn giữa các kiểu hộp khác nhau (ví dụ: hình vuông, hình tròn, hình chữ thập) và điều chỉnh các thuộc tính đường viền để đạt được hình ảnh trực quan mong muốn.

#### Hỏi: Làm cách nào để thêm các hộp kiểm được nhóm vào một trang cụ thể trong tài liệu PDF?

Đáp: Để thêm các hộp kiểm được nhóm vào một trang cụ thể trong tài liệu PDF, bạn cần tạo một`RadioButtonField` đối tượng với số trang mong muốn làm đối số. Sau đó, tạo`RadioButtonOptionField` các đối tượng đại diện cho từng tùy chọn nút radio và chỉ định vị trí của chúng bằng cách sử dụng`Rectangle` sự vật. Cuối cùng, thêm các tùy chọn này vào`RadioButtonField` và tùy chỉnh giao diện của chúng nếu cần trước khi thêm`RadioButtonField` sang dạng tài liệu.

#### Hỏi: Tôi có thể thêm nhiều nhóm hộp kiểm vào một tài liệu PDF không?

 Đáp: Có, bạn có thể thêm nhiều nhóm hộp kiểm vào một tài liệu PDF. Mỗi nhóm nên có một đặc điểm riêng`RadioButtonField` đối tượng và`RadioButtonOptionField` các đối tượng trong mỗi nhóm phải chia sẻ cùng một trang và có tên riêng cho các tùy chọn của chúng. Điều này đảm bảo rằng các nút radio trong mỗi nhóm hoạt động chính xác và các lựa chọn loại trừ lẫn nhau.

#### Câu hỏi: Các hộp kiểm được nhóm có được hỗ trợ trong tất cả các ứng dụng và trình xem PDF không?

Đáp: Có, các hộp kiểm được nhóm lại được hỗ trợ trong tất cả các ứng dụng và trình xem PDF tuân thủ tiêu chuẩn. Đặc tả PDF xác định các nút radio và hành vi nhóm của chúng, làm cho chúng được nhận dạng phổ biến ở định dạng PDF. Tuy nhiên, điều cần thiết là phải kiểm tra chức năng ở các trình xem PDF khác nhau để đảm bảo hoạt động nhất quán trên nhiều nền tảng khác nhau.