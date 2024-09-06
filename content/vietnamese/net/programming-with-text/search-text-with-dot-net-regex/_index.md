---
title: Tìm kiếm văn bản với Dot Net Regex
linktitle: Tìm kiếm văn bản với Dot Net Regex
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm văn bản bằng biểu thức chính quy .NET trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 480
url: /vi/net/programming-with-text/search-text-with-dot-net-regex/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET trong tài liệu PDF. Mã nguồn C# được cung cấp sẽ trình bày từng bước của quy trình.

## Điều kiện tiên quyết

Trước khi thực hiện hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để cài đặt vào dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) mà bạn thích và thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm lệnh using sau vào đầu tệp C# của bạn để nhập các không gian tên cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` biến:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo đối tượng .NET Regex

 Tạo một`.NET Regex` đối tượng để xác định mẫu tìm kiếm:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Thay thế`@"[\S]+"` với mẫu biểu thức chính quy bạn mong muốn.

## Bước 5: Tải tài liệu PDF

 Tải tài liệu PDF bằng cách sử dụng`Document` lớp học:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Thay thế`"SearchTextRegex.pdf"` bằng tên thực của tệp PDF của bạn.

## Bước 6: Lấy một trang cụ thể

Lấy trang mong muốn của tài liệu:

```csharp
Page page = document.Pages[1];
```

 Thay thế`1` với số trang mong muốn (chỉ mục dựa trên 1).

## Bước 7: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các trường hợp của biểu thức chính quy đầu vào:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Bước 8: Chấp nhận bộ hấp thụ cho trang

Chấp nhận bộ hấp thụ cho trang:

```csharp
page.Accept(textFragmentAbsorber);
```

## Bước 9: Lấy lại các đoạn văn bản đã trích xuất

Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 10: Lặp qua các đoạn văn bản

Lặp qua các đoạn văn bản đã lấy được và thực hiện các hành động mong muốn:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Sửa đổi mã trong vòng lặp để thực hiện các hành động tiếp theo trên từng đoạn văn bản nếu cần.

### Mã nguồn mẫu cho Tìm kiếm văn bản với Dot Net Regex sử dụng Aspose.PDF cho .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo đối tượng Regex để tìm tất cả các từ
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Mở tài liệu
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Nhận một trang cụ thể
Page page = document.Pages[1];
// Tạo đối tượng TextAbsorber để tìm tất cả các trường hợp của regex đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Chấp nhận bộ hấp thụ cho trang
page.Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các đoạn
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm văn bản bằng biểu thức chính quy .NET trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến truy cập các đoạn văn bản đã trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thực hiện tìm kiếm văn bản nâng cao trong các tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm văn bản bằng Dot Net Regex" là gì?

A: Hướng dẫn "Tìm kiếm văn bản bằng Dot Net Regex" hướng dẫn người dùng sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm văn bản trong tài liệu PDF bằng biểu thức chính quy .NET. Hướng dẫn cung cấp hướng dẫn từng bước và các mẫu mã C# để chứng minh quy trình.

#### H: Hướng dẫn này giúp ích như thế nào trong việc tìm kiếm văn bản bằng biểu thức chính quy .NET trong PDF?

A: Hướng dẫn này giúp người dùng hiểu cách tận dụng các khả năng của Aspose.PDF cho .NET để tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET trong tài liệu PDF. Bằng cách làm theo các bước và ví dụ mã được cung cấp, người dùng có thể tìm kiếm hiệu quả các mẫu văn bản khớp với biểu thức chính quy đã chỉ định của họ.

#### H: Cần có những điều kiện tiên quyết nào để làm theo hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt vào dự án của mình bằng NuGet.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn sử dụng các tính năng của thư viện để tìm kiếm và làm việc với các tài liệu PDF.

#### H: Tôi có thể sử dụng hướng dẫn này để tìm kiếm bất kỳ loại văn bản cụ thể nào bằng biểu thức chính quy .NET không?

 A: Có, hướng dẫn này cung cấp hướng dẫn về cách tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET trong tài liệu PDF. Bạn có thể tùy chỉnh`.NET Regex` đối tượng để xác định mẫu tìm kiếm cụ thể mà bạn muốn sử dụng.

#### H: Làm thế nào để chỉ định mẫu biểu thức chính quy .NET để tìm kiếm trong hướng dẫn này?

 A: Để chỉ định mẫu biểu thức chính quy .NET mà bạn muốn tìm kiếm, hãy tạo một`.NET Regex` đối tượng và thiết lập mẫu của nó bằng cú pháp biểu thức chính quy thích hợp. Thay thế mặc định`@"[\S]+"` trong mã hướng dẫn với biểu thức chính quy bạn mong muốn.

#### H: Làm thế nào để lấy lại các thuộc tính của đoạn văn bản đã trích xuất?

 A: Sau khi chấp nhận`TextFragmentAbsorber` đối với một trang cụ thể của PDF, bạn có thể lấy lại các đoạn văn bản đã trích xuất bằng cách sử dụng`TextFragments` thuộc tính của đối tượng absorber. Điều này cung cấp quyền truy cập vào bộ sưu tập các đoạn văn bản khớp với biểu thức chính quy .NET đã chỉ định.

#### H: Tôi có thể tùy chỉnh mã để thực hiện các hành động bổ sung trên mỗi đoạn văn bản được trích xuất không?

A: Chắc chắn rồi. Mã mẫu của hướng dẫn bao gồm một vòng lặp để lặp qua các đoạn văn bản đã lấy được. Bạn có thể tùy chỉnh mã trong vòng lặp này để thực hiện các hành động bổ sung trên mỗi đoạn văn bản đã trích xuất dựa trên yêu cầu của dự án.

#### H: Làm thế nào để lưu tài liệu PDF đã chỉnh sửa sau khi trích xuất các đoạn văn bản?

A: Hướng dẫn này chủ yếu tập trung vào việc tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET và truy xuất các đoạn văn bản. Nếu bạn có ý định sửa đổi PDF, bạn có thể tham khảo tài liệu Aspose.PDF khác để tìm hiểu cách thao tác và lưu tài liệu dựa trên nhu cầu cụ thể của bạn.