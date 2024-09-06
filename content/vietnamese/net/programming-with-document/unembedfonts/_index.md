---
title: Bỏ nhúng phông chữ và tối ưu hóa tệp PDF
linktitle: Bỏ nhúng phông chữ và tối ưu hóa tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để lấy Phông chữ Unembed và tối ưu hóa tệp PDF. Hướng dẫn từng bước.
type: docs
weight: 370
url: /vi/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ cung cấp nhiều tính năng để làm việc với các tài liệu PDF. Một trong những tính năng của nó là lấy các phông chữ không nhúng từ một tài liệu PDF. Điều này có thể hữu ích nếu bạn cần trích xuất phông chữ từ một tài liệu PDF và sử dụng chúng trong các ứng dụng khác.

chúng tôi sẽ cung cấp hướng dẫn từng bước để giải thích mã nguồn C# sau đây về tính năng lấy phông chữ chưa nhúng của Aspose.PDF cho .NET.

## Bước 1: Đặt đường dẫn đến thư mục tài liệu

Trước khi bắt đầu, chúng ta cần thiết lập đường dẫn đến thư mục chứa tài liệu PDF của chúng ta. Chúng ta sẽ lưu trữ đường dẫn này trong một biến có tên là "dataDir".

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 2: Mở Tài liệu PDF

 Bước đầu tiên là tải tài liệu PDF mà bạn muốn thực hiện việc này, sử dụng`Document` lớp Aspose.PDF cho .NET. Đoạn mã sau đây cho thấy cách tải tài liệu PDF:

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Bước 3: Thiết lập tùy chọn UnembedFonts

 Để lấy phông chữ chưa nhúng từ tài liệu PDF, bạn cần thiết lập`UnembedFonts` tùy chọn để`true` . Tùy chọn này có sẵn trong`OptimizationOptions` lớp. Đoạn mã sau đây cho thấy cách thiết lập`UnembedFonts` lựa chọn:

```csharp
// Đặt tùy chọn UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Bước 4: Tối ưu hóa tài liệu PDF

 Sau khi thiết lập`UnembedFonts` tùy chọn, bạn có thể tối ưu hóa tài liệu PDF bằng cách sử dụng`OptimizeResources` phương pháp của`Document` lớp. Đoạn mã sau đây cho thấy cách tối ưu hóa tài liệu PDF:

```csharp
// Tối ưu hóa tài liệu PDF bằng OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Bước 5: Lưu tài liệu đã cập nhật

 Sau khi tài liệu PDF được tối ưu hóa, bạn có thể lưu tài liệu đã cập nhật bằng cách sử dụng`Save` phương pháp của`Document`lớp. Đoạn mã sau đây cho biết cách lưu tài liệu đã cập nhật:

```csharp
// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Bước 6: Lấy kích thước tệp gốc và tệp đã giảm

 Cuối cùng, bạn có thể lấy được kích thước tệp gốc và kích thước tệp đã giảm của tài liệu PDF bằng cách sử dụng`FileInfo` lớp System.IO. Đoạn mã sau đây cho thấy cách lấy kích thước tệp gốc và kích thước tệp đã giảm:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Mã nguồn ví dụ để lấy phông chữ không nhúng bằng Aspose.PDF cho .NET

Sau đây là mã nguồn ví dụ đầy đủ để lấy phông chữ không nhúng từ tài liệu PDF bằng Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Đặt tùy chọn UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Tối ưu hóa tài liệu PDF bằng OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách sử dụng Aspose.PDF cho .NET để lấy phông chữ không nhúng từ tài liệu PDF. Bằng cách làm theo hướng dẫn từng bước, bạn có thể dễ dàng triển khai tính năng này trong các ứng dụng C# của mình. Việc không nhúng phông chữ có thể có lợi khi bạn cần làm việc riêng với các phông chữ đã trích xuất hoặc đảm bảo sử dụng phông chữ nhất quán trên nhiều nền tảng khác nhau.

## Câu hỏi thường gặp

#### H: Mục đích của việc hủy nhúng phông chữ khỏi tài liệu PDF là gì?

A: Việc bỏ nhúng phông chữ khỏi tài liệu PDF cho phép bạn trích xuất phông chữ nhúng và sử dụng chúng trong các ứng dụng khác. Điều này có thể hữu ích để đảm bảo hiển thị phông chữ nhất quán và giữ nguyên giao diện trực quan của tài liệu.

#### H: Làm thế nào để chỉ định đường dẫn đến thư mục tài liệu trong mã C#?

 A: Để chỉ định đường dẫn đến thư mục tài liệu, hãy thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã có đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

####  Q: Cái gì làm`UnembedFonts` option do, and where is it set?

 A: Cái`UnembedFonts` tùy chọn, có sẵn trong`OptimizationOptions` lớp, bật hoặc tắt việc bỏ nhúng phông chữ khỏi tài liệu PDF. Để đặt tùy chọn này thành`true`, sử dụng mã sau:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### H: Tôi có thể hoàn nguyên những thay đổi đã thực hiện trong quá trình tối ưu hóa không?

A: Aspose.PDF for .NET không thực hiện thay đổi vĩnh viễn đối với tài liệu PDF gốc trong quá trình tối ưu hóa. Quá trình tối ưu hóa được thực hiện trên một bản sao của tài liệu, giữ nguyên bản gốc.

#### H: Làm thế nào tôi có thể kiểm tra kích thước file gốc và file đã giảm sau khi tối ưu hóa?

 A: Bạn có thể sử dụng`FileInfo` lớp của`System.IO` để có được kích thước tệp gốc và tệp đã giảm. Sau đây là đoạn mã ví dụ để đạt được điều này:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```