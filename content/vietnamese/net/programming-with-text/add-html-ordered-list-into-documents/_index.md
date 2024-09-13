---
title: Thêm danh sách có thứ tự HTML vào tài liệu
linktitle: Thêm danh sách HTMLOrdered vào tài liệu
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm danh sách có thứ tự HTML vào tài liệu bằng Aspose.PDF cho .NET.
type: docs
weight: 30
url: /vi/net/programming-with-text/add-html-ordered-list-into-documents/
---
Trong hướng dẫn này, bạn sẽ học cách sử dụng thư viện Aspose.PDF cho .NET để thêm danh sách có thứ tự HTML vào tài liệu. Mã được cung cấp sẽ trình bày các bước cần thiết để hoàn thành nhiệm vụ này.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn thêm danh sách có thứ tự HTML, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu và đường dẫn tệp đầu ra
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

 Tiếp theo, xác định vị trí dòng ghi`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` và thay thế`"AddHTMLOrderedListIntoDocuments_out.pdf"` với tên mong muốn cho tệp PDF đầu ra của bạn.

## Bước 4: Tạo một đối tượng Document mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Tạo đối tượng HtmlFragment với nội dung HTML
 Khởi tạo một`HtmlFragment` đối tượng có nội dung HTML mà bạn muốn thêm vào tài liệu. Trong mã được cung cấp, nội dung HTML được gán cho biến`t`. Bạn có thể sửa đổi nội dung HTML khi cần thiết.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Bước 6: Thêm một trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = doc.Pages.Add();
```

## Bước 7: Thêm HtmlFragment vào trang
 Thêm vào`HtmlFragment` phản đối trang bằng cách sử dụng`Add` phương pháp của`Paragraphs` bộ sưu tập.

```csharp
page.Paragraphs.Add(t);
```

## Bước 8: Lưu tài liệu PDF
 Lưu tệp PDF kết quả bằng cách sử dụng`Save` phương pháp của`Document` đối tượng. Chỉ định đường dẫn tệp đầu ra mà bạn đã đặt ở Bước 3.

```csharp
doc.Save(outFile);
```

### Mã nguồn mẫu để Thêm danh sách HTMLOrdered vào tài liệu bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Đường dẫn đến tài liệu đầu ra.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Khởi tạo đối tượng HtmlFragment với đoạn HTML tương ứng
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Thêm Trang vào Bộ sưu tập Trang
Page page = doc.Pages.Add();
// Thêm HtmlFragment vào bên trong trang
page.Paragraphs.Add(t);
//Lưu tệp PDF kết quả
doc.Save(outFile);
```

## Phần kết luận
Bạn đã thêm thành công danh sách có thứ tự HTML vào tài liệu bằng Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

Hãy nhớ tùy chỉnh nội dung HTML và điều chỉnh mã theo yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này hướng dẫn bạn quy trình thêm danh sách có thứ tự HTML vào tài liệu bằng thư viện Aspose.PDF cho .NET. Hướng dẫn cung cấp hướng dẫn từng bước và đoạn mã để giúp bạn thực hiện nhiệm vụ này.

#### H: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

A: Bạn cần nhập các không gian tên sau vào đầu tệp mã của mình:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu và đường dẫn tệp đầu ra?

 A: Trong mã, xác định vị trí dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn. Ngoài ra, hãy tìm dòng`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` và thay thế`"AddHTMLOrderedListIntoDocuments_out.pdf"` với tên tệp PDF đầu ra mong muốn của bạn.

#### H: Tôi có thể tùy chỉnh nội dung HTML được thêm vào tài liệu không?

 A: Chắc chắn rồi! Ở Bước 5, bạn sẽ tạo một`HtmlFragment` đối tượng được đặt tên`t` chứa nội dung HTML. Bạn có thể sửa đổi nội dung HTML trong dấu ngoặc kép để phù hợp với yêu cầu của bạn.

#### H: Làm thế nào để thêm danh sách có thứ tự HTML vào một trang trong tài liệu?

 A: Ở Bước 7, bạn sẽ thêm`HtmlFragment` sự vật (`t` ) vào trang bằng cách sử dụng`Add` phương pháp của`Paragraphs` bộ sưu tập. Điều này sẽ tích hợp danh sách có thứ tự HTML vào tài liệu một cách liền mạch.

#### H: Làm thế nào để lưu tài liệu PDF kết quả?

 A: Sau khi thêm nội dung HTML và sắp xếp nó trên một trang, bạn có thể lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` đối tượng. Hãy đảm bảo cung cấp đúng đường dẫn tệp đầu ra mà bạn đã đặt trước đó.

#### H: Bạn có thể cung cấp bản tóm tắt mã nguồn mẫu để tham khảo không?

A: Chắc chắn rồi! Sau đây là phiên bản tóm tắt của mã nguồn mẫu được cung cấp trong hướng dẫn này:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách tận dụng thư viện Aspose.PDF cho .NET để kết hợp danh sách có thứ tự HTML vào tài liệu. Kiến thức mới tìm thấy này có thể được áp dụng để nâng cao quy trình tạo và xử lý tài liệu của bạn.