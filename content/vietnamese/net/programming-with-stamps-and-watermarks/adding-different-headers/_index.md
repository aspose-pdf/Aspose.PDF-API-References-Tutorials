---
title: Thêm các tiêu đề khác nhau vào tệp PDF
linktitle: Thêm các tiêu đề khác nhau vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách dễ dàng thêm các tiêu đề khác nhau vào mỗi trang trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm các tiêu đề khác nhau vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để thêm các tiêu đề tùy chỉnh vào từng trang của tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu PDF

Bước đầu tiên là tải tài liệu PDF hiện có vào dự án của bạn. Thực hiện như sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu nguồn
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 3: Tạo bộ đệm tiêu đề

Bây giờ bạn đã tải lên tài liệu PDF, bạn có thể tạo dấu tiêu đề để thêm vào. Thực hiện như sau:

```csharp
// Tạo ba bộ đệm tiêu đề
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Đoạn mã trên tạo ra ba bộ đệm tiêu đề mới chứa văn bản được chỉ định.

## Bước 4: Cấu hình thuộc tính bộ đệm tiêu đề

Trước khi thêm dấu tiêu đề vào tài liệu PDF, bạn có thể cấu hình các thuộc tính khác nhau cho mỗi dấu, chẳng hạn như căn chỉnh, kích thước, màu sắc, v.v. Thực hiện như sau:

```csharp
// Cấu hình bộ đệm tiêu đề đầu tiên
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Cấu hình bộ đệm tiêu đề thứ hai
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Cấu hình bộ đệm tiêu đề thứ ba
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Bạn có thể điều chỉnh các thuộc tính này khi cần thiết cho từng bộ đệm tiêu đề.

## Bước 5: Thêm Dấu Tiêu đề vào PDF

Bây giờ dấu tiêu đề đã sẵn sàng, bạn có thể thêm chúng vào từng trang cụ thể của tài liệu PDF. Thực hiện như sau:

```csharp
// Thêm bộ đệm tiêu đề vào các trang cụ thể
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Đoạn mã trên sẽ thêm từng dấu tiêu đề vào trang tương ứng của tài liệu PDF.

## Bước 6: Lưu tài liệu đầu ra

Sau khi thêm dấu tiêu đề, bạn có thể lưu tài liệu PDF đã chỉnh sửa. Thực hiện như sau:

```csharp
// Lưu tài liệu đã cập nhật
doc.Save(dataDir);
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu để Thêm các Tiêu đề Khác nhau bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tài liệu nguồn mở
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Tạo ba con tem
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// Đặt căn chỉnh tem (đặt tem ở đầu trang, căn giữa theo chiều ngang)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Chỉ định kiểu phông chữ là In đậm
stamp1.TextState.FontStyle = FontStyles.Bold;

// Đặt thông tin màu nền trước của văn bản thành màu đỏ
stamp1.TextState.ForegroundColor = Color.Red;

// Chỉ định kích thước phông chữ là 14
stamp1.TextState.FontSize = 14;

// Bây giờ chúng ta cần thiết lập căn chỉnh theo chiều dọc của đối tượng tem thứ 2 là Top
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Đặt thông tin căn chỉnh theo chiều ngang cho tem là Căn giữa
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Đặt hệ số thu phóng cho đối tượng tem
stamp2.Zoom = 10;

//Thiết lập định dạng của đối tượng tem thứ 3
// Chỉ định thông tin căn chỉnh theo chiều dọc cho đối tượng tem là TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Đặt thông tin căn chỉnh theo chiều ngang cho đối tượng tem là Căn giữa
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Thiết lập góc quay cho đối tượng tem
stamp3.RotateAngle = 35;

// Đặt màu hồng làm màu nền cho tem
stamp3.TextState.BackgroundColor = Color.Pink;

// Thay đổi thông tin mặt phông chữ cho tem thành Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Con dấu đầu tiên được thêm vào trang đầu tiên;
doc.Pages[1].AddStamp(stamp1);

// Con dấu thứ hai được thêm vào trang thứ hai;
doc.Pages[2].AddStamp(stamp2);

// Con dấu thứ ba được thêm vào trang thứ ba.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Lưu tài liệu đã cập nhật
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Phần kết luận

Xin chúc mừng! Bạn đã học được cách thêm các tiêu đề khác nhau vào mỗi trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng kiến thức này vào các dự án của riêng mình để tùy chỉnh tiêu đề cho tài liệu PDF của bạn.

### Câu hỏi thường gặp về việc thêm các tiêu đề khác nhau vào tệp PDF

#### H: Mục đích của việc thêm nhiều tiêu đề khác nhau vào tệp PDF bằng Aspose.PDF cho .NET là gì?

A: Thêm các tiêu đề khác nhau vào tệp PDF bằng Aspose.PDF cho .NET cho phép bạn tùy chỉnh nội dung hiển thị ở đầu mỗi trang. Tính năng này đặc biệt hữu ích để thêm tiêu đề, tên phần, số trang và thông tin khác thay đổi trên các trang khác nhau của tài liệu PDF.

#### H: Tôi có thể tùy chỉnh giao diện của từng tiêu đề như căn chỉnh, phông chữ, kích thước, màu sắc và xoay không?

 A: Có, bạn có thể tùy chỉnh hoàn toàn giao diện của từng tem tiêu đề. Mã nguồn C# được cung cấp sẽ trình bày cách thiết lập các thuộc tính khác nhau của`TextStamp` các đối tượng cho mỗi tiêu đề, bao gồm căn chỉnh theo chiều dọc và chiều ngang, kiểu phông chữ, kích thước phông chữ, màu phông chữ, màu nền và góc xoay.

#### H: Có thể thêm nhiều dấu tiêu đề vào cùng một trang của tài liệu PDF không?

A: Trong khi hướng dẫn được cung cấp chứng minh cách thêm các tiêu đề khác nhau vào các trang riêng biệt của tài liệu PDF, bạn có thể điều chỉnh mã để thêm nhiều dấu tiêu đề vào cùng một trang. Điều này có thể hữu ích nếu bạn muốn hiển thị các tiêu đề khác nhau trong cùng một phần.

#### H: Làm sao tôi có thể đảm bảo tiêu đề không trùng với nội dung chính của các trang PDF?

 A: Để tránh chồng chéo, bạn có thể điều chỉnh`VerticalAlignment`, `HorizontalAlignment` và các thuộc tính khác của`TextStamp` đối tượng. Các thiết lập này sẽ kiểm soát vị trí đặt tiêu đề trên trang, cho phép bạn định vị chúng theo cách không cản trở nội dung chính.

#### H: Tôi có thể sử dụng phương pháp này để thêm tiêu đề vào các tài liệu PDF hiện có với số trang khác nhau không?

A: Có, bạn có thể điều chỉnh mã nguồn được cung cấp để thêm tiêu đề vào các tài liệu PDF hiện có với số trang khác nhau. Chỉ cần điều chỉnh mã để phù hợp với số tiêu đề bạn muốn thêm và liên kết từng tiêu đề với trang mong muốn.

#### H: Tôi phải làm sao nếu muốn thêm tiêu đề vào các trang cụ thể, không chỉ ba trang đầu tiên?

 A: Hướng dẫn này trình bày cách thêm tiêu đề vào ba trang đầu tiên cho mục đích minh họa. Để thêm tiêu đề vào các trang cụ thể ngoài ba trang đầu tiên, hãy điều chỉnh mã bằng cách tham chiếu đến các chỉ mục trang tương ứng và tạo`TextStamp` đối tượng cho mỗi trang.

#### H: Tôi có thể sử dụng hình ảnh làm tiêu đề thay vì văn bản không?

 A: Hướng dẫn được cung cấp tập trung vào việc thêm tiêu đề dựa trên văn bản. Tuy nhiên, bạn có thể áp dụng cách tiếp cận tương tự để thêm tiêu đề dựa trên hình ảnh bằng cách sử dụng`ImageStamp` các đối tượng thay vì`TextStamp` đối tượng. Điều này sẽ liên quan đến việc tạo và cấu hình`ImageStamp` các đối tượng có đặc tính mong muốn.

#### H: Tôi có thể áp dụng kiến thức này để thêm các chân trang khác nhau vào mỗi trang của tài liệu PDF như thế nào?

 A: Có thể áp dụng cách tiếp cận tương tự được trình bày trong hướng dẫn này để thêm các chân trang khác nhau vào mỗi trang của tài liệu PDF. Thay vì tiêu đề, bạn sẽ tạo và cấu hình`TextStamp` hoặc`ImageStamp` các đối tượng và thêm chúng vào cuối mỗi trang bằng cách sử dụng`AddStamp` phương pháp.

#### H: Tôi có thể tự động hóa quy trình thêm tiêu đề vào nhiều tài liệu PDF trong một thao tác hàng loạt không?

A: Có, bạn có thể tự động hóa quy trình thêm tiêu đề vào nhiều tài liệu PDF bằng cách sử dụng một tập lệnh hoặc chương trình lặp qua danh sách tài liệu và áp dụng quy trình đóng dấu tiêu đề cho từng tài liệu.