---
title: Nhận cửa sổ tài liệu
linktitle: Nhận cửa sổ tài liệu
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng tính năng GetDocumentWindow của Aspose.PDF cho .NET để lấy thông tin về thuộc tính cửa sổ của tài liệu PDF.
type: docs
weight: 170
url: /vi/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF for .NET là một thư viện thao tác PDF mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi các tệp PDF trong các ứng dụng .NET của họ. Một trong những tính năng mà thư viện này cung cấp là khả năng truy xuất thông tin về các thuộc tính cửa sổ của tài liệu. Hướng dẫn này sẽ hướng dẫn bạn qua các bước sử dụng`GetDocumentWindow` tính năng của Aspose.PDF dành cho .NET để lấy thông tin về thuộc tính cửa sổ của tài liệu PDF.

## Bước 1: Cài đặt Aspose.PDF cho .NET

 Để sử dụng Aspose.PDF cho .NET trong các ứng dụng .NET của bạn, trước tiên bạn phải cài đặt thư viện. Bạn có thể tải xuống phiên bản mới nhất của thư viện từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net).

Sau khi tải xuống thư viện, hãy giải nén nội dung của tệp ZIP vào một thư mục trên máy tính của bạn. Sau đó, bạn sẽ cần thêm tham chiếu đến Aspose.PDF cho DLL .NET trong dự án .NET của mình.

## Bước 2: Tải Tài liệu PDF

 Sau khi bạn đã cài đặt Aspose.PDF cho .NET và thêm tham chiếu đến DLL trong dự án .NET của mình, bạn có thể bắt đầu sử dụng`GetDocumentWindow`tính năng để lấy thông tin về thuộc tính cửa sổ của tài liệu PDF.

Bước đầu tiên để sử dụng tính năng này là tải tài liệu PDF mà bạn muốn lấy thông tin. Để thực hiện việc này, bạn có thể sử dụng mã sau:

```csharp
// Đường dẫn đến tài liệu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Trong đoạn mã trên, hãy thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu PDF của bạn được đặt. Mã này sẽ tải tài liệu PDF vào một`Document` đối tượng mà sau đó bạn có thể sử dụng để lấy thông tin về thuộc tính cửa sổ của tài liệu.

## Bước 3: Lấy Thuộc tính Cửa sổ của Tài liệu

Để lấy thông tin về thuộc tính cửa sổ của tài liệu PDF, bạn có thể sử dụng mã sau:

```csharp
// Lấy lại các thuộc tính cửa sổ của tài liệu
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

Trong đoạn mã trên, mỗi dòng sẽ lấy một thuộc tính cửa sổ khác nhau của tài liệu PDF và xuất ra bảng điều khiển. Bạn có thể tùy chỉnh đoạn mã này để chỉ lấy các thuộc tính mà bạn quan tâm.

### Mã nguồn ví dụ để lấy cửa sổ tài liệu của tệp PDF bằng Aspose.PDF cho .NET 

 Sau đây là mã nguồn đầy đủ để lấy các thuộc tính cửa sổ của tài liệu PDF bằng cách sử dụng`GetDocumentWindow` Tính năng của Aspose.PDF dành cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Nhận các thuộc tính tài liệu khác nhau
// Vị trí của cửa sổ tài liệu - Mặc định: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Thứ tự đọc chủ yếu; xác định vị trí của trang
// Khi hiển thị cạnh nhau - Mặc định: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Thanh tiêu đề của cửa sổ có hiển thị tiêu đề tài liệu không
// Nếu sai, thanh tiêu đề sẽ hiển thị tên tệp PDF - Mặc định: sai
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Có nên thay đổi kích thước cửa sổ tài liệu để phù hợp với kích thước của
// Trang hiển thị đầu tiên - Mặc định: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Có nên ẩn thanh menu của ứng dụng xem không - Mặc định: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Có nên ẩn thanh công cụ của ứng dụng xem không - Mặc định: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Có nên ẩn các thành phần UI như thanh cuộn không
// Và chỉ hiển thị nội dung trang - Mặc định: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Chế độ trang của tài liệu. Cách hiển thị tài liệu khi thoát khỏi chế độ toàn màn hình.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Bố cục trang tức là một trang, một cột
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Tài liệu sẽ hiển thị như thế nào khi mở
// Tức là hiển thị hình thu nhỏ, toàn màn hình, hiển thị bảng đính kèm
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.PDF cho .NET để lấy thông tin về thuộc tính cửa sổ của tài liệu PDF. Bằng cách tải tài liệu PDF và truy cập thuộc tính cửa sổ của tài liệu, bạn có thể thu thập thông tin về cách tài liệu sẽ được hiển thị khi mở trong ứng dụng xem. Aspose.PDF cho .NET cung cấp một bộ tính năng mạnh mẽ để làm việc với các tệp PDF theo chương trình, khiến nó trở thành một công cụ hữu ích để thao tác PDF trong các ứng dụng .NET.

### Câu hỏi thường gặp

#### H: Mục đích của việc lấy thuộc tính cửa sổ của tài liệu PDF là gì?

A: Truy xuất thuộc tính cửa sổ của tài liệu PDF cho phép bạn thu thập thông tin về cách tài liệu PDF sẽ được hiển thị khi mở trong ứng dụng xem. Các thuộc tính này kiểm soát nhiều khía cạnh khác nhau như vị trí cửa sổ, chế độ hiển thị và khả năng hiển thị của các thành phần UI.

#### H: Làm thế nào tôi có thể cài đặt Aspose.PDF cho .NET vào dự án .NET của mình?

 A: Để cài đặt Aspose.PDF cho .NET, bạn cần tải xuống thư viện từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net). Sau khi tải xuống, hãy giải nén nội dung của tệp ZIP và thêm tham chiếu đến Aspose.PDF cho .NET DLL trong dự án .NET của bạn.

#### H: Tôi có thể tùy chỉnh mã để chỉ lấy các thuộc tính cửa sổ cụ thể không?

A: Có, bạn có thể tùy chỉnh mã để lấy các thuộc tính cửa sổ cụ thể bằng cách bình luận các dòng bạn không cần. Mỗi dòng trong mã tương ứng với một thuộc tính cửa sổ cụ thể, do đó bạn có thể bao gồm hoặc loại trừ các thuộc tính dựa trên yêu cầu của mình.

#### H: Tôi có thể lấy những loại thuộc tính cửa sổ nào khi sử dụng Aspose.PDF cho .NET?

A: Khi sử dụng Aspose.PDF cho .NET, bạn có thể truy xuất nhiều thuộc tính cửa sổ khác nhau của tài liệu PDF, bao gồm căn giữa cửa sổ, thiết lập bố cục trang, kiểm soát cách hiển thị thanh công cụ và thanh menu, v.v.