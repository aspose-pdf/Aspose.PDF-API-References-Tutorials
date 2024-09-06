---
title: Hiển thị các ký hiệu có thể thay thế trong tệp PDF
linktitle: Hiển thị các ký hiệu có thể thay thế trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách hiển thị các ký hiệu có thể thay thế trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 310
url: /vi/net/programming-with-text/rendering-replaceable-symbols/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách hiển thị các ký hiệu có thể thay thế trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn từng bước để tạo tệp PDF, thêm đoạn văn bản có dấu xuống dòng, thiết lập thuộc tính văn bản, định vị văn bản và lưu tệp PDF bằng mã nguồn C# được cung cấp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục bạn mong muốn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu PDF và Trang

 Tiếp theo, chúng ta tạo một tài liệu PDF mới và thêm một trang vào đó bằng cách sử dụng`Document` lớp và`Page` lớp từ thư viện Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Bước 3: Thêm đoạn văn bản có dấu xuống dòng

 Chúng tôi tạo ra một`TextFragment` đối tượng và thiết lập văn bản của nó để bao gồm các dấu xuống dòng (`Environment.NewLine`) để biểu diễn nhiều dòng văn bản.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Bước 4: Thiết lập Thuộc tính Đoạn văn bản

Chúng ta có thể thiết lập nhiều thuộc tính khác nhau cho đoạn văn bản nếu muốn, chẳng hạn như cỡ chữ, phông chữ, màu nền và màu nền trước.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Bước 5: Tạo đoạn văn bản và vị trí

 Chúng tôi tạo ra một`TextParagraph` đối tượng, thêm đoạn văn bản vào đoạn văn và đặt vị trí của đoạn văn trên trang.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Bước 6: Thêm đoạn văn bản vào trang

 Chúng tôi tạo ra một`TextBuilder` đối tượng với trang và thêm đoạn văn bản vào trình tạo văn bản.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Bước 7: Lưu tài liệu PDF

Cuối cùng, chúng ta lưu tài liệu PDF vào tệp đầu ra đã chỉ định.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để Hiển thị Ký hiệu có thể thay thế bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Khởi tạo TextFragment mới với văn bản chứa các dấu xuống dòng bắt buộc
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Đặt thuộc tính đoạn văn bản nếu cần thiết
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Tạo đối tượng TextParagraph
TextParagraph par = new TextParagraph();
// Thêm TextFragment mới vào đoạn văn
par.AppendLine(textFragment);
// Đặt vị trí đoạn văn
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Tạo đối tượng TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Thêm TextParagraph bằng TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách hiển thị các ký hiệu có thể thay thế trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tạo PDF, thêm văn bản với các dấu xuống dòng, thiết lập thuộc tính văn bản, định vị văn bản trên trang và lưu PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Kết xuất ký hiệu có thể thay thế trong tệp PDF" là gì?

A: Hướng dẫn "Kết xuất ký hiệu có thể thay thế trong tệp PDF" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để tạo tài liệu PDF bao gồm các ký hiệu có thể thay thế. Các ký hiệu này được biểu diễn dưới dạng các đoạn văn bản có dấu xuống dòng để tạo nội dung nhiều dòng.

#### H: Tại sao tôi lại muốn hiển thị các ký hiệu có thể thay thế trong tài liệu PDF?

A: Việc hiển thị các ký hiệu có thể thay thế rất hữu ích khi bạn cần tạo nội dung PDF động bao gồm thông tin cụ thể của người dùng hoặc biến. Các ký hiệu này hoạt động như các trình giữ chỗ có thể được thay thế bằng dữ liệu thực tế trong thời gian chạy, chẳng hạn như giá trị trường biểu mẫu hoặc thông tin chi tiết được cá nhân hóa.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo.

#### H: Làm thế nào để hiển thị các ký hiệu có thể thay thế trong tài liệu PDF bằng thư viện Aspose.PDF?

A: Hướng dẫn sẽ hướng dẫn bạn từng bước trong quy trình này:

1.  Tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp học.
2.  Thêm một trang vào tài liệu bằng cách sử dụng`Page` lớp học.
3.  Tạo một`TextFragment` đối tượng có dấu xuống dòng (`Environment.NewLine`) để biểu diễn nội dung nhiều dòng.
4. Tùy chỉnh các thuộc tính của đoạn văn bản như cỡ chữ, phông chữ, màu nền và màu nền trước.
5.  Tạo một`TextParagraph` đối tượng, thêm đoạn văn bản vào đó và đặt vị trí của đoạn văn trên trang.
6.  Tạo một`TextBuilder` đối tượng với trang và thêm đoạn văn bản vào đó.
7. Lưu tài liệu PDF.

#### Q: Mục đích của việc sử dụng dấu xuống dòng (`Environment.NewLine`) in the text fragment?

 A: Các dấu xuống dòng được sử dụng để tạo nội dung nhiều dòng trong một đoạn văn bản duy nhất. Bằng cách sử dụng`Environment.NewLine`bạn có thể chỉ ra vị trí cần ngắt dòng trong văn bản.

#### H: Tôi có thể tùy chỉnh giao diện của các ký hiệu có thể thay thế không?

A: Có, bạn có thể tùy chỉnh nhiều thuộc tính khác nhau của đoạn văn bản, chẳng hạn như kích thước phông chữ, phông chữ, màu nền và màu nền trước. Các thuộc tính này xác định giao diện trực quan của các ký hiệu có thể thay thế trong tài liệu PDF.

#### H: Làm thế nào để xác định vị trí của văn bản trên trang?

 A: Bạn có thể thiết lập vị trí của văn bản bằng cách tạo một`TextParagraph` đối tượng và sử dụng`Position` thuộc tính để chỉ định tọa độ X và Y trên trang nơi đoạn văn sẽ được định vị.

#### H: Kết quả mong đợi khi thực thi mã được cung cấp là gì?

A: Bằng cách làm theo hướng dẫn và chạy mã C# được cung cấp, bạn sẽ tạo một tài liệu PDF bao gồm các ký hiệu có thể thay thế. Các ký hiệu có thể thay thế sẽ được biểu diễn dưới dạng các đoạn văn bản có dấu xuống dòng và các thuộc tính tùy chỉnh.

#### H: Tôi có thể sử dụng phương pháp này để tạo tài liệu PDF được cá nhân hóa một cách linh hoạt không?

A: Có, phương pháp này phù hợp để tạo tài liệu PDF động với thông tin được cá nhân hóa. Bằng cách thay thế các ký hiệu có thể thay thế bằng dữ liệu thực tế, bạn có thể tạo nội dung PDF tùy chỉnh cho từng người dùng hoặc kịch bản.