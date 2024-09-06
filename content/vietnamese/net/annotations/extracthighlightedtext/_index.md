---
title: Trích xuất văn bản được tô sáng trong tệp PDF
linktitle: Trích xuất văn bản được tô sáng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất hiệu quả văn bản được tô sáng từ tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn này. Hoàn hảo cho phân tích dữ liệu và xem xét nội dung.
type: docs
weight: 60
url: /vi/net/annotations/extracthighlightedtext/
---
## Giới thiệu

Khi làm việc với các tệp PDF, việc trích xuất văn bản được tô sáng có thể là một nhiệm vụ quan trọng, cho dù là để phân tích dữ liệu, xem xét nội dung hay chỉ đơn giản là sắp xếp các ghi chú của bạn. Nếu bạn đang sử dụng Aspose.PDF cho .NET, quy trình này rất đơn giản và hiệu quả. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách trích xuất văn bản được tô sáng từ tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ đề cập đến mọi thứ từ các điều kiện tiên quyết đến hướng dẫn từng bước, đảm bảo bạn hiểu toàn diện vào cuối bài.

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, bạn cần chuẩn bị một số thứ sau:

-  Aspose.PDF cho Thư viện .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF. Nếu chưa, bạn có thể tải xuống từ[trang phát hành](https://releases.aspose.com/pdf/net/).
- Môi trường phát triển: Bạn nên thiết lập một môi trường phát triển khả dụng, chẳng hạn như Visual Studio.
- Kiến thức cơ bản về C#: Sự quen thuộc với ngôn ngữ lập trình C# và lập trình hướng đối tượng là điều cần thiết.
-  Giấy phép Aspose hợp lệ: Mặc dù bạn có thể bắt đầu bằng bản dùng thử miễn phí, hãy cân nhắc việc lấy[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) hoặc mua một cái từ[đây](https://purchase.aspose.com/buy) để sử dụng không hạn chế.

## Nhập gói

Để bắt đầu, bạn cần nhập các không gian tên cần thiết vào dự án C# của mình. Điều này rất quan trọng để truy cập các lớp và phương thức do Aspose.PDF cung cấp cho .NET.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bây giờ, chúng ta hãy phân tích quy trình trích xuất văn bản được tô sáng từ tệp PDF bằng Aspose.PDF cho .NET. Mỗi bước được giải thích chi tiết để giúp bạn hiểu các khái niệm cơ bản và cách triển khai.

## Bước 1: Thiết lập thư mục dự án của bạn

Trước tiên, bạn cần thiết lập thư mục dự án nơi lưu trữ tệp PDF của bạn. Đây chính là nơi phép thuật xảy ra.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế đến thư mục nơi tệp PDF nằm. Thư mục này là nơi ứng dụng sẽ lấy tệp PDF để xử lý.

## Bước 2: Tải Tài liệu PDF

 Tiếp theo, bạn cần tải tài liệu PDF mà bạn muốn trích xuất văn bản được tô sáng. Điều này được thực hiện bằng cách sử dụng`Document` lớp được cung cấp bởi Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

 Các`Document` lớp được khởi tạo bằng đường dẫn đến tệp PDF. Ở đây,`"ExtractHighlightedText.pdf"` là tên của tệp PDF có chứa văn bản được tô sáng. Đảm bảo rằng tệp này tồn tại trong thư mục đã chỉ định.

## Bước 3: Truy cập Bộ sưu tập chú thích

Sau khi tài liệu PDF được tải, bước tiếp theo là truy cập vào các chú thích trên trang đầu tiên của tài liệu. Chú thích được sử dụng trong PDF để thêm thông tin bổ sung như điểm nổi bật, bình luận, v.v.

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

 Các`Annotations` tài sản của`Page` đối tượng cung cấp quyền truy cập vào tất cả các chú thích trên một trang cụ thể của PDF. Ở đây, chúng ta đang lặp qua từng chú thích trên trang đầu tiên.

## Bước 4: Lọc chú thích văn bản được tô sáng

Bây giờ chúng ta đã có quyền truy cập vào tất cả các chú thích, chúng ta cần lọc chỉ các chú thích văn bản được tô sáng. Điều này đạt được bằng cách kiểm tra loại của từng chú thích.

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

 Các`TextMarkupAnnotation` lớp được sử dụng để biểu diễn chú thích đánh dấu văn bản, bao gồm cả phần tô sáng.`is` từ khóa kiểm tra xem chú thích có phải là loại`TextMarkupAnnotation` và nếu có, nó sẽ chuyển chú thích tới`TextMarkupAnnotation`.

## Bước 5: Trích xuất văn bản được tô sáng

Sau khi xác định được chú thích được tô sáng, bước tiếp theo là trích xuất văn bản có liên quan đến phần tô sáng đó.

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

 Các`GetMarkedTextFragments()` phương pháp trả về một tập hợp`TextFragment` đối tượng, mỗi đối tượng đại diện cho một phần của văn bản được tô sáng. Chúng tôi lặp qua bộ sưu tập này và in văn bản của từng đoạn vào bảng điều khiển.

## Phần kết luận

Trích xuất văn bản được tô sáng từ PDF bằng Aspose.PDF cho .NET là một tính năng mạnh mẽ có thể hợp lý hóa quy trình làm việc của bạn, đặc biệt là nếu bạn đang xử lý các tài liệu lớn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng triển khai chức năng này trong các dự án của riêng mình. Cho dù bạn đang sắp xếp ghi chú, chuẩn bị báo cáo hay tiến hành phân tích dữ liệu, phương pháp này cung cấp giải pháp liền mạch để trích xuất và sử dụng văn bản được tô sáng.

## Câu hỏi thường gặp

### Tôi có thể trích xuất các loại chú thích khác bằng phương pháp này không?  
 Có, bạn có thể trích xuất các loại chú thích khác bằng cách sửa đổi`if` điều kiện để kiểm tra các loại chú thích khác nhau, chẳng hạn như`TextAnnotation`, `StampAnnotation`, vân vân.

### Có thể trích xuất văn bản được tô sáng từ tất cả các trang của PDF không?  
Hoàn toàn có thể! Bạn có thể lặp qua từng trang của tài liệu PDF và áp dụng cùng một logic trích xuất để thu thập văn bản được tô sáng từ mọi trang.

### Tôi có cần giấy phép để sử dụng Aspose.PDF cho .NET không?  
 Mặc dù bạn có thể bắt đầu bằng bản dùng thử miễn phí, nhưng bạn nên mua[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)hoặc mua giấy phép đầy đủ để có quyền truy cập không giới hạn vào tất cả các tính năng.

### Tôi có thể lưu văn bản đã trích xuất vào một tệp thay vì in nó ra bảng điều khiển không?  
Có, bạn có thể dễ dàng sửa đổi mã để lưu văn bản đã trích xuất vào tệp văn bản hoặc bất kỳ định dạng mong muốn nào khác.

### Aspose.PDF có hỗ trợ các nền tảng khác ngoài .NET không?  
Có, Aspose.PDF cũng hỗ trợ Java và các nền tảng khác, cung cấp chức năng tương tự trên nhiều môi trường khác nhau.