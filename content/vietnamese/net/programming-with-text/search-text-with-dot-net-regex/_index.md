---
title: Tìm kiếm văn bản với Dot Net Regex
linktitle: Tìm kiếm văn bản với Dot Net Regex
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 480
url: /vi/net/programming-with-text/search-text-with-dot-net-regex/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm văn bản bằng cách sử dụng các biểu thức chính quy .NET trong tài liệu PDF. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

## Điều kiện tiên quyết

Trước khi tiếp tục với hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể lấy nó từ trang web Aspose hoặc sử dụng NuGet để cài đặt nó trong dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm các lệnh sử dụng sau vào đầu tệp C# của bạn để nhập các không gian tên được yêu cầu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` Biến đổi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo đối tượng .NET Regex

 Tạo một`.NET Regex` đối tượng để xác định mẫu tìm kiếm:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Thay thế`@"[\S]+"` với mẫu biểu thức chính quy mong muốn của bạn.

## Bước 5: Tải tài liệu PDF

 Tải tài liệu PDF bằng cách sử dụng`Document` lớp học:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Thay thế`"SearchTextRegex.pdf"` bằng tên thật của tệp PDF của bạn.

## Bước 6: Nhận một trang cụ thể

Nhận trang mong muốn của tài liệu:

```csharp
Page page = document.Pages[1];
```

 Thay thế`1` với số trang mong muốn (chỉ mục dựa trên 1).

## Bước 7: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các phiên bản của biểu thức chính quy đầu vào:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Bước 8: Chấp nhận bộ hấp thụ cho trang

Chấp nhận bộ hấp thụ cho trang:

```csharp
page.Accept(textFragmentAbsorber);
```

## Bước 9: Truy xuất các đoạn văn bản đã trích xuất

Lấy các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tài sản của`TextFragmentAbsorber` sự vật:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Bước 10: Lặp lại các đoạn văn bản

Lặp lại các đoạn văn bản được truy xuất và thực hiện các hành động mong muốn:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Sửa đổi mã trong vòng lặp để thực hiện các hành động tiếp theo trên từng đoạn văn bản nếu cần.

### Mã nguồn mẫu cho Văn bản tìm kiếm bằng Dot Net Regex bằng Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo đối tượng Regex để tìm tất cả các từ
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Mở tài liệu
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Nhận một trang cụ thể
Page page = document.Pages[1];
// Tạo đối tượng TextAbsorber để tìm tất cả các phiên bản của biểu thức chính quy đầu vào
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Chấp nhận bộ hấp thụ cho trang
page.Accept(textFragmentAbsorber);
// Lấy các đoạn văn bản được trích xuất
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Lặp lại các mảnh vỡ
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến truy cập các đoạn văn bản được trích xuất. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thực hiện tìm kiếm văn bản nâng cao trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Tìm kiếm văn bản bằng Dot Net Regex" là gì?

Đáp: Hướng dẫn "Tìm kiếm văn bản bằng Dot Net Regex" nhằm mục đích hướng dẫn người dùng sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm văn bản trong tài liệu PDF bằng cách sử dụng biểu thức chính quy .NET. Hướng dẫn này cung cấp hướng dẫn từng bước và mẫu mã C# để minh họa quy trình.

#### Hỏi: Hướng dẫn này giúp ích như thế nào trong việc tìm kiếm văn bản bằng cách sử dụng biểu thức chính quy .NET trong tệp PDF?

Đáp: Hướng dẫn này giúp người dùng hiểu cách tận dụng các khả năng của Aspose.PDF dành cho .NET để tìm kiếm văn bản bằng cách sử dụng các biểu thức chính quy .NET trong tài liệu PDF. Bằng cách làm theo các bước được cung cấp và ví dụ về mã, người dùng có thể tìm kiếm hiệu quả các mẫu văn bản khớp với các biểu thức chính quy đã chỉ định của họ.

#### Câu hỏi: Cần có những điều kiện tiên quyết nào để thực hiện theo hướng dẫn này?

Đáp: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc cài đặt nó trong dự án của bạn bằng NuGet.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET. Điều này sẽ cho phép bạn sử dụng các tính năng của thư viện để tìm kiếm và làm việc với các tài liệu PDF.

#### Hỏi: Tôi có thể sử dụng hướng dẫn này để tìm kiếm bất kỳ loại văn bản cụ thể nào bằng cách sử dụng biểu thức chính quy .NET không?

 Đáp: Có, hướng dẫn này cung cấp hướng dẫn về cách tìm kiếm văn bản bằng cách sử dụng các biểu thức chính quy .NET trong tài liệu PDF. Bạn có thể tùy chỉnh`.NET Regex` đối tượng để xác định mẫu tìm kiếm cụ thể mà bạn muốn sử dụng.

#### Câu hỏi: Làm cách nào để chỉ định mẫu biểu thức chính quy .NET cần tìm kiếm trong hướng dẫn này?

 Đáp: Để chỉ định mẫu biểu thức chính quy .NET mà bạn muốn tìm kiếm, hãy tạo một`.NET Regex` đối tượng và đặt mẫu của nó bằng cú pháp biểu thức chính quy thích hợp. Thay thế mặc định`@"[\S]+"` trong mã của hướng dẫn bằng biểu thức chính quy mà bạn mong muốn.

#### Câu hỏi: Làm cách nào để truy xuất thuộc tính của các đoạn văn bản được trích xuất?

 A: Sau khi chấp nhận`TextFragmentAbsorber` đối với một trang cụ thể của PDF, bạn có thể truy xuất các đoạn văn bản được trích xuất bằng cách sử dụng`TextFragments` tính chất của vật hấp thụ. Điều này cung cấp quyền truy cập vào một tập hợp các đoạn văn bản khớp với biểu thức chính quy .NET được chỉ định.

#### Câu hỏi: Tôi có thể tùy chỉnh mã để thực hiện các hành động bổ sung trên từng đoạn văn bản được trích xuất không?

Đ: Chắc chắn rồi. Mã mẫu của hướng dẫn này bao gồm một vòng lặp để lặp qua các đoạn văn bản được truy xuất. Bạn có thể tùy chỉnh mã trong vòng lặp này để thực hiện các hành động bổ sung trên từng đoạn văn bản được trích xuất dựa trên yêu cầu dự án của bạn.

#### Hỏi: Làm cách nào để lưu tài liệu PDF đã sửa đổi sau khi trích xuất các đoạn văn bản?

Đáp: Hướng dẫn này chủ yếu tập trung vào việc tìm kiếm văn bản bằng cách sử dụng các biểu thức chính quy .NET và truy xuất các đoạn văn bản. Nếu bạn có ý định sửa đổi tệp PDF, bạn có thể tham khảo tài liệu Aspose.PDF khác để tìm hiểu cách thao tác và lưu tài liệu dựa trên nhu cầu cụ thể của bạn.