---
title: Mở rộng dấu trang trong tệp PDF
linktitle: Mở rộng dấu trang trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng mở rộng dấu trang trong tệp PDF để cải thiện khả năng điều hướng với Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-bookmarks/expand-bookmarks/
---
Mở rộng dấu trang trong tệp PDF sẽ hiển thị tất cả dấu trang đang mở theo mặc định. Với Aspose.PDF for .NET, bạn có thể dễ dàng mở rộng dấu trang bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF có dấu trang mà bạn muốn mở rộng. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Mở tài liệu PDF

Bây giờ chúng tôi sẽ mở tài liệu PDF có dấu trang mà chúng tôi muốn mở rộng bằng mã sau:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 4: Đặt chế độ hiển thị trang

Ở bước này chúng ta sẽ thiết lập mặc định chế độ hiển thị trang là hiển thị bookmark. Chúng tôi sử dụng`PageMode` tài sản của`doc` đối tượng để đặt chế độ trang mong muốn. Đây là mã tương ứng:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Bước 5: Duyệt dấu trang và mở rộng chúng

 Bây giờ chúng ta sẽ lặp qua từng mục dấu trang trong bộ sưu tập dấu trang của tài liệu và đặt trạng thái mở của từng mục thành`true` để mở rộng chúng theo mặc định. Đây là mã tương ứng:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Bước 6: Lưu file cập nhật

 Cuối cùng, chúng tôi lưu tệp PDF đã cập nhật bằng cách sử dụng`Save` phương pháp của`doc` sự vật. Đây là mã tương ứng:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Mở rộng Dấu trang bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document doc = new Document(dataDir + "input.pdf");
// Đặt chế độ xem trang tức là hiển thị hình thu nhỏ, toàn màn hình, hiển thị bảng đính kèm
doc.PageMode = PageMode.UseOutlines;
// Duyệt qua từng mục Ouline trong bộ sưu tập phác thảo của tệp PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Đặt trạng thái mở cho mục phác thảo
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Lưu đầu ra
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để phát triển dấu trang bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để hiển thị tất cả dấu trang mặc định trong tài liệu PDF của mình.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng thao tác dấu trang nâng cao.

### Câu hỏi thường gặp về mở rộng dấu trang trong tệp PDF

#### Hỏi: Dấu trang trong tệp PDF là gì?

Đáp: Dấu trang trong tệp PDF là công cụ hỗ trợ điều hướng cho phép người dùng nhanh chóng chuyển đến các phần hoặc trang cụ thể trong tài liệu. Chúng cung cấp một cách thuận tiện để truy cập các phần khác nhau của tài liệu.

#### Hỏi: Tại sao tôi muốn mở rộng dấu trang trong tệp PDF?

Đáp: Việc mở rộng dấu trang có thể cải thiện trải nghiệm người dùng bằng cách hiển thị tất cả dấu trang ở trạng thái mở rộng theo mặc định. Điều này cung cấp cho người dùng cái nhìn tổng quan rõ ràng về cấu trúc của tài liệu và cho phép họ dễ dàng điều hướng đến các phần khác nhau.

#### Câu hỏi: Làm cách nào để nhập các thư viện cần thiết cho dự án C# của tôi?

Đáp: Để nhập thư viện cần thiết cho dự án C# của bạn, hãy sử dụng lệnh nhập sau:

```csharp
using Aspose.Pdf;
```

Lệnh này cho phép bạn sử dụng các lớp và phương thức do Aspose.PDF cung cấp cho .NET.

#### Hỏi: Làm cách nào để chỉ định đường dẫn đến thư mục tài liệu?

 Đáp: Trong mã nguồn được cung cấp, hãy thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tệp PDF mà bạn muốn làm việc. Điều này đảm bảo rằng mã có thể định vị được tệp PDF mục tiêu.

#### H: Làm cách nào để mở tài liệu PDF để mở rộng dấu trang của nó?

Trả lời: Để mở tài liệu PDF nhằm mở rộng dấu trang, hãy sử dụng mã sau:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Thay thế`"input.pdf"` với tên tập tin thực tế.

#### Hỏi: Làm cách nào để đặt chế độ hiển thị trang hiển thị dấu trang theo mặc định?

Đáp: Để đặt chế độ hiển thị trang thành hiển thị dấu trang theo mặc định, hãy sử dụng`PageMode` tài sản của`doc` sự vật:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Hỏi: Làm cách nào để mở rộng tất cả dấu trang trong tài liệu PDF?

 Đáp: Để mở rộng tất cả dấu trang, hãy duyệt qua từng mục dấu trang trong bộ sưu tập phác thảo của tài liệu và đặt`Open` tài sản để`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Câu hỏi: Điều gì xảy ra nếu một dấu trang có các dấu trang con lồng nhau?

Đáp: Nếu một dấu trang có các dấu trang con lồng nhau, việc mở rộng dấu trang gốc cũng sẽ mở rộng các dấu trang con của nó, cung cấp cái nhìn toàn diện về cấu trúc của tài liệu.

#### H: Làm cách nào để lưu tệp PDF đã cập nhật sau khi mở rộng dấu trang?

Trả lời: Để lưu tệp PDF đã cập nhật sau khi mở rộng dấu trang, hãy sử dụng mã sau:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Hỏi: Tôi có thể tùy chỉnh giao diện của dấu trang mở rộng không?

Trả lời: Mặc dù hướng dẫn này tập trung vào việc mở rộng dấu trang theo mặc định, nhưng bạn có thể tùy chỉnh giao diện của dấu trang bằng cách sử dụng các tính năng và thuộc tính khác của Aspose.PDF.