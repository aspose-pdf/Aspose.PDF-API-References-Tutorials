---
title: Tìm kiếm và lấy trang văn bản trong tệp PDF
linktitle: Tìm kiếm và lấy trang văn bản trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm và lấy văn bản từ một trang cụ thể trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 430
url: /vi/net/programming-with-text/search-and-get-text-page/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm và lấy văn bản từ một trang cụ thể trong tệp PDF. Mã nguồn C# được cung cấp sẽ trình bày từng bước của quy trình.

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

## Bước 3: Tải tài liệu PDF

 Đặt đường dẫn đến thư mục tài liệu PDF của bạn và tải tài liệu bằng cách sử dụng`Document` lớp học:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tìm kiếm và trích xuất văn bản từ một trang

 Tạo một`TextFragmentAbsorber`đối tượng để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào trên một trang cụ thể:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Thay thế`"Figure"` với văn bản thực tế mà bạn muốn tìm kiếm.

## Bước 5: Tìm kiếm trên một trang cụ thể

Chấp nhận bộ hấp thụ cho một trang cụ thể của tài liệu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Bước 6: trích xuất các đoạn văn bản

Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 7: Lặp qua các đoạn văn bản và phân đoạn

Lặp qua các đoạn văn bản getd và các phân đoạn của chúng, rồi truy cập vào các thuộc tính của chúng:

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

Bạn có thể sửa đổi mã trong vòng lặp để thực hiện các hành động tiếp theo trên mỗi phân đoạn văn bản.

### Mã nguồn mẫu cho Trang tìm kiếm và lấy văn bản sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các đoạn
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm và lấy văn bản từ một trang cụ thể của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ việc tải tài liệu đến truy cập các đoạn văn bản đã trích xuất. Bây giờ bạn có thể kết hợp

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm và lấy trang văn bản" là gì?

A: Hướng dẫn "Tìm kiếm và lấy trang văn bản" được thiết kế để minh họa cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm và lấy văn bản từ một trang cụ thể trong tệp PDF. Hướng dẫn cung cấp hướng dẫn chi tiết và mã C# mẫu để chứng minh quy trình.

#### H: Hướng dẫn này giúp ích gì trong việc trích xuất văn bản từ một trang cụ thể trong tài liệu PDF?

A: Hướng dẫn này hướng dẫn bạn quy trình trích xuất văn bản từ một trang cụ thể của tài liệu PDF bằng thư viện Aspose.PDF. Hướng dẫn phác thảo các bước cần thiết và cung cấp mã C# để tìm kiếm cụm từ văn bản đã chỉ định trên trang đã chọn và truy xuất các phân đoạn văn bản liên quan.

#### H: Cần có những điều kiện tiên quyết nào để thực hiện hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn này, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để tích hợp vào dự án của mình.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn sử dụng các khả năng của thư viện trong dự án của mình.

#### H: Tôi có thể tìm kiếm văn bản trên một trang cụ thể của tài liệu PDF không?

A: Vâng, hướng dẫn này trình bày cách tìm kiếm văn bản trên một trang cụ thể của tài liệu PDF. Nó bao gồm việc sử dụng`TextFragmentAbsorber` lớp để xác định vị trí các trường hợp của cụm từ văn bản cụ thể trên trang đã chọn.

#### H: Làm thế nào để truy cập các đoạn văn bản được trích xuất từ một trang cụ thể?

 A: Sau khi tìm kiếm văn bản trên trang được chỉ định, bạn có thể truy cập các đoạn văn bản đã trích xuất bằng cách sử dụng`TextSegments` tài sản của`TextFragment` đối tượng. Thuộc tính này cung cấp quyền truy cập vào một bộ sưu tập`TextSegment` các đối tượng chứa văn bản được trích xuất và thông tin liên quan.

#### H: Tôi có thể lấy thông tin gì từ các đoạn văn bản được trích xuất?

A: Bạn có thể lấy nhiều chi tiết khác nhau từ các đoạn văn bản đã trích xuất, bao gồm nội dung văn bản, vị trí (tọa độ X và Y), thông tin phông chữ (tên, kích thước, màu sắc, v.v.) và nhiều thông tin khác. Mã mẫu của hướng dẫn này trình bày cách truy cập và in các chi tiết này cho từng đoạn văn bản.

#### H: Tôi có thể thực hiện các hành động tùy chỉnh trên các đoạn văn bản đã trích xuất không?

A: Chắc chắn rồi. Khi bạn đã trích xuất được các đoạn văn bản, bạn có thể tùy chỉnh mã trong vòng lặp để thực hiện các hành động bổ sung trên mỗi đoạn. Điều này có thể bao gồm lưu văn bản đã trích xuất, phân tích các mẫu văn bản hoặc áp dụng các thay đổi định dạng.