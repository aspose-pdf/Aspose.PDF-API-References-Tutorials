---
title: Nhận tất cả các phông chữ trong tệp PDF
linktitle: Nhận tất cả các phông chữ trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để lấy tất cả phông chữ được sử dụng trong tệp PDF theo chương trình với hướng dẫn từng bước và mã ví dụ này.
type: docs
weight: 160
url: /vi/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với tệp PDF theo chương trình. Một trong những tính năng mà nó cung cấp là khả năng lấy tất cả các phông chữ được sử dụng trong tệp PDF. Điều này có thể hữu ích nếu bạn cần phân tích hoặc thao tác theo chương trình các phông chữ trong tệp PDF.

Trong hướng dẫn này, chúng ta sẽ thảo luận về cách sử dụng Aspose.PDF cho .NET để lấy tất cả các phông chữ được sử dụng trong tài liệu PDF. Chúng tôi sẽ cung cấp hướng dẫn từng bước về cách thực hiện việc này, cùng với mã nguồn ví dụ.

## Bước 1: Tạo một ứng dụng C# Console mới
Để bắt đầu, hãy tạo một Ứng dụng Console C# mới trong Visual Studio. Bạn có thể đặt tên tùy ý. Sau khi dự án được tạo, bạn cần thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập không gian tên Aspose.PDF
Thêm dòng mã sau vào đầu tệp C# của bạn để nhập không gian tên Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Bước 3: Tải tài liệu PDF
Tải tài liệu PDF mà bạn muốn lấy phông chữ:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 4: Lấy tất cả các phông chữ
Lấy tất cả các phông chữ được sử dụng trong tài liệu PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Bước 5: In tất cả các phông chữ
In tất cả các phông chữ được sử dụng trong tài liệu PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Mã nguồn ví dụ cho Get All Fonts sử dụng Aspose.PDF cho .NET
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã thảo luận về cách lấy tất cả các phông chữ được sử dụng trong tài liệu PDF bằng Aspose.PDF cho .NET. Việc lấy tất cả các phông chữ được sử dụng trong tài liệu PDF có thể hữu ích nếu bạn cần phân tích hoặc thao tác theo chương trình các phông chữ trong tài liệu PDF. Aspose.PDF cho .NET cung cấp API đơn giản và dễ sử dụng để làm việc với tài liệu PDF, bao gồm lấy tất cả các phông chữ được sử dụng trong tài liệu PDF.

### Câu hỏi thường gặp

#### H: Tại sao tôi cần phải có tất cả phông chữ được sử dụng trong tài liệu PDF?

A: Việc thu thập tất cả phông chữ được sử dụng trong tài liệu PDF có thể hữu ích nếu bạn cần phân tích hoặc thao tác phông chữ theo chương trình cho nhiều mục đích khác nhau, chẳng hạn như thay thế phông chữ hoặc tùy chỉnh phông chữ.

#### H: Làm thế nào tôi có thể lấy được tất cả phông chữ được sử dụng trong tài liệu PDF bằng Aspose.PDF cho .NET?

 A: Bạn có thể lấy tất cả các phông chữ được sử dụng trong tài liệu PDF bằng cách sử dụng Aspose.PDF cho .NET bằng cách gọi`GetAllFonts` phương pháp của`FontUtilities` lớp. Phương pháp này trả về một mảng`Aspose.Pdf.Text.Font` đối tượng đại diện cho phông chữ được sử dụng trong tài liệu PDF.

#### H: Tôi có thể lọc phông chữ dựa trên các tiêu chí nhất định không?

A: Có, bạn có thể lọc phông chữ dựa trên các tiêu chí nhất định bằng Aspose.PDF cho .NET. Sau khi có tất cả các phông chữ, bạn có thể phân tích phông chữ theo chương trình và áp dụng logic lọc khi cần.

#### H: Aspose.PDF cho .NET có tương thích với nhiều định dạng phông chữ khác nhau không?

A: Có, Aspose.PDF for .NET tương thích với nhiều định dạng phông chữ, bao gồm phông chữ TrueType, OpenType và Type 1. Nó có thể hoạt động với nhiều định dạng phông chữ khác nhau và xử lý chúng trong quá trình thao tác tài liệu PDF.