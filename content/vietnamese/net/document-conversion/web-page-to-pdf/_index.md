---
title: Trang Web Sang PDF
linktitle: Trang Web Sang PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước chuyển đổi trang web sang PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 320
url: /vi/net/document-conversion/web-page-to-pdf/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách chuyển đổi một trang web sang PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ có thể chuyển đổi các trang web thành tài liệu PDF một cách dễ dàng.

## Giới thiệu
Chuyển đổi trang web sang định dạng PDF là yêu cầu phổ biến trong nhiều ứng dụng. Bằng cách chuyển đổi nội dung web sang PDF, bạn có thể dễ dàng giữ nguyên bố cục, định dạng và hình ảnh của trang web gốc. Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép bạn thực hiện chuyển đổi này một cách hiệu quả và chính xác.

## Yêu cầu
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Visual Studio được cài đặt trên máy của bạn
- Thư viện Aspose.PDF cho .NET (bạn có thể tải xuống từ trang web chính thức của Aspose)
- Kiến thức cơ bản về lập trình C#


## Bước 1: Xác định thư mục tài liệu
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn bạn muốn lưu tệp PDF đã tạo.

## Bước 2: Tạo yêu cầu web
```csharp
WebRequest request = WebRequest.Create("https://vi.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Tạo một đối tượng yêu cầu web và chỉ định URL của trang web bạn muốn chuyển đổi. Bạn có thể thay thế URL bằng bất kỳ trang web nào bạn muốn.

## Bước 3: Nhận phản hồi trên web
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Gửi yêu cầu web và lấy phản hồi từ máy chủ.

## Bước 4: Đọc nội dung trang web
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Đọc nội dung trang web bằng cách sử dụng`StreamReader`và lưu trữ nó trong`responseFromServer` Biến đổi.

## Bước 5: Chuyển đổi HTML sang PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://vi.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Tạo một`MemoryStream` đối tượng để tải nội dung trang web. Sau đó, tạo một thể hiện của`HtmlLoadOptions` và chuyển URL cơ sở của trang web. Tiếp theo, tạo một`Document` đối tượng bằng cách sử dụng luồng đã tải và các tùy chọn tải HTML. Đặt`IsLandscape` tài sản để`true` nếu bạn muốn tệp PDF ở hướng ngang. Cuối cùng, lưu tài liệu PDF vào thư mục được chỉ định

.

## Bước 6: Xử lý ngoại lệ
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Nắm bắt mọi trường hợp ngoại lệ có thể xảy ra trong quá trình chuyển đổi và hiển thị thông báo lỗi.

### Mã nguồn ví dụ cho Trang web sang PDF bằng Aspose.PDF for .NET

```csharp
try
{
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tạo một yêu cầu cho URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Nếu máy chủ yêu cầu, hãy đặt thông tin xác thực.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Hết thời gian tính bằng mili giây trước khi hết yêu cầu
	// Yêu cầu.Timeout = 100;

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Tải tệp HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Lưu đầu ra dưới dạng PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách chuyển đổi một trang web sang PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi đã xem hướng dẫn từng bước giải thích mã nguồn C# được cung cấp. Bằng cách làm theo các hướng dẫn này, bạn có thể dễ dàng tích hợp chức năng chuyển đổi trang web sang PDF vào các ứng dụng .NET của riêng mình.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng C#. Nó cung cấp nhiều chức năng khác nhau, bao gồm chuyển đổi các trang web sang PDF.

#### Hỏi: Tại sao tôi muốn chuyển đổi một trang web sang PDF?

Đáp: Việc chuyển đổi các trang web sang PDF rất hữu ích trong việc giữ nguyên bố cục, định dạng và hình ảnh của nội dung web gốc. Nó cho phép bạn tạo ảnh chụp nhanh của trang web để xem hoặc chia sẻ ngoại tuyến với người khác.

#### Hỏi: Điều kiện tiên quyết cho hướng dẫn này là gì?

Đáp: Để làm theo hướng dẫn này, bạn cần cài đặt Visual Studio trên máy của mình, thư viện Aspose.PDF cho .NET và hiểu biết cơ bản về lập trình C#.

#### Hỏi: Tôi có thể chuyển đổi bất kỳ trang web nào sang PDF không?

Trả lời: Có, bạn có thể chuyển đổi bất kỳ trang web nào sang PDF bằng cách cung cấp URL của trang web trong mã. Aspose.PDF for .NET sẽ truy xuất nội dung web và chuyển đổi nó sang định dạng PDF.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh đầu ra PDF, chẳng hạn như hướng trang?

 Trả lời: Bạn có thể tùy chỉnh đầu ra PDF bằng cách sử dụng các tùy chọn như`IsLandscape` để thiết lập hướng trang. Trong mã được cung cấp,`options.PageInfo.IsLandscape = true` được sử dụng để tạo tệp PDF theo hướng ngang.