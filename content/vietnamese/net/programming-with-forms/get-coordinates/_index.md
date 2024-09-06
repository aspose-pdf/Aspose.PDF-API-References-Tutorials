---
title: Nhận tọa độ trường biểu mẫu PDF
linktitle: Nhận tọa độ trường biểu mẫu PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng lấy tọa độ trường biểu mẫu PDF trong tài liệu PDF của bạn bằng Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-forms/get-coordinates/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách lấy tọa độ trường biểu mẫu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# từng bước để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu đầu ra

Tải tài liệu PDF đầu ra:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Bước 3: Tìm các trường đã thêm

Tìm các trường biểu mẫu đã thêm (trong ví dụ này, chúng tôi sử dụng các trường "Item1", "Item2" và "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Bước 4: Hiển thị vị trí các mục con cho mỗi trường

Duyệt qua các tùy chọn cho từng trường và xem tọa độ của từng mục con:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Mã nguồn mẫu để Lấy Tọa độ bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tài liệu đầu ra
	Document doc1 = new Document( dataDir + "input.pdf");
	// Tìm thêm trường
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Và hiển thị vị trí của các mục con cho từng mục.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lấy tọa độ trường biểu mẫu bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng lấy tọa độ của các phần tử con của trường biểu mẫu trong tài liệu PDF bằng Aspose.PDF.

### Câu hỏi thường gặp

#### H: Tôi có thể sử dụng phương pháp này để lấy tọa độ cho bất kỳ loại trường biểu mẫu nào trong Aspose.PDF cho .NET không?

A: Có, bạn có thể sử dụng phương pháp này để lấy tọa độ cho nhiều loại trường biểu mẫu khác nhau trong Aspose.PDF cho .NET. Mã nguồn C# được cung cấp minh họa cách lấy tọa độ cho các trường RadioButton, nhưng bạn có thể áp dụng phương pháp tương tự cho các loại trường biểu mẫu khác, chẳng hạn như TextBox, CheckBox, ListBox, v.v.

#### H: Làm thế nào tôi có thể sửa đổi hoặc điều chỉnh tọa độ trường biểu mẫu?

A: Tọa độ trường biểu mẫu dựa trên hệ tọa độ của tài liệu PDF, trong đó gốc tọa độ (0,0) nằm ở góc dưới bên trái của trang. Để sửa đổi hoặc điều chỉnh tọa độ trường biểu mẫu, bạn có thể cập nhật`Rect` thuộc tính của trường biểu mẫu tương ứng hoặc các mục con của nó, chẳng hạn như RadioButtonOptionField.

#### H: Tôi có thể lấy tọa độ của các trường biểu mẫu được thêm theo chương trình vào tài liệu PDF không?

A: Có, bạn có thể lấy tọa độ của các trường biểu mẫu được thêm theo chương trình vào tài liệu PDF. Aspose.PDF cho .NET cho phép bạn thêm các trường biểu mẫu một cách động và sau khi thêm, bạn có thể lấy tọa độ của chúng bằng cách sử dụng phương pháp được trình bày trong hướng dẫn này.

#### H: Mục đích của việc lấy tọa độ trường biểu mẫu là gì?

A: Việc lấy tọa độ trường biểu mẫu có thể hữu ích khi bạn cần thực hiện các thao tác hoặc xác thực liên quan đến bố cục cụ thể trên các trường biểu mẫu trong tài liệu PDF. Nó cho phép bạn định vị và căn chỉnh chính xác các trường biểu mẫu dựa trên tọa độ của chúng, đảm bảo rằng chúng xuất hiện chính xác trong tài liệu và cung cấp trải nghiệm người dùng liền mạch.

#### H: Tọa độ của trường biểu mẫu được thể hiện bằng điểm hay đơn vị khác?

A: Tọa độ trường biểu mẫu trong Aspose.PDF cho .NET được thể hiện bằng điểm. Một điểm tương đương với 1/72 inch, khiến nó trở thành đơn vị đo lường chuẩn trong định dạng PDF.