---
title: Xoay văn bản bằng cách sử dụng đoạn văn bản trong tệp PDF
linktitle: Xoay văn bản bằng cách sử dụng đoạn văn bản trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách xoay văn bản bằng các đoạn văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 390
url: /vi/net/programming-with-text/rotate-text-using-text-fragment/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để xoay văn bản bằng cách sử dụng các đoạn văn bản trong tệp PDF. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Bước 3: Tạo tài liệu PDF

 Khởi tạo`Document` đối tượng để tạo một tài liệu PDF mới:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Thêm trang

 Nhận một trang cụ thể từ tài liệu bằng cách sử dụng`Pages.Add()` phương pháp:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Bước 5: Tạo đoạn văn bản

 Tạo nhiều`TextFragment` các đối tượng, đặt văn bản và thuộc tính của chúng cũng như chỉ định vị trí của chúng trên trang:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Điều chỉnh văn bản, vị trí và các thuộc tính khác theo ý muốn.

## Bước 6: Tạo TextBuilder và nối các đoạn văn bản

 Tạo một`TextBuilder` đối tượng sử dụng`pdfPage` và nối các đoạn văn bản vào trang PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Bước 7: Lưu tài liệu PDF

 Lưu tài liệu PDF đã sửa đổi vào một tệp bằng cách sử dụng`Save` phương pháp:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Đảm bảo thay thế`"TextFragmentTests_Rotated1_out.pdf"` với tên tệp đầu ra mong muốn.

### Mã nguồn mẫu cho Xoay văn bản bằng đoạn văn bản bằng Aspose.PDF cho .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng tài liệu
Document pdfDocument = new Document();
// Nhận trang cụ thể
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Tạo đoạn văn bản
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Đặt thuộc tính văn bản
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Tạo đoạn văn bản xoay
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Đặt thuộc tính văn bản
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Tạo đoạn văn bản xoay
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Đặt thuộc tính văn bản
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// tạo đối tượng TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Nối đoạn văn bản vào trang PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Lưu tài liệu
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách xoay văn bản bằng cách sử dụng các đoạn văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ tạo tài liệu đến lưu phiên bản đã sửa đổi. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thao tác xoay văn bản trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Xoay văn bản bằng đoạn văn bản" là gì?

Đáp: Hướng dẫn "Xoay văn bản bằng cách sử dụng đoạn văn bản" nhằm mục đích hướng dẫn bạn qua quá trình sử dụng thư viện Aspose.PDF cho .NET để xoay văn bản bằng cách sử dụng các đoạn văn bản trong tài liệu PDF. Hướng dẫn này cung cấp hướng dẫn từng bước và mã mẫu để đạt được chức năng này.

#### Hỏi: "xoay văn bản bằng cách sử dụng các đoạn văn bản" nghĩa là gì?

Trả lời: Xoay văn bản bằng cách sử dụng các đoạn văn bản đề cập đến khả năng áp dụng xoay cho các đoạn văn bản riêng lẻ trong tài liệu PDF bằng thư viện Aspose.PDF. Kỹ thuật này cho phép bạn kiểm soát hướng của văn bản ở các góc hoặc vị trí khác nhau trong nội dung PDF.

#### Hỏi: Tại sao tôi muốn xoay các đoạn văn bản trong tài liệu PDF?

Đáp: Xoay các đoạn văn bản trong tài liệu PDF có thể hữu ích cho nhiều mục đích khác nhau, chẳng hạn như nhấn mạnh nội dung cụ thể, tạo ra các thiết kế nghệ thuật hoặc cải thiện bố cục và khả năng đọc.

#### Câu hỏi: Làm cách nào để thiết lập dự án cho phần hướng dẫn?

A: Để thiết lập dự án:

1. Tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.
3. Thêm các lệnh sử dụng cần thiết vào tệp C# của bạn.

#### Hỏi: Làm cách nào tôi có thể tạo một tài liệu PDF mới?

 Đáp: Để tạo một tài liệu PDF mới, hãy khởi tạo một`Document`đối tượng từ thư viện Aspose.PDF. Bạn có thể sử dụng đối tượng này để thêm trang và nội dung vào PDF.

#### Câu hỏi: Làm cách nào để xoay các đoạn văn bản bằng cách sử dụng các đoạn văn bản?

Đáp: Để xoay các đoạn văn bản bằng cách sử dụng các đoạn văn bản:

1.  Tạo nên`TextFragment` các đối tượng.
2. Đặt văn bản và thuộc tính của các đoạn văn bản.
3. Chỉ định vị trí của các đoạn văn bản trên trang.
4.  Thiết lập góc quay bằng cách sử dụng`TextState.Rotation` thuộc tính của đoạn văn bản.
5.  Tạo một`TextBuilder`đối tượng và nối các đoạn văn bản vào trang PDF.

#### Câu hỏi: Tôi có thể áp dụng các góc xoay khác nhau cho các đoạn văn bản khác nhau không?

 Đáp: Có, bạn có thể áp dụng các góc xoay khác nhau cho các góc quay khác nhau.`TextFragment` các đối tượng. Mỗi đoạn văn bản có thể có góc xoay riêng được chỉ định bằng cách sử dụng`TextState.Rotation` tài sản.

#### Hỏi: Làm cách nào để lưu tài liệu PDF có đoạn văn bản được xoay?

 Đáp: Để lưu tài liệu PDF có các đoạn văn bản được xoay, hãy sử dụng`Save` phương pháp của`Document` đối tượng và cung cấp đường dẫn và tên tệp đầu ra mong muốn.