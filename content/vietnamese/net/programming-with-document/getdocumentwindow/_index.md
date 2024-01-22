---
title: Nhận cửa sổ tài liệu
linktitle: Nhận cửa sổ tài liệu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng tính năng GetDocumentWindow của Aspose.PDF dành cho .NET để truy xuất thông tin về thuộc tính cửa sổ của tài liệu PDF.
type: docs
weight: 170
url: /vi/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET là một thư viện thao tác PDF mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi các tệp PDF trong ứng dụng .NET của họ. Một trong những tính năng được thư viện này cung cấp là khả năng truy xuất thông tin về thuộc tính cửa sổ của tài liệu. Hướng dẫn này sẽ hướng dẫn bạn các bước sử dụng`GetDocumentWindow` tính năng của Aspose.PDF cho .NET để truy xuất thông tin về thuộc tính cửa sổ của tài liệu PDF.

## Bước 1: Cài đặt Aspose.PDF cho .NET

 Để sử dụng Aspose.PDF cho .NET trong các ứng dụng .NET của bạn, trước tiên bạn phải cài đặt thư viện. Bạn có thể tải xuống phiên bản mới nhất của thư viện từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net).

Khi bạn đã tải xuống thư viện, hãy trích xuất nội dung của tệp ZIP vào một thư mục trên máy tính của bạn. Sau đó, bạn sẽ cần thêm tham chiếu đến Aspose.PDF for .NET DLL trong dự án .NET của mình.

## Bước 2: Tải tài liệu PDF

Khi bạn đã cài đặt Aspose.PDF cho .NET và thêm tham chiếu đến DLL trong dự án .NET của mình, bạn có thể bắt đầu sử dụng`GetDocumentWindow` tính năng truy xuất thông tin về thuộc tính cửa sổ của tài liệu PDF.

Bước đầu tiên khi sử dụng tính năng này là tải tài liệu PDF mà bạn muốn lấy thông tin. Để làm điều này, bạn có thể sử dụng đoạn mã sau:

```csharp
// Đường dẫn tới tài liệu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Mở tài liệu PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Trong đoạn mã trên, thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục chứa tài liệu PDF của bạn. Mã này sẽ tải tài liệu PDF vào một`Document` đối tượng mà sau đó bạn có thể sử dụng để truy xuất thông tin về các thuộc tính cửa sổ của tài liệu.

## Bước 3: Truy xuất thuộc tính cửa sổ của tài liệu

Để truy xuất thông tin về thuộc tính cửa sổ của tài liệu PDF, bạn có thể sử dụng mã sau:

```csharp
// Truy xuất thuộc tính cửa sổ của tài liệu
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Trong đoạn mã trên, mỗi dòng truy xuất một thuộc tính cửa sổ khác nhau của tài liệu PDF và xuất nó ra bảng điều khiển. Bạn có thể tùy chỉnh mã này để chỉ truy xuất các thuộc tính mà bạn quan tâm.

### Mã nguồn mẫu cho cửa sổ lấy tài liệu của tệp PDF bằng Aspose.PDF for .NET 

 Đây là mã nguồn đầy đủ để truy xuất các thuộc tính cửa sổ của tài liệu PDF bằng cách sử dụng`GetDocumentWindow` tính năng của Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Nhận các thuộc tính tài liệu khác nhau
// Vị trí cửa sổ tài liệu - Mặc định: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Thứ tự đọc chiếm ưu thế; xác định vị trí của trang
// Khi hiển thị cạnh nhau - Mặc định: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Thanh tiêu đề của cửa sổ có hiển thị tiêu đề tài liệu hay không
// Nếu sai, thanh tiêu đề hiển thị tên tệp PDF - Mặc định: sai
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Có thay đổi kích thước cửa sổ tài liệu cho vừa với kích thước của
// Trang hiển thị đầu tiên - Mặc định: sai
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Có ẩn thanh menu của ứng dụng xem hay không - Mặc định: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Có ẩn thanh công cụ của ứng dụng xem hay không - Mặc định: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Có ẩn các thành phần giao diện người dùng như thanh cuộn hay không
// Và chỉ để lại nội dung trang được hiển thị - Mặc định: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Chế độ trang của tài liệu. Cách hiển thị tài liệu khi thoát khỏi chế độ toàn màn hình.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Bố cục trang tức là một trang, một cột
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Tài liệu sẽ hiển thị như thế nào khi mở
// Tức là hiển thị hình thu nhỏ, toàn màn hình, hiển thị bảng đính kèm
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.PDF cho .NET để truy xuất thông tin về các thuộc tính cửa sổ của tài liệu PDF. Bằng cách tải tài liệu PDF và truy cập các thuộc tính cửa sổ của nó, bạn có thể thu thập thông tin về cách hiển thị tài liệu khi mở trong ứng dụng xem. Aspose.PDF for .NET cung cấp một bộ tính năng mạnh mẽ để làm việc với các tệp PDF theo chương trình, khiến nó trở thành một công cụ có giá trị để thao tác PDF trong các ứng dụng .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của việc truy xuất các thuộc tính cửa sổ của tài liệu PDF là gì?

Đáp: Truy xuất thuộc tính cửa sổ của tài liệu PDF cho phép bạn thu thập thông tin về cách hiển thị tài liệu PDF khi mở trong ứng dụng xem. Các thuộc tính này kiểm soát các khía cạnh khác nhau như vị trí cửa sổ, chế độ hiển thị và khả năng hiển thị của các thành phần UI.

#### Câu hỏi: Làm cách nào tôi có thể cài đặt Aspose.PDF cho .NET trong dự án .NET của mình?

 Trả lời: Để cài đặt Aspose.PDF cho .NET, bạn cần tải xuống thư viện từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net). Sau khi tải xuống, hãy trích xuất nội dung của tệp ZIP và thêm tham chiếu đến Aspose.PDF cho .NET DLL trong dự án .NET của bạn.

#### Câu hỏi: Tôi có thể tùy chỉnh mã để chỉ truy xuất các thuộc tính cửa sổ cụ thể không?

Đáp: Có, bạn có thể tùy chỉnh mã để truy xuất các thuộc tính cửa sổ cụ thể bằng cách nhận xét những dòng mà bạn không cần. Mỗi dòng trong mã tương ứng với một thuộc tính cửa sổ cụ thể, do đó bạn có thể bao gồm hoặc loại trừ các thuộc tính dựa trên yêu cầu của mình.

#### Câu hỏi: Tôi có thể truy xuất những loại thuộc tính cửa sổ nào bằng Aspose.PDF cho .NET?

Trả lời: Sử dụng Aspose.PDF cho .NET, bạn có thể truy xuất các thuộc tính cửa sổ khác nhau của tài liệu PDF, bao gồm căn giữa cửa sổ, đặt bố cục trang, kiểm soát hiển thị thanh công cụ và thanh menu, v.v.