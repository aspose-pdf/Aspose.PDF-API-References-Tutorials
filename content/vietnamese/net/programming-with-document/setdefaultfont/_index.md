---
title: Đặt Phông chữ Mặc định Trong Tệp PDF
linktitle: Đặt Phông chữ Mặc định Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách đặt phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này. Hoàn hảo cho các nhà phát triển muốn cải thiện tài liệu PDF.
type: docs
weight: 280
url: /vi/net/programming-with-document/setdefaultfont/
---
## Giới thiệu

Bạn đã bao giờ mở một tài liệu PDF và thấy rằng phông chữ bị thiếu hoặc không hiển thị đúng chưa? Điều đó có thể gây bực bội, phải không? Vâng, đừng lo lắng! Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách đặt phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET. Thư viện mạnh mẽ này cho phép bạn dễ dàng thao tác các tài liệu PDF và đặt phông chữ mặc định chỉ là một trong nhiều tính năng mà nó cung cấp. Vì vậy, hãy đội mũ lập trình của bạn và bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, bạn cần chuẩn bị một số thứ sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Đây là IDE tốt nhất cho phát triển .NET.
2.  Aspose.PDF cho .NET: Bạn sẽ cần tải xuống và cài đặt thư viện Aspose.PDF. Bạn có thể tìm thấy nó[đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Một chút quen thuộc với lập trình C# sẽ giúp bạn hiểu rõ hơn các ví dụ chúng tôi sẽ đề cập.

## Nhập gói

Để bắt đầu, bạn sẽ cần nhập các gói cần thiết vào dự án C# của mình. Sau đây là cách bạn có thể thực hiện:

1. Mở dự án Visual Studio của bạn.
2. Nhấp chuột phải vào dự án của bạn trong Solution Explorer và chọn "Quản lý gói NuGet".
3.  Tìm kiếm`Aspose.PDF` và cài đặt phiên bản mới nhất.

Sau khi cài đặt gói, bạn đã sẵn sàng để bắt đầu viết mã!

## Bước 1: Thiết lập dự án của bạn

### Tạo một dự án mới

Trước tiên, hãy tạo một dự án C# mới trong Visual Studio:

- Mở Visual Studio và chọn "Tạo dự án mới".
- Chọn "Console App (.NET Core)" và nhấp vào "Next".
-  Đặt tên cho dự án của bạn (ví dụ:`AsposePdfExample`) và nhấp vào "Tạo".

### Thêm Sử dụng Chỉ thị

 Bây giờ, hãy thêm các chỉ thị sử dụng cần thiết vào đầu`Program.cs` tài liệu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

Các chỉ thị này sẽ cho phép bạn truy cập các lớp và phương thức Aspose.PDF.

## Bước 2: Tải Tài liệu PDF

### Chỉ định Đường dẫn Tài liệu

Tiếp theo, bạn sẽ cần chỉ định đường dẫn đến tài liệu PDF mà bạn muốn làm việc. Sau đây là cách thực hiện:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Thay thế bằng thư mục thực tế của bạn
string documentName = Path.Combine(dataDir, "input.pdf");
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi lưu trữ tệp PDF của bạn.

### Tải Tài liệu

Bây giờ, hãy tải tài liệu PDF hiện có:

```csharp
using (FileStream fs = new FileStream(documentName, FileMode.Open))
{
    Document document = new Document(fs);
}
```

 Đoạn mã này mở tệp PDF và tạo một`Document` đối tượng mà bạn có thể thao tác.

## Bước 3: Đặt Phông chữ Mặc định

### Tạo PdfSaveOptions

 Bây giờ đến phần thú vị! Bạn sẽ cần tạo một phiên bản của`PdfSaveOptions` để chỉ định phông chữ mặc định:

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
```

### Chỉ định Tên Phông chữ Mặc định

Tiếp theo, bạn sẽ đặt tên phông chữ mặc định. Đối với ví dụ này, chúng tôi sẽ sử dụng "Arial":

```csharp
pdfSaveOptions.DefaultFontName = "Arial";
```

Dòng này yêu cầu Aspose.PDF sử dụng Arial làm phông chữ mặc định cho bất kỳ văn bản nào không có phông chữ được chỉ định.

## Bước 4: Lưu tài liệu

Cuối cùng, đã đến lúc lưu tài liệu PDF đã chỉnh sửa với phông chữ mặc định mới:

```csharp
document.Save(Path.Combine(dataDir, "output_out.pdf"), pdfSaveOptions);
```

 Dòng này lưu tài liệu dưới dạng`output_out.pdf` trong thư mục được chỉ định.

## Phần kết luận

Và bạn đã có nó! Bạn đã thiết lập thành công phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET. Tính năng đơn giản nhưng mạnh mẽ này có thể giúp đảm bảo rằng tài liệu của bạn trông chính xác như bạn muốn, ngay cả khi thiếu phông chữ. Vì vậy, lần tới khi bạn gặp phải sự cố phông chữ trong tệp PDF, bạn sẽ biết chính xác phải làm gì!

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF theo cách lập trình.

### Tôi có thể sử dụng phông chữ khác ngoài Arial không?
Có, bạn có thể chỉ định bất kỳ phông chữ nào được cài đặt trên hệ thống của bạn làm phông chữ mặc định.

### Aspose.PDF có miễn phí sử dụng không?
Aspose.PDF cung cấp bản dùng thử miễn phí, nhưng để có đầy đủ chức năng, bạn sẽ cần phải mua giấy phép.

### Tôi có thể tìm thêm tài liệu ở đâu?
 Bạn có thể tìm thấy tài liệu toàn diện[đây](https://reference.aspose.com/pdf/net/).

### Làm thế nào để tôi nhận được hỗ trợ cho Aspose.PDF?
 Bạn có thể nhận được hỗ trợ thông qua diễn đàn Aspose[đây](https://forum.aspose.com/c/pdf/10).