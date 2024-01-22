---
title: Văn bản và hình ảnh dưới dạng đoạn văn trong tệp PDF
linktitle: Văn bản và hình ảnh dưới dạng đoạn văn trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm văn bản và hình ảnh dưới dạng đoạn văn nội tuyến trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 530
url: /vi/net/programming-with-text/text-and-image-as-paragraph/
---
Hướng dẫn này giải thích cách thêm văn bản và hình ảnh dưới dạng đoạn văn nội tuyến trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

## Điều kiện tiên quyết

Trước khi tiếp tục với hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể lấy nó từ trang web Aspose hoặc sử dụng NuGet để cài đặt nó trong dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm các lệnh sử dụng sau vào đầu tệp C# của bạn để nhập các không gian tên được yêu cầu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` Biến đổi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo Tài liệu và Trang mới

 Tạo một cái mới`Document` đối tượng và thêm một trang vào bộ sưu tập trang của nó:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 5: Tạo TextFragment và thêm nó dưới dạng đoạn văn

 Tạo một`TextFragment` đối tượng và thêm nó vào bộ sưu tập đoạn văn của trang:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Bước 6: Thêm hình ảnh làm đoạn văn nội tuyến

 Tạo ra một`Aspose.Pdf.Image` đối tượng và đặt nó làm đoạn văn nội tuyến để nó xuất hiện ngay sau đoạn trước:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Tùy chọn: Đặt chiều cao hình ảnh
image.FixWidth = 100; // Tùy chọn: Đặt chiều rộng hình ảnh
page.Paragraphs.Add(image);
```

 Thay thế`"aspose-logo.jpg"` bằng tên tệp hình ảnh thực tế và điều chỉnh chiều cao và chiều rộng hình ảnh tùy chọn theo ý muốn.

## Bước 7: Thêm một TextFragment khác làm đoạn văn nội tuyến

 Khởi tạo lại`TextFragment` đối tượng có nội dung khác và thêm nó dưới dạng đoạn nội tuyến:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Bước 8: Lưu tài liệu PDF

Lưu tài liệu PDF đã sửa đổi:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Đảm bảo thay thế`"TextAndImageAsParagraph_out.pdf"` với tên tệp đầu ra mong muốn.

### Mã nguồn mẫu cho Văn bản và Hình ảnh Dưới dạng Đoạn sử dụng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo phiên bản tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của phiên bản Tài liệu
Page page = doc.Pages.Add();
// Tạo TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Thêm đoạn văn bản vào bộ sưu tập đoạn văn của đối tượng Trang
page.Paragraphs.Add(text);
// Tạo một ví dụ hình ảnh
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Đặt hình ảnh làm đoạn nội tuyến để nó xuất hiện ngay sau
// Đối tượng đoạn trước (TextFragment)
image.IsInLineParagraph = true;
// Chỉ định đường dẫn tệp hình ảnh
image.File = dataDir + "aspose-logo.jpg";
// Đặt chiều cao hình ảnh (tùy chọn)
image.FixHeight = 30;
// Đặt chiều rộng hình ảnh (tùy chọn)
image.FixWidth = 100;
// Thêm hình ảnh vào bộ sưu tập đoạn văn của đối tượng trang
page.Paragraphs.Add(image);
// Khởi tạo lại đối tượng TextFragment với các nội dung khác nhau
text = new TextFragment(" Hello Again..");
// Đặt TextFragment làm đoạn nội tuyến
text.IsInLineParagraph = true;
// Thêm TextFragment mới được tạo vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách thêm văn bản và hình ảnh dưới dạng đoạn văn nội tuyến trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến lưu tài liệu đã sửa đổi. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để tùy chỉnh bố cục văn bản và hình ảnh trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Văn bản và hình ảnh dưới dạng đoạn văn trong tệp PDF" là gì?

Trả lời: Hướng dẫn "Văn bản và hình ảnh dưới dạng đoạn trong tệp PDF" nhằm mục đích hướng dẫn người dùng cách thêm cả văn bản và hình ảnh dưới dạng đoạn văn nội tuyến trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước và mẫu mã C# để minh họa quy trình.

#### Hỏi: Hướng dẫn này giúp ích như thế nào trong việc thêm văn bản và hình ảnh làm đoạn văn nội tuyến?

Đáp: Hướng dẫn này giúp người dùng hiểu cách sử dụng Aspose.PDF cho .NET để kết hợp cả văn bản và hình ảnh dưới dạng đoạn văn nội tuyến trong tài liệu PDF. Bằng cách làm theo các bước được cung cấp và ví dụ về mã, người dùng có thể tạo tệp PDF với bố cục tùy chỉnh kết hợp văn bản và hình ảnh.

#### Câu hỏi: Cần có những điều kiện tiên quyết nào để thực hiện theo hướng dẫn này?

Đáp: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc cài đặt nó trong dự án của bạn bằng NuGet.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET. Điều này cho phép bạn sử dụng các tính năng của thư viện để làm việc với tài liệu PDF, đoạn văn bản và hình ảnh.

#### Hỏi: Tôi có thể sử dụng hướng dẫn này để thêm nhiều đoạn văn bản và hình ảnh vào một tệp PDF không?

Đáp: Có, bạn có thể sử dụng các mẫu mã được cung cấp để thêm nhiều phiên bản của cả đoạn văn bản và hình ảnh trong cùng một tài liệu PDF. Hướng dẫn này trình bày cách tạo các đoạn văn nội tuyến, giúp dễ dàng đưa vào các kết hợp văn bản và hình ảnh khác nhau.

#### Hỏi: Làm cách nào để chỉ định nội dung và hình thức của các đoạn văn bản và hình ảnh?

 Đáp: Phần hướng dẫn này trình bày cách tạo`TextFragment`các đối tượng để thể hiện các đoạn văn bản và`Aspose.Pdf.Image` đối tượng để biểu diễn hình ảnh. Bạn có thể tùy chỉnh nội dung, kích thước và hình thức của cả văn bản và hình ảnh bằng cách sử dụng các mẫu mã được cung cấp.

#### Hỏi: Tôi có thể điều chỉnh bố cục của các đoạn văn nội tuyến không?

 Đáp: Có, bạn có thể điều chỉnh bố cục của các đoạn nội tuyến bằng cách kiểm soát vị trí, kích thước và thứ tự của chúng trong trang. Hướng dẫn này cho biết cách đặt các thuộc tính nội tuyến, chẳng hạn như`IsInLineParagraph`, để kiểm soát bố cục của đoạn văn bản và hình ảnh.

#### Hỏi: Làm cách nào để lưu tài liệu PDF đã sửa đổi?

 Đáp: Để lưu tài liệu PDF đã sửa đổi, bạn có thể sử dụng`Save` phương pháp của`Document` sự vật. Hướng dẫn này cung cấp các mẫu mã minh họa cách lưu tài liệu PDF thu được.