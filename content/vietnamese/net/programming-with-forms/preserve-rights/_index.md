---
title: Bảo vệ quyền
linktitle: Bảo vệ quyền
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Bảo toàn quyền định dạng trong tài liệu PDF của bạn với Aspose.PDF cho .NET.
type: docs
weight: 210
url: /vi/net/programming-with-forms/preserve-rights/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách bảo toàn quyền biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# từng bước để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tài liệu

 Mở tài liệu PDF nguồn bằng cách sử dụng`FileStream` với quyền đọc và ghi:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Bước 3: Chỉnh sửa trường biểu mẫu

Duyệt qua tất cả các trường biểu mẫu trong tài liệu và thực hiện các thay đổi cần thiết. Trong ví dụ này, chúng tôi đang thay đổi giá trị của một trường biểu mẫu có "A1" trong tên của nó:

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

 Đừng quên đóng lại`FileStream` phản đối khi bạn hoàn tất:

```csharp
fs. Close();
```

### Mã nguồn mẫu cho Preserve Rights sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Đọc tệp PDF gốc bằng FileAccess của Read and Write.
// Chúng ta cần quyền ReadWrite vì sau khi sửa đổi,
// Chúng ta cần lưu nội dung đã cập nhật vào cùng một tài liệu/tệp.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Khởi tạo phiên bản Tài liệu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Lấy giá trị từ tất cả các trường
foreach (Field formField in pdfDocument.Form)
{
	// Nếu tên đầy đủ của trường chứa A1, hãy thực hiện thao tác
	if (formField.FullName.Contains("A1"))
	{
		// Đúc trường biểu mẫu thành TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Sửa đổi giá trị trường
		textBoxField.Value = "Testing";
	}
}
// Lưu tài liệu đã cập nhật trong FileStream
pdfDocument.Save();
// Đóng đối tượng File Stream
fs.Close();
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách bảo toàn quyền của biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng truy cập các trường biểu mẫu và thực hiện các thay đổi cụ thể trong khi vẫn bảo toàn quyền truy cập và quyền ghi.


### Câu hỏi thường gặp

#### H: Tôi có thể giữ nguyên quyền của các trường biểu mẫu cụ thể mà không ảnh hưởng đến các trường khác trong tài liệu PDF không?

 A: Có, bằng cách sử dụng`FullName` thuộc tính của các trường biểu mẫu, bạn có thể nhắm mục tiêu vào các trường biểu mẫu cụ thể để bảo toàn trong khi không làm ảnh hưởng đến các trường khác.

#### H: Tôi có thể giữ nguyên quyền của biểu mẫu trong tài liệu PDF được bảo vệ bằng mật khẩu không?

A: Có, Aspose.PDF for .NET cho phép bạn giữ nguyên quyền của biểu mẫu ngay cả trong các tài liệu PDF được bảo vệ bằng mật khẩu, miễn là bạn cung cấp đúng mật khẩu để truy cập và sửa đổi tệp.

#### H: Điều gì xảy ra nếu tôi cố gắng sửa đổi các trường biểu mẫu mà không có quyền truy cập phù hợp?

A: Nếu bạn cố gắng sửa đổi các trường biểu mẫu mà không có quyền truy cập phù hợp, những thay đổi sẽ không được lưu trong tài liệu PDF và bạn có thể nhận được ngoại lệ hoặc thông báo lỗi.

#### H: Aspose.PDF cho .NET có tương thích với tất cả các phiên bản .NET Framework không?

A: Có, Aspose.PDF cho .NET tương thích với mọi phiên bản .NET Framework, bao gồm .NET Core và .NET Standard.

#### H: Tôi có thể bảo toàn quyền định dạng trong tài liệu PDF bằng cách lập trình bằng các ngôn ngữ lập trình khác ngoài C# không?

A: Có, Aspose.PDF cho .NET hỗ trợ nhiều ngôn ngữ lập trình khác nhau, chẳng hạn như VB.NET và ASP.NET, ngoài C#.