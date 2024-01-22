---
title: Thêm thụt dòng tiếp theo vào tệp PDF
linktitle: Thêm thụt dòng tiếp theo vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm các dòng thụt lề tiếp theo vào văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-text/add-subsequent-lines-indent/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm các dòng thụt lề tiếp theo vào văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã mà bạn muốn thêm thụt lề các dòng tiếp theo, hãy thêm lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Tạo đối tượng Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Bước 5: Thêm trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Bước 6: Tạo TextFragment với các dòng thụt lề tiếp theo
 Khởi tạo một`TextFragment` đối tượng và cung cấp văn bản mong muốn. Trong mã được cung cấp, văn bản được gán cho biến`text` . Sau đó, khởi tạo`TextFormattingOptions` cho`TextFragment`và chỉ định`SubsequentLinesIndent` giá trị.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Bước 7: Thêm TextFragment vào trang
 Thêm`TextFragment` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(text);
```

## Bước 8: Lặp lại bước 6 và 7 cho các dòng bổ sung
Để thêm các dòng tiếp theo có cùng mức thụt lề, hãy lặp lại bước 6 và 7 cho mỗi dòng. Cập nhật nội dung văn bản nếu cần.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Bước 9: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Chỉ định đường dẫn tệp đầu ra.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Mã nguồn mẫu cho Thêm thụt dòng tiếp theo bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo đối tượng tài liệu mới
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Khởi tạo TextFormattingOptions cho đoạn văn bản và chỉ định giá trị SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Phần kết luận
Bạn đã thêm thành công các dòng thụt lề tiếp theo vào văn bản bằng Aspose.PDF for .NET. Bây giờ có thể tìm thấy tệp PDF kết quả tại đường dẫn tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Trọng tâm của hướng dẫn này là gì?

Đáp: Hướng dẫn này cung cấp hướng dẫn toàn diện về cách thêm các dòng thụt lề tiếp theo vào văn bản trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Nó bao gồm các ví dụ về mã nguồn C# để minh họa các bước cần thiết để đạt được điều này.

#### Câu hỏi: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

Đáp: Trong tệp mã mà bạn định thêm thụt lề các dòng tiếp theo, hãy nhập các vùng tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 A: Trong mã, xác định dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Câu hỏi: Làm cách nào để tạo đối tượng Tài liệu?

 Đáp: Ở Bước 4, bạn sẽ khởi tạo một`Document` đối tượng bằng cách sử dụng dòng mã sau:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Hỏi: Làm cách nào để thêm một trang vào tài liệu?

 Đáp: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Hỏi: Làm cách nào tôi có thể thêm các dòng thụt lề tiếp theo vào văn bản?

 Đáp: Ở Bước 6, bạn sẽ tạo một`TextFragment` đối tượng và gán văn bản mong muốn cho nó. Sau đó, bạn sẽ khởi tạo`TextFormattingOptions` cho`TextFragment`và chỉ định`SubsequentLinesIndent` giá trị:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Hỏi: Làm cách nào để thêm TextFragment vào tài liệu PDF?

 Đáp: Ở Bước 7, bạn sẽ thêm`TextFragment` sự vật (`text`) vào bộ sưu tập đoạn văn của trang:

```csharp
page.Paragraphs.Add(text);
```

#### Hỏi: Tôi có thể lặp lại quy trình này cho các dòng bổ sung không?

 Đáp: Có, ở Bước 8, bạn có thể lặp lại quy trình cho các dòng bổ sung có cùng mức thụt lề bằng cách tạo mới`TextFragment` các đối tượng và thêm chúng vào bộ sưu tập đoạn văn của trang.

#### Hỏi: Làm cách nào để lưu tài liệu PDF thu được?

 Đáp: Sau khi thêm văn bản có các dòng thụt lề tiếp theo, hãy sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách nâng cao khả năng đọc văn bản trong tài liệu PDF bằng cách thêm các dòng thụt lề tiếp theo bằng Aspose.PDF cho .NET. Kỹ thuật này có thể hữu ích cho nhiều loại tài liệu và báo cáo.