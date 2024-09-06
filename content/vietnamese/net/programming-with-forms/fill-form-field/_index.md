---
title: Điền vào trường mẫu PDF
linktitle: Điền vào trường mẫu PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng điền vào các trường biểu mẫu trong tài liệu PDF của bạn bằng Aspose.PDF cho .NET.
type: docs
weight: 80
url: /vi/net/programming-with-forms/fill-form-field/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách điền trường biểu mẫu bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# từng bước để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Trước tiên, hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở tài liệu

Mở tài liệu PDF hiện có:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Bước 3: Lấy trường

Lấy trường biểu mẫu mong muốn (trong ví dụ này, chúng tôi sử dụng trường "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Bước 4: Thay đổi giá trị trường

Sửa đổi giá trị trường bằng giá trị mong muốn:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Bước 5: Lưu tài liệu đã cập nhật

Lưu tài liệu PDF đã cập nhật:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu cho Trường điền biểu mẫu sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Nhận một cánh đồng
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Sửa đổi giá trị trường
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách điền trường biểu mẫu bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng thay đổi giá trị trường biểu mẫu trong tài liệu PDF của mình bằng Aspose.PDF.

### Câu hỏi thường gặp

#### H: Tôi có thể điền nhiều trường biểu mẫu trong một tài liệu PDF bằng Aspose.PDF cho .NET không?

A: Có, bạn có thể điền nhiều trường biểu mẫu vào một tài liệu PDF bằng Aspose.PDF cho .NET. Sau khi mở tài liệu PDF, bạn có thể lấy từng trường biểu mẫu riêng lẻ và sửa đổi giá trị của trường đó khi cần.

#### H: Làm thế nào để tìm tên các trường biểu mẫu trong tài liệu PDF?

 A: Để tìm tên của các trường biểu mẫu trong tài liệu PDF, bạn có thể lặp lại qua`pdfDocument.Form.Fields` bộ sưu tập. Mỗi trường biểu mẫu có một`FullName` thuộc tính chứa tên duy nhất của nó. Bạn có thể sử dụng các tên này để xác định và sửa đổi các trường biểu mẫu cụ thể.

#### H: Nếu trường biểu mẫu tôi muốn điền không tồn tại trong tài liệu PDF thì sao?

 A: Nếu trường biểu mẫu bạn muốn điền không tồn tại trong tài liệu PDF, hãy thử truy cập vào trường đó bằng`pdfDocument.Form["fieldName"]`sẽ trả về null. Do đó, điều cần thiết là phải đảm bảo rằng trường biểu mẫu tồn tại trước khi cố gắng điền vào. Bạn có thể thêm các trường biểu mẫu mới theo chương trình bằng cách sử dụng Aspose.PDF cho .NET nếu cần.

#### H: Tôi có thể điền dữ liệu động từ cơ sở dữ liệu hoặc nguồn dữ liệu khác vào các trường biểu mẫu không?

A: Có, bạn có thể điền dữ liệu động từ cơ sở dữ liệu hoặc bất kỳ nguồn dữ liệu nào khác vào trường biểu mẫu. Trước khi đặt giá trị trường, hãy truy xuất dữ liệu từ nguồn và sử dụng dữ liệu đó để đặt giá trị của trường biểu mẫu cho phù hợp.

#### H: Có bất kỳ hạn chế nào khi điền các trường biểu mẫu trong tài liệu PDF dựa trên XFA không?

A: Việc điền các trường biểu mẫu trong tài liệu PDF dựa trên XFA (Kiến trúc biểu mẫu XML) có thể có một số hạn chế do cấu trúc phức tạp của biểu mẫu XFA. Aspose.PDF cho .NET hỗ trợ điền các trường biểu mẫu trong biểu mẫu XFA, nhưng một số thuộc tính trường biểu mẫu cụ thể dành riêng cho biểu mẫu XFA có thể không được hỗ trợ đầy đủ trong AcroForms.