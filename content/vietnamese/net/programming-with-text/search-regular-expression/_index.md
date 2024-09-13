---
title: Tìm kiếm biểu thức chính quy trong tệp PDF
linktitle: Tìm kiếm biểu thức chính quy trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm và truy xuất văn bản bằng biểu thức chính quy trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 440
url: /vi/net/programming-with-text/search-regular-expression/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm và truy xuất văn bản khớp với biểu thức chính quy trong tệp PDF. Mã nguồn C# được cung cấp sẽ trình bày từng bước của quy trình.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tìm kiếm bằng biểu thức chính quy

 Tạo một`TextFragmentAbsorber` đối tượng và thiết lập mẫu biểu thức chính quy để tìm tất cả các cụm từ khớp với mẫu:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Giống như 1999-2000
```

 Thay thế`"\\d{4}-\\d{4}"` với mẫu biểu thức chính quy bạn mong muốn.

## Bước 5: Thiết lập tùy chọn tìm kiếm văn bản

 Tạo một`TextSearchOptions` đối tượng và đặt nó vào`TextSearchOptions` tài sản của`TextFragmentAbsorber` đối tượng để cho phép sử dụng biểu thức chính quy:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Bước 6: Tìm kiếm trên tất cả các trang

Chấp nhận bộ hấp thụ cho tất cả các trang của tài liệu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Bước 7: Lấy lại các đoạn văn bản đã trích xuất

 Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 8: Lặp qua các đoạn văn bản

Lặp qua các đoạn văn bản đã lấy được và truy cập vào các thuộc tính của chúng:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Bạn có thể sửa đổi mã trong vòng lặp để thực hiện các hành động tiếp theo trên từng đoạn văn bản.

### Mã nguồn mẫu cho Search Regular Expression sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Giống như 1999-2000
// Đặt tùy chọn tìm kiếm văn bản để chỉ định cách sử dụng biểu thức chính quy
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các đoạn
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm và truy xuất văn bản khớp với biểu thức chính quy trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ tải tài liệu đến truy cập các đoạn văn bản đã trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thực hiện tìm kiếm văn bản nâng cao trong các tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm biểu thức chính quy trong tệp PDF" là gì?

A: Hướng dẫn "Tìm kiếm biểu thức chính quy trong tệp PDF" nhằm mục đích giới thiệu cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm và trích xuất văn bản khớp với mẫu biểu thức chính quy được chỉ định trong tệp PDF. Hướng dẫn cung cấp hướng dẫn toàn diện và mã C# mẫu để chứng minh quy trình.

#### H: Hướng dẫn này giúp ích như thế nào trong việc tìm kiếm văn bản bằng biểu thức chính quy trong tài liệu PDF?

A: Hướng dẫn này cung cấp cách tiếp cận từng bước để sử dụng thư viện Aspose.PDF để thực hiện tìm kiếm văn bản trong tài liệu PDF dựa trên mẫu biểu thức chính quy. Hướng dẫn này trình bày chi tiết cách thiết lập dự án, tải tài liệu PDF, xác định mẫu biểu thức chính quy và truy xuất các đoạn văn bản khớp.

#### H: Cần có những điều kiện tiên quyết nào để thực hiện hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn này, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để tích hợp vào dự án của mình.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn tận dụng các khả năng của thư viện trong dự án của mình.

#### H: Tôi có thể sử dụng biểu thức chính quy để tìm kiếm văn bản trong tài liệu PDF không?

 A: Vâng, hướng dẫn này trình bày cách sử dụng biểu thức chính quy để tìm kiếm và trích xuất văn bản từ tài liệu PDF. Nó bao gồm việc sử dụng`TextFragmentAbsorber` lớp và chỉ định một mẫu biểu thức chính quy để tìm cụm từ khớp với mẫu được cung cấp.

#### H: Làm thế nào để xác định mẫu biểu thức chính quy cho tìm kiếm văn bản?

 A: Để xác định mẫu biểu thức chính quy cho tìm kiếm văn bản, hãy tạo một`TextFragmentAbsorber` đối tượng và thiết lập mẫu của nó bằng cách sử dụng`Text` tham số. Thay thế mẫu mặc định`"\\d{4}-\\d{4}"` trong mã hướng dẫn với mẫu biểu thức chính quy mong muốn của bạn.

#### H: Làm thế nào tôi có thể bật tính năng sử dụng biểu thức chính quy để tìm kiếm văn bản?

 A: Việc sử dụng biểu thức chính quy được kích hoạt bằng cách tạo một`TextSearchOptions` đối tượng và thiết lập giá trị của nó thành`true` . Gán đối tượng này cho`TextSearchOptions` tài sản của`TextFragmentAbsorber` Ví dụ. Điều này đảm bảo rằng mẫu biểu thức chính quy được áp dụng trong quá trình tìm kiếm văn bản.

#### H: Tôi có thể lấy các đoạn văn bản khớp với mẫu biểu thức chính quy không?

 A: Hoàn toàn đúng. Sau khi áp dụng tìm kiếm biểu thức chính quy trên tài liệu PDF, bạn có thể lấy lại các đoạn văn bản đã trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` đối tượng. Các đoạn văn bản này chứa các phân đoạn văn bản khớp với mẫu biểu thức chính quy đã chỉ định.

#### H: Tôi có thể truy cập những gì từ các đoạn văn bản đã lấy?

A: Từ các đoạn văn bản đã lấy, bạn có thể truy cập nhiều thuộc tính khác nhau như nội dung văn bản khớp, vị trí (tọa độ X và Y), thông tin phông chữ (tên, kích thước, màu sắc) và nhiều hơn nữa. Mã mẫu trong vòng lặp của hướng dẫn trình bày cách truy cập và hiển thị các thuộc tính này.

#### H: Làm thế nào tôi có thể tùy chỉnh các hành động trên các đoạn văn bản đã trích xuất?

A: Sau khi bạn đã trích xuất được các đoạn văn bản, bạn có thể tùy chỉnh mã trong vòng lặp để thực hiện các hành động bổ sung trên mỗi đoạn văn bản. Điều này có thể bao gồm lưu văn bản đã trích xuất, phân tích các mẫu hoặc triển khai các thay đổi định dạng dựa trên yêu cầu của bạn.