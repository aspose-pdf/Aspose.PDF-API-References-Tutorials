---
title: Thay đổi hướng
linktitle: Thay đổi hướng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để thay đổi hướng trang của PDF bằng Aspose.PDF cho .NET. Dễ dàng thực hiện và triển khai trong các dự án của bạn.
type: docs
weight: 10
url: /vi/net/programming-with-pdf-pages/change-orientation/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để thay đổi hướng trang của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được đóng gói và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Vào cuối hướng dẫn này, bạn sẽ biết cách thay đổi hướng trang của tài liệu PDF bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Aspose.PDF cho .NET được cài đặt trong môi trường phát triển của bạn

## Bước 1: Xác định thư mục tài liệu
Trước tiên, bạn cần thiết lập đường dẫn đến thư mục tài liệu của mình. Đây là vị trí tệp PDF đầu vào của bạn và là nơi bạn muốn lưu tệp PDF đầu ra đã sửa đổi của mình. Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu PDF
 Sau đó, bạn có thể tải tài liệu PDF từ tệp đầu vào bằng cách sử dụng`Document` lớp Aspose.PDF. Hãy chắc chắn chỉ định đúng đường dẫn đến tệp PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 3: Thay đổi hướng trang
Bây giờ chúng ta sẽ duyệt qua từng trang của tài liệu và thay đổi hướng của nó. Đối với mỗi trang, chúng ta sẽ sửa đổi kích thước của hộp phương tiện (`MediaBox`) bằng cách hoán đổi chiều rộng và chiều cao, sau đó chúng ta điều chỉnh tọa độ của hộp phương tiện để duy trì vị trí của trang. Cuối cùng, chúng ta đặt xoay trang thành 90 độ.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Bước 4: Lưu tài liệu PDF đã sửa đổi
 Cuối cùng, bạn có thể lưu tài liệu PDF đã sửa đổi vào tệp đầu ra bằng cách sử dụng`Save()` phương pháp của`Document`lớp. Hãy chắc chắn chỉ định đúng đường dẫn và tên tệp.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Thay đổi hướng sử dụng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Chúng ta phải di chuyển trang lên trên để bù đắp cho việc thay đổi kích thước trang
	// (cạnh dưới của trang là 0,0 và thông tin thường được đặt từ
	// Đầu trang. Đó là lý do tại sao chúng tôi di chuyển cạnh người yêu lên trên sự khác biệt giữa
	// Chiều cao cũ và mới.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Đôi khi chúng ta cũng cần thiết lập CropBox (nếu nó đã được thiết lập trong file gốc)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Thiết lập góc xoay của trang
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Lưu tập tin đầu ra
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách thay đổi hướng trang của tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước nêu trên, bạn có thể dễ dàng triển khai chức năng này trong các dự án của riêng mình. Hãy thoải mái khám phá thêm tài liệu Aspose.PDF để khám phá các tính năng hữu ích khác khi làm việc với tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của việc thay đổi hướng trang trong tài liệu PDF là gì?

A: Thay đổi hướng trang trong tài liệu PDF cho phép bạn xoay nội dung của trang 90 độ. Điều này có thể hữu ích trong các trường hợp cần hiển thị hoặc in nội dung gốc theo hướng khác, chẳng hạn như chuyển từ chế độ dọc sang chế độ ngang hoặc ngược lại.

#### H: Tôi có thể thay đổi hướng của các trang cụ thể trong tài liệu PDF không?

 A: Có, bạn có thể thay đổi hướng của các trang cụ thể trong tài liệu PDF. Trong mã nguồn C# được cung cấp,`foreach` vòng lặp được sử dụng để duyệt qua từng trang của tài liệu và thay đổi hướng của trang đó. Nếu bạn chỉ muốn thay đổi hướng của các trang cụ thể, bạn có thể sửa đổi vòng lặp để nhắm mục tiêu đến các trang đó dựa trên số trang hoặc các tiêu chí khác.

#### H: Việc thay đổi hướng trang có ảnh hưởng đến bố cục nội dung trên trang không?

A: Có, việc thay đổi hướng trang sẽ ảnh hưởng đến bố cục của nội dung trên trang. Nội dung sẽ được xoay 90 độ, chiều rộng và chiều cao của trang sẽ được hoán đổi. Do đó, vị trí và căn chỉnh của nội dung trên trang có thể thay đổi.

#### H: Tôi có thể xoay trang theo góc khác ngoài 90 độ không?

 A: Trong mã nguồn C# được cung cấp, xoay trang được thiết lập thành 90 độ bằng cách sử dụng`page.Rotate = Rotate.on90;` . Tuy nhiên, bạn có thể thay đổi góc quay thành các giá trị khác nếu cần. Ví dụ, bạn có thể sử dụng`Rotate.on180` để xoay trang 180 độ hoặc`Rotate.on270` để xoay nó 270 độ.

#### H: Tôi phải xử lý thế nào khi nội dung trang tràn ra sau khi thay đổi hướng?

A: Khi thay đổi hướng trang, kích thước của trang có thể thay đổi, có thể dẫn đến tràn nội dung. Để xử lý vấn đề này, bạn có thể cần điều chỉnh bố cục và định dạng nội dung trên trang. Bạn có thể sử dụng các tính năng do Aspose.PDF cung cấp cho .NET, chẳng hạn như thay đổi kích thước các thành phần, điều chỉnh lề hoặc sắp xếp lại nội dung, để đảm bảo nội dung trang vừa vặn sau khi thay đổi hướng.