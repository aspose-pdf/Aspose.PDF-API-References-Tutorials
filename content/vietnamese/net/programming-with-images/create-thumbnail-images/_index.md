---
title: Tạo hình ảnh thu nhỏ trong tệp PDF
linktitle: Tạo hình ảnh thu nhỏ trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng tạo hình ảnh thu nhỏ trong tệp PDF với Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-images/create-thumbnail-images/
---
Hướng dẫn này sẽ hướng dẫn bạn từng bước cách tạo hình thu nhỏ trong tệp PDF bằng Aspose.PDF cho .NET. Đảm bảo bạn đã thiết lập môi trường của mình và làm theo các bước dưới đây:

## Bước 1: Xác định thư mục tài liệu

Trước khi bắt đầu, hãy đảm bảo bạn thiết lập đúng thư mục cho các tài liệu. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã có đường dẫn đến thư mục chứa tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Lấy tên của tất cả các tệp PDF trong một thư mục

 Trong bước này, chúng ta sẽ lấy tên của tất cả các tệp PDF có trong thư mục được chỉ định bằng cách sử dụng C#`Directory`lớp. Các tập tin sẽ được lưu trữ trong một mảng chuỗi.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Bước 3: Duyệt tất cả các tệp PDF và các trang của chúng

 Trong bước này, chúng ta sẽ duyệt qua tất cả các tệp PDF và các trang của chúng để tạo hình thu nhỏ. Chúng ta sẽ sử dụng`for` vòng lặp để lặp qua tất cả các tập tin.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Mở tài liệu PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Duyệt qua tất cả các trang của tài liệu
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Tạo một luồng để lưu hình ảnh thu nhỏ
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Tạo đối tượng Độ phân giải
             Resolution resolution = new Resolution(300);
            
             // Tạo một thiết bị JPEG với các thuộc tính được chỉ định
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Chuyển đổi một trang cụ thể và lưu hình ảnh vào luồng
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Đóng luồng
             imageStream.Close();
         }
     }
}
```

### Mã nguồn mẫu để tạo hình ảnh thu nhỏ bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lấy tên của tất cả các tệp PDF trong một thư mục cụ thể
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Lặp lại tất cả các mục nhập tệp trong mảng
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Mở tài liệu
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Tạo đối tượng Resolution
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, độ phân giải, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Chuyển đổi một trang cụ thể và lưu hình ảnh vào luồng
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Đóng luồng
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Phần kết luận

Xin chúc mừng! Bạn đã tạo thành công hình thu nhỏ từ các tệp PDF bằng Aspose.PDF cho .NET. Hình thu nhỏ được lưu trong thư mục đã chỉ định. Bây giờ bạn có thể sử dụng các hình thu nhỏ này để hiển thị bản xem trước trực quan của các tệp PDF của mình.

### Câu hỏi thường gặp để tạo hình ảnh thu nhỏ trong tệp PDF

#### H: Mục đích của việc tạo hình ảnh thu nhỏ từ tệp PDF bằng Aspose.PDF cho .NET là gì?

A: Việc tạo hình ảnh thu nhỏ từ tệp PDF cho phép bạn tạo bản xem trước trực quan nhỏ của từng trang trong PDF, có thể hữu ích để xem trước và điều hướng nhanh qua nội dung.

#### H: Aspose.PDF for .NET hỗ trợ việc tạo hình ảnh thu nhỏ từ tệp PDF như thế nào?

 A: Aspose.PDF cho .NET cung cấp quy trình từng bước để mở tài liệu PDF, lặp lại qua các trang của chúng, tạo hình ảnh thu nhỏ và lưu chúng vào một thư mục được chỉ định bằng cách sử dụng`JpegDevice` lớp học.

#### H: Tại sao việc xác định thư mục tài liệu trước khi bắt đầu tạo hình ảnh thu nhỏ lại quan trọng?

A: Việc chỉ định thư mục tài liệu sẽ đảm bảo các tệp PDF được định vị chính xác và hình ảnh thu nhỏ thu được sẽ được lưu trong đường dẫn đầu ra mong muốn.

####  Q: Làm thế nào để`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A: Cái`Document` lớp cho phép bạn mở và thao tác các tài liệu PDF. Trong trường hợp này, nó được sử dụng để tải các tệp PDF mà từ đó hình ảnh thu nhỏ sẽ được tạo.

####  Q: Vai trò của`JpegDevice` class play in the creation of thumbnail images?

 A: Cái`JpegDevice` Lớp này chịu trách nhiệm chuyển đổi các trang PDF thành hình ảnh JPEG, được sử dụng làm hình ảnh thu nhỏ. Nó cho phép bạn chỉ định các thuộc tính như chiều rộng, chiều cao, độ phân giải và chất lượng.

#### H: Làm thế nào để chuyển đổi từng trang của tài liệu PDF thành hình ảnh thu nhỏ riêng lẻ?

 A: Một lồng nhau`for` vòng lặp được sử dụng để lặp lại qua từng tệp PDF và các trang của nó. Đối với mỗi trang, một thiết bị JPEG được tạo ra với các thuộc tính được chỉ định và`Process` phương pháp này được sử dụng để chuyển đổi trang thành hình ảnh thu nhỏ và lưu vào luồng.

#### H: Tôi có thể điều chỉnh độ phân giải hoặc chất lượng của hình ảnh thu nhỏ trong quá trình tạo không?

A: Có, bạn có thể sửa đổi các thuộc tính như độ phân giải, chiều rộng, chiều cao và chất lượng bằng cách cấu hình`JpegDevice` đối tượng trước khi chuyển đổi từng trang.

#### H: Làm thế nào tôi có thể sử dụng hình ảnh thu nhỏ được tạo ra trong các dự án hoặc ứng dụng của mình sau quá trình tạo?

A: Hình ảnh thu nhỏ kết quả có thể được sử dụng để cung cấp bản xem trước trực quan của tệp PDF, giúp người dùng nhanh chóng xác định và điều hướng qua nội dung.

#### : Có giới hạn nào về số lượng hình ảnh thu nhỏ có thể tạo từ tệp PDF bằng quy trình tạo này không?

A: Số lượng hình ảnh thu nhỏ được tạo ra phụ thuộc vào số trang trong mỗi tài liệu PDF. Mỗi trang sẽ được chuyển đổi thành một hình ảnh thu nhỏ riêng biệt.