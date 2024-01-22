---
title: Nhận đích đến siêu liên kết trong tệp PDF
linktitle: Nhận đích đến siêu liên kết trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất đích siêu liên kết trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ để thao tác và trích xuất thông tin trong tệp PDF bằng ngôn ngữ lập trình C#. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc trích xuất đích siêu liên kết từ tệp PDF bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển tích hợp (IDE) như Visual Studio.
- Thư viện Aspose.PDF cho .NET được cài đặt trên máy của bạn.

## Bước 1: Thiết lập môi trường phát triển

Trước khi bắt đầu viết mã, bạn cần thiết lập môi trường phát triển của mình bằng cách tạo dự án C# mới trong IDE yêu thích của bạn.

## Bước 2: Nhập tài liệu tham khảo Aspose.PDF

Để sử dụng Aspose.PDF cho .NET, bạn cần thêm các tham chiếu thích hợp vào dự án của mình. Thực hiện theo các bước bên dưới để nhập các tài liệu tham khảo cần thiết:

1. Trong dự án của bạn, nhấp chuột phải vào "Tài liệu tham khảo" và chọn "Thêm tài liệu tham khảo".
2. Trong cửa sổ "Thêm tài liệu tham khảo", định vị và chọn tệp DLL của Aspose.PDF cho .NET.
3. Nhấp vào "OK" để nhập tài liệu tham khảo vào dự án của bạn.

## Bước 3: Tải tệp PDF

Trước khi có thể trích xuất đích siêu liên kết, bạn phải tải tệp PDF vào ứng dụng của mình. Sử dụng đoạn mã sau để tải tệp PDF:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Tải tập tin PDF
Document document = new Document(dataDir + "input.pdf");
```

Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu của bạn và tệp PDF bạn muốn xử lý.

## Bước 4: Điều hướng các trang của tài liệu

Bây giờ tệp PDF đã được tải, bạn cần xem qua tất cả các trang của tài liệu. Điều này sẽ cho phép bạn có được

ir các chú thích siêu liên kết hiện diện trên mỗi trang. Sử dụng đoạn mã sau để lặp qua các trang của tài liệu:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Nhận chú thích liên kết của một trang cụ thể
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Tạo một danh sách để lưu trữ tất cả các liên kết
     IList<Annotation> list = selector. Selected;
     // Lặp qua từng mục trong danh sách
     foreach(LinkAnnotation a in list)
     {
         // In URL đích
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Mã này lặp qua từng trang của tài liệu và chọn các chú thích siêu liên kết có trên mỗi trang. Sau đó, nó lưu trữ các chú thích này vào danh sách và in URL đích cho mỗi liên kết.

## Bước 5: Lấy đích đến của siêu liên kết

Bước cuối cùng là trích xuất các đích đến siêu liên kết từ các chú thích siêu liên kết. Đoạn mã sau chỉ cho bạn cách thực hiện:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Sử dụng điểm đến như bạn muốn
     }
}
```

Trong mã này, chúng tôi lấy từng đích siêu liên kết từ các chú thích liên kết và lưu đích vào một biến. Sau đó, bạn có thể sử dụng điểm đến này theo ý muốn trong ứng dụng của mình.

### Mã nguồn mẫu cho Nhận đích siêu kết nối bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tập tin PDF
	Document document = new Document(dataDir + "input.pdf");
	// Duyệt qua tất cả các trang PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Nhận chú thích liên kết từ trang cụ thể
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Tạo danh sách chứa tất cả các liên kết
		IList<Annotation> list = selector.Selected;
		// Lặp lại thông qua mục invidiaul bên trong danh sách
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

### Câu hỏi thường gặp để nhận đích siêu liên kết trong tệp PDF

#### Hỏi: Đích siêu liên kết trong tệp PDF là gì?

Đáp: Đích siêu liên kết trong tệp PDF là một vị trí hoặc mục tiêu cụ thể mà siêu liên kết trỏ tới. Nó có thể là một URL, một trang trong cùng một tài liệu hoặc một tài liệu bên ngoài.

#### Câu hỏi: Việc trích xuất đích siêu liên kết có thể mang lại lợi ích cho việc phân tích tài liệu PDF của tôi như thế nào?

Trả lời: Việc trích xuất đích siêu liên kết cho phép bạn xác định và lập danh mục tất cả các mục tiêu mà siêu liên kết trỏ tới trong tài liệu PDF. Thông tin này có thể hữu ích cho việc xác thực nội dung, xác minh liên kết và phân tích dữ liệu.

#### Câu hỏi: Aspose.PDF cho .NET hỗ trợ trích xuất đích siêu liên kết như thế nào?

Trả lời: Aspose.PDF for .NET cung cấp các API mạnh mẽ để trích xuất đích siêu liên kết một cách dễ dàng. Hướng dẫn này trình bày từng bước cách trích xuất đích siêu liên kết bằng C#.

#### Câu hỏi: Tôi có thể trích xuất có chọn lọc các đích đến siêu liên kết dựa trên các tiêu chí nhất định không?

Trả lời: Có, bạn có thể trích xuất có chọn lọc các đích đến siêu liên kết bằng cách duyệt qua các trang của tài liệu PDF và lọc các chú thích siêu liên kết mong muốn dựa trên tiêu chí của bạn.

#### Hỏi: Có thể trích xuất đích siêu liên kết từ tài liệu PDF được bảo vệ bằng mật khẩu không?

Đáp: Aspose.PDF for .NET có thể trích xuất đích siêu liên kết từ các tài liệu PDF được bảo vệ bằng mật khẩu miễn là bạn cung cấp thông tin xác thực cần thiết khi mở tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng đích siêu liên kết được trích xuất trong ứng dụng của mình?

Đáp: Sau khi đã trích xuất đích đến siêu liên kết, bạn có thể sử dụng chúng để thực hiện nhiều hành động khác nhau, chẳng hạn như xác thực URL liên kết, tạo báo cáo hoặc triển khai điều hướng tùy chỉnh.

#### Câu hỏi: Có bất kỳ hạn chế nào khi trích xuất đích siêu liên kết không?

Đáp: Mặc dù việc trích xuất đích siêu liên kết rất hiệu quả nhưng điều cần thiết là phải xem xét cấu trúc của tài liệu PDF. Các siêu liên kết được nhúng trong đồ họa phức tạp hoặc nội dung đa phương tiện có thể yêu cầu xử lý bổ sung.

#### Câu hỏi: Tôi có thể trích xuất các thuộc tính khác của siêu liên kết, chẳng hạn như loại liên kết hoặc tọa độ không?

Đáp: Hướng dẫn này tập trung vào việc trích xuất các đích đến của siêu liên kết. Tuy nhiên, bạn có thể tham khảo tài liệu chính thức của Aspose.PDF để khám phá các tính năng nâng cao, bao gồm trích xuất các loại liên kết và tọa độ.