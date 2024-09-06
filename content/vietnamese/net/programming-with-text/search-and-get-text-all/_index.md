---
title: Tìm kiếm và lấy tất cả văn bản
linktitle: Tìm kiếm và lấy tất cả văn bản
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm và lấy văn bản từ tất cả các trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 420
url: /vi/net/programming-with-text/search-and-get-text-all/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm và lấy văn bản từ tất cả các trang của tài liệu PDF. Mã nguồn C# được cung cấp minh họa quy trình từng bước.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tìm kiếm và trích xuất văn bản

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Thay thế`"text"` với văn bản thực tế mà bạn muốn tìm kiếm.

## Bước 5: Tìm kiếm trên tất cả các trang

Chấp nhận bộ hấp thụ cho tất cả các trang của tài liệu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Bước 6: trích xuất các đoạn văn bản

Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 7: Lặp qua các đoạn văn bản

Lặp qua các đoạn văn bản getd và truy cập các thuộc tính của chúng:

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

### Mã nguồn mẫu cho Tìm kiếm và Lấy tất cả văn bản bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm và lấy văn bản từ tất cả các trang của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ việc tải tài liệu đến truy cập các đoạn văn bản đã trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để phân tích và xử lý nội dung văn bản trong các tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm và lấy toàn bộ văn bản" là gì?

A: Hướng dẫn "Tìm kiếm và lấy tất cả văn bản" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm và trích xuất văn bản từ tất cả các trang của tài liệu PDF. Hướng dẫn cung cấp hướng dẫn từng bước cùng với mã C# mẫu để thực hiện tìm kiếm và truy xuất văn bản.

#### H: Hướng dẫn này giúp ích gì trong việc trích xuất văn bản từ tài liệu PDF?

A: Hướng dẫn này hướng dẫn bạn quy trình trích xuất văn bản từ tất cả các trang của tài liệu PDF. Nó sử dụng thư viện Aspose.PDF để định vị các cụm từ văn bản cụ thể và lấy thông tin liên quan, chẳng hạn như vị trí, thuộc tính phông chữ và màu sắc.

#### H: Cần có những điều kiện tiên quyết nào để thực hiện hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn này, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để tích hợp vào dự án của mình.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn truy cập chức năng của thư viện trong dự án của mình.

#### H: Làm thế nào để tìm kiếm văn bản cụ thể trong tài liệu PDF?

 A: Bạn có thể sử dụng`TextFragmentAbsorber`lớp để tìm các trường hợp của một cụm từ tìm kiếm cụ thể trong tài liệu PDF. Bằng cách tạo một trường hợp của lớp này và chỉ định văn bản mục tiêu, bạn có thể nắm bắt tất cả các lần xuất hiện của văn bản đó.

#### H: Tôi có thể tìm kiếm văn bản trên tất cả các trang của tài liệu PDF không?

 A: Có, hướng dẫn này trình bày cách tìm kiếm văn bản trên tất cả các trang của tài liệu PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Phương pháp này được sử dụng để chấp nhận bộ hấp thụ cho tất cả các trang, cho phép bạn tìm kiếm văn bản mong muốn trên mọi trang.

#### H: Làm thế nào để truy cập vào các đoạn văn bản đã trích xuất?

 A: Sau khi tìm kiếm văn bản, bạn có thể truy cập các đoạn văn bản đã trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` đối tượng. Thuộc tính này cung cấp quyền truy cập vào một bộ sưu tập`TextFragment` các đối tượng chứa văn bản được trích xuất và thông tin liên quan.

#### H: Tôi có thể lấy thông tin gì từ các đoạn văn bản được trích xuất?

A: Bạn có thể lấy nhiều chi tiết khác nhau từ các đoạn văn bản đã trích xuất, chẳng hạn như nội dung văn bản thực tế, vị trí (tọa độ X và Y), thông tin phông chữ (tên, kích thước, màu sắc, v.v.) và nhiều thông tin khác. Mã mẫu của hướng dẫn này trình bày cách truy cập và in các chi tiết này.

#### H: Tôi có thể thực hiện thêm các thao tác nào khác trên các đoạn văn bản đã trích xuất không?

A: Chắc chắn rồi. Sau khi bạn đã trích xuất được các đoạn văn bản, bạn có thể sửa đổi mã trong vòng lặp để thực hiện các hành động tùy chỉnh trên từng đoạn. Điều này có thể bao gồm lưu văn bản đã trích xuất, phân tích các mẫu văn bản hoặc áp dụng các thay đổi định dạng.