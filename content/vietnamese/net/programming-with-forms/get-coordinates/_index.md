---
title: Nhận tọa độ trường biểu mẫu PDF
linktitle: Nhận tọa độ trường biểu mẫu PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng lấy tọa độ trường biểu mẫu PDF trong tài liệu PDF của bạn với Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-forms/get-coordinates/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách lấy tọa độ trường biểu mẫu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu đầu ra

Tải tài liệu PDF đầu ra:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Bước 3: Tìm các trường đã thêm

Tìm các trường biểu mẫu đã thêm (trong ví dụ này, chúng tôi đang sử dụng các trường "Item1", "Item2" và "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Bước 4: Hiển thị vị trí các mục con theo từng trường

Chuyển qua các tùy chọn cho từng trường và xem tọa độ cho từng mục phụ:

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

### Mã nguồn mẫu để Nhận Tọa độ bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tài liệu đầu ra
	Document doc1 = new Document( dataDir + "input.pdf");
	// Tìm các trường bổ sung
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Và hiển thị vị trí của các mục phụ cho từng mục.
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

Trong hướng dẫn này, chúng ta đã tìm hiểu cách lấy tọa độ trường biểu mẫu bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng truy xuất tọa độ của các thành phần phụ của trường biểu mẫu trong tài liệu PDF bằng Aspose.PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể sử dụng phương pháp này để lấy tọa độ cho bất kỳ loại trường biểu mẫu nào trong Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể sử dụng phương pháp này để lấy tọa độ cho nhiều loại trường biểu mẫu khác nhau trong Aspose.PDF cho .NET. Mã nguồn C# được cung cấp minh họa cách lấy tọa độ cho các trường RadioButton, nhưng bạn có thể điều chỉnh cách tiếp cận tương tự cho các loại trường biểu mẫu khác, chẳng hạn như TextBox, CheckBox, ListBox, v.v.

#### Câu hỏi: Làm cách nào tôi có thể sửa đổi hoặc điều chỉnh tọa độ trường biểu mẫu?

Đáp: Tọa độ trường biểu mẫu dựa trên hệ tọa độ của tài liệu PDF, trong đó gốc (0,0) nằm ở góc dưới cùng bên trái của trang. Để sửa đổi hoặc điều chỉnh tọa độ trường biểu mẫu, bạn có thể cập nhật`Rect` thuộc tính của trường biểu mẫu tương ứng hoặc các mục con của nó, chẳng hạn như RadioButtonOptionField.

#### Câu hỏi: Tôi có thể lấy tọa độ của các trường biểu mẫu được thêm vào tài liệu PDF theo chương trình không?

Đáp: Có, bạn có thể lấy tọa độ của các trường biểu mẫu đã được thêm vào tài liệu PDF theo chương trình. Aspose.PDF for .NET cho phép bạn thêm các trường biểu mẫu một cách linh hoạt và sau khi thêm, bạn có thể truy xuất tọa độ của chúng bằng cách sử dụng phương pháp được trình bày trong hướng dẫn này.

#### Câu hỏi: Mục đích của việc truy xuất tọa độ trường biểu mẫu là gì?

Đáp: Việc truy xuất tọa độ trường biểu mẫu có thể hữu ích khi bạn cần thực hiện các thao tác hoặc xác thực liên quan đến bố cục cụ thể trên các trường biểu mẫu trong tài liệu PDF. Nó cho phép bạn định vị và căn chỉnh chính xác các trường biểu mẫu dựa trên tọa độ của chúng, đảm bảo rằng chúng xuất hiện chính xác trong tài liệu và mang lại trải nghiệm liền mạch cho người dùng.

#### Câu hỏi: Tọa độ trường biểu mẫu có được biểu thị bằng điểm hoặc đơn vị khác không?

Trả lời: Tọa độ trường biểu mẫu trong Aspose.PDF cho .NET được biểu thị bằng điểm. Một điểm tương đương với 1/72 inch, khiến nó trở thành đơn vị đo lường tiêu chuẩn ở định dạng PDF.