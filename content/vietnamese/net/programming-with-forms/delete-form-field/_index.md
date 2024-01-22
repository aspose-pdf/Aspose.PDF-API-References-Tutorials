---
title: Xóa trường biểu mẫu trong tài liệu PDF
linktitle: Xóa trường biểu mẫu trong tài liệu PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng xóa các trường biểu mẫu không mong muốn trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-forms/delete-form-field/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách xóa trường biểu mẫu bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Trước tiên, hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở tài liệu

Mở tài liệu PDF hiện có:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Bước 3: Xóa một trường cụ thể

Xóa một trường biểu mẫu cụ thể bằng tên của nó:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Bước 4: Lưu tài liệu đã chỉnh sửa

Lưu tài liệu PDF đã sửa đổi:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu để Xóa Trường biểu mẫu bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Xóa một trường cụ thể theo tên
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Lưu tài liệu đã sửa đổi
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách xóa trường biểu mẫu bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng xóa các trường biểu mẫu không mong muốn khỏi tài liệu PDF của mình bằng Aspose.PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể xóa nhiều trường biểu mẫu cùng một lúc bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể xóa nhiều trường biểu mẫu cùng một lúc bằng Aspose.PDF cho .NET. Đơn giản chỉ cần gọi`Delete` phương thức cho từng trường biểu mẫu bạn muốn xóa.

#### Câu hỏi: Làm cách nào để kiểm tra xem trường biểu mẫu có tồn tại hay không trước khi thử xóa nó?

 Trả lời: Bạn có thể kiểm tra xem trường biểu mẫu có tồn tại hay không trước khi thử xóa nó bằng cách sử dụng`Contains` phương pháp của`Form` tài sản. Ví dụ:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### Hỏi: Điều gì xảy ra nếu tôi cố xóa trường biểu mẫu không tồn tại trong tài liệu PDF?

 Đáp: Nếu bạn cố xóa một trường biểu mẫu không tồn tại trong tài liệu PDF,`Delete` phương thức sẽ không đưa ra lỗi hoặc ngoại lệ. Đơn giản là nó sẽ không làm gì cả vì không có trường nào để xóa.

#### Câu hỏi: Tôi có thể xóa các loại trường biểu mẫu khác nhau, chẳng hạn như trường văn bản, hộp kiểm và nút radio không?

 Đáp: Có, bạn có thể xóa các loại trường biểu mẫu khác nhau, chẳng hạn như trường văn bản, hộp kiểm và nút radio, bằng cách sử dụng cùng một loại`Delete` phương thức trong Aspose.PDF cho .NET. Chỉ cần chuyển tên của trường bạn muốn xóa làm tham số cho phương thức.

#### Câu hỏi: Có thể hoàn tác việc xóa trường biểu mẫu trong tài liệu PDF không?

Trả lời: Không, sau khi xóa trường biểu mẫu bằng Aspose.PDF dành cho .NET, bạn không thể hoàn tác việc này theo chương trình. Bạn nên tạo bản sao lưu của tài liệu PDF trước khi thực hiện bất kỳ thay đổi nào đối với tài liệu đó để bạn có thể hoàn nguyên về tài liệu gốc nếu cần.