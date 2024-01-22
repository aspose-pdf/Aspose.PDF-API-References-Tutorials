---
title: Thêm HTML bằng DOM
linktitle: Thêm HTML bằng DOM
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm nội dung HTML bằng DOM trong Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-text/add-html-using-dom/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm nội dung HTML bằng DOM (Mô hình đối tượng tài liệu) trong Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

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
```

## Bước 3: Đặt thư mục tài liệu và đường dẫn file đầu ra
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

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
 Khởi tạo một`HtmlFragment` đối tượng và cung cấp nội dung HTML mong muốn. Trong mã được cung cấp, nội dung HTML được gán cho biến`titel`. Bạn có thể sửa đổi nội dung HTML nếu cần.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Bước 7: Thiết lập thông tin ký quỹ
Điều chỉnh lề dưới và trên của đoạn HTML nếu cần. Trong mã được cung cấp, lề dưới được đặt thành 10 và lề trên được đặt thành 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Bước 8: Thêm HtmlFragment vào trang
 Thêm`HtmlFragment` phản đối việc thu thập đoạn văn của trang.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Bước 9: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Chỉ định đường dẫn tệp đầu ra mà bạn đã đặt ở Bước 3.

```csharp
doc.Save(dataDir);
```

## Bước 10: Hiển thị thông báo thành công
Hiển thị thông báo thành công cùng với đường dẫn lưu tệp PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để Thêm HTMLSử dụng DOM bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
Page page = doc.Pages.Add();
// Khởi tạo HtmlFragment bằng nội dung HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Đặt thông tin lề dưới
titel.Margin.Bottom = 10;
// Đặt thông tin lề trên
titel.Margin.Top = 200;
// Thêm đoạn HTML vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã thêm thành công nội dung HTML bằng DOM trong Aspose.PDF cho .NET. Bây giờ có thể tìm thấy tệp PDF kết quả tại đường dẫn tệp đầu ra được chỉ định.

### Câu hỏi thường gặp

#### Hỏi: Mục tiêu của hướng dẫn này là gì?

Đáp: Hướng dẫn này nhằm mục đích cung cấp hướng dẫn từng bước về cách thêm nội dung HTML vào tài liệu PDF bằng Mô hình đối tượng tài liệu (DOM) trong Aspose.PDF cho .NET. Nó bao gồm các đoạn mã nguồn C# để giúp bạn hiểu và triển khai quy trình.

#### Câu hỏi: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

Đáp: Trong tệp mã mà bạn dự định thêm nội dung HTML, hãy nhập vùng tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
```

#### Hỏi: Làm cách nào để chỉ định thư mục tài liệu và đường dẫn tệp đầu ra?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Câu hỏi: Làm cách nào để tạo đối tượng Tài liệu?

 A: Ở Bước 4, khởi tạo một`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

#### Hỏi: Làm cách nào để thêm một trang vào tài liệu?

 Đáp: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập:

```csharp
Page page = doc.Pages.Add();
```

#### Câu hỏi: Làm cách nào tôi có thể đặt nội dung HTML bằng DOM?

 Đáp: Ở Bước 6, bạn sẽ tạo một`HtmlFragment` đối tượng và gán nội dung HTML mong muốn của bạn cho nó. Nội dung HTML được gán cho biến`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### Hỏi: Tôi có thể điều chỉnh lề của nội dung HTML không?

Đáp: Có, ở Bước 7, bạn có thể điều chỉnh lề dưới và lề trên của đoạn HTML nếu cần:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### Hỏi: Làm cách nào để thêm HTMLFragment vào tài liệu PDF?

 Đáp: Ở Bước 8, bạn sẽ thêm`HtmlFragment` sự vật (`titel`) vào bộ sưu tập đoạn văn của trang:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Hỏi: Làm cách nào để lưu tài liệu PDF thu được?

 Đáp: Sau khi thêm nội dung HTML và điều chỉnh lề, hãy sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu PDF:

```csharp
doc.Save(dataDir);
```

#### Hỏi: Có cách nào để xác minh xem quá trình này có thành công không?

Trả lời: Chắc chắn, ở Bước 10, thông báo thành công sẽ được hiển thị cùng với đường dẫn lưu tệp PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách sử dụng Mô hình đối tượng tài liệu (DOM) trong Aspose.PDF cho .NET để thêm nội dung HTML vào tài liệu PDF. Kiến thức này cho phép bạn nâng cao khả năng tạo PDF của mình.