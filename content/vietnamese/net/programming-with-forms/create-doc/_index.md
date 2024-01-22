---
title: Tạo tài liệu
linktitle: Tạo tài liệu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng tạo tài liệu bằng các nút radio bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-forms/create-doc/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách tạo tài liệu bằng các nút radio bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

##Bước 1: Chuẩn bị

Trước tiên, hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu mới

Tạo một đối tượng Document mới để giữ tài liệu PDF:

```csharp
Document doc = new Document();
```

## Bước 3: Thêm trang

Thêm một trang mới vào tài liệu:

```csharp
Page page = doc.Pages.Add();
```

## Bước 4: Thêm trường nút radio

Tạo trường nút radio và đặt vị trí cũng như kích thước của nó:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Bước 5: Thêm tùy chọn nút radio

Thêm các tùy chọn mong muốn vào trường nút radio. Bạn có thể đặt tọa độ và kích thước của từng tùy chọn nếu cần:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Bước 6: Thêm trường nút radio vào biểu mẫu

Thêm trường nút radio vào bộ sưu tập Trường biểu mẫu tài liệu:

```csharp
doc.Form.Add(field);
```

## Bước 7: Lưu tài liệu

Lưu tài liệu PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu để tạo tài liệu bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tạo một tài liệu mới
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Thêm trường nút radio
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Thêm tùy chọn nút radio. xin lưu ý rằng các tùy chọn này nằm
	// Không theo chiều ngang cũng không theo chiều dọc.
	// Bạn có thể thử đặt bất kỳ tọa độ nào (và thậm chí cả kích thước) cho chúng.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Lưu tài liệu PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo tài liệu bằng các nút radio bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng thêm các nút radio vào tài liệu PDF của mình bằng Aspose.PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của các nút radio trong tài liệu bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của các nút radio trong tài liệu bằng Aspose.PDF for .NET. Bạn có thể đặt các thuộc tính như kích thước, màu sắc, kiểu đường viền, v.v. để tùy chỉnh giao diện của các nút radio.

#### Câu hỏi: Làm cách nào tôi có thể thêm nhóm nút radio với các tùy chọn loại trừ lẫn nhau?

Đáp: Để tạo các tùy chọn loại trừ lẫn nhau, bạn có thể thêm nhiều trường nút radio có cùng tên. Điều này sẽ đảm bảo rằng khi một tùy chọn được chọn, các tùy chọn khác có cùng tên sẽ tự động được bỏ chọn.

#### Câu hỏi: Có thể đặt tùy chọn được chọn mặc định cho các nút radio không?

Trả lời: Có, bạn có thể đặt tùy chọn được chọn mặc định cho các nút radio bằng Aspose.PDF cho .NET. Bạn có thể dùng`Selected` tài sản của`RadioButtonOptionField` đối tượng để đánh dấu một tùy chọn là được chọn theo mặc định.

#### Câu hỏi: Tôi có thể thêm trình xử lý sự kiện vào nút radio không?

 Trả lời: Có, bạn có thể thêm trình xử lý sự kiện vào nút radio bằng Aspose.PDF cho .NET. Bạn có thể liên kết các hành động JavaScript, chẳng hạn như`OnValueChanged`, tới các nút radio để thực hiện các hành động cụ thể khi người dùng chọn một tùy chọn.

#### Câu hỏi: Làm cách nào tôi có thể truy xuất tùy chọn đã chọn từ nhóm nút radio sau khi người dùng thực hiện lựa chọn?

 Đáp: Bạn có thể truy xuất tùy chọn đã chọn từ nhóm nút radio bằng Aspose.PDF for .NET. Sau khi người dùng lựa chọn, bạn có thể truy cập vào`Selected` tài sản của`RadioButtonOptionField` đối tượng để kiểm tra tùy chọn nào được chọn.