---
title: Cung cấp thông tin xác thực trong quá trình HTML sang PDF
linktitle: Cung cấp thông tin xác thực trong quá trình HTML sang PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để chuyển đổi HTML sang PDF bằng cách cung cấp thông tin xác thực với Aspose.PDF cho .NET.
type: docs
weight: 240
url: /vi/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi tệp HTML sang PDF đồng thời cung cấp thông tin xác thực khi truy cập URL bảo mật bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể chuyển đổi nội dung HTML sang PDF bằng thông tin xác thực phù hợp.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tìm nạp nội dung HTML an toàn
Trong bước này, chúng tôi sẽ tìm nạp nội dung HTML an toàn từ một URL bằng thông tin xác thực thích hợp. Sử dụng mã sau đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo một yêu cầu cho URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Nếu cần cho máy chủ, hãy đặt thông tin xác thực.
request.Credentials = CredentialCache.DefaultCredentials;
// Nhận được phản hồi.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Nhận luồng chứa nội dung được máy chủ trả về.
Stream dataStream = response. GetResponseStream();
// Mở luồng bằng StreamReader để dễ dàng truy cập.
StreamReader reader = new StreamReader(dataStream);
// Đọc nội dung.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực tế nơi bạn muốn lưu tệp PDF kết quả.

## Bước 2: Chuyển đổi HTML sang PDF bằng cách cung cấp thông tin xác thực
Bây giờ chúng tôi sẽ tải nội dung HTML được truy xuất và chuyển đổi nó sang định dạng PDF đồng thời cung cấp thông tin xác thực phù hợp. Sử dụng mã sau đây:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Tải tệp HTML
Document pdfDocument = new Document(stream, options);
```

## Bước 3: Lưu tệp PDF kết quả
Cuối cùng, chúng tôi sẽ lưu tệp PDF kết quả. Sử dụng mã sau đây:

```csharp
// Lưu tệp PDF kết quả
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Đoạn mã trên lưu tệp PDF kết quả với tên tệp`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Mã nguồn mẫu cho Cung cấp thông tin xác thực trong HTML sang PDF bằng Aspose.PDF cho .NET

```csharp
try
{
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Tạo một yêu cầu cho URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Nếu máy chủ yêu cầu, hãy đặt thông tin xác thực.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Nhận được phản hồi.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Nhận luồng chứa nội dung được máy chủ trả về.
	Stream dataStream = response.GetResponseStream();
	// Mở luồng bằng StreamReader để dễ dàng truy cập.
	StreamReader reader = new StreamReader(dataStream);
	// Đọc nội dung.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Tải tệp HTML
	Document pdfDocument = new Document(stream, options);
	// Lưu tập tin kết quả
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước chuyển đổi tệp HTML sang PDF đồng thời cung cấp thông tin xác thực khi truy cập URL bảo mật bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, bạn sẽ có thể chuyển đổi thành công nội dung HTML sang PDF trong khi cung cấp thông tin xác thực chính xác.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ hỗ trợ các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng C#. Nó cung cấp một loạt các chức năng, bao gồm chuyển đổi HTML sang PDF.

#### Hỏi: Làm cách nào tôi có thể tìm nạp nội dung HTML an toàn từ một URL?

 Đáp: Để tìm nạp nội dung HTML an toàn từ một URL, bạn có thể sử dụng`WebRequest` lớp trong C#. Đảm bảo đặt thông tin xác thực phù hợp bằng cách sử dụng`Credentials` tài sản.

#### Hỏi: Điều kiện tiên quyết cho hướng dẫn này là gì?

Đáp: Trước khi tiếp tục phần hướng dẫn, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

#### Câu hỏi: Aspose.PDF cho .NET xử lý các tài nguyên bên ngoài như thế nào trong khi chuyển đổi HTML sang PDF?

 Đáp: Aspose.PDF for .NET cung cấp`HtmlLoadOptions`lớp để xử lý các tài nguyên bên ngoài trong quá trình chuyển đổi HTML sang PDF. Bạn có thể đặt thông tin xác thực tài nguyên bên ngoài bằng cách sử dụng`ExternalResourcesCredentials` tài sản.

#### Hỏi: Tôi có thể tùy chỉnh tên tệp cho tệp PDF thu được không?

 Đáp: Có, bạn có thể tùy chỉnh tên tệp cho tệp PDF thu được bằng cách sửa đổi mã lưu tài liệu PDF. Chỉ cần thay đổi tên tệp mong muốn trong`pdfDocument.Save()` phương pháp.