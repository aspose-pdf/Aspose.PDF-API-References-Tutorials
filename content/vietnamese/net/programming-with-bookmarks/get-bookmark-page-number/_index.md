---
title: Nhận số trang đánh dấu trong tệp PDF
linktitle: Nhận số trang đánh dấu trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng lấy số trang đánh dấu trong tệp PDF với Aspose.PDF cho .NET.
type: docs
weight: 60
url: /vi/net/programming-with-bookmarks/get-bookmark-page-number/
---
Việc lấy số trang được liên kết với dấu trang trong tệp PDF có thể hữu ích cho việc điều hướng. Với Aspose.PDF for .NET, bạn có thể dễ dàng lấy số trang của dấu trang bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf.Facades;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF mà bạn muốn trích xuất số trang đánh dấu từ đó. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Tạo trình chỉnh sửa dấu trang

 Bây giờ chúng ta sẽ tạo một`PdfBookmarkEditor` đối tượng để thao tác đánh dấu tài liệu. Sử dụng mã sau đây:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Bước 4: Mở tệp PDF

 Ở bước này, chúng tôi mở tệp PDF bằng cách sử dụng`BindPdf` phương pháp của trình soạn thảo dấu trang. Đây là mã tương ứng:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Bước 5: Trích xuất dấu trang

 Bây giờ chúng ta sẽ trích xuất dấu trang từ tài liệu bằng cách sử dụng`ExtractBookmarks` phương pháp của trình soạn thảo dấu trang. Đây là mã tương ứng:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Bước 6: Duyệt bookmark và lấy số trang

 Cuối cùng, chúng tôi lặp lại các dấu trang được trích xuất và lấy số trang liên quan đến từng dấu trang bằng cách sử dụng một`foreach` vòng. Đây là mã tương ứng:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Mã nguồn mẫu để Nhận số trang đánh dấu bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Mở tệp PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Trích xuất dấu trang
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để lấy số trang đánh dấu bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để truy xuất thông tin điều hướng được liên kết với từng dấu trang trong tài liệu PDF của mình.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng thao tác dấu trang nâng cao.

### Câu hỏi thường gặp về lấy số trang đánh dấu trong tệp PDF

#### Hỏi: Dấu trang trong tệp PDF là gì?

Đáp: Dấu trang trong tệp PDF là công cụ hỗ trợ điều hướng cho phép người dùng nhanh chóng chuyển đến các phần hoặc trang cụ thể trong tài liệu. Chúng nâng cao trải nghiệm người dùng bằng cách cung cấp lối tắt đến nội dung có liên quan.

#### Hỏi: Tại sao tôi muốn truy xuất số trang đánh dấu từ tệp PDF?

Đáp: Truy xuất số trang của dấu trang giúp người dùng điều hướng qua tài liệu hiệu quả hơn, cung cấp chỉ dẫn rõ ràng về vị trí dẫn đến mỗi dấu trang. Điều này đặc biệt hữu ích cho các tài liệu dài hơn có nhiều phần.

#### Câu hỏi: Làm cách nào để nhập các thư viện cần thiết cho dự án C# của tôi?

Đáp: Để nhập thư viện cần thiết cho dự án C# của bạn, hãy sử dụng lệnh nhập sau:

```csharp
using Aspose.Pdf.Facades;
```

Lệnh này cho phép bạn sử dụng các lớp và phương thức do Aspose.PDF cung cấp cho .NET.

#### Hỏi: Làm cách nào để chỉ định đường dẫn đến thư mục tài liệu?

 Đáp: Trong mã nguồn được cung cấp, hãy thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế đến thư mục chứa tệp PDF mà bạn muốn trích xuất số trang dấu trang. Điều này đảm bảo rằng mã có thể định vị được tệp PDF mục tiêu.

#### Hỏi: Làm cách nào để tạo trình chỉnh sửa dấu trang?

Đáp: Để tạo trình chỉnh sửa dấu trang, hãy sử dụng đoạn mã sau:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Hỏi: Làm cách nào để mở tệp PDF để thao tác đánh dấu?

Trả lời: Để mở tệp PDF nhằm trích xuất thông tin dấu trang, hãy sử dụng mã sau:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Thay thế`"GetBookmarks.pdf"` với tên tập tin thực tế.

#### Hỏi: Làm cách nào để trích xuất dấu trang từ tệp PDF?

 Đáp: Để trích xuất dấu trang từ tệp PDF, hãy sử dụng`ExtractBookmarks` phương pháp của trình chỉnh sửa dấu trang:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Hỏi: Làm cách nào để truy xuất và hiển thị số trang dấu trang?

 Đáp: Lặp lại các dấu trang đã được trích xuất bằng cách sử dụng một`foreach` vòng lặp và truy cập`PageNumber` thuộc tính của mỗi dấu trang để truy xuất và hiển thị số trang liên quan của nó:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Câu hỏi: Tôi có thể sửa đổi thuộc tính dấu trang bằng cách sử dụng phương pháp này không?

 Trả lời: Trong khi hướng dẫn này tập trung vào việc truy xuất số trang dấu trang, bạn có thể sửa đổi các thuộc tính dấu trang khác bằng cách sử dụng tương tự`Bookmark`đối tượng và các thuộc tính liên quan.

#### Hỏi: Làm cách nào để lưu tệp PDF đã cập nhật sau khi trích xuất thông tin dấu trang?

Trả lời: Trích xuất dấu trang không sửa đổi tệp PDF gốc. Nếu bạn muốn lưu bất kỳ thay đổi nào, bạn có thể thực hiện bằng các phương pháp khác do Aspose.PDF cung cấp cho .NET.