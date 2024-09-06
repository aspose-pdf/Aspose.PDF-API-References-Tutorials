---
title: Thiết lập kích thước hình ảnh trong tệp PDF
linktitle: Thiết lập kích thước hình ảnh trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để thiết lập kích thước hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 270
url: /vi/net/programming-with-images/set-image-size/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thiết lập kích thước hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET. Thực hiện theo các bước sau để thực hiện thao tác này một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Cài đặt và cấu hình Visual Studio hoặc bất kỳ môi trường phát triển nào khác.
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET đã được cài đặt. Bạn có thể tải xuống từ trang web chính thức của Aspose.

## Bước 1: Tạo tài liệu PDF

Để bắt đầu, hãy sử dụng mã sau để tạo một tài liệu PDF mới:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Khởi tạo một đối tượng Tài liệu
Document doc = new Document();

// Thêm một trang vào bộ sưu tập các trang của tệp PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Bước 2: Thêm hình ảnh

Tiếp theo, chúng ta sẽ thêm hình ảnh vào trang tài liệu PDF. Sử dụng mã sau:

```csharp
// Tạo một phiên bản hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Đặt chiều rộng và chiều cao của hình ảnh theo điểm
img. FixWidth = 100;
img. FixHeight = 100;

//Đặt loại hình ảnh thành không xác định (Unknown)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Đường dẫn đến tệp nguồn hình ảnh
img.File = dataDir + "aspose-logo.jpg";

// Thêm hình ảnh vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(img);
```

Hãy đảm bảo cung cấp đúng đường dẫn đến tệp hình ảnh nguồn.

## Bước 3: Thiết lập thuộc tính trang

Cuối cùng, chúng ta sẽ thiết lập các thuộc tính của trang, bao gồm chiều rộng và chiều cao. Sử dụng mã sau:

```csharp
// Thiết lập thuộc tính trang
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Mã nguồn mẫu để Đặt kích thước hình ảnh bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// thêm trang vào bộ sưu tập trang của tệp PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Tạo một phiên bản hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Đặt chiều rộng và chiều cao của hình ảnh theo điểm
img.FixWidth = 100;
img.FixHeight = 100;
// Đặt loại hình ảnh là SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Đường dẫn đến tệp nguồn
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Thiết lập thuộc tính trang
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// lưu tệp PDF kết quả
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bạn đã thiết lập thành công kích thước hình ảnh trong tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng phương pháp này vào các dự án của riêng mình để điều chỉnh kích thước hình ảnh trong tệp PDF.

### Câu hỏi thường gặp về việc thiết lập kích thước hình ảnh trong tệp PDF

#### H: Mục đích của việc thiết lập kích thước hình ảnh trong tài liệu PDF bằng Aspose.PDF cho .NET là gì?

A: Mục đích của việc thiết lập kích thước hình ảnh trong tài liệu PDF là để kiểm soát kích thước của hình ảnh khi thêm vào PDF. Điều này cho phép bạn điều chỉnh giao diện và bố cục của hình ảnh trong tệp PDF của mình.

#### H: Quá trình thiết lập kích thước hình ảnh trong tài liệu PDF diễn ra như thế nào?

 A: Quá trình này bao gồm việc tạo ra một`Aspose.Pdf.Image` ví dụ, chỉ định chiều rộng và chiều cao của nó bằng cách sử dụng`FixWidth` Và`FixHeight` thuộc tính, sau đó thêm hình ảnh vào tài liệu PDF. Ngoài ra, bạn có thể thiết lập kích thước của chính trang để chứa hình ảnh.

#### H: Tôi có thể thiết lập kích thước của hình ảnh theo tỷ lệ phần trăm cụ thể của kích thước trang không?

A: Mã được cung cấp thiết lập chiều rộng và chiều cao tuyệt đối của hình ảnh theo điểm. Nếu bạn muốn thiết lập kích thước của hình ảnh dựa trên phần trăm kích thước trang, bạn sẽ cần tính toán kích thước cho phù hợp và điều chỉnh mã cho phù hợp.

####  Q: Ý nghĩa của việc này là gì?`FileType` property when adding an image to the PDF document?

 A: Cái`FileType`thuộc tính chỉ định loại hình ảnh được thêm vào tài liệu PDF. Trong mã được cung cấp, giá trị`Unknown` cho biết loại hình ảnh không xác định và Aspose.PDF sẽ cố gắng xác định loại hình ảnh dựa trên phần mở rộng tệp.

#### H: Tôi có thể thêm nhiều hình ảnh vào một trang bằng phương pháp này không?

 A: Có, bạn có thể thêm nhiều hình ảnh vào một trang bằng cách tạo nhiều`Aspose.Pdf.Image` và thêm chúng vào bộ sưu tập đoạn văn của trang. Đảm bảo điều chỉnh vị trí và bố cục của hình ảnh khi cần thiết.

#### H: Làm thế nào tôi có thể kiểm soát vị trí và căn chỉnh của hình ảnh được thêm vào trang?

 A: Vị trí và sự căn chỉnh của hình ảnh được thêm vào có thể được kiểm soát bằng cách điều chỉnh tọa độ và bố cục của hình ảnh bằng các thuộc tính như`img.Left`, `img.Top`và các thuộc tính định dạng đoạn văn.

####  Q: Mục đích của việc thiết lập các thuộc tính trang bằng cách sử dụng là gì?`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Thiết lập thuộc tính trang cho phép bạn xác định kích thước của chính trang đó. Điều này đảm bảo rằng kích thước trang phù hợp với hình ảnh được thêm vào và bất kỳ nội dung nào khác mà bạn có thể có trên trang.

#### H: Tôi có thể đặt kích thước khác nhau cho các hình ảnh khác nhau trong cùng một tài liệu PDF không?

 A: Có, bạn có thể thiết lập các kích thước khác nhau cho các hình ảnh khác nhau bằng cách tạo các hình ảnh riêng biệt.`Aspose.Pdf.Image` trường hợp và điều chỉnh`FixWidth`, `FixHeight`và các thuộc tính vị trí cho mỗi hình ảnh.

#### H: Làm thế nào tôi có thể tích hợp phương pháp này vào các dự án của mình để thiết lập kích thước hình ảnh trong tệp PDF?

A: Để tích hợp phương pháp này vào các dự án của bạn, hãy làm theo các bước được nêu và sửa đổi mã khi cần. Bạn có thể sử dụng phương pháp này để thêm hình ảnh có kích thước cụ thể vào tài liệu PDF của mình dựa trên yêu cầu của ứng dụng.