---
title: Thay thế phông chữ bị thiếu
linktitle: Thay thế phông chữ bị thiếu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để thay thế phông chữ bị thiếu trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 260
url: /vi/net/document-conversion/replace-missing-fonts/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thay thế phông chữ bị thiếu trong tệp PDF bằng Aspose.PDF cho .NET. Khi bạn mở tệp PDF trên máy bị thiếu phông chữ cụ thể, có thể có vấn đề về hiển thị phông chữ. Trong những trường hợp như vậy, có thể thay thế font chữ bị thiếu bằng một font chữ khác có sẵn trên máy. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể thay thế các phông chữ bị thiếu trong tệp PDF.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tìm phông chữ bị thiếu
Bước đầu tiên là tìm phông chữ bị thiếu trong tệp PDF. Sử dụng mã sau đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Tìm phông chữ gốc
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Phông chữ bị thiếu trên máy đích
     // Thêm thay thế phông chữ đơn giản
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực tế nơi chứa tệp PDF của bạn.

## Bước 2: Thay thế phông chữ bị thiếu
Tiếp theo, chúng ta sẽ thay thế font chữ bị thiếu bằng một font chữ khác có sẵn. Sử dụng mã sau đây:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Chuyển đổi tệp PDF sang định dạng PDF/A và loại bỏ lỗi
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Lưu tệp PDF kết quả
pdf.Save(fileNew.FullName);
```

 Hãy chắc chắn để thay thế`"input.pdf"` với đường dẫn thực tế tới tệp PDF gốc của bạn và`"newfile_out.pdf"` với tên mong muốn cho tệp PDF kết quả.

## Bước 3: Lưu tệp PDF kết quả
Cuối cùng, chúng tôi sẽ lưu tệp PDF kết quả với phông chữ được thay thế. Sử dụng mã sau đây:

```csharp
// Lưu tệp PDF kết quả
pdf.Save(fileNew.FullName);
```

Đảm bảo rằng bạn đã đặt đường dẫn đích chính xác cho tệp PDF kết quả.

### Mã nguồn ví dụ cho Thay thế phông chữ bị thiếu bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Máy đích bị thiếu phông chữ
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước thay thế phông chữ bị thiếu trong tệp PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, bạn sẽ có thể thay thế thành công các phông chữ bị thiếu trong tệp PDF của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng C#. Nó cung cấp nhiều chức năng khác nhau, bao gồm khả năng thay thế phông chữ bị thiếu trong tệp PDF.

#### Hỏi: Tại sao tôi lại gặp phải tình trạng thiếu phông chữ trong tệp PDF?

Trả lời: Việc thiếu phông chữ trong tệp PDF có thể xảy ra khi tệp được mở trên máy chưa cài đặt các phông chữ cần thiết. Điều này có thể dẫn đến việc thay thế phông chữ, ảnh hưởng đến hình thức trực quan của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tìm và thay thế các phông chữ bị thiếu trong tệp PDF bằng Aspose.PDF cho .NET?

 Đáp: Để tìm và thay thế các phông chữ bị thiếu, bạn có thể sử dụng`FontRepository.FindFont` phương pháp để kiểm tra sự hiện diện của phông chữ được yêu cầu. Nếu phông chữ bị thiếu, bạn có thể thêm phông chữ thay thế bằng cách sử dụng`FontRepository.Substitutions` tài sản.

#### Hỏi: Tôi có thể tùy chỉnh quá trình thay thế phông chữ không?

Trả lời: Có, bạn có thể tùy chỉnh quy trình thay thế phông chữ bằng cách chỉ định một phông chữ khác để thay thế. Trong mã được cung cấp, chúng tôi đã sử dụng Arial để thay thế cho phông chữ "AgencyFB" bị thiếu nhưng bạn có thể chọn phông chữ khác tùy theo sở thích của mình.

#### Câu hỏi: Làm cách nào để đảm bảo tính chính xác của việc hiển thị phông chữ sau khi thay thế?

Trả lời: Aspose.PDF for .NET cung cấp khả năng xử lý phông chữ mạnh mẽ, đảm bảo hiển thị phông chữ chính xác sau khi thay thế. Bạn có thể xem trước tệp PDF kết quả để xác minh việc thay thế phông chữ.