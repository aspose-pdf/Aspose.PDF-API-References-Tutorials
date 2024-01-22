---
title: Tìm kiếm trang phân đoạn văn bản trong tệp PDF
linktitle: Tìm kiếm trang phân đoạn văn bản trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tìm kiếm các đoạn văn bản trên một trang trong tệp PDF và truy xuất thuộc tính của chúng bằng Aspose.PDF cho .NET.
type: docs
weight: 470
url: /vi/net/programming-with-text/search-text-segments-page/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm các đoạn văn bản cụ thể trên một trang của tệp PDF và truy xuất các thuộc tính của chúng. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

## Điều kiện tiên quyết

Trước khi tiếp tục với hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể lấy nó từ trang web Aspose hoặc sử dụng NuGet để cài đặt nó trong dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm các lệnh sử dụng sau vào đầu tệp C# của bạn để nhập các không gian tên được yêu cầu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` Biến đổi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tải tài liệu PDF

 Tải tài liệu PDF bằng cách sử dụng`Document` lớp học:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Thay thế`"SearchTextSegmentsPage.pdf"` bằng tên thật của tệp PDF của bạn.

## Bước 5: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các phiên bản của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Thay thế`"text"` với cụm từ tìm kiếm mong muốn của bạn.

## Bước 6: Chấp nhận phần hấp thụ cho một trang cụ thể

Chấp nhận phần hấp thụ cho trang mong muốn của tài liệu:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Thay thế`2` với số trang mong muốn (chỉ mục dựa trên 1).

## Bước 7: Truy xuất các đoạn văn bản đã trích xuất

 Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 8: Lặp lại các đoạn văn bản

Lặp lại các đoạn văn bản được truy xuất và truy cập các thuộc tính của chúng:

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

Sửa đổi mã trong vòng lặp để thực hiện các hành động tiếp theo trên từng đoạn văn bản nếu cần.

### Mã nguồn mẫu cho Trang phân đoạn văn bản tìm kiếm bằng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các phiên bản của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản được trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các mảnh vỡ
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

Chúc mừng! Bạn đã học thành công cách tìm kiếm các đoạn văn bản cụ thể trên một trang của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ tải tài liệu đến truy cập các đoạn văn bản được trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thực hiện tìm kiếm phân đoạn văn bản nâng cao trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Tìm kiếm trang phân đoạn văn bản trong tệp PDF" là gì?

Đáp: Hướng dẫn "Tìm kiếm trang phân đoạn văn bản trong tệp PDF" cung cấp hướng dẫn toàn diện về cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm các phân đoạn văn bản cụ thể trên một trang cụ thể của tài liệu PDF. Nó bao gồm quá trình thiết lập một dự án, tải tài liệu PDF, tìm kiếm các đoạn văn bản và truy xuất các thuộc tính của chúng bằng mã C#.

#### Hỏi: Hướng dẫn này giúp ích như thế nào trong việc tìm kiếm các đoạn văn bản cụ thể trong tài liệu PDF?

Đáp: Hướng dẫn này trình bày quy trình định vị và trích xuất các đoạn văn bản cụ thể trên một trang cụ thể của tài liệu PDF. Bằng cách làm theo các bước và mẫu mã được cung cấp, người dùng có thể tìm kiếm các đoạn văn bản mong muốn một cách hiệu quả và truy xuất thông tin về thuộc tính của chúng.

#### Câu hỏi: Cần có những điều kiện tiên quyết nào để thực hiện theo hướng dẫn này?

Đáp: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc cài đặt nó trong dự án của bạn bằng NuGet.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn sử dụng các tính năng của thư viện để tìm kiếm và làm việc với các tài liệu PDF.

#### Hỏi: Tôi có thể sử dụng hướng dẫn này để tìm kiếm các đoạn văn bản cụ thể trên bất kỳ trang nào của tệp PDF không?

Đáp: Có, hướng dẫn này cung cấp hướng dẫn về cách tìm kiếm các đoạn văn bản cụ thể trên trang đã chọn của tài liệu PDF. Nó hướng dẫn người dùng thiết lập dự án, tải tệp PDF và sử dụng thư viện Aspose.PDF để định vị và truy xuất các thuộc tính của các đoạn văn bản mong muốn.

#### Hỏi: Làm cách nào để chỉ định văn bản tôi muốn tìm kiếm trong hướng dẫn này?

 Đáp: Để chỉ định văn bản bạn muốn tìm kiếm, hãy tạo một`TextFragmentAbsorber` đối tượng và đặt tham số tìm kiếm của nó bằng cách sử dụng`Text` tài sản. Thay thế mặc định`"text"` trong mã của hướng dẫn với cụm từ tìm kiếm bạn muốn.

#### Câu hỏi: Làm cách nào để truy xuất thuộc tính của các đoạn văn bản được trích xuất?

Sau khi chấp nhận`TextFragmentAbsorber` đối với một trang cụ thể của PDF, bạn có thể truy xuất các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tính chất của vật hấp thụ. Điều này cung cấp quyền truy cập vào một tập hợp các đoạn văn bản, mỗi đoạn chứa nhiều đoạn văn bản.

#### Câu hỏi: Tôi có thể tùy chỉnh mã để thực hiện các hành động bổ sung trên từng đoạn văn bản không?

Đ: Chắc chắn rồi. Mã mẫu của hướng dẫn này cung cấp một vòng lặp để lặp qua các đoạn văn bản được truy xuất. Bạn có thể tùy chỉnh mã trong vòng lặp này để thực hiện các hành động bổ sung trên từng đoạn văn bản, dựa trên yêu cầu dự án của bạn.

#### Hỏi: Làm cách nào để lưu tài liệu PDF đã sửa đổi sau khi trích xuất các đoạn văn bản?

Đáp: Hướng dẫn này chủ yếu tập trung vào việc tìm kiếm các đoạn văn bản và truy xuất các thuộc tính của chúng. Nếu bạn có ý định sửa đổi tệp PDF, bạn có thể tham khảo tài liệu Aspose.PDF khác để tìm hiểu cách thao tác và lưu tài liệu dựa trên nhu cầu cụ thể của bạn.