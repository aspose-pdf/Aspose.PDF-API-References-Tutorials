---
title: Đặt kích thước hình ảnh trong tệp PDF
linktitle: Đặt kích thước hình ảnh trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để đặt kích thước hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 270
url: /vi/net/programming-with-images/set-image-size/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách đặt kích thước hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET. Hãy làm theo các bước sau để thực hiện thao tác này một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ môi trường phát triển nào khác được cài đặt và định cấu hình.
- Có kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF dành cho .NET được cài đặt. Bạn có thể tải xuống từ trang web chính thức của Aspose.

## Bước 1: Tạo tài liệu PDF

Để bắt đầu, hãy sử dụng mã sau để tạo tài liệu PDF mới:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Khởi tạo một đối tượng Tài liệu
Document doc = new Document();

// Thêm một trang vào bộ sưu tập các trang của tệp PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Bước 2: Thêm hình ảnh

Tiếp theo, chúng tôi sẽ thêm hình ảnh vào trang của tài liệu PDF. Sử dụng mã sau đây:

```csharp
// Tạo một ví dụ hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Đặt chiều rộng và chiều cao của hình ảnh theo điểm
img. FixWidth = 100;
img. FixHeight = 100;

// Đặt loại hình ảnh thành không xác định (Không xác định)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Đường dẫn đến tập tin nguồn hình ảnh
img.File = dataDir + "aspose-logo.jpg";

// Thêm hình ảnh vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(img);
```

Đảm bảo cung cấp đường dẫn chính xác tới tệp nguồn hình ảnh.

## Bước 3: Thiết lập thuộc tính trang

Cuối cùng, chúng ta sẽ thiết lập các thuộc tính của trang, bao gồm chiều rộng và chiều cao của trang. Sử dụng mã sau đây:

```csharp
// Đặt thuộc tính trang
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Mã nguồn mẫu cho Đặt kích thước hình ảnh bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// thêm trang vào bộ sưu tập trang của tệp PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Tạo một ví dụ hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Đặt chiều rộng và chiều cao của hình ảnh theo điểm
img.FixWidth = 100;
img.FixHeight = 100;
// Đặt loại hình ảnh là SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Đường dẫn tới file nguồn
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Đặt thuộc tính trang
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// lưu tệp PDF kết quả
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bạn đã đặt thành công kích thước hình ảnh trong tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng phương pháp này cho các dự án của riêng mình để điều chỉnh kích thước hình ảnh trong tệp PDF.

### Câu hỏi thường gặp về đặt kích thước hình ảnh trong tệp PDF

#### Câu hỏi: Mục đích của việc đặt kích thước hình ảnh trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

Đáp: Mục đích của việc đặt kích thước hình ảnh trong tài liệu PDF là để kiểm soát kích thước của hình ảnh khi nó được thêm vào PDF. Điều này cho phép bạn điều chỉnh giao diện và bố cục của hình ảnh trong tệp PDF của mình.

#### Hỏi: Quá trình thiết lập kích thước hình ảnh trong tài liệu PDF diễn ra như thế nào?

 Đáp: Quá trình này bao gồm việc tạo ra một`Aspose.Pdf.Image` ví dụ, chỉ định chiều rộng và chiều cao của nó bằng cách sử dụng`FixWidth` Và`FixHeight` thuộc tính, sau đó thêm hình ảnh vào tài liệu PDF. Ngoài ra, bạn có thể đặt kích thước của trang để chứa hình ảnh.

#### Hỏi: Tôi có thể đặt kích thước của hình ảnh theo tỷ lệ phần trăm cụ thể của kích thước trang không?

Đáp: Mã được cung cấp đặt chiều rộng và chiều cao tuyệt đối của hình ảnh theo điểm. Nếu bạn muốn đặt kích thước của hình ảnh dựa trên tỷ lệ phần trăm kích thước trang, bạn cần tính toán kích thước tương ứng và điều chỉnh mã cho phù hợp.

####  Hỏi: Ý nghĩa của`FileType` property when adding an image to the PDF document?

 Đáp: Cái`FileType`thuộc tính chỉ định loại hình ảnh được thêm vào tài liệu PDF. Trong mã được cung cấp, giá trị`Unknown` cho biết loại hình ảnh không xác định và Aspose.PDF sẽ cố gắng xác định loại hình ảnh dựa trên phần mở rộng tệp.

#### Hỏi: Tôi có thể thêm nhiều hình ảnh vào một trang bằng phương pháp này không?

 Đáp: Có, bạn có thể thêm nhiều hình ảnh vào một trang bằng cách tạo nhiều hình ảnh.`Aspose.Pdf.Image` các phiên bản và thêm chúng vào bộ sưu tập đoạn văn của trang. Đảm bảo điều chỉnh vị trí và bố cục của hình ảnh nếu cần.

#### Hỏi: Làm cách nào tôi có thể kiểm soát vị trí và căn chỉnh của hình ảnh được thêm vào trên trang?

 Trả lời: Bạn có thể kiểm soát vị trí và căn chỉnh của hình ảnh được thêm bằng cách điều chỉnh tọa độ và bố cục của hình ảnh bằng các thuộc tính như`img.Left`, `img.Top`và các thuộc tính định dạng đoạn văn.

####  Hỏi: Mục đích của việc thiết lập các thuộc tính trang bằng cách sử dụng`page.PageInfo.Width` and `page.PageInfo.Height`?

Trả lời: Việc đặt thuộc tính trang cho phép bạn xác định kích thước của chính trang đó. Điều này đảm bảo rằng kích thước trang phù hợp với hình ảnh được thêm vào và bất kỳ nội dung nào khác mà bạn có thể có trên trang.

#### Hỏi: Tôi có thể đặt các kích thước khác nhau cho các hình ảnh khác nhau trong cùng một tài liệu PDF không?

 Đáp: Có, bạn có thể đặt các kích thước khác nhau cho các hình ảnh khác nhau bằng cách tạo các kích thước riêng biệt.`Aspose.Pdf.Image` trường hợp và điều chỉnh`FixWidth`, `FixHeight`và thuộc tính vị trí cho mỗi hình ảnh.

#### Hỏi: Làm cách nào tôi có thể tích hợp phương pháp này vào các dự án của riêng mình để đặt kích thước hình ảnh trong tệp PDF?

Đáp: Để tích hợp phương pháp này vào dự án của bạn, hãy làm theo các bước đã nêu và sửa đổi mã nếu cần. Bạn có thể sử dụng phương pháp này để thêm hình ảnh có kích thước cụ thể vào tài liệu PDF dựa trên yêu cầu của ứng dụng.