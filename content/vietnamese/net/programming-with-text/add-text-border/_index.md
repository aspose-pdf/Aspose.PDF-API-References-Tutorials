---
title: Thêm đường viền văn bản vào tệp PDF
linktitle: Thêm đường viền văn bản vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm đường viền văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 70
url: /vi/net/programming-with-text/add-text-border/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm đường viền văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã mà bạn muốn thêm đường viền văn bản, hãy thêm lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Tạo đối tượng Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document pdfDocument = new Document();
```

## Bước 5: Thêm trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Bước 6: Tạo một đoạn văn bản
 Tạo một`TextFragment` đối tượng và cung cấp văn bản mong muốn. Đặt vị trí của đoạn văn bản bằng cách sử dụng`Position` tài sản. Trong mã được cung cấp, văn bản được đặt thành "văn bản chính" và được đặt ở vị trí (100, 600) trên trang.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Bước 7: Đặt thuộc tính văn bản
Tùy chỉnh các thuộc tính văn bản như cỡ chữ, loại phông chữ, màu nền, màu nền trước, v.v. Trong mã được cung cấp, các thuộc tính như cỡ chữ, phông chữ, màu nền, màu nền trước và màu nét được đặt cho đoạn văn bản.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Bước 8: Kích hoạt viền văn bản
 Để bật đường viền văn bản, hãy đặt`DrawTextRectangleBorder`thuộc tính của đoạn văn bản`TextState` ĐẾN`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Bước 9: Thêm TextFragment vào trang
 Sử dụng`TextBuilder` lớp để thêm`TextFragment` phản đối trang.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Bước 10: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Chỉ định đường dẫn tệp đầu ra mà bạn đã đặt ở Bước 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Mã nguồn mẫu để Thêm viền văn bản bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo đối tượng tài liệu mới
Document pdfDocument = new Document();
// Nhận trang cụ thể
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Tạo đoạn văn bản
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Đặt thuộc tính văn bản
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Đặt thuộc tính StrokeColor để vẽ đường viền (vuốt) xung quanh hình chữ nhật văn bản
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Đặt giá trị thuộc tính DrawTextRectangleBorder thành true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Lưu tài liệu
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Phần kết luận
Bạn đã thêm thành công đường viền văn bản vào tài liệu PDF của mình bằng Aspose.PDF for .NET. Bây giờ có thể tìm thấy tệp PDF kết quả tại đường dẫn tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Trọng tâm chính của hướng dẫn này là gì?

Đáp: Hướng dẫn này hướng dẫn bạn quy trình thêm đường viền văn bản vào tệp PDF bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết để đạt được điều này.

#### Câu hỏi: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

Đáp: Trong tệp mã nơi bạn muốn thêm đường viền văn bản, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 A: Trong mã, xác định dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Câu hỏi: Làm cách nào để tạo đối tượng Tài liệu?

 Đáp: Ở Bước 4, bạn sẽ khởi tạo một`Document` đối tượng bằng cách sử dụng dòng mã sau:

```csharp
Document pdfDocument = new Document();
```

#### Hỏi: Làm cách nào để thêm một trang vào tài liệu?

 Đáp: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Câu hỏi: Làm cách nào để tạo TextFragment và đặt vị trí của nó?

 Đáp: Ở Bước 6, bạn sẽ tạo một`TextFragment`đối tượng và đặt vị trí của nó trên trang bằng cách sử dụng`Position` tài sản:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh các thuộc tính văn bản, bao gồm cả đường viền văn bản?

Đáp: Ở Bước 7, bạn sẽ tùy chỉnh các thuộc tính văn bản khác nhau như cỡ chữ, loại phông chữ, màu nền, màu nền trước và đường viền văn bản:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Hỏi: Làm cách nào để thêm TextFragment vào tài liệu PDF?

 Đáp: Ở Bước 9, bạn sẽ sử dụng`TextBuilder` lớp để thêm`TextFragment` phản đối trang:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Hỏi: Làm cách nào để lưu tài liệu PDF thu được?

 Đáp: Sau khi thêm văn bản có đường viền, hãy sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Hỏi: Điểm chính của hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách nâng cao tài liệu PDF của mình bằng cách thêm đường viền văn bản bằng Aspose.PDF cho .NET. Điều này có thể đặc biệt hữu ích để nhấn mạnh nội dung văn bản cụ thể trong tệp PDF của bạn.