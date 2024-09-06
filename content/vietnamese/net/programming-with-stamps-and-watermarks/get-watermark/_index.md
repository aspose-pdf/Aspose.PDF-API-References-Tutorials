---
title: Nhận hình mờ từ tệp PDF
linktitle: Nhận hình mờ từ tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất hình mờ từ tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-stamps-and-watermarks/get-watermark/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách lấy hình mờ từ tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để lặp qua các hiện vật của một trang cụ thể và lấy loại hình mờ, văn bản và vị trí.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu PDF

Bước đầu tiên là tải tài liệu PDF hiện có vào dự án của bạn. Thực hiện như sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 3: Lấy hình mờ

Bây giờ bạn đã tải tài liệu PDF, bạn có thể lặp lại các hiện vật trang cụ thể để lấy thông tin hình mờ. Sau đây là cách thực hiện:

```csharp
// Duyệt các hiện vật và lấy loại hình mờ, văn bản và vị trí
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Đoạn mã trên lặp qua tất cả các hiện vật trên trang đầu tiên của tài liệu PDF và hiển thị loại phụ, văn bản và hình chữ nhật (vị trí) của mỗi hình mờ gặp phải.

### Mã nguồn mẫu để Nhận Watermark bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Lặp lại và lấy loại bồn, văn bản và vị trí của hiện vật
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Phần kết luận

Xin chúc mừng! Bạn đã học được cách lấy thông tin hình mờ từ tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để phân tích và xử lý hình mờ trong tài liệu PDF của mình.

### Câu hỏi thường gặp để có hình mờ từ tệp PDF

#### H: Hình mờ trong tài liệu PDF là gì và tại sao tôi cần phải trích xuất thông tin của nó?

A: Hình mờ trong tài liệu PDF là hình ảnh hoặc văn bản dễ nhận biết được chồng lên nội dung của tài liệu, thường để chỉ trạng thái, quyền sở hữu hoặc tính chất bảo mật của tài liệu. Việc trích xuất thông tin hình mờ có thể hữu ích để phân tích tính xác thực của tài liệu, xác định nguồn tài liệu hoặc xử lý tài liệu dựa trên sự hiện diện của hình mờ.

#### H: Mã nguồn C# được cung cấp giúp trích xuất thông tin hình mờ từ tệp PDF như thế nào?

 A: Mã được cung cấp minh họa cách tải một tài liệu PDF hiện có, lặp lại qua các hiện vật của một trang cụ thể và trích xuất thông tin về hình mờ. Nó thực hiện điều này bằng cách truy cập`Subtype`, `Text` , Và`Rectangle` tính chất của từng hiện vật.

####  Q: Cái gì làm`Subtype` property of an artifact represent?

 A: Cái`Subtype` thuộc tính của một hiện vật biểu thị loại hiện vật. Đối với hình mờ, nó chỉ ra rằng hiện vật là hình mờ.

#### H: Mã xác định vị trí (hình chữ nhật) của hình mờ trên trang như thế nào?

 A: Mã sử dụng`Rectangle` thuộc tính của hiện vật để xác định vị trí của hình mờ.`Rectangle` thuộc tính này biểu thị hình chữ nhật giới hạn của hiện vật trên trang.

#### H: Tôi có thể sửa đổi mã để trích xuất thông tin bổ sung về hình mờ, chẳng hạn như hình dạng hoặc màu sắc của hình mờ không?

A: Có, bạn có thể sửa đổi mã để truy cập các thuộc tính khác của hiện vật, chẳng hạn như hình thức hoặc màu sắc, nếu thông tin đó có sẵn và phù hợp với trường hợp sử dụng của bạn.

#### H: Tôi có thể trích xuất thông tin hình mờ từ nhiều trang của tài liệu PDF bằng mã này không?

A: Có, bạn có thể sửa đổi mã để lặp qua các hiện vật trên nhiều trang bằng cách thay đổi chỉ mục trang trong vòng lặp để truy cập các hiện vật từ các trang khác nhau.

#### H: Điều gì xảy ra nếu không có hình mờ trên trang được chỉ định?

A: Nếu không có hình mờ trên trang được chỉ định, vòng lặp sẽ không thực hiện và không có thông tin hình mờ nào được hiển thị.

#### H: Tôi có thể sử dụng thông tin hình mờ đã trích xuất để xử lý thêm như thế nào?

A: Thông tin hình mờ được trích xuất có thể được sử dụng cho nhiều mục đích khác nhau, chẳng hạn như ghi nhật ký, phân tích, báo cáo hoặc tự động hóa các hành động cụ thể dựa trên sự hiện diện hoặc thuộc tính của hình mờ.

#### H: Tôi có thể sửa đổi mã này để trích xuất thông tin về các loại hiện vật khác trong tài liệu PDF không?

A: Có, bạn có thể sửa đổi mã để trích xuất thông tin về các loại hiện vật khác bằng cách truy cập vào thuộc tính của chúng theo cách tương tự.

#### H: Làm thế nào tôi có thể truy cập vào các hình mờ không phải là hiện vật nhưng là một phần của nội dung PDF?

A: Các hình mờ không phải là hiện vật có thể là một phần của chính nội dung PDF, chẳng hạn như hình ảnh hoặc văn bản. Để trích xuất thông tin về các loại hình mờ này, bạn có thể cần phân tích nội dung PDF và xác định các thành phần cụ thể đại diện cho hình mờ.