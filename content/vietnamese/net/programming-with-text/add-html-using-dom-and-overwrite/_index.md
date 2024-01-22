---
title: Thêm HTML bằng cách sử dụng ghi đè DOM và PDF
linktitle: Thêm HTML bằng DOM và ghi đè
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm nội dung HTML bằng cách sử dụng ghi đè DOM và PDF trong Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm nội dung HTML bằng DOM (Mô hình đối tượng tài liệu) trong Aspose.PDF cho .NET. Ngoài ra, bạn sẽ tìm hiểu cách ghi đè kiểu cho nội dung HTML. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã mà bạn muốn thêm nội dung HTML, hãy thêm các lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Đặt thư mục tài liệu và đường dẫn file đầu ra
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 4: Tạo đối tượng Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Thêm trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = doc.Pages.Add();
```

## Bước 6: Tạo HtmlFragment với nội dung HTML
 Khởi tạo một`HtmlFragment` đối tượng và cung cấp nội dung HTML mong muốn. Trong mã được cung cấp, nội dung HTML được gán cho biến`title`. Bạn có thể sửa đổi nội dung HTML nếu cần.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Bước 7: Ghi đè style cho nội dung HTML
 Để ghi đè kiểu của nội dung HTML, bạn có thể sửa đổi`TextState` thuộc tính của`HtmlFragment` sự vật. Trong mã được cung cấp, họ phông chữ được đổi thành "Arial" và cỡ chữ được đặt thành 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Bước 8: Thiết lập thông tin ký quỹ
Điều chỉnh lề dưới và trên của đoạn HTML nếu cần. Trong mã được cung cấp, lề dưới được đặt thành 10 và lề trên được đặt thành 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Bước 9: Thêm HtmlFragment vào trang
 Thêm`HtmlFragment` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(title);
```

## Bước 10: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Chỉ định đường dẫn tệp đầu ra mà bạn đã đặt ở Bước 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Thêm HTMLSử dụng DOMVà ghi đè bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Khởi tạo HtmlFragment bằng nội dung HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Họ phông chữ từ 'Verdana' sẽ được đặt lại thành 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Đặt thông tin lề dưới
title.Margin.Bottom = 10;
// Đặt thông tin lề trên
title.Margin.Top = 400;
// Thêm đoạn HTML vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(title);
// Lưu tệp PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
```

## Phần kết luận
Bạn đã thêm thành công nội dung HTML bằng DOM trong Aspose.PDF cho .NET và ghi đè kiểu cho nội dung HTML. Bây giờ có thể tìm thấy tệp PDF kết quả tại đường dẫn tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Trọng tâm của hướng dẫn này là gì?

Đáp: Hướng dẫn này được thiết kế để hướng dẫn bạn quy trình thêm nội dung HTML vào tài liệu PDF bằng Mô hình đối tượng tài liệu (DOM) trong Aspose.PDF cho .NET. Ngoài ra, bạn sẽ tìm hiểu cách ghi đè kiểu cho nội dung HTML, cho phép bạn tùy chỉnh giao diện của nó. Hướng dẫn này cung cấp các đoạn mã nguồn C# để minh họa các bước cần thiết.

#### Câu hỏi: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

Đáp: Trong tệp mã nơi bạn định thêm nội dung HTML, hãy nhập các vùng tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Hỏi: Làm cách nào để chỉ định thư mục tài liệu và đường dẫn tệp đầu ra?

 A: Trong mã, xác định dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Câu hỏi: Làm cách nào để tạo đối tượng Tài liệu?

 Đáp: Ở Bước 4, bạn sẽ khởi tạo một`Document` đối tượng bằng cách sử dụng dòng mã sau:

```csharp
Document doc = new Document();
```

#### Hỏi: Làm cách nào để thêm một trang vào tài liệu?

 Đáp: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Page page = doc.Pages.Add();
```

#### Câu hỏi: Làm cách nào tôi có thể đặt nội dung HTML bằng DOM?

 Đáp: Ở Bước 6, bạn sẽ tạo một`HtmlFragment` đối tượng và gán nội dung HTML mong muốn của bạn cho nó. Nội dung HTML được gán cho biến`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Câu hỏi: Làm cách nào tôi có thể ghi đè các kiểu của nội dung HTML?

 Đáp: Ở Bước 7, bạn sẽ ghi đè các kiểu của nội dung HTML bằng cách sửa đổi`TextState` thuộc tính của`HtmlFragment` sự vật. Ví dụ: bạn có thể thay đổi họ phông chữ thành "Arial" và đặt cỡ chữ thành 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Hỏi: Tôi có thể điều chỉnh lề của nội dung HTML không?

Đáp: Có, ở Bước 8, bạn có thể điều chỉnh lề dưới và trên của đoạn HTML nếu cần:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Hỏi: Làm cách nào để thêm HtmlFragment vào tài liệu PDF?

 Đáp: Ở Bước 9, bạn sẽ thêm`HtmlFragment` sự vật (`title`) vào bộ sưu tập đoạn văn của trang:

```csharp
page.Paragraphs.Add(title);
```

#### Hỏi: Làm cách nào để lưu tài liệu PDF thu được?

 Đáp: Sau khi thêm nội dung HTML và tùy chỉnh kiểu của nó, hãy sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách kết hợp nội dung HTML bằng Mô hình đối tượng tài liệu (DOM) trong Aspose.PDF cho .NET. Ngoài ra, bạn còn có khả năng ghi đè các kiểu để điều chỉnh giao diện của nội dung HTML trong tài liệu PDF thu được.