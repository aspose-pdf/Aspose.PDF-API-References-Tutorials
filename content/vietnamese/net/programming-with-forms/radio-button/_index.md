---
title: Nút radio
linktitle: Nút radio
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng thêm nút radio vào tài liệu PDF của bạn với Aspose.PDF cho .NET.
type: docs
weight: 220
url: /vi/net/programming-with-forms/radio-button/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách thêm nút radio vào tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# từng bước để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Khởi tạo một đối tượng tài liệu

Khởi tạo đối tượng Tài liệu để tạo tài liệu PDF mới:

```csharp
Document pdfDocument = new Document();
```

## Bước 3: Thêm trang

Thêm một trang vào tài liệu PDF:

```csharp
pdfDocument.Pages.Add();
```

## Bước 4: Khởi tạo đối tượng RadioButtonField

Khởi tạo đối tượng RadioButtonField chỉ định số trang làm đối số:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Bước 5: Thêm tùy chọn nút radio

Thêm tùy chọn nút radio vào đối tượng RadioButtonField bằng cách chỉ định tọa độ của mỗi tùy chọn với đối tượng Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Bước 6: Thêm nút radio vào biểu mẫu

Thêm nút radio vào đối tượng Form của tài liệu:

```csharp
pdfDocument.Form.Add(radio);
```

## Bước 7: Lưu tài liệu PDF

Lưu tài liệu PDF đã tạo:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu cho Nút Radio sử dụng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Khởi tạo đối tượng Tài liệu
	Document pdfDocument = new Document();
	// Thêm một trang vào tệp PDF
	pdfDocument.Pages.Add();
	// Khởi tạo đối tượng RadioButtonField với số trang làm đối số
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Thêm tùy chọn nút radio đầu tiên và cũng chỉ định nguồn gốc của nó bằng cách sử dụng đối tượng Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Thêm tùy chọn nút radio thứ hai
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Thêm nút radio vào đối tượng biểu mẫu của đối tượng Tài liệu
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Lưu tệp PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thêm nút radio vào tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng tạo nút radio và đặt nó vào một trang cụ thể trong tài liệu PDF của mình.


### Câu hỏi thường gặp

#### H: Tôi có thể tùy chỉnh giao diện của nút radio, chẳng hạn như kích thước và màu sắc của nó không?

 A: Có, bạn có thể tùy chỉnh giao diện của nút radio bằng cách sử dụng`Rectangle` tọa độ của đối tượng để xác định kích thước và vị trí của nó. Aspose.PDF cho .NET cho phép bạn điều chỉnh giao diện của nút radio cho phù hợp với nhu cầu của bạn.

#### H: Tôi có thể thêm nhiều nút radio có nhóm khác nhau trên cùng một trang không?

A: Có, bạn có thể thêm nhiều nút radio với các nhóm khác nhau trên cùng một trang. Mỗi nhóm nút radio có thể có một tên duy nhất và chỉ có thể chọn một tùy chọn trong mỗi nhóm tại một thời điểm.

#### H: Làm thế nào tôi có thể thêm nhãn hoặc mô tả văn bản vào tùy chọn nút radio?

 A: Để thêm nhãn hoặc mô tả văn bản vào các tùy chọn nút radio, bạn có thể sử dụng`TextStamp`lớp từ Aspose.PDF cho .NET để phủ văn bản lên tài liệu PDF theo tọa độ cụ thể.

#### H: Aspose.PDF cho .NET có tương thích với tất cả các phiên bản .NET Framework không?

A: Có, Aspose.PDF cho .NET tương thích với mọi phiên bản .NET Framework, bao gồm .NET Core và .NET Standard.

#### H: Tôi có thể lập trình để kiểm soát việc lựa chọn tùy chọn nút radio trong tài liệu PDF không?

 A: Có, bạn có thể lập trình kiểm soát việc lựa chọn tùy chọn nút radio bằng cách sử dụng`IsSelected` tài sản của`RadioButtonOption` lớp. Thuộc tính này cho phép bạn thiết lập một tùy chọn cụ thể thành đã chọn.