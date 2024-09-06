---
title: Số trang trong Header Footer sử dụng hộp nổi
linktitle: Số trang trong Header Footer sử dụng hộp nổi
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm số trang vào đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 150
url: /vi/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm số trang vào phần đầu trang và phần chân trang của tài liệu PDF bằng FloatingBox với Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để tạo tài liệu PDF, thêm trang, tạo FloatingBox, đặt vị trí của nó và thêm số trang vào đó, sau đó lưu tài liệu PDF đã sửa đổi.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu PDF và thêm trang

Bước đầu tiên là tạo một phiên bản của tài liệu PDF và thêm một trang vào đó. Sau đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Khởi tạo tài liệu PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Thêm một trang vào tài liệu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

## Bước 3: Tạo FloatingBox và thêm số trang

Bây giờ trang đã được thêm vào tài liệu PDF, chúng ta có thể tạo FloatingBox, đặt vị trí của nó và thêm số trang vào đó. Sau đây là cách thực hiện:

```csharp
// Tạo một FloatingBox có chiều rộng là 140 và chiều cao là 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Đặt vị trí bên trái của đoạn văn
box1. Left = 2;

// Đặt vị trí đầu của đoạn văn
box1. Top = 10;

// Thêm số trang vào FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Thêm FloatingBox vào trang
page.Paragraphs.Add(box1);
```

Đoạn mã trên tạo ra một FloatingBox có chiều rộng là 140 và chiều cao là 80. Tiếp theo, chúng ta thiết lập vị trí của nó bằng cách chỉ định các giá trị left và top. Cuối cùng, chúng ta thêm số trang vào FloatingBox bằng cách sử dụng TextFragment có cú pháp "($p/ $P )" sẽ được thay thế bằng số trang hiện tại và tổng số trang.

## Bước 4: Lưu tài liệu PDF đã sửa đổi

Sau khi số trang được thêm vào đầu trang hoặc chân trang bằng FloatingBox, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Thực hiện như sau:

```csharp
// Lưu tài liệu PDF đã sửa đổi
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu cho Số trang trong Đầu trang Chân trang Sử dụng Hộp nổi sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo phiên bản Tài liệu
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Thêm một trang vào tài liệu pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// Khởi tạo một thể hiện mới của lớp FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Giá trị float chỉ ra vị trí bên trái của đoạn văn
box1.Left = 2;

// Giá trị float chỉ ra vị trí trên cùng của đoạn văn
box1.Top = 10;

// Thêm các macro vào bộ sưu tập đoạn văn của FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Thêm một floatingBox vào trang
page.Paragraphs.Add(box1);

// Lưu tài liệu
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm số trang vào phần đầu trang và phần chân trang của tài liệu PDF bằng FloatingBox với Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh phần đầu trang và phần chân trang của mình bằng cách thêm thông tin động như số trang.

### Câu hỏi thường gặp

#### H: FloatingBox là gì và được sử dụng như thế nào để thêm số trang vào phần đầu trang hoặc phần chân trang của tài liệu PDF?

A: FloatingBox là một thành phần bố cục đa năng trong Aspose.PDF có thể chứa nhiều nội dung khác nhau, bao gồm văn bản và hình ảnh. Trong hướng dẫn này, nó được sử dụng để tạo một vùng chứa cho số trang, cho phép bạn chèn động số trang hiện tại và tổng số trang vào đầu trang hoặc chân trang.

#### H: Mã nguồn C# được cung cấp thực hiện việc thêm số trang bằng FloatingBox như thế nào?

A: Đoạn mã này minh họa cách tạo tài liệu PDF, thêm trang, tạo FloatingBox, đặt vị trí của nó trong trang và chèn số trang bằng TextFragment. Cú pháp "($p/ $P )" trong TextFragment được thay thế bằng số trang hiện tại và tổng số trang.

#### H: Tôi có thể tùy chỉnh giao diện và định dạng của số trang được thêm vào bằng FloatingBox không?

A: Có, bạn có thể tùy chỉnh giao diện của số trang bằng cách sửa đổi các thuộc tính của TextFragment trong FloatingBox. Bạn có thể thay đổi kích thước phông chữ, màu sắc, kiểu, căn chỉnh và các tùy chọn định dạng khác.

#### H: Có thể thêm các thành phần động khác nhau, chẳng hạn như ngày và giờ, vào đầu trang hoặc chân trang bằng cách sử dụng phương pháp tương tự không?

A: Hoàn toàn có thể, bạn có thể thêm các thành phần động khác nhau như ngày, giờ, siêu dữ liệu tài liệu hoặc văn bản tùy chỉnh bằng cách sửa đổi nội dung TextFragment trong FloatingBox. Bạn có thể sử dụng các macro như "($p/ $P )" cho số trang hoặc "($date)" cho ngày hiện tại.

#### H: Làm thế nào để xác định vị trí của FloatingBox trong phần đầu trang hoặc chân trang?
 A: Mã được cung cấp thiết lập vị trí của FloatingBox bằng cách sử dụng`Left` Và`Top` thuộc tính. Bạn có thể điều chỉnh các giá trị này để định vị FloatingBox theo ý muốn trong phần đầu trang hoặc chân trang.

#### H: Tôi có thể sử dụng phông chữ hoặc kiểu khác cho số trang ở đầu trang hoặc chân trang không?

A: Có, bạn có thể tùy chỉnh phông chữ, kiểu và các thuộc tính định dạng khác của văn bản số trang bằng cách sửa đổi thuộc tính TextFragment trong FloatingBox.

#### H: Điều gì xảy ra nếu nội dung trong FloatingBox vượt quá kích thước của nó?

A: Nếu nội dung trong FloatingBox vượt quá kích thước của nó, nó có thể bị cắt bỏ hoặc có thể phát sinh vấn đề về bố cục. Đảm bảo rằng kích thước của FloatingBox phù hợp để chứa nội dung và cân nhắc điều chỉnh bố cục trang nếu cần.

#### H: Có thể thêm nhiều FloatingBox có nội dung khác nhau vào phần đầu trang hoặc phần chân trang của cùng một trang không?

A: Có, bạn có thể thêm nhiều FloatingBox có nội dung khác nhau vào phần đầu trang hoặc chân trang của cùng một trang bằng cách tạo các phiên bản FloatingBox riêng biệt và thêm chúng vào bộ sưu tập Đoạn văn của trang.

#### H: Tôi có thể sử dụng phương pháp FloatingBox để thêm nội dung vào các phần khác của tài liệu PDF, chẳng hạn như phần thân hoặc lề không?

A: Mặc dù FloatingBox thường được sử dụng cho phần đầu trang và chân trang, bạn cũng có thể sử dụng chúng để thêm nội dung vào các phần khác của tài liệu PDF, chẳng hạn như phần thân hoặc lề, bằng cách định vị chúng cho phù hợp trong trang.