---
title: Nút radio theo chiều ngang và chiều dọc
linktitle: Nút radio theo chiều ngang và chiều dọc
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng tạo các nút radio ngang và dọc trong tài liệu PDF của bạn bằng Aspose.PDF cho .NET.
type: docs
weight: 180
url: /vi/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách tạo các nút radio được sắp xếp theo chiều ngang và chiều dọc trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của mình:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu

Tải tài liệu PDF hiện có:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Bước 3: Tùy chỉnh tùy chọn nút radio

Tùy chỉnh các tùy chọn nút radio bằng cách đặt các thuộc tính sau:

```csharp
formEditor. RadioGap = 4; // Khoảng cách giữa hai tùy chọn nút radio
formEditor. RadioHoriz = true; //Bố cục ngang của các nút radio
formEditor.RadioButtonItemSize = 20; // Kích thước của nút radio
formEditor.Facade.BorderWidth = 1; // Chiều rộng của đường viền nút radio
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Màu đường viền nút radio
```

## Bước 4: Thêm nút radio ngang

Thêm các nút radio được sắp xếp theo chiều ngang bằng cách chỉ định các tùy chọn và vị trí của trường:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Bước 5: Thêm nút radio dọc

Thêm các nút radio được sắp xếp theo chiều dọc bằng cách chỉ định các tùy chọn và vị trí của trường:

```csharp
formEditor. RadioHoriz = false; // Bố cục dọc của các nút radio
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Bước 6: Lưu tài liệu

Lưu tài liệu PDF đã sửa đổi:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Mã nguồn mẫu cho Nút radio theo chiều ngang và chiều dọc bằng cách sử dụng Aspose.PDF for .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tài liệu đã lưu trước đó
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap là khoảng cách giữa hai tùy chọn nút radio.
	formEditor.RadioGap = 4;
	// Thêm nút radio ngang
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize nếu kích thước của mục nút radio.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Thêm nút radio khác nằm dọc
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Lưu tài liệu PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách tạo các nút radio được sắp xếp theo chiều ngang và chiều dọc trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng tùy chỉnh bố cục của các nút radio và thêm chúng vào tài liệu PDF của mình bằng Aspose.PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Các nút radio được sắp xếp theo chiều ngang và chiều dọc trong tài liệu PDF là gì?

Đáp: Các nút radio được sắp xếp theo chiều ngang và chiều dọc trong tài liệu PDF đề cập đến hướng bố cục của các tùy chọn nút radio. Bố cục ngang đặt các tùy chọn nút radio cạnh nhau, cho phép người dùng thực hiện lựa chọn từ trái sang phải. Mặt khác, bố cục dọc xếp chồng các tùy chọn nút radio lên nhau, cho phép người dùng thực hiện lựa chọn từ trên xuống dưới.

#### Câu hỏi: Làm cách nào để tùy chỉnh giao diện của các tùy chọn nút radio trong Aspose.PDF cho .NET?

Trả lời: Bạn có thể tùy chỉnh giao diện của các tùy chọn nút radio trong Aspose.PDF for .NET bằng cách điều chỉnh một số thuộc tính. API cung cấp các tùy chọn để đặt khoảng cách giữa hai tùy chọn nút radio (`RadioGap`), hướng bố cục (`RadioHoriz`), kích thước của các mục nút radio (`RadioButtonItemSize`), chiều rộng đường viền và màu sắc của các nút radio, v.v.

#### Hỏi: Tôi có thể thêm cả nút radio ngang và dọc vào cùng một tài liệu PDF không?

Trả lời: Có, bạn có thể thêm cả nút radio ngang và dọc vào cùng một tài liệu PDF bằng Aspose.PDF for .NET. Mã nguồn mẫu được cung cấp trong hướng dẫn này trình bày cách trước tiên thêm các nút radio được sắp xếp theo chiều ngang, sau đó thêm một bộ nút radio khác được sắp xếp theo chiều dọc vào cùng một tài liệu PDF.

#### Câu hỏi: Tôi có thể đặt các tùy chọn nút radio khác nhau cho từng nhóm nút radio không?

 Trả lời: Có, bạn có thể đặt các tùy chọn nút radio khác nhau cho từng nhóm nút radio. Mỗi nhóm nên có một đặc điểm riêng`RadioButtonField` đối tượng và`RadioButtonOptionField` các đối tượng trong mỗi nhóm phải chia sẻ cùng một trang và có tên riêng cho các tùy chọn của chúng. Điều này đảm bảo rằng các nút radio trong mỗi nhóm hoạt động chính xác và các lựa chọn loại trừ lẫn nhau.

#### Câu hỏi: Cài đặt bố cục và giao diện của các nút radio có được hỗ trợ trong tất cả các ứng dụng và trình xem PDF không?

Trả lời: Có, cài đặt bố cục và giao diện của các nút radio được hỗ trợ trong tất cả các ứng dụng và trình xem PDF tuân thủ tiêu chuẩn. Đặc tả PDF xác định các nút radio và các thuộc tính khác nhau của chúng, giúp chúng được nhận dạng phổ biến ở định dạng PDF. Tuy nhiên, điều cần thiết là phải kiểm tra giao diện và hoạt động của các nút radio trong các trình xem PDF khác nhau để đảm bảo hiển thị nhất quán trên nhiều nền tảng khác nhau.