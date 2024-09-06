---
title: Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn
linktitle: Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 400
url: /vi/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để xoay văn bản bằng đoạn văn bản và đoạn văn. Mã nguồn C# được cung cấp minh họa quy trình từng bước.

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

## Bước 3: Tạo tài liệu PDF

 Khởi tạo`Document` đối tượng để tạo một tài liệu PDF mới:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Thêm trang

 Lấy một trang cụ thể từ tài liệu bằng cách sử dụng`Pages.Add()` phương pháp:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Bước 5: Tạo các đoạn văn bản

 Tạo nhiều`TextFragment` đối tượng, thiết lập văn bản và thuộc tính của chúng, và chỉ định góc quay:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Điều chỉnh văn bản, góc xoay và các thuộc tính khác theo ý muốn.

## Bước 6: Thêm các đoạn văn bản vào trang

 Thêm các đoạn văn bản đã tạo vào trang bằng cách thêm chúng vào`Paragraphs` bộ sưu tập:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Bước 7: Lưu tài liệu PDF

 Lưu tài liệu PDF đã sửa đổi vào một tệp bằng cách sử dụng`Save` phương pháp:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Hãy chắc chắn thay thế`"TextFragmentTests_Rotated3_out.pdf"` với tên tập tin đầu ra mong muốn.

### Mã nguồn mẫu cho Xoay văn bản bằng đoạn văn bản và đoạn văn sử dụng Aspose.PDF cho .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng tài liệu
Document pdfDocument = new Document();
// Lấy trang cụ thể
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Tạo đoạn văn bản
TextFragment textFragment1 = new TextFragment("main text");
// Đặt thuộc tính văn bản
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Tạo đoạn văn bản
TextFragment textFragment2 = new TextFragment("rotated text");
// Đặt thuộc tính văn bản
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Đặt vòng quay
textFragment2.TextState.Rotation = 315;
// Tạo đoạn văn bản
TextFragment textFragment3 = new TextFragment("rotated text");
// Đặt thuộc tính văn bản
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Đặt vòng quay
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Lưu tài liệu
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách xoay văn bản bằng các đoạn văn bản và đoạn văn trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ việc tạo tài liệu đến lưu phiên bản đã sửa đổi. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thao tác xoay văn bản trong các tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Xoay văn bản bằng đoạn văn và đoạn văn" là gì?

A: Hướng dẫn "Xoay văn bản bằng đoạn văn bản và đoạn văn" hướng dẫn bạn quy trình sử dụng thư viện Aspose.PDF cho .NET để xoay văn bản bằng cả đoạn văn bản và đoạn văn trong tài liệu PDF. Hướng dẫn cung cấp hướng dẫn từng bước và mã mẫu để đạt được chức năng này.

#### H: Bài hướng dẫn này khác với các bài hướng dẫn xoay văn bản trước như thế nào?

A: Hướng dẫn này kết hợp việc sử dụng các đoạn văn bản và đoạn văn để đạt được mục tiêu xoay văn bản trong tài liệu PDF. Nó trình bày cách xoay từng đoạn văn bản riêng lẻ và sau đó thêm chúng vào trang.`Paragraphs` bộ sưu tập để đạt được hiệu ứng xoay văn bản toàn diện hơn.

#### H: Lợi ích của việc sử dụng đoạn văn bản và đoạn văn để xoay văn bản là gì?

A: Sử dụng các đoạn văn bản và đoạn văn cùng nhau cho phép xoay văn bản linh hoạt hơn. Các đoạn văn bản cho phép xoay và định dạng riêng lẻ, trong khi các đoạn văn cung cấp cấu trúc để sắp xếp và định vị các đoạn văn bản trong một trang.

#### H: Tôi có thể áp dụng các góc xoay khác nhau cho các đoạn văn bản khác nhau trong cùng một đoạn văn không?

 A: Có, bạn có thể áp dụng các góc quay khác nhau cho các`TextFragment` các đối tượng trong cùng một đoạn văn. Mỗi đoạn văn bản có thể có góc quay riêng được chỉ định bằng cách sử dụng`TextState.Rotation` tài sản.

#### H: Có thể tạo được hiệu ứng xoay văn bản phức tạp bằng phương pháp này không?

A: Có, bằng cách kết hợp các đoạn văn bản với nhiều góc xoay khác nhau và sắp xếp chúng trong các đoạn văn, bạn có thể tạo ra các hiệu ứng xoay văn bản phức tạp và tùy chỉnh, giúp tăng tính hấp dẫn trực quan cho tài liệu PDF của bạn.

#### H: Các bước nào liên quan đến việc xoay văn bản bằng cách sử dụng các đoạn văn bản và đoạn văn?

A: Các bước bao gồm:

1. Thiết lập dự án bằng cách tạo một dự án C# mới và thêm tham chiếu đến thư viện Aspose.PDF cho .NET.
2. Tạo tài liệu PDF và thêm trang.
3. Tạo các đoạn văn bản, thiết lập thuộc tính của chúng và chỉ định góc xoay.
4.  Thêm các đoạn văn bản vào trang bằng cách sử dụng`Paragraphs` bộ sưu tập.
5. Lưu tài liệu PDF đã chỉnh sửa.

#### H: Tôi có thể áp dụng xoay cho toàn bộ đoạn văn không?

 A: Có, bạn có thể áp dụng xoay cho toàn bộ đoạn văn bằng cách thiết lập`TextState.Rotation` thuộc tính của chính đoạn văn đó. Điều này sẽ xoay tất cả các đoạn văn bản trong đoạn văn đó.