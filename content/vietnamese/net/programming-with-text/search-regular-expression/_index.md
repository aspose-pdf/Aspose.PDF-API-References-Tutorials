---
title: Tìm kiếm biểu thức chính quy trong tệp PDF
linktitle: Tìm kiếm biểu thức chính quy trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tìm kiếm và truy xuất văn bản bằng cách sử dụng cụm từ thông dụng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 440
url: /vi/net/programming-with-text/search-regular-expression/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm và truy xuất văn bản khớp với biểu thức chính quy trong tệp PDF. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tìm kiếm bằng biểu thức chính quy

 Tạo một`TextFragmentAbsorber` đối tượng và đặt mẫu biểu thức chính quy để tìm tất cả các cụm từ khớp với mẫu:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Như 1999-2000
```

 Thay thế`"\\d{4}-\\d{4}"` với mẫu biểu thức chính quy mong muốn của bạn.

## Bước 5: Đặt tùy chọn tìm kiếm văn bản

 Tạo một`TextSearchOptions` đối tượng và đặt nó vào`TextSearchOptions` tài sản của`TextFragmentAbsorber` đối tượng để cho phép sử dụng biểu thức chính quy:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Bước 6: Tìm kiếm trên tất cả các trang

Chấp nhận phần hấp thụ cho tất cả các trang của tài liệu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Bước 7: Truy xuất các đoạn văn bản đã trích xuất

Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 8: Lặp qua các đoạn văn bản

Lặp lại các đoạn văn bản được truy xuất và truy cập các thuộc tính của chúng:

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

### Mã nguồn mẫu cho Tìm kiếm biểu thức chính quy bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Như 1999-2000
// Đặt tùy chọn tìm kiếm văn bản để chỉ định cách sử dụng biểu thức chính quy
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Chúc mừng! Bạn đã học thành công cách tìm kiếm và truy xuất văn bản khớp với biểu thức chính quy trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ tải tài liệu đến truy cập các đoạn văn bản được trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thực hiện tìm kiếm văn bản nâng cao trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Tìm kiếm biểu thức chính quy trong tệp PDF" là gì?

Đáp: Hướng dẫn "Tìm kiếm biểu thức chính quy trong tệp PDF" nhằm mục đích giới thiệu cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm và trích xuất văn bản khớp với mẫu biểu thức chính quy được chỉ định trong tệp PDF. Hướng dẫn này cung cấp hướng dẫn toàn diện và mã C# mẫu để minh họa quy trình.

#### Hỏi: Hướng dẫn này giúp ích như thế nào trong việc tìm kiếm văn bản bằng cách sử dụng các biểu thức thông thường trong tài liệu PDF?

Đáp: Hướng dẫn này cung cấp cách tiếp cận từng bước để sử dụng thư viện Aspose.PDF để tiến hành tìm kiếm văn bản trong tài liệu PDF dựa trên mẫu biểu thức chính quy. Nó trình bày chi tiết cách thiết lập dự án, tải tài liệu PDF, xác định mẫu biểu thức chính quy và truy xuất các đoạn văn bản phù hợp.

#### Hỏi: Điều kiện tiên quyết để làm theo hướng dẫn này là gì?

Đáp: Trước khi bắt đầu hướng dẫn này, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc sử dụng NuGet để tích hợp nó vào dự án của bạn.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn tận dụng khả năng của thư viện trong dự án của mình.

#### Câu hỏi: Tôi có thể sử dụng biểu thức chính quy để tìm kiếm văn bản trong tài liệu PDF không?

 Đáp: Có, hướng dẫn này trình bày cách sử dụng biểu thức chính quy để tìm kiếm và trích xuất văn bản từ tài liệu PDF. Nó bao gồm việc sử dụng các`TextFragmentAbsorber` lớp và chỉ định mẫu biểu thức chính quy để tìm các cụm từ khớp với mẫu được cung cấp.

#### Câu hỏi: Làm cách nào để xác định mẫu biểu thức chính quy cho tìm kiếm văn bản?

 Đáp: Để xác định mẫu biểu thức chính quy cho tìm kiếm văn bản, hãy tạo một`TextFragmentAbsorber` đối tượng và thiết lập mẫu của nó bằng cách sử dụng`Text` tham số. Thay thế mẫu mặc định`"\\d{4}-\\d{4}"` trong mã của hướng dẫn bằng mẫu biểu thức chính quy mà bạn mong muốn.

#### Câu hỏi: Làm cách nào tôi có thể bật tính năng sử dụng biểu thức chính quy để tìm kiếm văn bản?

 Đáp: Việc sử dụng biểu thức chính quy được kích hoạt bằng cách tạo một`TextSearchOptions` đối tượng và đặt giá trị của nó thành`true` . Gán đối tượng này vào`TextSearchOptions` tài sản của`TextFragmentAbsorber` ví dụ. Điều này đảm bảo rằng mẫu biểu thức chính quy được áp dụng trong quá trình tìm kiếm văn bản.

#### Câu hỏi: Tôi có thể truy xuất các đoạn văn bản khớp với mẫu biểu thức chính quy không?

 Đ: Chắc chắn rồi. Sau khi áp dụng tìm kiếm biểu thức chính quy trên tài liệu PDF, bạn có thể truy xuất các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật. Các đoạn văn bản này chứa các đoạn văn bản khớp với mẫu biểu thức chính quy đã chỉ định.

#### Câu hỏi: Tôi có thể truy cập những gì từ các đoạn văn bản được truy xuất?

Trả lời: Từ các đoạn văn bản được truy xuất, bạn có thể truy cập các thuộc tính khác nhau như nội dung văn bản trùng khớp, vị trí (tọa độ X và Y), thông tin phông chữ (tên, kích thước, màu sắc), v.v. Mã mẫu trong vòng lặp của hướng dẫn này minh họa cách truy cập và hiển thị các thuộc tính này.

#### Câu hỏi: Làm cách nào tôi có thể tùy chỉnh các thao tác trên các đoạn văn bản được trích xuất?

Đáp: Sau khi đã trích xuất các đoạn văn bản, bạn có thể tùy chỉnh mã trong vòng lặp để thực hiện các hành động bổ sung trên từng đoạn văn bản. Điều này có thể bao gồm lưu văn bản được trích xuất, phân tích mẫu hoặc thực hiện các thay đổi định dạng dựa trên yêu cầu của bạn.