---
title: Tìm kiếm và nhận tất cả văn bản
linktitle: Tìm kiếm và nhận tất cả văn bản
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tìm kiếm và nhận văn bản từ tất cả các trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 420
url: /vi/net/programming-with-text/search-and-get-text-all/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm và lấy văn bản từ tất cả các trang của tài liệu PDF. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

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

## Bước 3: Tải tài liệu PDF

 Đặt đường dẫn đến thư mục tài liệu PDF của bạn và tải tài liệu bằng cách sử dụng`Document` lớp học:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tìm kiếm và trích xuất văn bản

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các phiên bản của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Thay thế`"text"` với văn bản thực tế mà bạn muốn tìm kiếm.

## Bước 5: Tìm kiếm trên tất cả các trang

Chấp nhận phần hấp thụ cho tất cả các trang của tài liệu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Bước 6: trích xuất các đoạn văn bản

Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 7: Lặp qua các đoạn văn bản

Lặp lại các đoạn văn bản nhận được và truy cập các thuộc tính của chúng:

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

### Mã nguồn mẫu cho Tìm kiếm và Nhận tất cả văn bản bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các phiên bản của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản được trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các mảnh vỡ
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

Chúc mừng! Bạn đã học thành công cách tìm kiếm và lấy văn bản từ tất cả các trang của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ tải tài liệu đến truy cập các đoạn văn bản được trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để phân tích và xử lý nội dung văn bản trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Tìm kiếm và lấy tất cả văn bản" là gì?

Đáp: Hướng dẫn "Tìm kiếm và lấy tất cả văn bản" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm và trích xuất văn bản từ tất cả các trang của tài liệu PDF. Hướng dẫn này cung cấp hướng dẫn từng bước cùng với mã C# mẫu để thực hiện tìm kiếm và truy xuất văn bản.

#### Hỏi: Hướng dẫn này giúp ích như thế nào trong việc trích xuất văn bản từ tài liệu PDF?

Đáp: Hướng dẫn này hướng dẫn bạn quy trình trích xuất văn bản từ tất cả các trang của tài liệu PDF. Nó sử dụng thư viện Aspose.PDF để định vị các cụm từ văn bản cụ thể và truy xuất thông tin liên quan, chẳng hạn như vị trí, thuộc tính phông chữ và màu sắc.

#### Hỏi: Điều kiện tiên quyết để làm theo hướng dẫn này là gì?

Đáp: Trước khi bắt đầu hướng dẫn này, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc sử dụng NuGet để tích hợp nó vào dự án của bạn.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn truy cập chức năng của thư viện trong dự án của bạn.

#### Hỏi: Làm cách nào để tìm kiếm văn bản cụ thể trong tài liệu PDF?

Đáp: Bạn có thể sử dụng`TextFragmentAbsorber`class để tìm các phiên bản của cụm từ tìm kiếm cụ thể trong tài liệu PDF. Bằng cách tạo một thể hiện của lớp này và chỉ định văn bản đích, bạn có thể nắm bắt được tất cả các lần xuất hiện của văn bản đó.

#### Hỏi: Tôi có thể tìm kiếm văn bản trên tất cả các trang của tài liệu PDF không?

 Đáp: Có, hướng dẫn này trình bày cách tìm kiếm văn bản trên tất cả các trang của tài liệu PDF. Các`pdfDocument.Pages.Accept(textFragmentAbsorber)` được sử dụng để chấp nhận bộ hấp thụ cho tất cả các trang, cho phép bạn tìm kiếm văn bản mong muốn trên mỗi trang.

#### Câu hỏi: Làm cách nào để truy cập các đoạn văn bản được trích xuất?

 Trả lời: Sau khi tìm kiếm văn bản, bạn có thể truy cập các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật. Thuộc tính này cung cấp quyền truy cập vào một bộ sưu tập`TextFragment` các đối tượng chứa văn bản được trích xuất và thông tin liên quan.

#### Hỏi: Tôi có thể lấy thông tin gì từ các đoạn văn bản được trích xuất?

Trả lời: Bạn có thể truy xuất nhiều chi tiết khác nhau từ các đoạn văn bản được trích xuất, chẳng hạn như nội dung văn bản thực tế, vị trí (tọa độ X và Y), thông tin phông chữ (tên, kích thước, màu sắc, v.v.), v.v.. Mã mẫu của hướng dẫn này trình bày cách truy cập và in các chi tiết này.

#### Câu hỏi: Tôi có thể thực hiện thêm thao tác nào trên các đoạn văn bản được trích xuất không?

Đ: Chắc chắn rồi. Sau khi đã trích xuất các đoạn văn bản, bạn có thể sửa đổi mã trong vòng lặp để thực hiện các hành động tùy chỉnh trên từng đoạn. Điều này có thể bao gồm việc lưu văn bản được trích xuất, phân tích các mẫu văn bản hoặc áp dụng các thay đổi về định dạng.