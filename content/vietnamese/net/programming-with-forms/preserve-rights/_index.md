---
title: Bảo vệ quyền
linktitle: Bảo vệ quyền
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Bảo toàn quyền biểu mẫu trong tài liệu PDF của bạn với Aspose.PDF for .NET.
type: docs
weight: 210
url: /vi/net/programming-with-forms/preserve-rights/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách bảo vệ quyền biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của mình:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu

 Mở tài liệu PDF nguồn bằng cách sử dụng`FileStream` với quyền đọc và viết:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Bước 3: Chỉnh sửa trường biểu mẫu

Đi qua tất cả các trường biểu mẫu trong tài liệu và thực hiện những thay đổi cần thiết. Trong ví dụ này, chúng tôi đang thay đổi giá trị của trường biểu mẫu có tên "A1":

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Bước 4: Lưu tài liệu đã cập nhật

Lưu tài liệu PDF đã sửa đổi:

```csharp
pdfDocument.Save();
```

##  Bước 5: Đóng`FileStream`

 Đừng quên đóng cửa`FileStream` phản đối khi bạn hoàn thành:

```csharp
fs. Close();
```

### Mã nguồn mẫu cho Bảo vệ quyền bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Đọc biểu mẫu PDF nguồn với FileAccess của Đọc và Viết.
// Chúng tôi cần quyền ReadWrite vì sau khi sửa đổi,
// Chúng ta cần lưu nội dung cập nhật trong cùng một tài liệu/tệp.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Khởi tạo phiên bản tài liệu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Nhận giá trị từ tất cả các trường
foreach (Field formField in pdfDocument.Form)
{
	// Nếu tên đầy đủ của trường chứa A1, hãy thực hiện thao tác
	if (formField.FullName.Contains("A1"))
	{
		// Truyền trường biểu mẫu dưới dạng TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Sửa đổi giá trị trường
		textBoxField.Value = "Testing";
	}
}
// Lưu tài liệu đã cập nhật vào save FileStream
pdfDocument.Save();
// Đóng đối tượng File Stream
fs.Close();
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách bảo vệ quyền của biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng truy cập các trường biểu mẫu và thực hiện các thay đổi cụ thể trong khi vẫn duy trì quyền truy cập và quyền ghi.


### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể bảo lưu quyền của các trường biểu mẫu cụ thể mà không ảnh hưởng đến các trường khác trong tài liệu PDF không?

 Đ: Có, bằng cách sử dụng`FullName` thuộc tính của các trường biểu mẫu, bạn có thể nhắm mục tiêu các trường biểu mẫu cụ thể để bảo tồn trong khi không ảnh hưởng đến các trường khác.

#### Câu hỏi: Tôi có thể bảo vệ quyền của biểu mẫu trong tài liệu PDF được bảo vệ bằng mật khẩu không?

Đáp: Có, Aspose.PDF for .NET cho phép bạn bảo lưu các quyền của biểu mẫu ngay cả trong các tài liệu PDF được bảo vệ bằng mật khẩu, miễn là bạn cung cấp mật khẩu chính xác để truy cập và sửa đổi tệp.

#### Câu hỏi: Điều gì xảy ra nếu tôi cố gắng sửa đổi các trường biểu mẫu mà không có quyền truy cập thích hợp?

Đáp: Nếu bạn cố gắng sửa đổi các trường biểu mẫu mà không có quyền truy cập thích hợp thì những thay đổi đó sẽ không được lưu trong tài liệu PDF và bạn có thể nhận được một ngoại lệ hoặc thông báo lỗi.

#### Câu hỏi: Aspose.PDF for .NET có tương thích với tất cả các phiên bản .NET Framework không?

Trả lời: Có, Aspose.PDF cho .NET tương thích với tất cả các phiên bản .NET Framework, bao gồm .NET Core và .NET Standard.

#### Câu hỏi: Tôi có thể bảo toàn quyền biểu mẫu trong tài liệu PDF theo chương trình bằng các ngôn ngữ lập trình khác ngoài C# không?

Đáp: Có, Aspose.PDF for .NET hỗ trợ nhiều ngôn ngữ lập trình khác nhau, chẳng hạn như VB.NET và ASP.NET, ngoài C#.