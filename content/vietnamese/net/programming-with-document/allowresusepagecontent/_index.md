---
title: Cho phép sử dụng lại nội dung trang
linktitle: Cho phép sử dụng lại nội dung trang
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tối ưu hóa tệp PDF bằng cách bật tính năng "Cho phép sử dụng lại nội dung trang" bằng Aspose.PDF cho .NET. Giảm kích thước tập tin và cải thiện hiệu suất.
type: docs
weight: 50
url: /vi/net/programming-with-document/allowresusepagecontent/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách bật tính năng "Cho phép sử dụng lại nội dung trang" bằng Aspose.PDF cho .NET. Tính năng này tối ưu hóa tài liệu PDF bằng cách sử dụng lại nội dung trang, giảm kích thước tệp và cải thiện hiệu suất. Thực hiện theo hướng dẫn từng bước dưới đây:

## Bước 1: Tải tài liệu PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Bước 2: Đặt tùy chọn AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Bước 3: Tối ưu hóa tài liệu PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Bước 4: Lưu tài liệu đã cập nhật

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Bước 5: Kiểm tra việc giảm kích thước file

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Chúc mừng! Bạn đã cho phép sử dụng lại thành công nội dung trang trong tài liệu PDF của mình.

### Mã nguồn ví dụ về Cho phép tái sử dụng nội dung trang bằng Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Đặt tùy chọn AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Tối ưu hóa tài liệu PDF bằng OptimizeOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Giờ đây, bạn có thể tối ưu hóa tài liệu PDF của mình một cách hiệu quả bằng cách cho phép sử dụng lại nội dung trang.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách bật tính năng "Cho phép sử dụng lại nội dung trang" bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp và sử dụng mã nguồn C#, bạn có thể tối ưu hóa tài liệu PDF của mình một cách hiệu quả bằng cách cho phép sử dụng lại nội dung trang. Việc tối ưu hóa này giúp tạo ra các tệp PDF nhỏ hơn, có thể dẫn đến thời gian tải nhanh hơn và cải thiện hiệu suất khi xử lý các tài liệu PDF lớn. Aspose.PDF for .NET cung cấp giải pháp mạnh mẽ và thân thiện với người dùng để tối ưu hóa PDF, cho phép bạn tạo các tệp PDF hiệu quả và chất lượng cao một cách dễ dàng.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của việc bật tính năng "Cho phép sử dụng lại nội dung trang" trong tài liệu PDF là gì?

Đáp: Việc bật tính năng "Cho phép sử dụng lại nội dung trang" trong tài liệu PDF sẽ tối ưu hóa tệp bằng cách sử dụng lại nội dung trang, giúp giảm kích thước tệp và cải thiện hiệu suất tổng thể. Việc tối ưu hóa này giúp tạo ra các tệp PDF nhỏ hơn mà không ảnh hưởng đến chất lượng nội dung.

#### Hỏi: Tính năng "Cho phép sử dụng lại nội dung trang" hoạt động như thế nào?

Trả lời: Khi tính năng "Cho phép sử dụng lại nội dung trang" được bật, các đối tượng trang giống hệt nhau trong tài liệu PDF sẽ được chia sẻ và sử dụng lại thay vì bị trùng lặp cho mỗi lần xuất hiện. Việc chia sẻ nội dung trang này làm giảm đáng kể kích thước tệp tổng thể.

#### Câu hỏi: Tôi có thể hoàn nguyên việc tối ưu hóa và khôi phục tài liệu gốc không?

Trả lời: Không, sau khi thực hiện tối ưu hóa với "Cho phép sử dụng lại nội dung trang" và tài liệu PDF được lưu, các thay đổi sẽ là vĩnh viễn. Bạn nên sao lưu tài liệu gốc trước khi thực hiện bất kỳ tối ưu hóa nào.

#### Hỏi: Việc bật tính năng này có ảnh hưởng đến hình thức hoặc nội dung trực quan của tài liệu PDF không?

Trả lời: Việc bật tính năng "Cho phép sử dụng lại nội dung trang" không ảnh hưởng đến hình thức trực quan hoặc nội dung của tài liệu PDF. Nó chỉ tối ưu hóa cấu trúc bên trong của tệp để giảm sự dư thừa và nâng cao hiệu quả.

#### Câu hỏi: Aspose.PDF cho .NET có phải là giải pháp đáng tin cậy để tối ưu hóa và thao tác với PDF không?

Trả lời: Có, Aspose.PDF cho .NET là một thư viện đáng tin cậy và giàu tính năng để tối ưu hóa và thao tác PDF. Nó cung cấp các tùy chọn mở rộng để tối ưu hóa tệp PDF, bao gồm giảm kích thước tệp, loại bỏ các tài nguyên không sử dụng và nâng cao hiệu suất tổng thể.