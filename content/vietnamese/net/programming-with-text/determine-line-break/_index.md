---
title: Xác định ngắt dòng trong tệp PDF
linktitle: Xác định ngắt dòng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách xác định ngắt dòng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 130
url: /vi/net/programming-with-text/determine-line-break/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình xác định ngắt dòng trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã nơi bạn muốn xác định ngắt dòng, hãy thêm các lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Tạo phiên bản Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document doc = new Document();
```

## Bước 5: Thêm trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages`bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = doc.Pages.Add();
```

## Bước 6: Thêm đoạn văn bản có ngắt dòng
Tạo vòng lặp để thêm nhiều đoạn văn bản vào trang, mỗi đoạn chứa một đoạn có ngắt dòng.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Bước 7: Lưu tài liệu PDF và trích xuất thông tin ngắt dòng
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Sau đó, trích xuất thông tin ngắt dòng bằng cách sử dụng`GetNotifications` phương pháp của trang mong muốn.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Mã nguồn mẫu để Xác định ngắt dòng bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Phần kết luận
Bạn đã xác định thành công ngắt dòng trong tài liệu PDF bằng Aspose.PDF cho .NET. Thông tin ngắt dòng đã được trích xuất và lưu vào một tệp văn bản.

### Câu hỏi thường gặp

#### Hỏi: Trọng tâm chính của hướng dẫn này là gì?

Đáp: Hướng dẫn này tập trung vào việc hướng dẫn bạn quy trình xác định ngắt dòng trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết để đạt được điều này.

#### Câu hỏi: Tôi nên nhập những không gian tên nào cho hướng dẫn này?

Đáp: Trong tệp mã nơi bạn muốn xác định ngắt dòng, hãy nhập các vùng tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Câu hỏi: Làm cách nào để tạo một phiên bản Tài liệu mới?

 Đáp: Ở Bước 4, bạn sẽ khởi tạo một`Document` đối tượng bằng cách sử dụng mã được cung cấp.

#### Hỏi: Làm cách nào để thêm một trang vào tài liệu?

 Đáp: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập.

#### Câu hỏi: Làm cách nào để thêm các đoạn văn bản có dấu ngắt dòng?

Đáp: Ở Bước 6, bạn sẽ tạo một vòng lặp để thêm nhiều đoạn văn bản vào trang, mỗi đoạn chứa một đoạn có ngắt dòng.

#### Hỏi: Làm cách nào để lưu tài liệu PDF và trích xuất thông tin ngắt dòng?

 Đáp: Ở Bước 7, bạn sẽ lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Sau đó, bạn sẽ trích xuất thông tin ngắt dòng bằng cách sử dụng`GetNotifications` phương pháp của trang mong muốn và lưu nó vào một tập tin văn bản.

#### Câu hỏi: Mục đích của thông tin ngắt dòng được trích xuất là gì?

Đáp: Thông tin ngắt dòng được trích xuất cung cấp chi tiết về ngắt dòng và thông báo có trong tài liệu PDF. Điều này có thể hữu ích cho việc phân tích và hiểu cách cấu trúc văn bản và đoạn văn trong tài liệu.

#### Hỏi: Điểm chính của hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học được cách xác định ngắt dòng trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng kiến thức này để trích xuất và phân tích thông tin ngắt dòng từ tệp PDF theo chương trình.