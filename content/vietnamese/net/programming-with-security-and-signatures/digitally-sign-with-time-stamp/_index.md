---
title: Ký số có dấu thời gian trong tệp PDF
linktitle: Ký số có dấu thời gian trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thực hiện chữ ký số có dấu thời gian trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình ký số vào tệp PDF có dấu thời gian bằng Aspose.PDF cho .NET. Chữ ký số có dấu thời gian đảm bảo tính xác thực và toàn vẹn của tài liệu bằng cách thêm dấu vân tay điện tử có dấu thời gian.

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
using Aspose.Pdf.Forms;
```

## Bước 3: Chữ ký số có dấu thời gian

Bước đầu tiên là thực hiện chữ ký số có dấu thời gian trên tệp PDF. Mã được cung cấp cho biết cách thực hiện chữ ký này với Aspose.PDF cho .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Mã này tải tệp PDF, tạo chữ ký số có dấu thời gian bằng tệp PFX (khóa riêng) và các tham số dấu thời gian đã chỉ định. Sau đó, chữ ký được thêm vào tệp PDF và lưu với hậu tố "_ngoài".

### Mã nguồn mẫu cho Ký số có Dấu thời gian sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Người dùng/Mật khẩu có thể được bỏ qua
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Tạo bất kỳ loại chữ ký nào trong ba loại
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Lưu tệp PDF đầu ra
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã thực hiện thành công chữ ký số có dấu thời gian trên tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này bao gồm quy trình từng bước từ việc tạo chữ ký đến lưu tệp PDF đã cập nhật. Bây giờ bạn có thể sử dụng tính năng này để thêm chữ ký số có dấu thời gian vào tệp PDF của mình.

### Câu hỏi thường gặp về ký số có đóng dấu thời gian trong tệp PDF

#### H: Mục đích của việc ký số có dấu thời gian là gì?

A: Ký số kèm dấu thời gian sẽ thêm dấu vân tay điện tử có dấu thời gian vào tệp PDF, đảm bảo tính xác thực và toàn vẹn của tài liệu tại một thời điểm cụ thể.

#### H: Cần có những điều kiện tiên quyết nào để bắt đầu hướng dẫn này?

A: Trước khi bắt đầu, hãy đảm bảo bạn có hiểu biết cơ bản về ngôn ngữ lập trình C#, đã cài đặt Visual Studio và thư viện Aspose.PDF cho .NET.

#### H: Tôi có thể thiết lập môi trường phát triển của mình như thế nào?

A: Thực hiện theo các bước được cung cấp để thiết lập môi trường phát triển của bạn, bao gồm tạo một dự án C# mới trong Visual Studio và nhập các không gian tên cần thiết.

#### H: Làm thế nào để thêm chữ ký số có dấu thời gian vào tệp PDF?

A: Mã mẫu được cung cấp sẽ hướng dẫn cách tải tệp PDF, tạo chữ ký số có dấu thời gian bằng tệp PFX (khóa riêng) và cài đặt dấu thời gian đã chỉ định, thêm chữ ký vào tệp PDF và lưu tệp đã cập nhật.

#### H: Tệp PFX là gì và tại sao nó được sử dụng trong ví dụ này?

A: Tệp PFX (Định dạng trao đổi cá nhân) chứa khóa riêng và chứng chỉ. Nó được sử dụng ở đây để cung cấp chức năng mã hóa cho chữ ký số. Đảm bảo bạn thay thế chỗ giữ chỗ bằng tệp PFX và mật khẩu của mình.

#### H: TimestampSettings là gì?

A: TimestampSettings xác định cài đặt cho máy chủ dấu thời gian được sử dụng để thêm dấu thời gian điện tử vào chữ ký. Nó bao gồm URL máy chủ dấu thời gian và thông tin xác thực người dùng tùy chọn.

#### H: Tôi có thể sử dụng máy chủ dấu thời gian khác ngoài máy chủ trong ví dụ không?
 A: Có, bạn có thể sử dụng bất kỳ máy chủ dấu thời gian tương thích nào. Thay thế URL và nếu cần, cung cấp thông tin đăng nhập người dùng phù hợp trong`TimestampSettings` sự vật.

#### H: Mục đích của việc chỉ định hình chữ nhật chữ ký là gì?

A: Hình chữ nhật chữ ký xác định vị trí và kích thước của chữ ký số xuất hiện trên trang PDF. Điều chỉnh các giá trị này để định vị chữ ký theo ý muốn.

#### H: Điều gì xảy ra nếu máy chủ dấu thời gian không khả dụng trong quá trình ký?

A: Nếu máy chủ dấu thời gian không khả dụng trong quá trình ký, quá trình này có thể không thành công hoặc mất nhiều thời gian hơn. Đảm bảo máy chủ dấu thời gian của bạn đáng tin cậy và có thể truy cập được.

#### H: Làm thế nào tôi có thể xác minh sự hiện diện của dấu thời gian trong tệp PDF đã ký?

 A: Bạn có thể kiểm tra PDF đã ký bằng cách sử dụng mã mẫu được cung cấp.`TimestampSettings` bạn đã sử dụng khi ký sẽ có trong phần thông tin chi tiết về chữ ký.

#### H: Chữ ký số có dấu thời gian có ràng buộc về mặt pháp lý không?

A: Chữ ký số có dấu thời gian có giá trị pháp lý ở nhiều khu vực pháp lý và thường được coi là đáng tin cậy hơn chữ ký số đơn giản. Tham khảo ý kiến chuyên gia pháp lý tại khu vực pháp lý của bạn để biết các quy định cụ thể.

#### H: Tôi có thể thêm nhiều chữ ký số có dấu thời gian vào tệp PDF không?

A: Có, bạn có thể thêm nhiều chữ ký số có dấu thời gian vào tệp PDF bằng cách gọi quy trình tạo chữ ký nhiều lần. Mỗi chữ ký sẽ có dấu thời gian riêng.