---
title: Tìm kiếm văn bản và vẽ hình chữ nhật
linktitle: Tìm kiếm văn bản và vẽ hình chữ nhật
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm văn bản trong PDF, vẽ hình chữ nhật xung quanh văn bản tìm thấy và lưu tài liệu đã sửa đổi bằng Aspose.PDF cho .NET.
type: docs
weight: 460
url: /vi/net/programming-with-text/search-text-and-draw-rectangle/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm văn bản cụ thể trong tài liệu PDF, vẽ hình chữ nhật xung quanh văn bản tìm thấy và lưu tài liệu đã sửa đổi. Mã nguồn C# được cung cấp minh họa quy trình từng bước.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Thay thế`"SearchAndGetTextFromAll.pdf"` bằng tên thực của tệp PDF của bạn.

## Bước 5: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Thay thế`@"[\S]+"` với mẫu biểu thức chính quy bạn mong muốn.

## Bước 6: Bật tìm kiếm biểu thức chính quy

 Cho phép tìm kiếm biểu thức chính quy bằng cách thiết lập`TextSearchOptions` Tính chất của chất hấp thụ:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Bước 7: Tìm kiếm trên tất cả các trang

Chấp nhận bộ hấp thụ cho tất cả các trang của tài liệu:

```csharp
document.Pages.Accept(textAbsorber);
```

## Bước 8: Vẽ một hình chữ nhật xung quanh văn bản tìm thấy

 Tạo một`PdfContentEditor` đối tượng và lặp qua các đoạn văn bản đã lấy được, vẽ một hình chữ nhật xung quanh mỗi đoạn văn bản:

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

 Hãy chắc chắn thay thế`"SearchTextAndDrawRectangle_out.pdf"` với tên tập tin đầu ra mong muốn.

### Mã nguồn mẫu cho Tìm kiếm văn bản và vẽ hình chữ nhật bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
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

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm văn bản cụ thể trong tài liệu PDF, vẽ hình chữ nhật xung quanh văn bản tìm thấy và lưu tài liệu đã sửa đổi bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến thực hiện các hành động cần thiết. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thao tác văn bản và vẽ hình chữ nhật trong tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm văn bản và vẽ hình chữ nhật" là gì?

A: Hướng dẫn "Tìm kiếm văn bản và vẽ hình chữ nhật" hướng dẫn người dùng quy trình sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm văn bản cụ thể trong tài liệu PDF, vẽ hình chữ nhật xung quanh các phân đoạn văn bản tìm thấy và lưu tài liệu đã sửa đổi. Hướng dẫn cung cấp hướng dẫn chi tiết và các mẫu mã C# để minh họa từng bước của quy trình.

#### H: Hướng dẫn này giúp ích gì khi vẽ hình chữ nhật xung quanh văn bản cụ thể trong tài liệu PDF?

A: Hướng dẫn này cung cấp hướng dẫn toàn diện về cách định vị và vẽ hình chữ nhật xung quanh các phân đoạn văn bản cụ thể trong tài liệu PDF. Hướng dẫn này trình bày quy trình thiết lập dự án, tải tài liệu PDF, bật tìm kiếm biểu thức chính quy, vẽ hình chữ nhật xung quanh các phân đoạn văn bản tìm thấy và lưu PDF đã sửa đổi.

#### H: Cần có những điều kiện tiên quyết nào để làm theo hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt vào dự án của mình bằng NuGet.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn. Sau đó, thêm tham chiếu đến thư viện Aspose.PDF cho .NET vào dự án của bạn. Điều này sẽ cho phép bạn sử dụng chức năng của thư viện để thao tác với các tài liệu PDF.

#### H: Tôi có thể vẽ hình chữ nhật xung quanh văn bản cụ thể bằng hướng dẫn này không?

A: Có, hướng dẫn tập trung vào việc vẽ các hình chữ nhật xung quanh các phân đoạn văn bản cụ thể trong tài liệu PDF. Nó trình bày cách định vị văn bản mong muốn bằng cách sử dụng biểu thức chính quy, tạo các hình chữ nhật xung quanh các phân đoạn văn bản đã xác định và lưu PDF đã sửa đổi.

#### H: Làm thế nào để tôi có thể chỉ định văn bản tôi muốn tìm kiếm và vẽ hình chữ nhật xung quanh?

 A: Để chỉ định văn bản bạn muốn tìm kiếm và vẽ hình chữ nhật xung quanh, hãy tạo một`TextFragmentAbsorber` đối tượng và thiết lập mẫu của nó bằng cách sử dụng`Text` tham số. Thay thế mẫu mặc định`@"[\S]+"` trong mã hướng dẫn với mẫu biểu thức chính quy mong muốn của bạn.

#### H: Làm thế nào để bật tìm kiếm biểu thức chính quy cho văn bản?

 A: Tìm kiếm biểu thức chính quy được kích hoạt bằng cách tạo một`TextSearchOptions` đối tượng và thiết lập giá trị của nó thành`true` . Gán đối tượng này cho`TextSearchOptions` tài sản của`TextFragmentAbsorber` Ví dụ. Điều này đảm bảo rằng mẫu biểu thức chính quy được sử dụng trong quá trình tìm kiếm văn bản.

#### H: Làm thế nào để vẽ hình chữ nhật xung quanh văn bản tìm thấy?

 A: Sau khi xác định các đoạn văn bản bằng cách sử dụng`TextFragmentAbsorber` , hướng dẫn cung cấp một vòng lặp để lặp qua các phân đoạn này. Đối với mỗi phân đoạn văn bản, hướng dẫn trình bày cách tạo một hình chữ nhật xung quanh nó bằng cách sử dụng`DrawBox` phương pháp và chỉ định hình dạng của hình chữ nhật.

#### H: Các bước để lưu tệp PDF đã chỉnh sửa có hình chữ nhật được vẽ là gì?

A: Sau khi vẽ các hình chữ nhật xung quanh các đoạn văn bản mong muốn, hãy sử dụng`Document` lớp học`Save` phương pháp lưu tài liệu đã chỉnh sửa. Mã mẫu của hướng dẫn trình bày cách lưu PDF đã chỉnh sửa và hiển thị thông báo thành công.

#### H: Tôi có thể tùy chỉnh giao diện của các hình chữ nhật đã vẽ không?

 A: Có, bạn có thể tùy chỉnh giao diện của các hình chữ nhật được vẽ. Trong mã mẫu của hướng dẫn,`DrawBox` phương pháp này được sử dụng để tạo hình chữ nhật. Bạn có thể sửa đổi các thuộc tính như màu sắc, kiểu dáng và độ dày để tùy chỉnh giao diện của hình chữ nhật được vẽ.