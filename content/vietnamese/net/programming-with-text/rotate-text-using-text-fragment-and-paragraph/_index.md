---
title: Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn
linktitle: Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách xoay văn bản bằng đoạn văn bản và đoạn văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 400
url: /vi/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

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

 Tạo nhiều`TextFragment` các đối tượng, đặt văn bản và thuộc tính của chúng cũng như chỉ định góc xoay:

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

## Bước 6: Thêm đoạn văn bản vào trang

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

 Đảm bảo thay thế`"TextFragmentTests_Rotated3_out.pdf"` với tên tệp đầu ra mong muốn.

### Mã nguồn mẫu để Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn bằng Aspose.PDF cho .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng tài liệu
Document pdfDocument = new Document();
// Nhận trang cụ thể
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
// Đặt xoay
textFragment2.TextState.Rotation = 315;
// Tạo đoạn văn bản
TextFragment textFragment3 = new TextFragment("rotated text");
// Đặt thuộc tính văn bản
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Đặt xoay
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Lưu tài liệu
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách xoay văn bản bằng cách sử dụng các đoạn văn bản và đoạn văn trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ tạo tài liệu đến lưu phiên bản đã sửa đổi. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thao tác xoay văn bản trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn" là gì?

Đáp: Hướng dẫn "Xoay văn bản bằng cách sử dụng đoạn văn bản và đoạn văn" nhằm mục đích hướng dẫn bạn qua quá trình sử dụng thư viện Aspose.PDF cho .NET để xoay văn bản bằng cách sử dụng cả đoạn văn bản và đoạn văn trong tài liệu PDF. Hướng dẫn này cung cấp hướng dẫn từng bước và mã mẫu để đạt được chức năng này.

#### Hỏi: Hướng dẫn này khác với các hướng dẫn xoay văn bản trước đó như thế nào?

Đáp: Hướng dẫn này kết hợp việc sử dụng các đoạn văn bản và đoạn văn để xoay văn bản trong tài liệu PDF. Nó trình bày cách xoay các đoạn văn bản riêng lẻ và sau đó thêm chúng vào trang`Paragraphs` bộ sưu tập để đạt được hiệu ứng xoay văn bản toàn diện hơn.

#### Hỏi: Lợi ích của việc sử dụng các đoạn văn bản và đoạn văn để xoay văn bản là gì?

Đáp: Việc sử dụng các đoạn văn bản và đoạn văn cùng nhau cho phép xoay văn bản linh hoạt hơn. Các đoạn văn bản cho phép cài đặt xoay và định dạng riêng lẻ, trong khi các đoạn văn cung cấp cấu trúc để sắp xếp và định vị các đoạn văn bản trong một trang.

#### Hỏi: Tôi có thể áp dụng các góc xoay khác nhau cho các đoạn văn bản khác nhau trong cùng một đoạn văn không?

 Đáp: Có, bạn có thể áp dụng các góc xoay khác nhau cho các góc quay khác nhau.`TextFragment` các đối tượng trong cùng một đoạn. Mỗi đoạn văn bản có thể có góc xoay riêng được chỉ định bằng cách sử dụng`TextState.Rotation` tài sản.

#### Hỏi: Có thể đạt được hiệu ứng xoay văn bản phức tạp bằng phương pháp này không?

Đáp: Có, bằng cách kết hợp các đoạn văn bản với nhiều góc xoay khác nhau và sắp xếp chúng trong các đoạn văn, bạn có thể đạt được các hiệu ứng xoay văn bản phức tạp và tùy chỉnh, nâng cao sức hấp dẫn trực quan cho tài liệu PDF của mình.

#### Hỏi: Việc xoay văn bản bằng cách sử dụng các đoạn văn bản và đoạn văn bao gồm những bước nào?

Đáp: Các bước bao gồm:

1. Thiết lập dự án bằng cách tạo dự án C# mới và thêm tham chiếu vào thư viện Aspose.PDF cho .NET.
2. Tạo tài liệu PDF và thêm trang.
3. Tạo các đoạn văn bản, thiết lập thuộc tính của chúng và chỉ định các góc xoay.
4.  Thêm các đoạn văn bản vào trang bằng cách sử dụng`Paragraphs` bộ sưu tập.
5. Lưu tài liệu PDF đã sửa đổi.

#### Hỏi: Tôi có thể áp dụng xoay vòng cho toàn bộ đoạn văn không?

 Đáp: Có, bạn có thể áp dụng xoay cho toàn bộ đoạn văn bằng cách đặt`TextState.Rotation` thuộc tính của chính đoạn đó. Điều này sẽ xoay tất cả các đoạn văn bản trong đoạn văn đó.