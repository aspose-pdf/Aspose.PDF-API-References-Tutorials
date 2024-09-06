---
title: Tìm kiếm đoạn văn bản trang trong tệp PDF
linktitle: Tìm kiếm đoạn văn bản trang trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm các phân đoạn văn bản trên một trang trong tệp PDF và lấy các thuộc tính của chúng bằng Aspose.PDF cho .NET.
type: docs
weight: 470
url: /vi/net/programming-with-text/search-text-segments-page/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm các đoạn văn bản cụ thể trên một trang tệp PDF và lấy các thuộc tính của chúng. Mã nguồn C# được cung cấp minh họa quy trình từng bước.

## Điều kiện tiên quyết

Trước khi thực hiện hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để cài đặt vào dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) mà bạn thích và thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm lệnh using sau vào đầu tệp C# của bạn để nhập các không gian tên cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` biến:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tải tài liệu PDF

 Tải tài liệu PDF bằng cách sử dụng`Document` lớp học:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Thay thế`"SearchTextSegmentsPage.pdf"` bằng tên thực của tệp PDF của bạn.

## Bước 5: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Thay thế`"text"` với cụm từ tìm kiếm bạn mong muốn.

## Bước 6: Chấp nhận bộ hấp thụ cho một trang cụ thể

Chấp nhận bộ hấp thụ cho trang mong muốn của tài liệu:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Thay thế`2` với số trang mong muốn (chỉ mục dựa trên 1).

## Bước 7: Lấy lại các đoạn văn bản đã trích xuất

 Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 8: Lặp qua các đoạn văn bản

Lặp qua các đoạn văn bản đã lấy và truy cập vào các thuộc tính của chúng:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Sửa đổi mã trong vòng lặp để thực hiện các hành động tiếp theo trên mỗi phân đoạn văn bản nếu cần.

### Mã nguồn mẫu cho Trang phân đoạn văn bản tìm kiếm sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các đoạn
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm các đoạn văn bản cụ thể trên một trang của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ việc tải tài liệu đến việc truy cập các đoạn văn bản đã trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thực hiện tìm kiếm đoạn văn bản nâng cao trong các tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm đoạn văn bản trong tệp PDF" là gì?

A: Hướng dẫn "Search Text Segments Page In PDF File" cung cấp hướng dẫn toàn diện về cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm các đoạn văn bản cụ thể trên một trang cụ thể của tài liệu PDF. Hướng dẫn này bao gồm quy trình thiết lập dự án, tải tài liệu PDF, tìm kiếm các đoạn văn bản và truy xuất các thuộc tính của chúng bằng mã C#.

#### H: Hướng dẫn này giúp ích như thế nào trong việc tìm kiếm các đoạn văn bản cụ thể trong tài liệu PDF?

A: Hướng dẫn này trình bày quy trình định vị và trích xuất các đoạn văn bản cụ thể trên một trang cụ thể của tài liệu PDF. Bằng cách làm theo các bước và mẫu mã được cung cấp, người dùng có thể tìm kiếm hiệu quả các đoạn văn bản mong muốn và lấy thông tin về các thuộc tính của chúng.

#### H: Cần có những điều kiện tiên quyết nào để làm theo hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt vào dự án của mình bằng NuGet.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn sử dụng các tính năng của thư viện để tìm kiếm và làm việc với các tài liệu PDF.

#### H: Tôi có thể sử dụng hướng dẫn này để tìm kiếm các đoạn văn bản cụ thể trên bất kỳ trang nào của tệp PDF không?

A: Có, hướng dẫn này cung cấp hướng dẫn về cách tìm kiếm các đoạn văn bản cụ thể trên một trang đã chọn của tài liệu PDF. Nó hướng dẫn người dùng thiết lập một dự án, tải PDF và sử dụng thư viện Aspose.PDF để định vị và truy xuất các thuộc tính của các đoạn văn bản mong muốn.

#### H: Làm thế nào để chỉ định văn bản tôi muốn tìm kiếm trong hướng dẫn này?

 A: Để chỉ định văn bản bạn muốn tìm kiếm, hãy tạo một`TextFragmentAbsorber` đối tượng và thiết lập tham số tìm kiếm của nó bằng cách sử dụng`Text` thuộc tính. Thay thế mặc định`"text"` trong mã hướng dẫn với cụm từ tìm kiếm mong muốn của bạn.

#### H: Làm thế nào để lấy lại các thuộc tính của các đoạn văn bản đã trích xuất?

Sau khi chấp nhận`TextFragmentAbsorber` đối với một trang cụ thể của PDF, bạn có thể lấy các đoạn văn bản đã trích xuất bằng cách sử dụng`TextFragments` thuộc tính của đối tượng hấp thụ. Điều này cung cấp quyền truy cập vào bộ sưu tập các đoạn văn bản, mỗi đoạn chứa nhiều phân đoạn văn bản.

#### H: Tôi có thể tùy chỉnh mã để thực hiện các hành động bổ sung trên mỗi phân đoạn văn bản không?

A: Hoàn toàn đúng. Mã mẫu của hướng dẫn cung cấp một vòng lặp để lặp qua các phân đoạn văn bản đã truy xuất. Bạn có thể tùy chỉnh mã trong vòng lặp này để thực hiện các hành động bổ sung trên mỗi phân đoạn văn bản, dựa trên yêu cầu của dự án.

#### H: Làm thế nào để lưu tài liệu PDF đã chỉnh sửa sau khi trích xuất các đoạn văn bản?

A: Hướng dẫn này chủ yếu tập trung vào việc tìm kiếm các phân đoạn văn bản và lấy các thuộc tính của chúng. Nếu bạn có ý định sửa đổi PDF, bạn có thể tham khảo tài liệu Aspose.PDF khác để tìm hiểu cách thao tác và lưu tài liệu dựa trên nhu cầu cụ thể của bạn.