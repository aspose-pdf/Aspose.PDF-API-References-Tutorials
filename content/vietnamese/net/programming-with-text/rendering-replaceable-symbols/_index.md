---
title: Hiển thị các ký hiệu có thể thay thế trong tệp PDF
linktitle: Hiển thị các ký hiệu có thể thay thế trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách hiển thị các ký hiệu có thể thay thế trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 310
url: /vi/net/programming-with-text/rendering-replaceable-symbols/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách hiển thị các ký hiệu có thể thay thế trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng ta sẽ thực hiện quy trình từng bước tạo tệp PDF, thêm đoạn văn bản bằng dấu dòng mới, đặt thuộc tính văn bản, định vị văn bản và lưu tệp PDF bằng mã nguồn C# được cung cấp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Trước tiên, bạn cần đặt đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir`biến có đường dẫn đến thư mục bạn muốn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo tài liệu và trang PDF

 Tiếp theo, chúng tôi tạo một tài liệu PDF mới và thêm một trang vào đó bằng cách sử dụng`Document` lớp học và`Page` lớp từ thư viện Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Bước 3: Thêm đoạn văn bản bằng điểm đánh dấu dòng mới

 Chúng tôi tạo ra một`TextFragment`đối tượng và đặt văn bản của nó bao gồm các điểm đánh dấu dòng mới (`Environment.NewLine`) để thể hiện nhiều dòng văn bản.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Bước 4: Đặt thuộc tính đoạn văn bản

Chúng ta có thể đặt nhiều thuộc tính khác nhau cho đoạn văn bản nếu muốn, chẳng hạn như cỡ chữ, phông chữ, màu nền và màu nền trước.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Bước 5: Tạo đoạn văn bản và vị trí

 Chúng tôi tạo ra một`TextParagraph` đối tượng, nối đoạn văn bản vào đoạn văn và đặt vị trí của đoạn văn trên trang.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Bước 6: Thêm đoạn văn bản vào trang

 Chúng tôi tạo ra một`TextBuilder` đối tượng với trang và nối đoạn văn bản vào trình tạo văn bản.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Bước 7: Lưu tài liệu PDF

Cuối cùng, chúng tôi lưu tài liệu PDF vào tệp đầu ra được chỉ định.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để hiển thị các ký hiệu có thể thay thế bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Khởi tạo TextFragment mới với văn bản chứa các dấu dòng mới bắt buộc
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

Trong hướng dẫn này, bạn đã học cách hiển thị các ký hiệu có thể thay thế trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tạo tệp PDF, thêm văn bản bằng dấu dòng mới, đặt thuộc tính văn bản, định vị văn bản trên trang và lưu tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Hiển thị các ký hiệu có thể thay thế trong tệp PDF" là gì?

Đáp: Hướng dẫn "Hiển thị các ký hiệu có thể thay thế trong tệp PDF" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để tạo tài liệu PDF bao gồm các ký hiệu có thể thay thế. Các ký hiệu này được thể hiện dưới dạng các đoạn văn bản có dấu dòng mới để tạo nội dung nhiều dòng.

#### Câu hỏi: Tại sao tôi muốn hiển thị các ký hiệu có thể thay thế trong tài liệu PDF?

Đáp: Việc hiển thị các ký hiệu có thể thay thế rất hữu ích khi bạn cần tạo động nội dung PDF bao gồm thông tin có thể thay đổi hoặc thông tin cụ thể của người dùng. Các ký hiệu này đóng vai trò là phần giữ chỗ có thể được thay thế bằng dữ liệu thực tế trong thời gian chạy, chẳng hạn như giá trị trường biểu mẫu hoặc chi tiết được cá nhân hóa.

#### Hỏi: Làm cách nào để thiết lập thư mục tài liệu?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến có đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo.

#### Câu hỏi: Làm cách nào để hiển thị các ký hiệu có thể thay thế trong tài liệu PDF bằng thư viện Aspose.PDF?

Đáp: Hướng dẫn sẽ hướng dẫn bạn thực hiện từng bước quy trình:

1.  Tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp học.
2.  Thêm một trang vào tài liệu bằng cách sử dụng`Page` lớp học.
3.  Tạo một`TextFragment` đối tượng có dấu dòng mới (`Environment.NewLine`) để thể hiện nội dung nhiều dòng.
4. Tùy chỉnh các thuộc tính của đoạn văn bản như cỡ chữ, phông chữ, màu nền và màu nền trước.
5.  Tạo một`TextParagraph` đối tượng, nối đoạn văn bản vào nó và đặt vị trí của đoạn văn trên trang.
6.  Tạo một`TextBuilder` đối tượng với trang và nối thêm đoạn văn bản vào đó.
7. Lưu tài liệu PDF.

#### Hỏi: Mục đích của việc sử dụng dấu dòng mới là gì (`Environment.NewLine`) in the text fragment?

 Đáp: Điểm đánh dấu dòng mới được sử dụng để tạo nội dung nhiều dòng trong một đoạn văn bản. Bằng cách sử dụng`Environment.NewLine`, bạn có thể chỉ ra vị trí ngắt dòng sẽ xảy ra trong văn bản.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của các biểu tượng có thể thay thế được không?

Trả lời: Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của đoạn văn bản, chẳng hạn như cỡ chữ, phông chữ, màu nền và màu nền trước. Các thuộc tính này xác định hình thức trực quan của các ký hiệu có thể thay thế trong tài liệu PDF.

#### Hỏi: Làm cách nào để xác định vị trí của văn bản trên trang?

 Đáp: Bạn có thể đặt vị trí của văn bản bằng cách tạo một`TextParagraph` đối tượng và sử dụng`Position` thuộc tính để chỉ định tọa độ X và Y trên trang nơi đoạn văn sẽ được định vị.

#### Câu hỏi: Kết quả mong đợi của việc thực thi mã được cung cấp là gì?

Đáp: Bằng cách làm theo hướng dẫn và chạy mã C# được cung cấp, bạn sẽ tạo một tài liệu PDF bao gồm các ký hiệu có thể thay thế được. Các ký hiệu có thể thay thế sẽ được biểu diễn dưới dạng các đoạn văn bản với các điểm đánh dấu dòng mới và các thuộc tính tùy chỉnh.

#### Câu hỏi: Tôi có thể sử dụng phương pháp này để tạo động các tài liệu PDF được cá nhân hóa không?

Đáp: Có, phương pháp này phù hợp để tạo động các tài liệu PDF có thông tin được cá nhân hóa. Bằng cách thay thế các ký hiệu có thể thay thế bằng dữ liệu thực tế, bạn có thể tạo nội dung PDF tùy chỉnh cho từng người dùng hoặc từng tình huống.