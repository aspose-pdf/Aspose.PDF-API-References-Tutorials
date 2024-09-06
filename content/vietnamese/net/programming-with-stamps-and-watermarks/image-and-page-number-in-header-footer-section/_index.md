---
title: Hình ảnh và số trang trong phần Header Footer
linktitle: Hình ảnh và số trang trong phần Header Footer
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm hình ảnh và số trang vào đầu trang và chân trang của tài liệu PDF bằng Aspose.
type: docs
weight: 110
url: /vi/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để tạo trang, đặt đầu trang và chân trang, thêm hình ảnh vào đầu trang và văn bản có số trang vào chân trang tài liệu PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Tạo một trang trong tài liệu
Aspose.Pdf.Page page = doc.Pages.Add();
```

Đoạn mã trên tạo ra một đối tượng Tài liệu mới và một trang trống trong tài liệu PDF.

## Bước 3: Thêm tiêu đề bằng hình ảnh

Bây giờ trang đã được tạo, chúng ta có thể thêm phần tiêu đề có hình ảnh. Thực hiện như sau:

```csharp
// Tạo phần tiêu đề
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề trang
page. Header = header;

// Tạo một đối tượng hình ảnh
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Đặt đường dẫn hình ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Thêm hình ảnh vào tiêu đề trang của tài liệu PDF
header.Paragraphs.Add(image1);
```

Đoạn mã trên tạo ra một phần tiêu đề, đặt tiêu đề trang bằng phần này và thêm hình ảnh vào tiêu đề.

## Bước 4: Thêm chân trang với số trang

Bây giờ tiêu đề đã được thêm vào, chúng ta có thể thêm phần chân trang có số trang. Thực hiện như sau:

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

Đoạn mã trên tạo một phần chân trang, đặt phần chân trang của trang bằng phần này và thêm một TextFragment chứa văn bản "Trang: ($p của $P)"

  hiển thị số trang.

## Bước 5: Lưu tài liệu PDF đã sửa đổi

Sau khi thêm phần đầu trang và phần chân trang, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Thực hiện như sau:

```csharp
// Lưu tài liệu PDF đã sửa đổi
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu cho Hình ảnh và Số trang trong phần Đầu trang/Chân trang sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Tạo một trang trong đối tượng tài liệu
Aspose.Pdf.Page page = doc.Pages.Add();

// Tạo phần Tiêu đề của tài liệu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Đặt tiêu đề cho tệp PDF
page.Header = header;

// Tạo một đối tượng hình ảnh trong trang
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Thiết lập đường dẫn của tập tin hình ảnh
image1.File = dataDir + "aspose-logo.jpg";

// Thêm hình ảnh vào trang Header của file Pdf
header.Paragraphs.Add(image1);

//Tạo Phần Chân trang của tài liệu
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Đặt chân trang của tệp PDF
page.Footer = footer;

// Tạo một đối tượng Văn bản
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Thêm văn bản vào phần Tiêu đề của tệp Pdf
footer.Paragraphs.Add(txt);

// Lưu tệp PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học được cách thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng phương pháp này để tùy chỉnh phần đầu trang và chân trang trong tài liệu PDF của mình.

### Câu hỏi thường gặp

#### H: Mục đích của việc thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF là gì?

A: Thêm hình ảnh và số trang vào phần đầu trang và chân trang của tài liệu PDF có thể tăng cường sức hấp dẫn trực quan, thương hiệu và các yếu tố điều hướng. Hình ảnh có thể đại diện cho logo, hình mờ hoặc bất kỳ yếu tố đồ họa nào, trong khi số trang giúp người dùng theo dõi tiến trình của họ và xác định vị trí các trang cụ thể.

#### H: Mã nguồn C# được cung cấp giúp thêm hình ảnh và số trang vào đầu trang và chân trang của tài liệu PDF như thế nào?

A: Mã được cung cấp minh họa cách tạo tài liệu PDF, thêm trang và sau đó tùy chỉnh phần đầu trang và chân trang. Mã này cho biết cách thêm hình ảnh vào đầu trang và đoạn văn bản có đánh số trang vào chân trang.

#### H: Tôi có thể sử dụng bất kỳ định dạng hình ảnh nào cho phần đầu trang không và làm thế nào để chỉ định đường dẫn của nó?

 A: Có, bạn có thể sử dụng nhiều định dạng hình ảnh khác nhau (như JPEG, PNG, GIF, v.v.) cho hình ảnh tiêu đề. Đường dẫn của hình ảnh được chỉ định bằng cách sử dụng`File` tài sản của`Aspose.Pdf.Image` sự vật.

#### H: Làm thế nào để tùy chỉnh giao diện và vị trí của hình ảnh trong phần tiêu đề?

 A: Bạn có thể tùy chỉnh giao diện và vị trí của hình ảnh bằng cách điều chỉnh các thuộc tính của`Aspose.Pdf.Image` đối tượng trước khi thêm nó vào phần tiêu đề. Ví dụ, bạn có thể thiết lập kích thước, căn chỉnh, xoay, độ mờ, v.v. của hình ảnh.

####  Q: Mục đích của việc này là gì?`TextFragment` object used for the footer?

 A: Cái`TextFragment` Đối tượng được sử dụng để tạo và định dạng văn bản sẽ được hiển thị trong phần chân trang. Trong mã được cung cấp, nó được sử dụng để hiển thị số trang và tổng số trang.

#### H: Tôi có thể sửa đổi văn bản chân trang để bao gồm thông tin bổ sung hoặc định dạng không?

 A: Có, bạn có thể sửa đổi văn bản chân trang bằng cách sửa đổi nội dung của`TextFragment` đối tượng. Bạn có thể thêm văn bản bổ sung, thay đổi phông chữ, màu sắc và định dạng theo yêu cầu của bạn.

#### H: Tôi có thể áp dụng nội dung đầu trang và chân trang khác nhau cho các trang khác nhau của tài liệu PDF không?

 A: Có, bạn có thể áp dụng nội dung tiêu đề và chân trang khác nhau cho các trang khác nhau bằng cách tạo riêng`HeaderFooter` các đối tượng và gán chúng vào các trang cụ thể bằng cách sử dụng`Header` Và`Footer` tính chất của`Aspose.Pdf.Page` sự vật.

#### H: Tôi có thể tùy chỉnh thêm phần đầu trang và chân trang như thế nào, chẳng hạn như thay đổi kiểu phông chữ hoặc thêm các thành phần bổ sung?

A: Bạn có thể tùy chỉnh header và footer bằng cách sử dụng nhiều lớp và thuộc tính khác nhau do Aspose.PDF cung cấp cho .NET. Ví dụ, bạn có thể sử dụng các tùy chọn định dạng văn bản khác nhau, thêm nhiều đoạn văn, hình ảnh hoặc thậm chí là bảng vào phần header và footer.

#### H: Tôi có thể xóa hoặc xóa phần đầu trang và chân trang nếu cần không?

A: Có, bạn có thể xóa hoặc xóa phần đầu trang và chân trang bằng cách thiết lập`Header` Và`Footer` tính chất của`Aspose.Pdf.Page` phản đối`null`.

#### H: Làm sao tôi có thể đảm bảo hình ảnh và số trang được thêm vào luôn nhất quán trên các thiết bị và trình xem khác nhau?

A: Aspose.PDF cho .NET cung cấp chức năng tạo các tài liệu PDF chuẩn hóa và thống nhất, đảm bảo rằng hình ảnh và số trang được thêm vào sẽ xuất hiện thống nhất trên các thiết bị và trình xem PDF khác nhau.