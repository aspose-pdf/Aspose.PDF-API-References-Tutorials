---
title: Hình ảnh và Số trang trong Phần Đầu trang Chân trang Nội tuyến
linktitle: Hình ảnh và Số trang trong Phần Đầu trang Chân trang Nội tuyến
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm hình ảnh và số trang vào đầu trang và chân trang bằng cách sử dụng đoạn văn nội tuyến với Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để tạo trang, đặt đầu trang và chân trang, thêm hình ảnh và văn bản bằng cách sử dụng các đoạn văn nội tuyến trong phần đầu trang của tài liệu PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo Tài liệu PDF và Trang

Bước đầu tiên là tạo một đối tượng Document mới và một trang trong tài liệu PDF. Thực hiện như sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo một đối tượng Tài liệu mới
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Đoạn mã trên tạo ra một đối tượng Tài liệu mới và một trang trống trong tài liệu PDF.

## Bước 3: Thêm tiêu đề có hình ảnh và văn bản nội tuyến

Bây giờ trang đã được tạo, chúng ta có thể thêm phần tiêu đề có hình ảnh và văn bản bằng cách sử dụng đoạn văn nội tuyến. Sau đây là cách thực hiện:

```csharp
// Tạo phần tiêu đề
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề trang
page. Header = header;

// Tạo một đối tượng TextFragment cho văn bản nội tuyến đầu tiên
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Chỉ định màu văn bản
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Tạo một đối tượng Image cho hình ảnh
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Đặt đường dẫn hình ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Xác định kích thước của hình ảnh
image1.FixWidth = 50;
image1.FixHeight = 20;

// Chỉ ra rằng văn bản nội tuyến đầu tiên là một hình ảnh
image1.IsInLineParagraph = true;

// Tạo một văn bản nội tuyến thứ hai
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Thêm mục vào tiêu đề
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Đoạn mã trên tạo ra một phần tiêu đề, thiết lập tiêu đề trang bằng phần này, thêm một TextFragment có văn bản nội tuyến và một đối tượng Image nội tuyến.

## Bước 4: Lưu tài liệu PDF đã sửa đổi

Sau khi thêm tiêu đề có hình ảnh và văn bản nội tuyến, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Thực hiện như sau:

```csharp
// Lưu tài liệu PDF đã sửa đổi
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu cho Hình ảnh và Số trang trong phần Tiêu đề Chân trang Nội tuyến sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một đối tượng Document bằng cách gọi hàm tạo rỗng của nó
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Tạo một trang trong đối tượng Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Tạo phần Tiêu đề của tài liệu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề cho tệp PDF
page.Header = header;

// Tạo một đối tượng Văn bản
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Chỉ định màu sắc
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Tạo một đối tượng hình ảnh trong phần
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Thiết lập đường dẫn của tập tin hình ảnh
image1.File = dataDir + "aspose-logo.jpg";

//Thiết lập chiều rộng hình ảnh Thông tin
image1.FixWidth = 50;
image1.FixHeight = 20;

// Chỉ ra InlineParagraph của seg1 là một hình ảnh.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Lưu tệp PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng cách sử dụng đoạn văn nội tuyến với Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh phần đầu trang và chân trang của tài liệu PDF một cách linh hoạt.

### Câu hỏi thường gặp

#### H: Lợi ích của việc sử dụng đoạn văn nội tuyến để thêm hình ảnh và văn bản vào tiêu đề của tài liệu PDF là gì?

A: Sử dụng đoạn văn nội tuyến cho phép bạn tích hợp liền mạch hình ảnh và văn bản trong cùng một đoạn văn, cung cấp khả năng kiểm soát chính xác vị trí và định dạng của chúng. Phương pháp này đặc biệt hữu ích để tạo tiêu đề tùy chỉnh với các thành phần trực quan.

#### H: Mã nguồn C# được cung cấp thực hiện các đoạn văn nội tuyến cho phần tiêu đề trong tài liệu PDF như thế nào?

A: Mã được cung cấp minh họa cách tạo tài liệu PDF, thêm trang và tùy chỉnh tiêu đề bằng các đoạn văn nội tuyến. Mã này thêm một TextFragment có văn bản nội tuyến, một hình ảnh nội tuyến và một TextFragment nội tuyến khác.

#### H: Làm thế nào để chỉ định màu của văn bản nội tuyến trong tiêu đề?

 A: Màu của văn bản nội tuyến được chỉ định bằng cách sử dụng`ForegroundColor` tài sản của`TextState` của`TextFragment` sự vật.

#### H: Tôi có thể điều chỉnh kích thước của hình ảnh nội tuyến trong tiêu đề không?

 A: Có, bạn có thể điều chỉnh kích thước của hình ảnh nội tuyến bằng cách sử dụng`FixWidth` Và`FixHeight` tính chất của`Image` đối tượng. Điều này cho phép bạn kiểm soát chiều rộng và chiều cao của hình ảnh trong tiêu đề.

#### H: Tôi có thể thêm các thành phần nội tuyến bổ sung, chẳng hạn như siêu liên kết hoặc kiểu phông chữ khác nhau, vào tiêu đề không?

 A: Có, bạn có thể bao gồm các thành phần nội tuyến bổ sung trong tiêu đề bằng cách tạo thêm`TextFragment` hoặc`Image` đối tượng có các thuộc tính mong muốn. Điều này cho phép bạn tùy chỉnh tiêu đề hơn nữa, bao gồm siêu liên kết, kiểu phông chữ khác nhau hoặc các yếu tố trực quan khác.

#### H: Làm sao tôi có thể đảm bảo hình ảnh và văn bản trong dòng vẫn được căn chỉnh và định dạng đúng trên nhiều thiết bị và trình xem khác nhau?

A: Aspose.PDF cho .NET đảm bảo rằng hình ảnh và văn bản nội tuyến được căn chỉnh và định dạng chính xác, mang lại giao diện nhất quán trên các thiết bị và trình xem PDF khác nhau.

#### H: Tôi có thể áp dụng đoạn văn nội tuyến vào phần chân trang không?

 A: Có, bạn có thể áp dụng kỹ thuật tương tự khi sử dụng đoạn văn nội tuyến vào phần chân trang bằng cách tạo`Footer` đối tượng và thêm các thành phần nội tuyến như văn bản và hình ảnh vào đó.

#### H: Có thể kết hợp các đoạn văn nội tuyến với các phương pháp tùy chỉnh tiêu đề hoặc chân trang khác không?

A: Có, bạn có thể kết hợp các đoạn văn nội tuyến với các phương pháp tùy chỉnh tiêu đề hoặc chân trang khác do Aspose.PDF cung cấp cho .NET để tạo ra các thiết kế tiêu đề hoặc chân trang phức tạp và phù hợp hơn.

#### H: Tôi có thể xóa hoặc loại bỏ các phần tử nội tuyến khỏi tiêu đề nếu cần không?

 A: Có, bạn có thể xóa hoặc xóa các phần tử nội tuyến bằng cách sửa đổi nội dung của`HeaderFooter`đối tượng và xóa các đoạn văn nội tuyến tương ứng.

#### H: Làm thế nào tôi có thể áp dụng đoạn văn nội tuyến vào các trang cụ thể của tài liệu PDF?

 A: Để áp dụng các đoạn văn nội tuyến vào các trang cụ thể, bạn có thể tạo các đoạn văn riêng biệt`HeaderFooter` đối tượng cho mỗi trang và gán chúng bằng cách sử dụng`Header` tài sản của tương ứng`Aspose.Pdf.Page` đồ vật.