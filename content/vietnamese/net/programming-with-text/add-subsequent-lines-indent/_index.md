---
title: Thêm thụt lề các dòng tiếp theo trong tệp PDF
linktitle: Thêm thụt lề các dòng tiếp theo trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm thụt lề các dòng tiếp theo vào văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-text/add-subsequent-lines-indent/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm thụt lề các dòng tiếp theo vào văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn thêm thụt lề cho các dòng tiếp theo, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Tạo một đối tượng Document mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Bước 5: Thêm một trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Bước 6: Tạo một TextFragment với các dòng tiếp theo thụt lề
 Khởi tạo một`TextFragment` đối tượng và cung cấp văn bản mong muốn. Trong mã được cung cấp, văn bản được gán cho biến`text` . Sau đó, khởi tạo`TextFormattingOptions` cho`TextFragment` và chỉ định`SubsequentLinesIndent` giá trị.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Bước 7: Thêm TextFragment vào trang
 Thêm vào`TextFragment` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(text);
```

## Bước 8: Lặp lại bước 6 và 7 cho các dòng bổ sung
Để thêm các dòng tiếp theo có cùng thụt lề, hãy lặp lại bước 6 và 7 cho mỗi dòng. Cập nhật nội dung văn bản nếu cần.

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
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` đối tượng. Chỉ định đường dẫn tệp đầu ra.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Mã nguồn mẫu để Thêm thụt lề các dòng tiếp theo bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo đối tượng tài liệu mới
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//Khởi tạo TextFormattingOptions cho đoạn văn bản và chỉ định giá trị SubsequentLinesIndent
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
Bạn đã thêm thành công các dòng tiếp theo thụt lề vào văn bản bằng Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Trọng tâm của hướng dẫn này là gì?

A: Hướng dẫn này cung cấp hướng dẫn toàn diện về cách thêm thụt lề các dòng tiếp theo vào văn bản trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Nó bao gồm các ví dụ về mã nguồn C# để minh họa các bước cần thiết để đạt được điều này.

#### H: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

A: Trong tệp mã mà bạn định thêm thụt lề các dòng tiếp theo, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Trong mã, xác định vị trí dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để tạo đối tượng Tài liệu?

 A: Ở Bước 4, bạn sẽ tạo một phiên bản mới`Document` đối tượng bằng cách sử dụng dòng mã sau:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### H: Làm thế nào để thêm trang vào tài liệu?

 A: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### H: Làm thế nào để thêm thụt lề các dòng tiếp theo vào văn bản?

 A: Ở Bước 6, bạn sẽ tạo một`TextFragment` đối tượng và gán văn bản mong muốn cho nó. Sau đó, bạn sẽ khởi tạo`TextFormattingOptions` cho`TextFragment` và chỉ định`SubsequentLinesIndent` giá trị:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### H: Làm thế nào để thêm TextFragment vào tài liệu PDF?

 A: Ở Bước 7, bạn sẽ thêm`TextFragment` sự vật (`text`) vào bộ sưu tập đoạn văn của trang:

```csharp
page.Paragraphs.Add(text);
```

#### H: Tôi có thể lặp lại quy trình này cho các dòng bổ sung không?

A: Có, ở Bước 8, bạn có thể lặp lại quy trình cho các dòng bổ sung có cùng thụt lề bằng cách tạo mới`TextFragment` các đối tượng và thêm chúng vào bộ sưu tập đoạn văn của trang.

#### H: Làm thế nào để lưu tài liệu PDF kết quả?

 A: Sau khi thêm văn bản với các dòng tiếp theo thụt lề, hãy sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách tăng khả năng đọc văn bản trong tài liệu PDF bằng cách thêm thụt lề các dòng tiếp theo bằng Aspose.PDF cho .NET. Kỹ thuật này có thể hữu ích cho nhiều loại tài liệu và báo cáo khác nhau.