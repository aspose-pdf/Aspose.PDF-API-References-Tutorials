---
title: Tìm kiếm và lấy trang văn bản trong tệp PDF
linktitle: Tìm kiếm và lấy trang văn bản trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm và lấy văn bản từ một trang cụ thể trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 430
url: /vi/net/programming-with-text/search-and-get-text-page/
---
## Giới thiệu

Bạn đã bao giờ thấy mình cần tìm kiếm văn bản cụ thể trong một tài liệu PDF và trích xuất nó để sử dụng sau này chưa? Có thể bạn đang xây dựng một ứng dụng xử lý tài liệu và yêu cầu trích xuất dữ liệu chính xác hoặc có lẽ bạn chỉ cần phân tích cú pháp PDF một cách hiệu quả. Dù trường hợp của bạn là gì, bạn đã đến đúng nơi rồi! Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách tìm kiếm và lấy văn bản từ một trang trong tệp PDF bằng Aspose.PDF cho .NET. Cho dù bạn là người mới bắt đầu hay là một nhà phát triển dày dạn kinh nghiệm, hướng dẫn này sẽ hướng dẫn bạn từng bước theo cách trò chuyện và hấp dẫn. Sẵn sàng chưa? Hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi bắt đầu viết mã, hãy đảm bảo rằng bạn có mọi thứ cần thiết:

1.  Aspose.PDF cho Thư viện .NET: Bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/net/) hoặc nhận phiên bản dùng thử miễn phí từ cùng một liên kết. Để mua, hãy truy cập[Cửa hàng Aspose](https://purchase.aspose.com/buy).
2. .NET Framework: Bạn sẽ cần một môi trường phát triển .NET như Visual Studio.
3. Tệp PDF: Bạn sẽ cần một tệp PDF mẫu để chúng ta có thể tìm kiếm và trích xuất văn bản. Đối với hướng dẫn này, hãy giả sử tệp có tên là`SearchAndGetTextPage.pdf`.

## Nhập gói

Trước tiên, chúng ta cần nhập các không gian tên cần thiết để làm việc với Aspose.PDF cho .NET. Đảm bảo rằng chúng được bao gồm ở đầu mã của bạn.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Bây giờ chúng ta đã đề cập đến các điều kiện tiên quyết, hãy cùng phân tích từng bước mã. Mỗi bước đã được phác thảo rõ ràng để bạn dễ dàng theo dõi.

## Bước 1: Thiết lập đường dẫn đến thư mục tài liệu của bạn

Trước khi tương tác với PDF, bạn cần xác định đường dẫn đến nơi lưu trữ tài liệu PDF. Điều này đảm bảo chương trình có thể truy cập vào tệp.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Đây là đường dẫn đến thư mục lưu trữ các tệp PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tệp PDF được lưu trữ.

## Bước 2: Tải Tài liệu PDF

Bước tiếp theo là tải tài liệu PDF vào bộ nhớ để bạn có thể làm việc với nó. Sau đây là cách thực hiện:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Tài liệu: Đây là lớp Aspose.PDF tải tệp PDF.
- pdfDocument: Biến nơi lưu trữ tệp PDF của bạn sau khi được tải.

## Bước 3: Tạo đối tượng hấp thụ văn bản

 Các`TextFragmentAbsorber`lớp cho phép bạn tìm kiếm văn bản cụ thể trong PDF. Hãy tạo một phiên bản của lớp này để tìm tất cả các phiên bản của cụm từ tìm kiếm nhất định.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Lớp này chịu trách nhiệm tìm và trích xuất văn bản từ PDF.
- "Hình ảnh": Thay thế bằng bất kỳ văn bản nào bạn muốn tìm kiếm trong tệp PDF.

## Bước 4: Áp dụng Text Absorber cho toàn bộ PDF

Sau khi thiết lập trình hấp thụ văn bản, bạn cần yêu cầu chương trình tìm kiếm trong tất cả các trang của tệp PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Phương pháp này áp dụng trình hấp thụ văn bản vào PDF, quét mọi trang để tìm văn bản bạn đã chỉ định.

## Bước 5: Truy xuất và lặp lại qua văn bản đã trích xuất

Bây giờ chúng ta đã quét PDF, đã đến lúc lấy kết quả và hiển thị chúng. Chúng ta sẽ lặp qua các đoạn văn bản đã trích xuất.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Bộ sưu tập này lưu trữ tất cả các trường hợp của các đoạn văn bản được trình hấp thụ văn bản tìm thấy.

## Bước 6: Lặp qua từng đoạn và trích xuất dữ liệu

Bây giờ chúng ta sẽ lặp lại`textFragmentCollection` và trích xuất nhiều thuộc tính khác nhau của từng đoạn văn bản, chẳng hạn như vị trí, chi tiết phông chữ và màu sắc.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: Mỗi đoạn chứa các phần của văn bản được tìm thấy.
- TextSegment: Mỗi đoạn có thể có nhiều phân đoạn, đại diện cho các phần khác nhau của văn bản.
- TextState: Cung cấp thông tin chi tiết về phông chữ, kích thước và màu sắc của văn bản.

Trong vòng lặp này, chúng ta in ra các chi tiết như văn bản thực tế, vị trí của văn bản (tọa độ X và Y), phông chữ, phông chữ có được nhúng trong PDF hay không và màu nền của văn bản.

## Phần kết luận

Và bạn đã có nó! Bây giờ bạn đã tìm kiếm và trích xuất thành công văn bản từ tệp PDF bằng Aspose.PDF cho .NET. Thật đáng kinh ngạc khi bạn có thể linh hoạt đến thế nào với thư viện này. Cho dù bạn cần tìm kiếm văn bản cụ thể trong một tài liệu lớn, trích xuất văn bản đó hay phân tích các thuộc tính của văn bản đó, Aspose.PDF đều giúp bạn thực hiện dễ dàng. Thêm vào đó, với mã chúng tôi đã đề cập, bạn có đủ khả năng để điều chỉnh nó theo nhu cầu của mình. 

## Câu hỏi thường gặp

### Tôi có thể tìm kiếm nhiều cụm từ cùng một lúc không?  
 Có, bạn có thể sửa đổi mã để tìm kiếm nhiều cụm từ bằng cách tạo nhiều`TextFragmentAbsorber` đồ vật.

### Làm thế nào để trích xuất văn bản từ một trang cụ thể?  
 Bạn có thể nhắm mục tiêu vào một trang cụ thể bằng cách áp dụng`TextFragmentAbsorber` vào một trang duy nhất thay vì toàn bộ tài liệu. Ví dụ:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF cho .NET có miễn phí không?  
 Aspose.PDF là một sản phẩm thương mại, nhưng bạn có thể sử dụng nó với[dùng thử miễn phí](https://releases.aspose.com/).

### Tôi có thể trích xuất hình ảnh từ PDF bằng Aspose.PDF không?  
 Có, Aspose.PDF cho phép bạn trích xuất hình ảnh ngoài văn bản. Kiểm tra[tài liệu](https://reference.aspose.com/pdf/net/) để biết thêm chi tiết.

### Tôi phải làm sao nếu cần thêm trợ giúp hoặc hỗ trợ?  
 Bạn luôn có thể nhận được sự giúp đỡ từ[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/pdf/10).