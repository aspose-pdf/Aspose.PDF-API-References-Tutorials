---
title: Nhận Điểm Đến Siêu Liên Kết Trong Tệp PDF
linktitle: Nhận Điểm Đến Siêu Liên Kết Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất đích đến của siêu liên kết trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ để thao tác và trích xuất thông tin trong tệp PDF bằng ngôn ngữ lập trình C#. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc trích xuất các đích đến siêu liên kết từ tệp PDF bằng Aspose.PDF for .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển tích hợp (IDE) như Visual Studio.
- Thư viện Aspose.PDF dành cho .NET được cài đặt trên máy của bạn.

## Bước 1: Thiết lập môi trường phát triển

Trước khi bắt đầu viết code, bạn cần thiết lập môi trường phát triển bằng cách tạo một dự án C# mới trong IDE yêu thích của bạn.

## Bước 2: Nhập tham chiếu Aspose.PDF

Để sử dụng Aspose.PDF cho .NET, bạn cần thêm các tham chiếu thích hợp vào dự án của mình. Thực hiện theo các bước dưới đây để nhập các tham chiếu cần thiết:

1. Trong dự án của bạn, nhấp chuột phải vào "Tham chiếu" và chọn "Thêm tham chiếu".
2. Trong cửa sổ "Thêm tham chiếu", định vị và chọn các tệp DLL của Aspose.PDF cho .NET.
3. Nhấp vào "OK" để nhập tài liệu tham khảo vào dự án của bạn.

## Bước 3: Tải tệp PDF

Trước khi bạn có thể trích xuất các đích đến siêu liên kết, bạn phải tải tệp PDF vào ứng dụng của mình. Sử dụng mã sau để tải tệp PDF:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Tải tệp PDF
Document document = new Document(dataDir + "input.pdf");
```

Hãy đảm bảo chỉ định đúng đường dẫn đến thư mục tài liệu và tệp PDF bạn muốn xử lý.

## Bước 4: Điều hướng các trang của tài liệu

Bây giờ tệp PDF đã được tải, bạn cần duyệt qua tất cả các trang của tài liệu. Điều này sẽ cho phép bạn có được

ir các chú thích siêu liên kết có trên mỗi trang. Sử dụng mã sau để lặp qua các trang của tài liệu:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Nhận chú thích liên kết của một trang cụ thể
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Tạo danh sách để lưu trữ tất cả các liên kết
     IList<Annotation> list = selector. Selected;
     // Lặp qua từng mục trong danh sách
     foreach(LinkAnnotation a in list)
     {
         // In URL đích
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Mã này lặp qua từng trang của tài liệu và chọn các chú thích siêu liên kết có trên mỗi trang. Sau đó, nó lưu trữ các chú thích này trong một danh sách và in URL đích cho mỗi liên kết.

## Bước 5: Lấy đích đến của siêu liên kết

Bước cuối cùng là trích xuất các đích đến siêu liên kết từ các chú thích siêu liên kết. Mã sau đây cho bạn biết cách thực hiện:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Sử dụng điểm đến theo ý muốn của bạn
     }
}
```

Trong mã này, chúng ta lấy từng đích đến siêu liên kết từ chú thích liên kết và lưu trữ đích đến trong một biến. Sau đó, bạn có thể sử dụng đích đến này theo ý muốn trong ứng dụng của mình.

### Mã nguồn mẫu để Nhận Điểm đến Siêu liên kết bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tệp PDF
	Document document = new Document(dataDir + "input.pdf");
	// Duyệt qua tất cả các trang PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Nhận chú thích liên kết từ trang cụ thể
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Tạo danh sách chứa tất cả các liên kết
		IList<Annotation> list = selector.Selected;
		// Lặp lại qua từng mục riêng biệt bên trong danh sách
		foreach (LinkAnnotation a in list)
		{
			// In URL đích
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Câu hỏi thường gặp để lấy đích đến siêu liên kết trong tệp PDF

#### H: Điểm đến của siêu liên kết trong tệp PDF là gì?

A: Điểm đến của siêu liên kết trong tệp PDF là vị trí hoặc mục tiêu cụ thể mà siêu liên kết trỏ đến. Có thể là URL, trang trong cùng một tài liệu hoặc tài liệu bên ngoài.

#### H: Việc trích xuất đích đến của siêu liên kết có thể mang lại lợi ích gì cho việc phân tích tài liệu PDF của tôi?

A: Trích xuất các đích đến siêu liên kết cho phép bạn xác định và lập danh mục tất cả các mục tiêu mà siêu liên kết trỏ đến trong một tài liệu PDF. Thông tin này có thể hữu ích cho việc xác thực nội dung, xác minh liên kết và phân tích dữ liệu.

#### H: Aspose.PDF for .NET hỗ trợ trích xuất đích đến của siêu liên kết như thế nào?

A: Aspose.PDF cho .NET cung cấp các API mạnh mẽ để trích xuất các đích siêu liên kết một cách dễ dàng. Hướng dẫn này trình bày từng bước cách trích xuất các đích siêu liên kết bằng C#.

#### H: Tôi có thể trích xuất có chọn lọc các đích đến của siêu liên kết dựa trên các tiêu chí nhất định không?

A: Có, bạn có thể trích xuất có chọn lọc các đích đến siêu liên kết bằng cách lặp qua các trang của tài liệu PDF và lọc các chú thích siêu liên kết mong muốn dựa trên tiêu chí của bạn.

#### H: Có thể trích xuất đích đến của siêu liên kết từ các tài liệu PDF được bảo vệ bằng mật khẩu không?

A: Aspose.PDF cho .NET có thể trích xuất đích đến của siêu liên kết từ các tài liệu PDF được bảo vệ bằng mật khẩu miễn là bạn cung cấp thông tin xác thực cần thiết khi mở tài liệu.

#### H: Làm thế nào tôi có thể sử dụng các đích đến siêu liên kết đã trích xuất trong ứng dụng của mình?

A: Sau khi trích xuất các đích đến của siêu liên kết, bạn có thể sử dụng chúng để thực hiện nhiều hành động khác nhau, chẳng hạn như xác thực URL liên kết, tạo báo cáo hoặc triển khai điều hướng tùy chỉnh.

#### H: Có bất kỳ hạn chế nào khi trích xuất đích đến của siêu liên kết không?

A: Mặc dù trích xuất đích siêu liên kết rất mạnh mẽ, nhưng điều cần thiết là phải xem xét cấu trúc của tài liệu PDF. Các siêu liên kết được nhúng trong đồ họa phức tạp hoặc nội dung đa phương tiện có thể cần xử lý thêm.

#### H: Tôi có thể trích xuất các thuộc tính khác của siêu liên kết, chẳng hạn như loại liên kết hoặc tọa độ không?

A: Hướng dẫn tập trung vào việc trích xuất các đích đến siêu liên kết. Tuy nhiên, bạn có thể tham khảo tài liệu chính thức của Aspose.PDF để khám phá các tính năng nâng cao, bao gồm trích xuất các loại liên kết và tọa độ.