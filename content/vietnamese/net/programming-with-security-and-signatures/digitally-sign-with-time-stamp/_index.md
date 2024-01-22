---
title: Ký điện tử bằng dấu thời gian trong tệp PDF
linktitle: Ký điện tử bằng dấu thời gian trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thực hiện chữ ký điện tử có dấu thời gian trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình đăng nhập kỹ thuật số vào tệp PDF có dấu thời gian bằng Aspose.PDF cho .NET. Chữ ký số có dấu thời gian đảm bảo tính xác thực và tính toàn vẹn của tài liệu bằng cách thêm dấu vân tay điện tử có dấu thời gian.

## Bước 1: Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Cài đặt Visual Studio trên máy của bạn
- Thư viện Aspose.PDF để cài đặt .NET

## Bước 2: Thiết lập môi trường

Để bắt đầu, hãy làm theo các bước sau để thiết lập môi trường phát triển của bạn:

1. Mở Visual Studio và tạo một dự án C# mới.
2. Nhập các không gian tên cần thiết vào tệp mã của bạn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Bước 3: Chữ ký số có dấu thời gian

Bước đầu tiên là thực hiện chữ ký số có dấu thời gian trên file PDF. Mã được cung cấp cho biết cách đạt được chữ ký này bằng Aspose.PDF cho .NET.

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

Mã này tải tệp PDF, tạo chữ ký số có dấu thời gian bằng tệp PFX (khóa riêng) và các tham số dấu thời gian được chỉ định. Chữ ký sau đó được thêm vào file PDF và được lưu với hậu tố "_ngoài".

### Mã nguồn mẫu cho Ký điện tử bằng dấu thời gian bằng Aspose.PDF cho .NET 
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
		// Tạo bất kỳ loại nào trong ba loại chữ ký
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Lưu tệp PDF đầu ra
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã thực hiện thành công chữ ký điện tử có dấu thời gian trên tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này trình bày quy trình từng bước từ tạo chữ ký đến lưu tệp PDF đã cập nhật. Bây giờ bạn có thể sử dụng tính năng này để thêm chữ ký điện tử có dấu thời gian vào tệp PDF của mình.

### Câu hỏi thường gặp về ký điện tử có dấu thời gian trong tệp PDF

#### Câu hỏi: Mục đích của việc ký điện tử bằng dấu thời gian là gì?

Đáp: Ký điện tử bằng dấu thời gian sẽ thêm dấu vân tay điện tử có dấu thời gian vào tệp PDF, đảm bảo tính xác thực và toàn vẹn của tài liệu tại một thời điểm cụ thể.

#### Hỏi: Cần có những điều kiện tiên quyết nào để bắt đầu hướng dẫn này?

Đáp: Trước khi bắt đầu, hãy đảm bảo bạn có hiểu biết cơ bản về ngôn ngữ lập trình C#, đã cài đặt Visual Studio và cài đặt thư viện Aspose.PDF cho .NET.

#### Câu hỏi: Làm cách nào tôi có thể thiết lập môi trường phát triển của mình?

Đáp: Hãy làm theo các bước được cung cấp để thiết lập môi trường phát triển của bạn, bao gồm tạo dự án C# mới trong Visual Studio và nhập các vùng tên cần thiết.

#### Câu hỏi: Làm cách nào để thêm chữ ký điện tử có dấu thời gian vào tệp PDF?

Đáp: Mã mẫu được cung cấp minh họa cách tải tệp PDF, tạo chữ ký số có dấu thời gian bằng tệp PFX (khóa riêng) và cài đặt dấu thời gian được chỉ định, thêm chữ ký vào tệp PDF và lưu tệp đã cập nhật.

#### Hỏi: Tệp PFX là gì và tại sao nó được sử dụng trong ví dụ này?

Trả lời: Tệp PFX (Định dạng trao đổi cá nhân) chứa khóa riêng và chứng chỉ. Nó được sử dụng ở đây để cung cấp chức năng mã hóa cho chữ ký số. Đảm bảo bạn thay thế trình giữ chỗ bằng tệp PFX và mật khẩu của mình.

#### Câu hỏi: Cài đặt dấu thời gian là gì?

Trả lời: Cài đặt dấu thời gian xác định cài đặt cho máy chủ dấu thời gian được sử dụng để thêm dấu thời gian điện tử vào chữ ký. Nó bao gồm URL máy chủ dấu thời gian và thông tin xác thực người dùng tùy chọn.

#### Câu hỏi: Tôi có thể sử dụng máy chủ dấu thời gian khác với máy chủ trong ví dụ không?
 Đáp: Có, bạn có thể sử dụng bất kỳ máy chủ dấu thời gian tương thích nào. Thay thế URL và, nếu được yêu cầu, cung cấp thông tin xác thực người dùng phù hợp trong`TimestampSettings` sự vật.

#### Hỏi: Mục đích của việc chỉ định hình chữ nhật chữ ký là gì?

Đáp: Hình chữ nhật chữ ký xác định vị trí và kích thước của chữ ký số trên trang PDF. Điều chỉnh các giá trị này để định vị chữ ký như mong muốn.

#### Câu hỏi: Điều gì xảy ra nếu máy chủ dấu thời gian không khả dụng trong quá trình ký?

Trả lời: Nếu máy chủ dấu thời gian không khả dụng trong quá trình ký, quá trình này có thể không thành công hoặc mất nhiều thời gian hơn. Đảm bảo máy chủ dấu thời gian của bạn đáng tin cậy và có thể truy cập được.

#### Câu hỏi: Làm cách nào tôi có thể xác minh sự hiện diện của dấu thời gian trong tệp PDF đã ký?

 Đáp: Bạn có thể kiểm tra tệp PDF đã ký bằng cách sử dụng mã mẫu được cung cấp. Các`TimestampSettings` bạn đã sử dụng trong quá trình ký tên sẽ có sẵn trong chi tiết chữ ký.

#### Câu hỏi: Chữ ký số có dấu thời gian có bị ràng buộc về mặt pháp lý không?

Đáp: Chữ ký số có dấu thời gian có giá trị pháp lý ở nhiều khu vực pháp lý và thường được coi là đáng tin cậy hơn chữ ký số đơn giản. Tham khảo ý kiến các chuyên gia pháp lý trong khu vực pháp lý của bạn để biết các quy định cụ thể.

#### Câu hỏi: Tôi có thể thêm nhiều chữ ký điện tử có dấu thời gian vào một tệp PDF không?

Trả lời: Có, bạn có thể thêm nhiều chữ ký điện tử có dấu thời gian vào tệp PDF bằng cách gọi quy trình tạo chữ ký nhiều lần. Mỗi chữ ký sẽ có dấu thời gian riêng.