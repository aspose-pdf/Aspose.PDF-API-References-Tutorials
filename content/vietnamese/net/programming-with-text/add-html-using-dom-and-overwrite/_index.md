---
title: Thêm HTML bằng DOM và ghi đè PDF
linktitle: Thêm HTML bằng DOM và ghi đè
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm nội dung HTML bằng DOM và ghi đè PDF trong Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm nội dung HTML bằng DOM (Mô hình đối tượng tài liệu) trong Aspose.PDF cho .NET. Ngoài ra, bạn sẽ học cách ghi đè kiểu cho nội dung HTML. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn thêm nội dung HTML, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu và đường dẫn tệp đầu ra
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 4: Tạo một đối tượng Document mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Thêm một trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = doc.Pages.Add();
```

## Bước 6: Tạo một HtmlFragment với nội dung HTML
 Khởi tạo một`HtmlFragment` đối tượng và cung cấp nội dung HTML mong muốn. Trong mã được cung cấp, nội dung HTML được gán cho biến`title`. Bạn có thể sửa đổi nội dung HTML khi cần thiết.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Bước 7: Ghi đè các kiểu cho nội dung HTML
 Để ghi đè lên các kiểu của nội dung HTML, bạn có thể sửa đổi`TextState` tính chất của`HtmlFragment` đối tượng. Trong mã được cung cấp, họ phông chữ được thay đổi thành "Arial" và kích thước phông chữ được đặt thành 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Bước 8: Thiết lập thông tin lề
Điều chỉnh lề dưới và lề trên của đoạn mã HTML nếu cần. Trong mã được cung cấp, lề dưới được đặt thành 10 và lề trên được đặt thành 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Bước 9: Thêm HtmlFragment vào trang
 Thêm vào`HtmlFragment` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(title);
```

## Bước 10: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` đối tượng. Chỉ định đường dẫn tệp đầu ra mà bạn đã đặt ở Bước 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Thêm HTMLSử dụng DOMVà Ghi đè bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Thêm một trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Khởi tạo HtmlFragment với các nội dung HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Font-family từ 'Verdana' sẽ được thiết lập lại thành 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Đặt thông tin lề dưới
title.Margin.Bottom = 10;
// Đặt thông tin lề trên cùng
title.Margin.Top = 400;
// Thêm đoạn mã HTML vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(title);
// Lưu tệp PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
```

## Phần kết luận
Bạn đã thêm thành công nội dung HTML bằng DOM trong Aspose.PDF cho .NET và ghi đè lên các kiểu cho nội dung HTML. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Trọng tâm của hướng dẫn này là gì?

A: Hướng dẫn này được thiết kế để hướng dẫn bạn quy trình thêm nội dung HTML vào tài liệu PDF bằng Document Object Model (DOM) trong Aspose.PDF cho .NET. Ngoài ra, bạn sẽ học cách ghi đè kiểu cho nội dung HTML, cho phép bạn tùy chỉnh giao diện của nội dung đó. Hướng dẫn cung cấp các đoạn mã nguồn C# để minh họa các bước cần thiết.

#### H: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

A: Trong tệp mã mà bạn định thêm nội dung HTML, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu và đường dẫn tệp đầu ra?

 A: Trong mã, xác định vị trí dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để tạo đối tượng Tài liệu?

 A: Ở Bước 4, bạn sẽ tạo một phiên bản mới`Document` đối tượng bằng cách sử dụng dòng mã sau:

```csharp
Document doc = new Document();
```

#### H: Làm thế nào để thêm trang vào tài liệu?

 A: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Page page = doc.Pages.Add();
```

#### H: Làm thế nào tôi có thể thiết lập nội dung HTML bằng DOM?

 A: Ở Bước 6, bạn sẽ tạo một`HtmlFragment` đối tượng và gán nội dung HTML mong muốn của bạn cho nó. Nội dung HTML được gán cho biến`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### H: Làm thế nào tôi có thể ghi đè lên kiểu nội dung HTML?

 A: Ở Bước 7, bạn sẽ ghi đè các kiểu của nội dung HTML bằng cách sửa đổi`TextState` tính chất của`HtmlFragment` đối tượng. Ví dụ, bạn có thể thay đổi họ phông chữ thành "Arial" và đặt kích thước phông chữ thành 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### H: Tôi có thể điều chỉnh lề của nội dung HTML không?

A: Có, ở Bước 8, bạn có thể điều chỉnh lề dưới và lề trên của đoạn HTML tùy theo nhu cầu:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### H: Làm thế nào để thêm HtmlFragment vào tài liệu PDF?

 A: Ở Bước 9, bạn sẽ thêm`HtmlFragment` sự vật (`title`) vào bộ sưu tập đoạn văn của trang:

```csharp
page.Paragraphs.Add(title);
```

#### H: Làm thế nào để lưu tài liệu PDF kết quả?

 A: Sau khi thêm nội dung HTML và tùy chỉnh kiểu của nó, hãy sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách kết hợp nội dung HTML bằng Document Object Model (DOM) trong Aspose.PDF cho .NET. Ngoài ra, bạn đã có được khả năng ghi đè các kiểu để tùy chỉnh giao diện của nội dung HTML trong tài liệu PDF kết quả.