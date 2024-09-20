---
title: Tìm kiếm và lấy tất cả văn bản
linktitle: Tìm kiếm và lấy tất cả văn bản
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm và lấy văn bản từ tất cả các trang của tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 420
url: /vi/net/programming-with-text/search-and-get-text-all/
---
## Giới thiệu

Bạn đã bao giờ cần trích xuất văn bản cụ thể từ PDF nhưng thấy khó khăn chưa? Đôi khi, PDF có thể giống như các hộp chứa bị khóa, khiến bạn khó có thể lấy được thông tin cần thiết. Nhưng đây là tin tốt: với Aspose.PDF cho .NET, bạn có thể dễ dàng tìm kiếm và truy xuất văn bản từ bất kỳ PDF nào. Thư viện mạnh mẽ này cung cấp mọi thứ bạn cần để làm việc với PDF trong các ứng dụng .NET của mình, giúp việc trích xuất văn bản trở nên dễ dàng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tìm kiếm và trích xuất văn bản từ tệp PDF bằng Aspose.PDF cho .NET. Cho dù bạn đang xây dựng công cụ phân tích văn bản hay chỉ cần tự động trích xuất dữ liệu từ báo cáo PDF, bạn đã đến đúng nơi rồi!

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, hãy đảm bảo rằng bạn đã thiết lập mọi thứ:

1. Aspose.PDF cho .NET: Bạn sẽ cần tải xuống và cài đặt Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang tải xuống[đây](https://releases.aspose.com/pdf/net/).
2. Môi trường .NET: Đảm bảo bạn đã thiết lập .NET Framework hoặc .NET Core trên máy phát triển của mình.
3. Kiến thức cơ bản về C##: Khuyến khích có chút hiểu biết về C# và làm việc với các dự án .NET.
4.  Tài liệu PDF: Một tệp PDF mẫu mà chúng ta sẽ trích xuất văn bản. Trong ví dụ này, chúng ta sẽ sử dụng`SearchAndGetTextFromAll.pdf`.

## Nhập gói

Trước khi viết bất kỳ mã nào, bạn cần nhập các không gian tên cần thiết vào dự án của mình để làm việc với Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Các không gian tên này cung cấp quyền truy cập vào mô hình đối tượng tài liệu của PDF và cho phép chúng ta thao tác văn bản trong tệp.

Chúng ta hãy chia nhỏ quy trình thành các bước đơn giản để bạn có thể dễ dàng thực hiện.

## Bước 1: Thiết lập thư mục tài liệu

Trước tiên, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF của bạn. Điều này giúp ứng dụng xác định được tệp mà bạn sẽ trích xuất văn bản.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  Các`dataDir` biến phải trỏ đến thư mục nơi bạn`SearchAndGetTextFromAll.pdf` tập tin được lưu trữ.
-  Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế trên máy của bạn.

## Bước 2: Mở Tài liệu PDF

Tiếp theo, chúng ta sẽ mở tài liệu PDF bằng Aspose.PDF`Document` sự vật.

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Chúng tôi tạo một phiên bản mới của`Document` lớp bằng cách truyền đường dẫn tệp đầy đủ của PDF.
- Thao tác này sẽ tải tệp PDF vào bộ nhớ, giúp tệp này sẵn sàng để xử lý.

## Bước 3: Tạo một trình hấp thụ văn bản

 Các`TextFragmentAbsorber` đối tượng được sử dụng để tìm kiếm văn bản cụ thể trong PDF. Trong trường hợp này, chúng ta sẽ tìm kiếm từ "văn bản".

```csharp
// Tạo đối tượng TextAbsorber để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  Các`TextFragmentAbsorber` được khởi tạo bằng chuỗi`"text"`. Điều này có nghĩa là nó sẽ tìm kiếm bất kỳ lần xuất hiện nào của từ “text” trong tài liệu PDF.

## Bước 4: Chấp nhận Absorber cho tất cả các trang

Bây giờ, chúng ta sẽ hướng dẫn tài liệu PDF chấp nhận bộ hấp thụ và tìm kiếm văn bản trên tất cả các trang của tài liệu.

```csharp
// Chấp nhận bộ hấp thụ cho tất cả các trang
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  Các`Accept` phương pháp này được áp dụng cho các trang của tài liệu. Phương pháp này sẽ tìm kiếm tất cả các trang cho văn bản đã chỉ định.

## Bước 5: Trích xuất các đoạn văn bản

Sau khi bộ hấp thụ đã quét xong tài liệu, chúng ta có thể lấy lại các đoạn văn bản đã trích xuất.

```csharp
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  Các`TextFragments` tài sản của`TextFragmentAbsorber` trả về bộ sưu tập tất cả các đoạn văn bản khớp với thuật ngữ tìm kiếm.

## Bước 6: Lặp qua các đoạn văn bản

Bây giờ chúng ta đã có bộ sưu tập các đoạn văn bản, chúng ta sẽ lặp qua chúng và trích xuất thông tin chi tiết.

```csharp
// Lặp lại các đoạn
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  Các`foreach` vòng lặp lặp lại qua từng`TextFragment` trong bộ sưu tập.
- Chúng tôi in nhiều thuộc tính khác nhau của từng đoạn văn bản, chẳng hạn như văn bản thực tế, vị trí của văn bản trên trang, chi tiết phông chữ và kích thước phông chữ.
-  Các`XIndent` Và`YIndent` thuộc tính cung cấp tọa độ chính xác của đoạn văn bản trong PDF.

## Phần kết luận

Và bạn đã có nó! Chỉ với một vài dòng mã, chúng tôi đã tìm kiếm và trích xuất thành công văn bản từ PDF bằng Aspose.PDF cho .NET. Tính linh hoạt của Aspose.PDF cho phép bạn thao tác PDF theo nhiều cách, khiến nó trở thành lựa chọn tuyệt vời cho các nhà phát triển cần các giải pháp PDF mạnh mẽ trong môi trường .NET. Bạn có thể dễ dàng mở rộng ví dụ này để tìm kiếm các từ khác, trích xuất thêm chi tiết hoặc thậm chí thao tác nội dung PDF dựa trên nhu cầu của mình. Hy vọng rằng hướng dẫn này đã cung cấp cho bạn một cách tiếp cận rõ ràng và đơn giản để làm việc với PDF. Hãy tiếp tục và thử nghiệm với PDF của riêng bạn!

## Câu hỏi thường gặp

### Tôi có thể tìm kiếm nhiều từ cùng một lúc không?  
 Có, bạn có thể sửa đổi`TextFragmentAbsorber` để tìm kiếm nhiều cụm từ bằng cách điều chỉnh chuỗi tìm kiếm cho phù hợp.

### Nếu văn bản kéo dài nhiều dòng thì sao?  
Aspose.PDF vẫn sẽ nhận dạng và trích xuất văn bản ngay cả khi nó trải dài trên nhiều dòng. Bạn có thể xử lý từng phần riêng lẻ.

### Làm thế nào để lưu văn bản đã trích xuất vào một tệp?  
 Bạn có thể ghi văn bản đã trích xuất vào một tệp bằng cách sử dụng các thao tác I/O tệp C# chuẩn, chẳng hạn như`StreamWriter`.

### Aspose.PDF có hỗ trợ trích xuất văn bản từ các tệp PDF được quét không?  
Aspose.PDF không hỗ trợ OCR. Đối với PDF được quét, bạn sẽ cần một công cụ OCR để nhận dạng văn bản.

### Tôi phải xử lý các tệp PDF được mã hóa như thế nào?  
Nếu tệp PDF của bạn được bảo vệ bằng mật khẩu, bạn có thể mở khóa bằng Aspose.PDF bằng cách cung cấp mật khẩu khi tải tài liệu.