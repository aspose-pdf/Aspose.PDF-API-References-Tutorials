---
title: Thêm Ngày Giờ Vào Tệp PDF
linktitle: Thêm Ngày Giờ Vào Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm dấu ngày tháng và thời gian vào tệp PDF của bạn bằng Aspose.PDF cho .NET với hướng dẫn từng bước này. Hoàn hảo để tăng cường tính xác thực của tài liệu.
type: docs
weight: 10
url: /vi/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Giới thiệu

Khi nói đến việc quản lý tài liệu, đặc biệt là PDF, việc thêm dấu ngày và giờ có thể là một bước ngoặt. Cho dù bạn đang làm việc trên các tài liệu pháp lý, báo cáo dự án hay hóa đơn, dấu thời gian không chỉ tăng thêm tính xác thực mà còn cung cấp hồ sơ rõ ràng về thời điểm tài liệu được tạo hoặc sửa đổi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm dấu ngày và giờ vào tệp PDF bằng thư viện Aspose.PDF cho .NET. 

Bài viết này được thiết kế đơn giản và dễ hiểu, vì vậy ngay cả khi bạn mới làm quen với lập trình hoặc thư viện Aspose.PDF, bạn vẫn có thể triển khai tính năng này một cách tự tin. Hãy cùng tìm hiểu nhé!

## Điều kiện tiên quyết

Trước khi bắt đầu, bạn cần phải có một số điều kiện tiên quyết sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Đây là nơi bạn sẽ viết và thực thi mã của mình.
2. Aspose.PDF cho .NET: Bạn cần tải xuống và cài đặt thư viện Aspose.PDF. Bạn có thể tìm thấy phiên bản mới nhất[đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu các ví dụ tốt hơn, nhưng đừng lo lắng nếu bạn mới bắt đầu; chúng tôi sẽ giải thích mọi thứ theo từng bước.
4.  Tệp PDF: Chuẩn bị một tệp PDF mẫu. Đối với ví dụ của chúng tôi, chúng tôi sẽ sử dụng tệp có tên`AddTextStamp.pdf`.

Khi đã đáp ứng được những điều kiện tiên quyết này, bạn đã sẵn sàng để thêm dấu ngày tháng và thời gian vào tệp PDF của mình!

## Nhập gói

Để bắt đầu, bạn cần nhập các không gian tên cần thiết vào dự án C# của mình. Sau đây là cách thực hiện:

### Tạo một dự án mới

1. Mở Visual Studio: Khởi chạy ứng dụng Visual Studio của bạn.
2. Tạo dự án mới: Chọn “Tạo dự án mới” từ màn hình bắt đầu.
3. Chọn Console App: Chọn “Console App (.NET Framework)” từ danh sách mẫu dự án.
4.  Đặt tên cho dự án của bạn: Đặt tên cho dự án của bạn, ví dụ:`PDFDateTimeStamp`.

### Thêm tham chiếu Aspose.PDF

1. Nhấp chuột phải vào References: Trong Solution Explorer, nhấp chuột phải vào thư mục “References” của dự án của bạn.
2. Chọn “Thêm tham chiếu”: Chọn “Thêm tham chiếu” từ menu ngữ cảnh.
3. Duyệt tìm Aspose.PDF: Điều hướng đến vị trí bạn đã tải xuống Aspose.PDF và chọn nó. Nhấp vào “OK” để thêm nó vào dự án của bạn.

### Nhập không gian tên bắt buộc

 Ở đầu trang của bạn`Program.cs` tệp, bạn cần nhập các không gian tên sau:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Bây giờ chúng ta đã thiết lập xong mọi thứ, hãy chia nhỏ quy trình thêm dấu ngày tháng và thời gian vào tệp PDF thành các bước rõ ràng, dễ quản lý.

## Bước 1: Thiết lập thư mục tài liệu

Đầu tiên, bạn cần chỉ định thư mục chứa tệp PDF của bạn. Điều này rất quan trọng vì mã sẽ tìm kiếm tệp PDF trong thư mục này.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Thay thế bằng đường dẫn thực tế của bạn
```

 Hãy chắc chắn thay thế`YOUR DOCUMENT DIRECTORY` với đường dẫn thực tế đến tệp PDF của bạn.

## Bước 2: Mở Tài liệu PDF

Tiếp theo, bạn sẽ mở tài liệu PDF mà bạn muốn thêm dấu thời gian. 

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Dòng mã này khởi tạo`Document` lớp và tải tệp PDF của bạn vào`pdfDocument` sự vật.

## Bước 3: Tạo Dấu thời gian Ngày tháng

Bây giờ là lúc tạo ngày và dấu thời gian. Bạn sẽ định dạng nó để hiển thị theo cách cụ thể. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Đây,`DateTime.Now` lấy ngày và giờ hiện tại và`ToString` định dạng nó theo định dạng bạn mong muốn.

## Bước 4: Tạo một con dấu văn bản

Khi chuỗi ngày và giờ đã sẵn sàng, giờ đây bạn có thể tạo dấu văn bản để thêm vào tệp PDF của mình.

```csharp
// Tạo con dấu văn bản
TextStamp textStamp = new TextStamp(annotationText);
```

 Dòng này tạo ra một trường hợp mới của`TextStamp` sử dụng chuỗi ngày và giờ đã định dạng.

## Bước 5: Thiết lập Thuộc tính của Con dấu

Bạn có thể tùy chỉnh giao diện và vị trí của tem. Sau đây là cách thiết lập thuộc tính của tem:

```csharp
// Thiết lập thuộc tính của tem
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Ở bước này, chúng ta thiết lập lề và căn chỉnh con dấu vào góc dưới bên phải của trang PDF.

## Bước 6: Thêm tem vào PDF

Bây giờ là lúc thêm dấu văn bản vào tài liệu PDF của bạn. 

```csharp
// Thêm tem vào bộ sưu tập tem
pdfDocument.Pages[1].AddStamp(textStamp);
```

Dòng này thêm dấu vào trang đầu tiên của PDF. Bạn có thể thay đổi số trang nếu muốn đặt nó ở một trang khác.

## Bước 7: Tạo chú thích văn bản tự do (Tùy chọn)

Nếu bạn muốn thêm chú thích vào tem, bạn có thể tạo một`FreeTextAnnotation` như sau:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Bước tùy chọn này sẽ tạo chú thích văn bản tự do có thể cung cấp thêm bối cảnh hoặc thông tin về tem.

## Bước 8: Cấu hình Đường viền chú thích

Nếu bạn muốn tùy chỉnh đường viền chú thích, bạn cũng có thể thực hiện như sau:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Đoạn mã này đặt độ rộng đường viền thành 0, làm cho đường viền trở nên vô hình và thêm chú thích vào PDF.

## Bước 9: Lưu tài liệu PDF

Cuối cùng, bạn cần lưu tài liệu PDF đã chỉnh sửa. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Chỉ định tên tệp đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Dòng này lưu tệp PDF có dấu thời gian đã thêm vào một tệp mới. Bạn có thể kiểm tra thư mục đã chỉ định để xem đầu ra.

## Phần kết luận

Xin chúc mừng! Bạn đã thêm thành công dấu ngày và giờ vào tệp PDF bằng Aspose.PDF cho .NET. Tính năng đơn giản nhưng hiệu quả này có thể cải thiện tài liệu của bạn, giúp chúng chuyên nghiệp hơn và cung cấp hồ sơ rõ ràng về thời điểm chúng được tạo hoặc sửa đổi. 

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh định dạng ngày tháng trong dấu thời gian không?
 Có, bạn có thể sửa đổi`ToString`phương pháp thay đổi định dạng ngày tháng theo ý thích của bạn.

### Aspose.PDF có miễn phí sử dụng không?
 Aspose.PDF cung cấp bản dùng thử miễn phí, nhưng để có đầy đủ tính năng, bạn cần mua giấy phép. Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể thêm nhiều dấu thời gian vào một tệp PDF không?
 Chắc chắn rồi! Bạn có thể tạo nhiều`TextStamp` trường hợp và thêm chúng vào các trang hoặc vị trí khác nhau trong PDF.

### Nếu tôi không có Visual Studio thì sao?
Bạn có thể sử dụng bất kỳ IDE C# hoặc trình soạn thảo văn bản nào, nhưng để chạy và gỡ lỗi dự án, chúng tôi khuyên dùng Visual Studio.

### Tôi có thể tìm thêm ví dụ về cách sử dụng Aspose.PDF ở đâu?
 Bạn có thể khám phá thêm các ví dụ và hướng dẫn trong[Tài liệu Aspose.PDF](https://reference.aspose.com/pdf/net/).