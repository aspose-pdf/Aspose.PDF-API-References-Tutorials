---
title: Thêm TOC vào tệp PDF
linktitle: Thêm TOC vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm Mục lục vào PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này đơn giản hóa quy trình và đảm bảo điều hướng dễ dàng trong tài liệu của bạn.
type: docs
weight: 40
url: /vi/net/programming-with-document/addtoc/
---
## Giới thiệu

Bạn đã bao giờ cuộn vô tận qua một tệp PDF dài, ước rằng nó có Mục lục được sắp xếp hợp lý chưa? Vâng, hôm nay là ngày may mắn của bạn! Trong hướng dẫn này, bạn sẽ học cách thêm Mục lục vào tệp PDF của mình bằng Aspose.PDF cho .NET. Cho dù bạn đang làm việc trên một báo cáo phức tạp, một Sách điện tử hay một đề xuất kinh doanh, Mục lục có thể biến tài liệu của bạn thành một kiệt tác chuyên nghiệp, dễ điều hướng.

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn đã có mọi thứ cần thiết:

1. Aspose.PDF cho .NET: Đảm bảo bạn đã tải xuống và cài đặt thư viện Aspose.PDF. Bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/net/).
   
2. Môi trường phát triển: Đảm bảo rằng bạn đã thiết lập môi trường phát triển .NET như Visual Studio trên máy của mình.

3.  Giấy phép: Nếu bạn không có giấy phép, bạn có thể dùng thử miễn phí hoặc yêu cầu cấp giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

## Nhập gói

Để bắt đầu, hãy đảm bảo nhập các không gian tên cần thiết vào đầu tệp mã của bạn. Thực hiện như sau:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Các không gian tên này cho phép bạn truy cập các chức năng dành riêng cho PDF và thao tác các thành phần văn bản trong tài liệu của bạn.

Hãy chia nhỏ nhiệm vụ này thành các bước nhỏ. Mỗi bước sẽ hướng dẫn bạn quy trình tạo và chèn mục lục vào tài liệu PDF của bạn.

## Bước 1: Tải Tài liệu PDF

Điều đầu tiên chúng ta cần làm là tải tệp PDF hiện có mà chúng ta muốn thêm mục lục.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 Trong bước này, chúng tôi chỉ định đường dẫn đến thư mục tài liệu và tải PDF bằng cách sử dụng`Document` đối tượng. Hãy chắc chắn để thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tập tin của bạn.

## Bước 2: Chèn một trang mới cho mục lục

Tiếp theo, chúng ta chèn một trang mới vào đầu tài liệu PDF. Trang này sẽ lưu trữ Mục lục.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Bằng cách chèn trang mục lục vào đầu, chúng tôi đảm bảo rằng đây là điều đầu tiên mà người đọc nhìn thấy trong tệp PDF.

## Bước 3: Tạo Đối tượng thông tin TOC

Bây giờ, hãy tạo một đối tượng đại diện cho thông tin TOC. Chúng ta cũng sẽ thêm tiêu đề vào TOC để làm nổi bật nó.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Ở đây, chúng tôi đặt tiêu đề của Mục lục là "Mục lục", tăng kích thước phông chữ và in đậm để nhấn mạnh.

## Bước 4: Xác định các thành phần mục lục

Trong bước này, chúng tôi xác định các thành phần (hoặc tiêu đề) sẽ được hiển thị trong Mục lục. Các thành phần này sẽ giúp người đọc điều hướng đến các phần cụ thể của tài liệu.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Chúng tôi đã tạo một mảng chuỗi sẽ đóng vai trò là mục lục, tương ứng với các trang khác nhau trong tệp PDF.

## Bước 5: Tạo tiêu đề mục lục

Bây giờ đến phần quan trọng nhất—thêm tiêu đề vào Mục lục và liên kết chúng đến các trang tương ứng.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Sau đây là những gì đang xảy ra:
- Tiêu đề: Chúng tôi tạo ra một`Heading` đối tượng và thêm một`TextSegment` với nó.
- Trang đích: Chúng tôi thiết lập trang mà mỗi tiêu đề sẽ liên kết tới.
- Vị trí trên cùng: Chúng tôi chỉ định vị trí trên trang mà tiêu đề sẽ trỏ tới.
- Văn bản: Mỗi tiêu đề có tiêu đề tương ứng từ mảng mà chúng ta đã tạo trước đó.

Vòng lặp này tạo tiêu đề cho hai phần tử đầu tiên trong Mục lục và liên kết chúng với các trang tương ứng.

## Bước 6: Lưu PDF với TOC

Cuối cùng, sau khi đã thêm tất cả các thành phần mục lục, đã đến lúc lưu tệp PDF đã cập nhật.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Tệp hiện đã được lưu với TOC được thêm vào PDF. Xin chúc mừng—bạn đã thêm thành công Mục lục!

## Bước 7: Tin nhắn xác nhận

Để người dùng biết quá trình đã hoàn tất, chúng tôi sẽ hiển thị một thông báo đơn giản trong bảng điều khiển.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Phần kết luận

Và bạn đã có nó! Với Aspose.PDF cho .NET, việc thêm Mục lục vào PDF không chỉ dễ dàng mà còn có thể tùy chỉnh. Cho dù bạn cần tạo liên kết điều hướng đơn giản hay cấu trúc phức tạp, công cụ này đều có thể đáp ứng. Vì vậy, lần tới khi bạn làm việc trên một tệp PDF dài, đừng quên thêm Mục lục để có nét chuyên nghiệp!

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh giao diện của mục lục trong Aspose.PDF không?  
Có, bạn có thể tùy chỉnh hoàn toàn giao diện của mục lục, bao gồm kiểu phông chữ, kích thước và căn chỉnh.

### Làm thế nào để thêm tiêu đề phụ vào Mục lục?  
 Bạn có thể thêm tiêu đề phụ bằng cách điều chỉnh`Heading` mức độ (ví dụ,`Heading(2)`) để tạo mục lục phân cấp.

### Có thể tự động cập nhật Mục lục nếu tài liệu thay đổi không?  
Không, TOC sẽ không tự động cập nhật. Bạn sẽ cần phải tạo lại nếu cấu trúc tài liệu thay đổi.

### Tôi có thể liên kết mục lục với các tài liệu bên ngoài không?  
Có, bạn có thể sử dụng siêu liên kết để liên kết mục lục với các tệp PDF hoặc URL bên ngoài.

### Aspose.PDF có hỗ trợ mục lục đa cấp không?  
Có, Aspose.PDF hỗ trợ mục lục nhiều cấp cho các tài liệu phức tạp có nhiều tiểu mục.