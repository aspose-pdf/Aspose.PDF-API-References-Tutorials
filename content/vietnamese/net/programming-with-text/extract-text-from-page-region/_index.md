---
title: Trích xuất văn bản từ vùng trang trong tệp PDF
linktitle: Trích xuất văn bản từ vùng trang trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất văn bản từ một vùng cụ thể trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này. Thu thập và lưu văn bản hiệu quả từ tài liệu của bạn.
type: docs
weight: 190
url: /vi/net/programming-with-text/extract-text-from-page-region/
---
## Giới thiệu

Làm việc với PDF thường yêu cầu trích xuất nội dung cụ thể, cho dù đó là trích xuất dữ liệu từ biểu mẫu, bảng hoặc các phần nhất định của tài liệu. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách trích xuất văn bản từ một vùng cụ thể của PDF bằng Aspose.PDF cho .NET. Thay vì sàng lọc toàn bộ tài liệu, chúng tôi sẽ xác định chính xác vị trí văn bản nằm và trích xuất hiệu quả.

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn đã có các mục sau:

1.  Aspose.PDF cho .NET: Nếu bạn chưa tải xuống và cài đặt thư viện Aspose.PDF cho .NET, hãy tải xuống và cài đặt.[Tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/).
2. IDE: Bất kỳ môi trường phát triển .NET nào như Visual Studio.
3. .NET Framework: Đảm bảo dự án của bạn được thiết lập với .NET Framework phù hợp.
4. Tài liệu PDF: Một mẫu PDF mà chúng tôi sẽ trích xuất văn bản.

 Đừng quên rằng bạn có thể[nhận bản dùng thử miễn phí](https://releases.aspose.com/) của Aspose.PDF hoặc sử dụng[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để có đầy đủ chức năng.

## Nhập các gói cần thiết

Để bắt đầu làm việc với Aspose.PDF cho .NET, bạn cần nhập các không gian tên cần thiết vào dự án của mình. Các gói này cung cấp các lớp và phương thức cần thiết để xử lý tài liệu PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Bước 1: Thiết lập thư mục tài liệu và tải PDF

Bước đầu tiên là chỉ định vị trí tệp PDF của bạn và tải tệp đó vào dự án của bạn. Bạn có thể sử dụng đường dẫn thư mục cục bộ đến tệp PDF mà bạn muốn làm việc.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu PDF
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Bước này đảm bảo rằng tệp PDF được tải đúng cách và sẵn sàng để xử lý.`Document` lớp từ thư viện Aspose.PDF cho phép bạn thao tác với tệp PDF.

## Bước 2: Khởi tạo Text Absorber để trích xuất

 Trong bước này, chúng ta tạo ra một`TextAbsorber` đối tượng được thiết kế để trích xuất văn bản từ tài liệu PDF.`TextAbsorber` linh hoạt và có thể tùy chỉnh để tập trung vào các khu vực hoặc trang cụ thể.

```csharp
// Tạo một đối tượng TextAbsorber để trích xuất văn bản
TextAbsorber absorber = new TextAbsorber();
```

 Các`TextAbsorber`lớp là một công cụ mạnh mẽ có thể thu thập tất cả văn bản trong phạm vi bạn chỉ định.

## Bước 3: Xác định vùng trích xuất văn bản

Đây là nơi phép thuật xảy ra. Thay vì kéo văn bản từ toàn bộ trang, chúng ta có thể giới hạn việc trích xuất ở một vùng hình chữ nhật cụ thể của trang. Điều này hoàn hảo khi bạn biết chính xác vị trí của nội dung.

```csharp
// Giới hạn trích xuất văn bản trong một vùng cụ thể
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 Các`Rectangle` đối tượng cho phép bạn xác định tọa độ (theo điểm) của khu vực mà văn bản sẽ được trích xuất.`TextSearchOptions.LimitToPageBounds` đảm bảo chỉ trích xuất văn bản trong hình chữ nhật được chỉ định.

## Bước 4: Chấp nhận Absorber trên trang mong muốn

 Sau khi thiết lập vùng, bước tiếp theo là chấp nhận`TextAbsorber` cho trang cụ thể mà bạn muốn trích xuất văn bản. Ở đây, chúng ta sẽ tập trung vào trang đầu tiên của PDF.

```csharp
// Chấp nhận bộ hấp thụ cho trang đầu tiên
pdfDocument.Pages[1].Accept(absorber);
```

 Bằng cách gọi`Accept` phương pháp trên trang, chúng tôi hướng dẫn Aspose.PDF chạy trình hấp thụ và thu thập văn bản từ vùng đã xác định.

## Bước 5: Truy xuất và Lưu trữ Văn bản đã Trích xuất

 Sau khi bộ hấp thụ hoàn thành công việc của mình, đã đến lúc thu thập văn bản đã trích xuất và lưu lại. Bước này bao gồm việc lấy lại văn bản và ghi vào`.txt` tài liệu.

```csharp
// Lấy văn bản đã trích xuất
string extractedText = absorber.Text;

// Tạo một trình soạn thảo để lưu văn bản đã trích xuất
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Viết văn bản vào tập tin
tw.WriteLine(extractedText);

// Đóng luồng
tw.Close();
```

 Ở đây,`TextWriter` lớp được sử dụng để ghi văn bản đã trích xuất vào tệp văn bản. Điều này đảm bảo rằng nội dung đã trích xuất của bạn được lưu trữ an toàn để sử dụng sau này.

## Phần kết luận

 Trích xuất văn bản từ một vùng cụ thể trong tài liệu PDF có thể cực kỳ hữu ích, đặc biệt là khi xử lý nội dung có cấu trúc như biểu mẫu hoặc bảng. Sử dụng Aspose.PDF cho .NET, bạn có thể thực hiện nhiệm vụ này chỉ với một vài dòng mã. Bằng cách xác định một vùng, khởi tạo một`TextAbsorber`và lưu văn bản đã trích xuất, bạn có toàn quyền kiểm soát những gì được trích xuất từ tệp PDF của mình.

Cho dù bạn đang làm việc trên một dự án nhỏ hay quản lý các tài liệu lớn, phương pháp này cung cấp một cách hiệu quả để trích xuất dữ liệu có liên quan từ các tệp PDF mà không cần phải xem xét toàn bộ tài liệu.

## Câu hỏi thường gặp

### Tôi có thể trích xuất văn bản từ nhiều trang cùng một lúc không?
 Có, bằng cách lặp lại qua`Pages` bộ sưu tập của`pdfDocument` , bạn có thể áp dụng`TextAbsorber` đến nhiều trang.

### Nếu văn bản nằm ở một vùng khác của tệp PDF thì sao?
 Bạn có thể dễ dàng điều chỉnh`Rectangle` tọa độ để khớp với khu vực nơi văn bản của bạn được đặt.

### Cách này có hiệu quả với các tệp PDF được quét không?
Không, PDF được quét cần OCR (Nhận dạng ký tự quang học) để chuyển đổi hình ảnh thành văn bản. Aspose.PDF cũng cung cấp các tính năng OCR.

### Có cách nào để trích xuất văn bản dựa trên các từ khóa cụ thể không?
 Có, bạn có thể sử dụng`TextFragmentAbsorber` để trích xuất văn bản dựa trên từ khóa.

### Làm thế nào để trích xuất văn bản từ tệp PDF được mã hóa?
Trước tiên, bạn cần giải mã tệp PDF bằng cách cung cấp mật khẩu chính xác, sau đó tiến hành trích xuất văn bản.