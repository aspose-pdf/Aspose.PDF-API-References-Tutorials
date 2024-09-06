---
title: Xác định mật khẩu đúng trong tệp PDF
linktitle: Xác định mật khẩu đúng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xác định mật khẩu chính xác trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-security-and-signatures/determine-correct-password/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình xác định mật khẩu chính xác trong tệp PDF bằng Aspose.PDF cho .NET. Tính năng này cho phép bạn kiểm tra xem tệp PDF có được bảo vệ bằng mật khẩu hay không và tìm mật khẩu chính xác từ danh sách được xác định trước.

## Bước 1: Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Cài đặt Visual Studio trên máy của bạn
- Thư viện Aspose.PDF cho .NET đã được cài đặt

## Bước 2: Thiết lập môi trường

Để bắt đầu, hãy làm theo các bước sau để thiết lập môi trường phát triển của bạn:

1. Mở Visual Studio và tạo một dự án C# mới.
2. Nhập các không gian tên cần thiết vào tệp mã của bạn:

```csharp
using Aspose.Pdf;
```

## Bước 3: Tải tệp PDF nguồn

Bước đầu tiên là tải lên tệp PDF nguồn mà bạn muốn xác minh. Trong ví dụ này, chúng tôi giả sử bạn có tệp PDF có tên "IsPasswordProtected.pdf" trong thư mục đã chỉ định.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Hãy đảm bảo thay thế các chỗ giữ chỗ bằng vị trí thực tế của tệp PDF.

## Bước 4: Xác định mã hóa PDF nguồn

 Sau khi bạn đã tải lên tệp PDF nguồn, bạn có thể xác định xem nó có được mã hóa hay không bằng cách sử dụng`IsEncrypted` phương pháp của`PdfFileInfo` sự vật.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Câu lệnh này hiển thị tệp PDF có được bảo vệ bằng mật khẩu hay không.

## Bước 5: Tìm mật khẩu chính xác

Tiếp theo, chúng ta sẽ tìm kiếm mật khẩu đúng bằng cách sử dụng danh sách mật khẩu được xác định trước. Chúng ta duyệt qua từng mật khẩu trong danh sách và thử tải tài liệu PDF bằng mật khẩu đó.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Vòng lặp này kiểm tra từng từ pass trong danh sách. Nếu mật khẩu đúng, số trang trong tài liệu sẽ được hiển thị. Nếu không, một thông báo cho biết mật khẩu không đúng sẽ được hiển thị.


### Mã nguồn mẫu để Xác định mật khẩu chính xác bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Tải tệp PDF nguồn
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//Xác định xem tệp PDF nguồn có được mã hóa không
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã xác định thành công mật khẩu đúng cho tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này bao gồm quy trình từng bước, từ xác minh mã hóa tệp đến tìm mật khẩu đúng từ danh sách được xác định trước. Bây giờ bạn có thể sử dụng tính năng này để kiểm tra và tìm mật khẩu đúng cho tệp PDF của mình.

### Câu hỏi thường gặp để xác định mật khẩu chính xác trong tệp PDF

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này nhằm mục đích hướng dẫn bạn quy trình xác định mật khẩu chính xác cho tệp PDF bằng Aspose.PDF cho .NET. Tính năng này cho phép bạn kiểm tra xem tệp PDF có được bảo vệ bằng mật khẩu hay không và cố gắng tìm mật khẩu chính xác từ danh sách được xác định trước.

#### H: Cần có những điều kiện tiên quyết nào trước khi bắt đầu?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn có hiểu biết cơ bản về ngôn ngữ lập trình C#, đã cài đặt Visual Studio trên máy và đã cài đặt thư viện Aspose.PDF cho .NET.

#### H: Tôi thiết lập môi trường phát triển như thế nào?

A: Thực hiện theo các bước được cung cấp để thiết lập môi trường phát triển của bạn, bao gồm tạo một dự án C# mới trong Visual Studio và nhập các không gian tên cần thiết.

#### H: Làm sao để xác định tệp PDF có được mã hóa hay không?

 A: Sử dụng`PdfFileInfo` lớp để liên kết tệp PDF nguồn. Sau đó, sử dụng`IsEncrypted`thuộc tính để xác định xem tệp PDF có được bảo vệ bằng mật khẩu hay không.

#### H: Làm sao tôi có thể tìm đúng mật khẩu cho tệp PDF?

A: Sau khi xác định tệp PDF được mã hóa, bạn có thể thử tìm mật khẩu đúng bằng cách sử dụng danh sách mật khẩu được xác định trước. Mã mẫu được cung cấp sẽ trình bày cách lặp qua danh sách, thử từng mật khẩu và xác định xem mật khẩu có đúng không.

#### H: Điều gì xảy ra nếu tìm thấy mật khẩu đúng?

A: Nếu tìm thấy mật khẩu đúng, mã mẫu sẽ hiển thị số trang trong tài liệu PDF.

#### H: Nếu mật khẩu không đúng thì sao?

 A: Nếu mật khẩu không đúng, mã mẫu sẽ bắt được`InvalidPasswordException` và hiển thị thông báo cho biết mật khẩu không đúng.

#### H: Tôi có thể sử dụng danh sách mật khẩu khác không?

 A: Có, bạn có thể sửa đổi`passwords` mảng trong mã mẫu để bao gồm các mật khẩu bạn muốn kiểm tra.

#### H: Làm sao tôi biết mật khẩu đã được xác định thành công?

A: Nếu mã mẫu tải thành công tài liệu PDF bằng mật khẩu và hiển thị số trang thì có nghĩa là mật khẩu chính xác đã được xác định.

#### H: Tôi có thể đảm bảo tính bảo mật của mật khẩu trong khi kiểm tra như thế nào?

A: Hãy thận trọng khi sử dụng danh sách mật khẩu được xác định trước và tránh sử dụng mật khẩu nhạy cảm hoặc bí mật cho mục đích thử nghiệm. Ngoài ra, hãy xóa hoặc sửa đổi mã thử nghiệm trước khi triển khai ứng dụng của bạn.