---
title: Số Trang Trong Đầu Trang Chân Trang Sử Dụng Hộp Nổi
linktitle: Số Trang Trong Đầu Trang Chân Trang Sử Dụng Hộp Nổi
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm số trang vào đầu trang và chân trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 150
url: /vi/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm số trang vào đầu trang và chân trang của tài liệu PDF bằng cách sử dụng FloatBox với Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để tạo tài liệu PDF, thêm trang, tạo Hộp nổi, đặt vị trí và thêm số trang vào đó, sau đó lưu tài liệu PDF đã sửa đổi.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu PDF và thêm trang

Bước đầu tiên là tạo một phiên bản của tài liệu PDF và thêm một trang vào đó. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Khởi tạo tài liệu PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Thêm một trang vào tài liệu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF.

## Bước 3: Tạo FloatBox và thêm số trang

Bây giờ trang đã được thêm vào tài liệu PDF, chúng ta có thể tạo một Hộp nổi, đặt vị trí của nó và thêm số trang vào đó. Đây là cách thực hiện:

```csharp
// Tạo một FloatBox có chiều rộng 140 và chiều cao 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Đặt vị trí bên trái của đoạn văn
box1. Left = 2;

// Đặt vị trí trên cùng của đoạn văn
box1. Top = 10;

// Thêm số trang vào FloatBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Thêm hộp nổi vào trang
page.Paragraphs.Add(box1);
```

Đoạn mã trên tạo một FloatBox có chiều rộng là 140 và chiều cao là 80. Tiếp theo, chúng ta đặt vị trí của nó bằng cách chỉ định giá trị bên trái và trên cùng. Cuối cùng, chúng ta thêm số trang vào FloatBox bằng cách sử dụng TextFragment chứa cú pháp "($p/ $P )" sẽ được thay thế bằng số trang hiện tại và tổng số trang.

## Bước 4: Lưu tài liệu PDF đã sửa đổi

Khi số trang được thêm vào đầu trang hoặc chân trang bằng cách sử dụng FloatBox, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Đây là cách thực hiện:

```csharp
// Lưu tài liệu PDF đã sửa đổi
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Đoạn mã trên lưu tài liệu PDF đã chỉnh sửa vào thư mục được chỉ định.

### Mã nguồn mẫu cho Số trang trong Đầu trang Chân trang Sử dụng Hộp nổi bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo phiên bản tài liệu
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Thêm một trang vào tài liệu pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

//Khởi tạo một phiên bản mới của lớp FloatBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Giá trị float cho biết vị trí bên trái của đoạn văn
box1.Left = 2;

// Giá trị nổi cho biết vị trí trên cùng của đoạn văn
box1.Top = 10;

// Thêm macro vào bộ sưu tập đoạn văn của Hộp nổi
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Thêm một hộp nổi vào trang
page.Paragraphs.Add(box1);

// Lưu tài liệu
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm số trang vào đầu trang và chân trang của tài liệu PDF bằng cách sử dụng FloatBox với Aspose.PDF cho .NET. Bây giờ bạn có thể tùy chỉnh đầu trang và chân trang bằng cách thêm thông tin động như số trang.

### Câu hỏi thường gặp

#### Câu hỏi: Hộp nổi là gì và nó được sử dụng như thế nào để thêm số trang vào đầu trang hoặc chân trang của tài liệu PDF?

Trả lời: FloatBox là một thành phần bố cục linh hoạt trong Aspose.PDF có thể chứa nhiều nội dung khác nhau, bao gồm văn bản và hình ảnh. Trong hướng dẫn này, nó được sử dụng để tạo vùng chứa số trang, cho phép bạn chèn động số trang hiện tại và tổng số trang vào đầu trang hoặc chân trang.

#### Câu hỏi: Mã nguồn C# được cung cấp thực hiện việc cộng số trang bằng cách sử dụng Hộp nổi như thế nào?

Đáp: Đoạn mã trình bày cách tạo tài liệu PDF, thêm trang, tạo Hộp nổi, đặt vị trí của nó trong trang và chèn số trang bằng cách sử dụng TextFragment. Cú pháp "($p/ $P )" trong TextFragment được thay thế bằng số trang hiện tại và tổng số trang.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện và định dạng của số trang được thêm bằng cách sử dụng FloatBox không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của số trang bằng cách sửa đổi các thuộc tính của TextFragment trong FloatBox. Bạn có thể thay đổi kích thước phông chữ, màu sắc, kiểu, căn chỉnh và các tùy chọn định dạng khác.

#### Câu hỏi: Có thể thêm các phần tử động khác nhau, chẳng hạn như ngày và giờ, vào đầu trang hoặc chân trang bằng cách sử dụng phương pháp tương tự không?

Trả lời: Hoàn toàn có thể, bạn có thể thêm các yếu tố động khác nhau như ngày, giờ, siêu dữ liệu tài liệu hoặc văn bản tùy chỉnh bằng cách sửa đổi nội dung TextFragment trong FloatBox. Bạn có thể sử dụng macro như "($p/ $P )" cho số trang hoặc "($date)" cho ngày hiện tại.

#### Câu hỏi: Làm cách nào để chỉ định vị trí của Hộp nổi trong phần đầu trang hoặc chân trang?
 Trả lời: Mã được cung cấp đặt vị trí của Hộp nổi bằng cách sử dụng`Left` Và`Top` của cải. Bạn có thể điều chỉnh các giá trị này để định vị FloatBox như mong muốn trong phần đầu trang hoặc chân trang.

#### Hỏi: Tôi có thể sử dụng phông chữ hoặc kiểu khác cho số trang ở đầu trang hoặc chân trang không?

Trả lời: Có, bạn có thể tùy chỉnh phông chữ, kiểu và các thuộc tính định dạng khác của văn bản số trang bằng cách sửa đổi các thuộc tính TextFragment trong FloatBox.

#### Câu hỏi: Điều gì xảy ra nếu nội dung trong Hộp nổi vượt quá kích thước của nó?

Trả lời: Nếu nội dung trong Hộp nổi vượt quá kích thước của nó, nội dung đó có thể bị cắt bớt hoặc có thể phát sinh vấn đề về bố cục. Đảm bảo rằng kích thước của Hộp nổi phù hợp để chứa nội dung và xem xét điều chỉnh bố cục trang nếu cần.

#### Câu hỏi: Có thể thêm nhiều Hộp nổi có nội dung khác nhau vào đầu trang hoặc chân trang của cùng một trang không?

Trả lời: Có, bạn có thể thêm nhiều Hộp nổi có nội dung khác nhau vào đầu trang hoặc chân trang của cùng một trang bằng cách tạo các phiên bản Hộp nổi riêng biệt và thêm chúng vào bộ sưu tập Đoạn văn của trang.

#### Câu hỏi: Tôi có thể sử dụng phương pháp FloatBox để thêm nội dung vào các phần khác của tài liệu PDF, chẳng hạn như nội dung hoặc lề không?

Trả lời: Mặc dù Hộp nổi thường được sử dụng cho đầu trang và chân trang, nhưng bạn cũng có thể sử dụng chúng để thêm nội dung vào các phần khác của tài liệu PDF, chẳng hạn như nội dung hoặc lề, bằng cách định vị chúng phù hợp trong trang.