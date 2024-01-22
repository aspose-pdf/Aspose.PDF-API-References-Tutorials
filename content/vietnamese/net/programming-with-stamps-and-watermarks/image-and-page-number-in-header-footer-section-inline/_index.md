---
title: Hình ảnh và số trang trong phần chân trang đầu trang nội tuyến
linktitle: Hình ảnh và số trang trong phần chân trang đầu trang nội tuyến
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm hình ảnh và số trang vào đầu trang và chân trang bằng cách sử dụng các đoạn nội tuyến với Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để tạo trang, đặt đầu trang và chân trang, thêm hình ảnh và văn bản bằng cách sử dụng các đoạn nội tuyến trong tiêu đề của tài liệu PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu và trang PDF

Bước đầu tiên là tạo một đối tượng Tài liệu mới và một trang trong tài liệu PDF. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo một đối tượng Tài liệu mới
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Đoạn mã trên tạo một đối tượng Tài liệu mới và một trang trống trong tài liệu PDF.

## Bước 3: Thêm tiêu đề bằng hình ảnh và văn bản nội tuyến

Bây giờ trang đã được tạo, chúng ta có thể thêm phần tiêu đề có hình ảnh và văn bản bằng cách sử dụng các đoạn nội tuyến. Đây là cách thực hiện:

```csharp
// Tạo phần tiêu đề
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề trang
page. Header = header;

// Tạo đối tượng TextFragment cho văn bản nội tuyến đầu tiên
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Chỉ định màu văn bản
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Tạo đối tượng Image cho ảnh
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Đặt đường dẫn hình ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Xác định kích thước của hình ảnh
image1.FixWidth = 50;
image1.FixHeight = 20;

// Cho biết văn bản nội tuyến đầu tiên là hình ảnh
image1.IsInLineParagraph = true;

// Tạo văn bản nội tuyến thứ hai
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Thêm mục vào tiêu đề
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Đoạn mã trên tạo phần tiêu đề, đặt tiêu đề trang cho phần này, thêm TextFragment với văn bản nội tuyến và đối tượng Hình ảnh nội tuyến.

## Bước 4: Lưu tài liệu PDF đã sửa đổi

Sau khi thêm tiêu đề có hình ảnh và văn bản nội tuyến, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Đây là cách thực hiện:

```csharp
// Lưu tài liệu PDF đã sửa đổi
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Đoạn mã trên lưu tài liệu PDF đã chỉnh sửa vào thư mục được chỉ định.

### Mã nguồn mẫu cho Hình ảnh và Số trang trong Phần chân trang đầu trang Nội tuyến bằng cách sử dụng Aspose.PDF for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một đối tượng Tài liệu bằng cách gọi hàm tạo trống của nó
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Tạo một trang trong đối tượng Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Tạo phần tiêu đề của tài liệu
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

// Đặt đường dẫn của file ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Đặt chiều rộng hình ảnh Thông tin
image1.FixWidth = 50;
image1.FixHeight = 20;

// Cho biết InlineParagraph của seg1 là một hình ảnh.
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

Xin chúc mừng! Bạn đã học cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng cách sử dụng các đoạn nội tuyến với Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh đầu trang và chân trang của tài liệu PDF một cách linh hoạt.

### Câu hỏi thường gặp

#### Hỏi: Lợi ích của việc sử dụng đoạn văn nội tuyến để thêm hình ảnh và văn bản vào tiêu đề của tài liệu PDF là gì?

Đáp: Việc sử dụng các đoạn văn cùng dòng cho phép bạn tích hợp liền mạch hình ảnh và văn bản trong cùng một đoạn văn, cung cấp khả năng kiểm soát chính xác vị trí và định dạng của chúng. Phương pháp này đặc biệt hữu ích để tạo tiêu đề tùy chỉnh với các yếu tố trực quan.

#### Câu hỏi: Làm cách nào để mã nguồn C# được cung cấp đạt được các đoạn nội tuyến cho tiêu đề trong tài liệu PDF?

Đáp: Mã được cung cấp minh họa cách tạo tài liệu PDF, thêm trang và tùy chỉnh tiêu đề bằng cách sử dụng các đoạn nội tuyến. Nó thêm một TextFragment với văn bản nội tuyến, một hình ảnh nội tuyến và một TextFragment nội tuyến khác.

#### Câu hỏi: Làm cách nào để chỉ định màu của văn bản nội tuyến trong tiêu đề?

 Đáp: Màu của văn bản nội tuyến được xác định bằng cách sử dụng`ForegroundColor` tài sản của`TextState` sau đó`TextFragment` sự vật.

#### Câu hỏi: Tôi có thể điều chỉnh kích thước của hình ảnh nội tuyến trong tiêu đề không?

 Đáp: Có, bạn có thể điều chỉnh kích thước của hình ảnh nội tuyến bằng cách sử dụng`FixWidth` Và`FixHeight` thuộc tính của`Image` sự vật. Điều này cho phép bạn kiểm soát chiều rộng và chiều cao của hình ảnh trong tiêu đề.

#### Câu hỏi: Tôi có thể bao gồm các thành phần nội tuyến bổ sung, chẳng hạn như siêu liên kết hoặc các kiểu phông chữ khác nhau, trong tiêu đề không?

 Đáp: Có, bạn có thể bao gồm các phần tử nội tuyến bổ sung trong tiêu đề bằng cách tạo thêm`TextFragment` hoặc`Image` các đối tượng có thuộc tính mong muốn. Điều này cho phép bạn tùy chỉnh thêm tiêu đề, bao gồm siêu liên kết, kiểu phông chữ khác nhau hoặc các yếu tố hình ảnh khác.

#### Câu hỏi: Làm cách nào tôi có thể đảm bảo rằng hình ảnh và văn bản cùng dòng vẫn được căn chỉnh và định dạng chính xác trên các thiết bị và người xem khác nhau?

Đáp: Aspose.PDF for .NET đảm bảo rằng hình ảnh và văn bản nội tuyến được căn chỉnh và định dạng chính xác, mang lại hình thức nhất quán trên các thiết bị và trình xem PDF khác nhau.

#### Câu hỏi: Tôi có thể áp dụng các đoạn văn nội tuyến cho phần chân trang không?

 Đáp: Có, bạn có thể áp dụng kỹ thuật tương tự như sử dụng đoạn văn nội tuyến cho phần chân trang bằng cách tạo một`Footer` đối tượng và thêm các phần tử nội tuyến như văn bản và hình ảnh vào đó.

#### Câu hỏi: Có thể kết hợp các đoạn nội tuyến với các phương pháp tùy chỉnh đầu trang hoặc chân trang khác không?

Trả lời: Có, bạn có thể kết hợp các đoạn nội tuyến với các phương pháp tùy chỉnh đầu trang hoặc chân trang khác do Aspose.PDF cung cấp cho .NET để tạo các thiết kế đầu trang hoặc chân trang phức tạp hơn và phù hợp hơn.

#### Câu hỏi: Tôi có thể xóa hoặc xóa các thành phần nội tuyến khỏi tiêu đề nếu cần không?

 Đáp: Có, bạn có thể loại bỏ hoặc xóa các phần tử nội tuyến bằng cách sửa đổi nội dung của`HeaderFooter` đối tượng và loại bỏ các đoạn nội tuyến tương ứng.

#### Hỏi: Làm cách nào tôi có thể áp dụng các đoạn nội tuyến cho các trang cụ thể của tài liệu PDF?

 Đáp: Để áp dụng các đoạn nội tuyến cho các trang cụ thể, bạn có thể tạo các đoạn văn riêng biệt.`HeaderFooter` đối tượng cho mỗi trang và gán chúng bằng cách sử dụng`Header` tài sản tương ứng`Aspose.Pdf.Page` các đối tượng.