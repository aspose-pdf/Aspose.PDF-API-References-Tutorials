---
title: Thêm HTML bằng DOM
linktitle: Thêm HTML bằng DOM
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm nội dung HTML bằng DOM trong Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-text/add-html-using-dom/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm nội dung HTML bằng DOM (Mô hình đối tượng tài liệu) trong Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

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
```

## Bước 3: Thiết lập thư mục tài liệu và đường dẫn tệp đầu ra
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Tạo một đối tượng Document mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Thêm một trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = doc.Pages.Add();
```

## Bước 6: Tạo một HtmlFragment với nội dung HTML
 Khởi tạo một`HtmlFragment` đối tượng và cung cấp nội dung HTML mong muốn. Trong mã được cung cấp, nội dung HTML được gán cho biến`titel`. Bạn có thể sửa đổi nội dung HTML khi cần thiết.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Bước 7: Thiết lập thông tin lề
Điều chỉnh lề dưới và lề trên của đoạn mã HTML nếu cần. Trong mã được cung cấp, lề dưới được đặt thành 10 và lề trên được đặt thành 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Bước 8: Thêm HtmlFragment vào trang
 Thêm vào`HtmlFragment` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Bước 9: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` đối tượng. Chỉ định đường dẫn tệp đầu ra mà bạn đã đặt ở Bước 3.

```csharp
doc.Save(dataDir);
```

## Bước 10: Hiển thị thông báo thành công
Hiển thị thông báo thành công cùng với đường dẫn lưu tệp PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu cho Thêm HTMLSử dụng DOM bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Thêm một trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Khởi tạo HtmlFragment với các nội dung HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Đặt thông tin lề dưới
titel.Margin.Bottom = 10;
// Đặt thông tin lề trên cùng
titel.Margin.Top = 200;
// Thêm đoạn mã HTML vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã thêm thành công nội dung HTML bằng DOM trong Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Mục tiêu của hướng dẫn này là gì?

A: Hướng dẫn này nhằm mục đích cung cấp hướng dẫn từng bước về cách thêm nội dung HTML vào tài liệu PDF bằng Document Object Model (DOM) trong Aspose.PDF cho .NET. Nó bao gồm các đoạn mã nguồn C# để giúp bạn hiểu và triển khai quy trình.

#### H: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

A: Trong tệp mã mà bạn định thêm nội dung HTML, hãy nhập không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu và đường dẫn tệp đầu ra?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để tạo đối tượng Tài liệu?

 A: Ở Bước 4, khởi tạo một`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

#### H: Làm thế nào để thêm trang vào tài liệu?

 A: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Page page = doc.Pages.Add();
```

#### H: Làm thế nào tôi có thể thiết lập nội dung HTML bằng DOM?

 A: Ở Bước 6, bạn sẽ tạo một`HtmlFragment` đối tượng và gán nội dung HTML mong muốn của bạn cho nó. Nội dung HTML được gán cho biến`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### H: Tôi có thể điều chỉnh lề của nội dung HTML không?

A: Có, ở Bước 7, bạn có thể điều chỉnh lề dưới và lề trên của đoạn HTML tùy theo nhu cầu:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### H: Làm thế nào để thêm HTMLFragment vào tài liệu PDF?

 A: Ở Bước 8, bạn sẽ thêm`HtmlFragment` sự vật (`titel`) vào bộ sưu tập đoạn văn của trang:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### H: Làm thế nào để lưu tài liệu PDF kết quả?

 A: Sau khi thêm nội dung HTML và điều chỉnh lề, hãy sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu PDF:

```csharp
doc.Save(dataDir);
```

#### H: Có cách nào để xác minh xem quá trình này có thành công hay không?

A: Chắc chắn rồi, ở Bước 10, một thông báo thành công sẽ hiển thị cùng với đường dẫn lưu tệp PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách sử dụng Document Object Model (DOM) trong Aspose.PDF cho .NET để thêm nội dung HTML vào tài liệu PDF. Kiến thức này giúp bạn nâng cao khả năng tạo PDF của mình.