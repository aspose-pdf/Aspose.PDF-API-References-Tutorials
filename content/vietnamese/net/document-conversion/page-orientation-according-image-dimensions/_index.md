---
title: Định hướng trang theo kích thước hình ảnh
linktitle: Định hướng trang theo kích thước hình ảnh
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để đặt hướng trang dựa trên kích thước hình ảnh với Aspose.PDF cho .NET.
type: docs
weight: 80
url: /vi/net/document-conversion/page-orientation-according-image-dimensions/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập hướng trang dựa trên kích thước của hình ảnh bằng Aspose.PDF cho .NET. Chúng tôi sẽ lặp qua danh sách hình ảnh JPG trong một thư mục nhất định và tự động điều chỉnh hướng trang dựa trên chiều rộng của mỗi hình ảnh. Thực hiện theo các bước dưới đây để đạt được điều này.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Duyệt ảnh JPG
Ở bước này, chúng tôi sẽ duyệt tất cả các hình ảnh JPG trong một thư mục nhất định. Thực hiện theo mã dưới đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo một tài liệu PDF mới
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Truy xuất tên của tất cả các tệp JPG trong một thư mục cụ thể
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực nơi chứa hình ảnh JPG của bạn.

## Bước 2: Tạo trang và hình ảnh
Sau khi duyệt các tệp JPG, chúng tôi sẽ tạo một trang và hình ảnh cho mỗi tệp. Sử dụng mã sau đây:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Tạo đối tượng Trang
Aspose.Pdf.Page page = doc.Pages.Add();

// Tạo một đối tượng Hình ảnh
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Bước 3: Kiểm tra kích thước hình ảnh
Bây giờ hãy kiểm tra kích thước của từng hình ảnh để xác định hướng trang. Sử dụng mã sau đây:

```csharp
// Tạo đối tượng BitMap để lấy thông tin từ file ảnh
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Kiểm tra xem chiều rộng của hình ảnh có lớn hơn chiều rộng của trang hay không
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Nếu chiều rộng của hình ảnh nhỏ hơn chiều rộng của trang, hãy đặt hướng của trang thành dọc
page.PageInfo.IsLandscape = false;
```

## Bước 4: Thêm hình ảnh vào tài liệu PDF
Sau khi kiểm tra kích thước của hình ảnh, chúng ta sẽ thêm hình ảnh vào bộ sưu tập đoạn văn của tài liệu PDF. Sử dụng mã sau đây:

```csharp
// Thêm hình ảnh vào bộ sưu tập đoạn văn của tài liệu PDF
page.Paragraphs.Add(image1);
```

## Bước 5: Lưu tệp PDF
Khi chúng tôi đã thêm tất cả hình ảnh vào tài liệu PDF, bây giờ chúng tôi có thể lưu tệp PDF kết quả. Đây là bước cuối cùng:

```csharp
// Lưu tệp PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục mong muốn nơi bạn muốn lưu tệp PDF đầu ra.

### Mã nguồn mẫu cho Định hướng trang theo kích thước hình ảnh bằng Aspose.PDF for .NET

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Truy xuất tên của tất cả các tệp JPG trong một Thư mục cụ thể
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Tạo một đối tượng trang
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Tạo đối tượng hình ảnh
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Tạo đối tượng BitMap để lấy thông tin file ảnh
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Kiểm tra độ rộng của file ảnh có lớn hơn Page width hay không
	if (myimage.Width > page.PageInfo.Width)
		// Nếu chiều rộng Hình ảnh lớn hơn chiều rộng trang thì hãy đặt hướng trang thành Ngang
		page.PageInfo.IsLandscape = true;
	else
		// Nếu chiều rộng Hình ảnh nhỏ hơn chiều rộng trang thì hãy đặt hướng trang thành Chân dung
		page.PageInfo.IsLandscape = false;
	// Thêm hình ảnh vào bộ sưu tập đoạn văn của tài liệu PDF
	page.Paragraphs.Add(image1);
}
// Lưu tệp Pdf
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước thiết lập hướng trang dựa trên kích thước của hình ảnh bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn nêu trên, giờ đây bạn có thể tạo tài liệu PDF với hướng trang chính xác cho từng hình ảnh. Tính năng này hữu ích khi bạn có hình ảnh có kích thước khác nhau và muốn nhúng chúng vào tài liệu PDF.

### Câu hỏi thường gặp

#### Hỏi: Tôi có thể sử dụng các định dạng hình ảnh khác thay vì JPG để đặt hướng trang dựa trên kích thước hình ảnh không?

Đáp: Có, bạn có thể sử dụng các định dạng hình ảnh khác như PNG, BMP hoặc GIF ngoài JPG để đặt hướng trang dựa trên kích thước hình ảnh. Mã được cung cấp lặp qua tất cả các tệp hình ảnh có phần mở rộng ".JPG", nhưng bạn cũng có thể sửa đổi mã này để bao gồm các định dạng hình ảnh khác.

#### Hỏi: Điều gì sẽ xảy ra nếu kích thước của hình ảnh bằng chính xác chiều rộng của trang?

Đáp: Nếu chiều rộng của hình ảnh bằng chính xác chiều rộng của trang thì hướng trang sẽ được đặt thành dọc. Trong mã được cung cấp, hướng trang chỉ được đặt thành ngang nếu chiều rộng của hình ảnh lớn hơn chiều rộng của trang.

#### Câu hỏi: Tôi có thể tùy chỉnh logic định hướng trang dựa trên các yêu cầu cụ thể không?

Đáp: Có, bạn có thể tùy chỉnh logic định hướng trang dựa trên các yêu cầu cụ thể. Ví dụ: bạn có thể đặt giá trị ngưỡng để xác định khi nào nên đặt hướng trang thành ngang hoặc dọc. Ngoài ra, bạn có thể xem xét các yếu tố như chiều cao hình ảnh hoặc tỷ lệ khung hình để xác định hướng trang.

#### Hỏi: Tôi có thể thêm nội dung khác, chẳng hạn như văn bản hoặc bảng, vào tài liệu PDF cùng với hình ảnh không?

Đáp: Có, bạn có thể thêm nội dung khác, chẳng hạn như văn bản hoặc bảng, vào tài liệu PDF cùng với hình ảnh. Aspose.PDF for .NET cung cấp một bộ tính năng phong phú để thao tác với tài liệu PDF, bao gồm thêm văn bản, hình ảnh, bảng và các thành phần khác vào trang.