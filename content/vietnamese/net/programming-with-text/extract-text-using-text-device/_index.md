---
title: Trích xuất văn bản bằng thiết bị Text
linktitle: Trích xuất văn bản bằng thiết bị Text
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất văn bản từ tài liệu PDF bằng Text Device trong Aspose.PDF cho .NET.
type: docs
weight: 210
url: /vi/net/programming-with-text/extract-text-using-text-device/
---
## Giới thiệu

Trích xuất văn bản từ PDF có thể rất khó khăn, đặc biệt là khi xử lý các tài liệu có nhiều định dạng, phông chữ nhúng hoặc bố cục phức tạp. Nhưng với Aspose.PDF cho .NET, quá trình này trở nên dễ dàng! Cho dù bạn muốn chuyển đổi các trang của PDF thành văn bản thuần túy để phân tích thêm hay chỉ cần trích xuất các phần cụ thể, Aspose.PDF đều có thể giúp bạn. Trong hướng dẫn này, chúng tôi sẽ chia nhỏ từng bước cách trích xuất văn bản từ PDF bằng lớp TextDevice trong Aspose.PDF. Chúng tôi cũng sẽ cung cấp các giải thích rõ ràng để bạn có thể dễ dàng áp dụng các phương pháp tương tự vào các dự án của riêng mình.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu với mã, hãy đảm bảo bạn đã có mọi thứ để làm theo. Sau đây là những gì bạn cần:

1.  Aspose.PDF cho .NET: Tải xuống phiên bản mới nhất từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác.
3. .NET Framework: Đảm bảo rằng dự án của bạn hướng tới .NET Framework 4.x trở lên.
4. Tệp PDF đầu vào: Tệp PDF mà bạn sẽ sử dụng để trích xuất văn bản. Đặt tệp này vào một thư mục trên máy của bạn (chúng tôi sẽ gọi đây là`YOUR DOCUMENT DIRECTORY`).

## Nhập gói

Ở đầu mã của bạn, bạn sẽ cần nhập các không gian tên cần thiết để làm việc với Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Bước 1: Tải tài liệu PDF của bạn

 Trước khi trích xuất văn bản, chúng ta cần tải tài liệu PDF vào bộ nhớ. Trong bước này, bạn sẽ mở PDF của mình bằng Aspose.PDF`Document` lớp. Điều này sẽ cho phép bạn truy cập tất cả các trang và nội dung trong tệp.

```csharp
// Xác định đường dẫn đến tài liệu PDF của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tài liệu PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Ở đây, chúng tôi đang sử dụng`Document pdfDocument = new Document(dataDir + "input.pdf");` để tải PDF.`dataDir` biến giữ đường dẫn thư mục của tệp PDF của bạn. Điều này sẽ cho phép chúng ta truy cập vào toàn bộ tài liệu, cho phép chúng ta lặp qua các trang và trích xuất nội dung.

## Bước 2: Thiết lập trình tạo chuỗi để lưu trữ văn bản

 Bây giờ tài liệu đã được tải, chúng ta cần một cách để lưu trữ văn bản đã trích xuất. Đối với điều này, chúng ta sẽ sử dụng`StringBuilder` cho phép nối chuỗi hiệu quả.

```csharp
// StringBuilder để giữ văn bản đã trích xuất
StringBuilder builder = new StringBuilder();
```

 Chúng tôi khởi tạo một`StringBuilder`Ví dụ, sẽ thu thập văn bản được trích xuất từ mỗi trang. Đây là cách hiệu quả hơn để xử lý các chuỗi lớn so với việc nối chuỗi thông thường trong một vòng lặp.

## Bước 3: Lặp qua các trang PDF

 Tiếp theo, chúng tôi lặp qua từng trang của tài liệu PDF để trích xuất văn bản. Chúng tôi sẽ xử lý từng trang riêng lẻ bằng cách sử dụng`TextDevice` Lớp này có nhiệm vụ chuyển đổi nội dung PDF sang định dạng văn bản.

```csharp
// Lặp qua tất cả các trang trong PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Xử lý từng trang để trích xuất văn bản
}
```

Vòng lặp này đi qua mọi trang của PDF (`pdfDocument.Pages` ). Đối với mỗi trang, chúng tôi sẽ trích xuất văn bản và thêm nó vào`StringBuilder`.

## Bước 4: Trích xuất văn bản từ mỗi trang

 Bây giờ, chúng ta thiết lập quy trình trích xuất văn bản cho từng trang. Ở đây, chúng ta sẽ tạo một`TextDevice` đối tượng và sử dụng nó để xử lý các trang PDF.`TextDevice` trích xuất văn bản thô hoặc đã định dạng dựa trên các tùy chọn trích xuất mà chúng tôi thiết lập.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Tạo một thiết bị văn bản để trích xuất văn bản
    TextDevice textDevice = new TextDevice();
    
    // Đặt tùy chọn trích xuất văn bản ở chế độ 'Pure'
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Trích xuất văn bản từ trang hiện tại và lưu vào luồng bộ nhớ
    textDevice.Process(pdfPage, textStream);

    // Chuyển đổi luồng bộ nhớ thành văn bản
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Thêm văn bản đã trích xuất vào StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : Các`TextDevice` lớp được sử dụng để trích xuất văn bản từ PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Tùy chọn này trích xuất văn bản thô mà không giữ lại bất kỳ định dạng nào như phông chữ hoặc vị trí. Bạn cũng có thể sử dụng`TextFormattingMode.Raw` nếu bạn cần kiểm soát định dạng nhiều hơn.
- `textDevice.Process(pdfPage, textStream);` : Quá trình này xử lý từng trang của PDF và lưu trữ văn bản đã trích xuất trong một`MemoryStream`.
-  Cuối cùng, chúng tôi chuyển đổi văn bản từ`MemoryStream` vào một chuỗi và thêm nó vào`StringBuilder`.

## Bước 5: Lưu văn bản đã trích xuất vào một tệp

 Sau khi xử lý tất cả các trang, văn bản được lưu trữ trong`StringBuilder`Bước cuối cùng là lưu văn bản đã trích xuất này vào một tệp.

```csharp
// Xác định đường dẫn đầu ra cho tệp văn bản
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Lưu văn bản đã trích xuất vào một tập tin
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Điều này ghi toàn bộ nội dung của`StringBuilder` vào một tập tin văn bản.
- Đường dẫn cho tệp đầu ra được thiết lập bằng cách thêm tên tệp (`"input_Text_Extracted_out.txt"` ) đến`dataDir` con đường.

## Phần kết luận

Trích xuất văn bản từ PDF bằng Aspose.PDF cho .NET là một quá trình đơn giản và hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng mở tài liệu PDF, lặp qua các trang và trích xuất văn bản vào tệp văn bản. Điều này đặc biệt hữu ích khi xử lý khối lượng lớn dữ liệu PDF, thực hiện phân tích văn bản hoặc chuyển đổi tài liệu để thao tác thêm.

Với Aspose.PDF, bạn không chỉ giới hạn ở việc trích xuất văn bản—bạn có thể xử lý chú thích, thao tác hình ảnh hoặc thậm chí chuyển đổi PDF sang các định dạng khác như HTML hoặc Word. Tính linh hoạt và sức mạnh của thư viện này khiến nó trở thành một công cụ vô giá để quản lý PDF trong các ứng dụng .NET.

## Câu hỏi thường gặp

### Aspose.PDF có thể trích xuất văn bản từ tệp PDF dạng hình ảnh không?
Không, Aspose.PDF được thiết kế để trích xuất văn bản từ PDF dựa trên nội dung. Đối với PDF dựa trên hình ảnh, cần có công nghệ OCR.

### Aspose.PDF có giữ nguyên định dạng khi trích xuất văn bản không?
Theo mặc định, văn bản được trích xuất mà không có định dạng, nhưng bạn có thể điều chỉnh các tùy chọn trích xuất nếu muốn giữ lại một số định dạng.

### Tôi có thể trích xuất văn bản từ một phạm vi trang cụ thể không?
Có, bạn có thể sửa đổi mã để lặp qua một phạm vi trang cụ thể thay vì tất cả các trang.

### Có những chế độ trích xuất văn bản nào trong Aspose.PDF?
Aspose.PDF cung cấp hai chế độ: Raw và Pure. Chế độ Raw cố gắng giữ nguyên bố cục gốc, trong khi chế độ Pure chỉ trích xuất văn bản mà không định dạng.

### Aspose.PDF cho .NET có tương thích với .NET Core không?
Có, Aspose.PDF cho .NET hoàn toàn tương thích với .NET Core và .NET Framework.