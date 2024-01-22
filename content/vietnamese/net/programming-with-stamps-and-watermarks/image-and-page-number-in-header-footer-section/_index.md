---
title: Hình ảnh và số trang trong phần Header Footer
linktitle: Hình ảnh và số trang trong phần Header Footer
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm hình ảnh và số trang vào đầu trang và chân trang của tài liệu PDF bằng Aspose.
type: docs
weight: 110
url: /vi/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn C# được cung cấp để tạo trang, đặt đầu trang và chân trang, thêm hình ảnh vào đầu trang và văn bản kèm số trang vào chân trang tài liệu PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu
Aspose.Pdf.Page page = doc.Pages.Add();
```

Đoạn mã trên tạo một đối tượng Tài liệu mới và một trang trống trong tài liệu PDF.

## Bước 3: Thêm tiêu đề bằng hình ảnh

Bây giờ trang đã được tạo, chúng ta có thể thêm phần tiêu đề có hình ảnh. Đây là cách thực hiện:

```csharp
// Tạo phần tiêu đề
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề trang
page. Header = header;

// Tạo một đối tượng Hình ảnh
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Đặt đường dẫn hình ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Thêm hình ảnh vào tiêu đề trang của tài liệu PDF
header.Paragraphs.Add(image1);
```

Đoạn mã trên tạo phần tiêu đề, đặt tiêu đề trang cho phần này và thêm hình ảnh vào tiêu đề.

## Bước 4: Thêm footer kèm theo số trang

Bây giờ tiêu đề đã được thêm, chúng ta có thể thêm phần chân trang có số trang. Đây là cách thực hiện:

```csharp
// Tạo phần chân trang
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Xác định chân trang của tài liệu PDF
page. Footer = footer;

// Tạo một đối tượng TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Thêm văn bản có số trang vào chân trang của tài liệu PDF
footer.Paragraphs.Add(txt);
```

Đoạn mã trên tạo phần chân trang, đặt chân trang của trang với phần này và thêm TextFragment chứa văn bản "Trang: ($p của $P )"

  trong đó hiển thị số trang.

## Bước 5: Lưu tài liệu PDF đã sửa đổi

Sau khi thêm đầu trang và chân trang, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Đây là cách thực hiện:

```csharp
// Lưu tài liệu PDF đã sửa đổi
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Đoạn mã trên lưu tài liệu PDF đã chỉnh sửa vào thư mục được chỉ định.

### Mã nguồn mẫu cho Hình ảnh và Số trang trong Phần chân trang đầu trang sử dụng Aspose.PDF for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Tạo một trang trong đối tượng tài liệu
Aspose.Pdf.Page page = doc.Pages.Add();

// Tạo phần tiêu đề của tài liệu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề cho tệp PDF
page.Header = header;

// Tạo một đối tượng hình ảnh trong trang
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Đặt đường dẫn của file ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Thêm hình ảnh vào trang Header của file Pdf
header.Paragraphs.Add(image1);

//Tạo phần Footer của tài liệu
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Đặt chân trang của tệp PDF
page.Footer = footer;

// Tạo một đối tượng Văn bản
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Thêm văn bản vào phần Header của file Pdf
footer.Paragraphs.Add(txt);

// Lưu tệp Pdf
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng phương pháp này để tùy chỉnh đầu trang và chân trang trong tài liệu PDF của mình.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của việc thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF là gì?

Đáp: Việc thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF có thể nâng cao tính hấp dẫn trực quan, thương hiệu và các yếu tố điều hướng của tài liệu đó. Hình ảnh có thể đại diện cho biểu tượng, hình mờ hoặc bất kỳ thành phần đồ họa nào, trong khi số trang giúp người dùng theo dõi tiến trình của họ và định vị các trang cụ thể.

#### Câu hỏi: Mã nguồn C# được cung cấp giúp thêm hình ảnh và số trang vào đầu trang và chân trang của tài liệu PDF như thế nào?

Đáp: Mã được cung cấp minh họa cách tạo tài liệu PDF, thêm trang, sau đó tùy chỉnh phần đầu trang và chân trang. Nó cho thấy cách thêm hình ảnh vào đầu trang và một đoạn văn bản có đánh số trang ở chân trang.

#### Hỏi: Tôi có thể sử dụng bất kỳ định dạng hình ảnh nào cho tiêu đề không và làm cách nào để chỉ định đường dẫn của nó?

 Trả lời: Có, bạn có thể sử dụng nhiều định dạng hình ảnh khác nhau (chẳng hạn như JPEG, PNG, GIF, v.v.) cho hình ảnh tiêu đề. Đường dẫn của hình ảnh được chỉ định bằng cách sử dụng`File` tài sản của`Aspose.Pdf.Image` sự vật.

#### Hỏi: Làm cách nào để tùy chỉnh giao diện và vị trí của hình ảnh trong phần tiêu đề?

 Đáp: Bạn có thể tùy chỉnh hình thức và vị trí của hình ảnh bằng cách điều chỉnh các thuộc tính của`Aspose.Pdf.Image` đối tượng trước khi thêm nó vào phần tiêu đề. Ví dụ: bạn có thể đặt kích thước, căn chỉnh, xoay, độ mờ của hình ảnh, v.v.

####  Hỏi: Mục đích của việc này là gì?`TextFragment` object used for the footer?

 Đáp: Cái`TextFragment` đối tượng được sử dụng để tạo và định dạng văn bản sẽ hiển thị ở phần chân trang. Trong mã được cung cấp, nó được sử dụng để hiển thị số trang và tổng số trang.

#### Hỏi: Tôi có thể sửa đổi văn bản chân trang để bao gồm thông tin hoặc định dạng bổ sung không?

 Trả lời: Có, bạn có thể sửa đổi văn bản chân trang bằng cách sửa đổi nội dung của`TextFragment` sự vật. Bạn có thể thêm văn bản bổ sung, thay đổi phông chữ, màu sắc và định dạng theo yêu cầu của mình.

#### Hỏi: Tôi có thể áp dụng các nội dung đầu trang và chân trang khác nhau cho các trang khác nhau của tài liệu PDF không?

 Đáp: Có, bạn có thể áp dụng các nội dung đầu trang và chân trang khác nhau cho các trang khác nhau bằng cách tạo các nội dung riêng biệt.`HeaderFooter` các đối tượng và gán chúng vào các trang cụ thể bằng cách sử dụng`Header` Và`Footer` thuộc tính của`Aspose.Pdf.Page` sự vật.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh thêm đầu trang và chân trang, chẳng hạn như thay đổi kiểu phông chữ hoặc thêm các thành phần bổ sung?

Trả lời: Bạn có thể tùy chỉnh đầu trang và chân trang bằng cách sử dụng nhiều lớp và thuộc tính khác nhau do Aspose.PDF cung cấp cho .NET. Ví dụ: bạn có thể sử dụng các tùy chọn định dạng văn bản khác nhau, thêm nhiều đoạn văn, hình ảnh hoặc thậm chí bảng vào phần đầu trang và chân trang.

#### Hỏi: Tôi có thể xóa hoặc xóa phần đầu trang và chân trang nếu cần không?

Trả lời: Có, bạn có thể xóa hoặc xóa phần đầu trang và chân trang bằng cách đặt`Header` Và`Footer` thuộc tính của`Aspose.Pdf.Page` chủ đề`null`.

#### Hỏi: Làm cách nào tôi có thể đảm bảo rằng hình ảnh và số trang được thêm vào vẫn nhất quán trên các thiết bị và người xem khác nhau?

Trả lời: Aspose.PDF for .NET cung cấp chức năng tạo tài liệu PDF nhất quán và chuẩn hóa, đảm bảo rằng hình ảnh và số trang được thêm vào sẽ xuất hiện nhất quán trên các thiết bị và trình xem PDF khác nhau.