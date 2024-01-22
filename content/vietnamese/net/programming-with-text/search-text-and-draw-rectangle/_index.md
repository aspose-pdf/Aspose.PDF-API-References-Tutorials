---
title: Tìm kiếm văn bản và vẽ hình chữ nhật
linktitle: Tìm kiếm văn bản và vẽ hình chữ nhật
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tìm kiếm văn bản trong PDF, vẽ hình chữ nhật xung quanh văn bản tìm thấy và lưu tài liệu đã sửa đổi bằng Aspose.PDF cho .NET.
type: docs
weight: 460
url: /vi/net/programming-with-text/search-text-and-draw-rectangle/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm văn bản cụ thể trong tài liệu PDF, vẽ hình chữ nhật xung quanh văn bản tìm thấy và lưu tài liệu đã sửa đổi. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Thay thế`"SearchAndGetTextFromAll.pdf"` bằng tên thật của tệp PDF của bạn.

## Bước 5: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các phiên bản của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Thay thế`@"[\S]+"` với mẫu biểu thức chính quy mong muốn của bạn.

## Bước 6: Kích hoạt tìm kiếm biểu thức chính quy

 Bật tìm kiếm biểu thức chính quy bằng cách đặt`TextSearchOptions` Tính chất của chất hấp thụ:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Bước 7: Tìm kiếm trên tất cả các trang

Chấp nhận phần hấp thụ cho tất cả các trang của tài liệu:

```csharp
document.Pages.Accept(textAbsorber);
```

## Bước 8: Vẽ hình chữ nhật xung quanh văn bản tìm thấy

 Tạo một`PdfContentEditor` đối tượng và lặp qua các đoạn văn bản được truy xuất, vẽ một hình chữ nhật xung quanh mỗi đoạn văn bản:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Bước 9: Lưu tài liệu đã sửa đổi

Lưu tài liệu đã sửa đổi:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Đảm bảo thay thế`"SearchTextAndDrawRectangle_out.pdf"` với tên tệp đầu ra mong muốn.

### Mã nguồn mẫu cho Tìm kiếm văn bản và vẽ hình chữ nhật bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách tìm kiếm văn bản cụ thể trong tài liệu PDF, vẽ hình chữ nhật xung quanh văn bản tìm thấy và lưu tài liệu đã sửa đổi bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến thực hiện các hành động cần thiết. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thao tác văn bản và vẽ hình chữ nhật trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của bài hướng dẫn "Tìm kiếm văn bản và vẽ hình chữ nhật" là gì?

Trả lời: Hướng dẫn "Tìm kiếm văn bản và vẽ hình chữ nhật" nhằm mục đích hướng dẫn người dùng trong quá trình sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm văn bản cụ thể trong tài liệu PDF, vẽ hình chữ nhật xung quanh các đoạn văn bản tìm thấy và lưu phần đã sửa đổi tài liệu. Hướng dẫn này cung cấp hướng dẫn chi tiết và mẫu mã C# để minh họa từng bước của quy trình.

#### Hỏi: Hướng dẫn này giúp vẽ hình chữ nhật xung quanh văn bản cụ thể trong tài liệu PDF như thế nào?

Đáp: Hướng dẫn này cung cấp hướng dẫn toàn diện về cách định vị và vẽ hình chữ nhật xung quanh các đoạn văn bản cụ thể trong tài liệu PDF. Nó trình bày quá trình thiết lập dự án, tải tài liệu PDF, cho phép tìm kiếm biểu thức chính quy, vẽ hình chữ nhật xung quanh các đoạn văn bản tìm thấy và lưu tệp PDF đã sửa đổi.

#### Câu hỏi: Cần có những điều kiện tiên quyết nào để thực hiện theo hướng dẫn này?

Đáp: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc cài đặt nó trong dự án của bạn bằng NuGet.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn. Sau đó, thêm tham chiếu đến thư viện Aspose.PDF for .NET vào dự án của bạn. Điều này sẽ cho phép bạn sử dụng chức năng của thư viện để thao tác với các tài liệu PDF.

#### Hỏi: Tôi có thể vẽ hình chữ nhật xung quanh văn bản cụ thể bằng hướng dẫn này không?

Đáp: Có, hướng dẫn này tập trung vào việc vẽ các hình chữ nhật xung quanh các đoạn văn bản cụ thể trong tài liệu PDF. Nó trình bày cách định vị văn bản mong muốn bằng cách sử dụng các biểu thức thông thường, tạo hình chữ nhật xung quanh các đoạn văn bản đã xác định và lưu tệp PDF đã sửa đổi.

#### Hỏi: Làm cách nào tôi có thể chỉ định văn bản tôi muốn tìm kiếm và vẽ các hình chữ nhật xung quanh?

 Đáp: Để chỉ định văn bản bạn muốn tìm kiếm và vẽ các hình chữ nhật xung quanh, hãy tạo một`TextFragmentAbsorber` đối tượng và thiết lập mẫu của nó bằng cách sử dụng`Text` tham số. Thay thế mẫu mặc định`@"[\S]+"` trong mã của hướng dẫn bằng mẫu biểu thức chính quy mà bạn mong muốn.

#### Câu hỏi: Làm cách nào để bật tính năng tìm kiếm biểu thức chính quy cho văn bản?

 Đáp: Tìm kiếm biểu thức chính quy được kích hoạt bằng cách tạo một`TextSearchOptions` đối tượng và đặt giá trị của nó thành`true` . Gán đối tượng này vào`TextSearchOptions` tài sản của`TextFragmentAbsorber` ví dụ. Điều này đảm bảo rằng mẫu biểu thức chính quy được sử dụng trong quá trình tìm kiếm văn bản.

#### Hỏi: Làm cách nào để vẽ hình chữ nhật xung quanh văn bản tìm thấy?

 A: Sau khi xác định các đoạn văn bản bằng cách sử dụng`TextFragmentAbsorber` , hướng dẫn cung cấp một vòng lặp để lặp qua các phân đoạn này. Đối với mỗi đoạn văn bản, hướng dẫn này trình bày cách tạo một hình chữ nhật xung quanh nó bằng cách sử dụng`DrawBox` phương thức và chỉ định diện mạo của hình chữ nhật.

#### Hỏi: Các bước để lưu tệp PDF đã sửa đổi có hình chữ nhật được vẽ là gì?

Đáp: Sau khi vẽ các hình chữ nhật xung quanh các đoạn văn bản mong muốn, hãy sử dụng`Document` lớp học`Save` phương pháp lưu tài liệu đã sửa đổi. Mã mẫu của hướng dẫn này giới thiệu cách lưu tệp PDF đã chỉnh sửa và hiển thị thông báo thành công.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của các hình chữ nhật được vẽ không?

 Đáp: Có, bạn có thể tùy chỉnh hình thức của các hình chữ nhật đã vẽ. Trong mã mẫu của hướng dẫn,`DrawBox` phương pháp được sử dụng để tạo hình chữ nhật. Bạn có thể sửa đổi các thuộc tính như màu sắc, kiểu dáng và độ dày để tùy chỉnh hình thức của hình chữ nhật đã vẽ.