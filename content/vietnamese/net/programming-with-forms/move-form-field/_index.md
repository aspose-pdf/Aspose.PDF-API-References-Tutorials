---
title: Di chuyển trường biểu mẫu
linktitle: Di chuyển trường biểu mẫu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng di chuyển các trường biểu mẫu trong tài liệu PDF của bạn bằng Aspose.PDF cho .NET.
type: docs
weight: 200
url: /vi/net/programming-with-forms/move-form-field/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách di chuyển trường biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của mình:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu

Tải tài liệu PDF hiện có:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Bước 3: Lấy trường biểu mẫu

Lấy trường biểu mẫu bạn muốn di chuyển:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Bước 4: Thay đổi vị trí trường

Thay đổi vị trí của trường biểu mẫu bằng cách xác định vùng hình chữ nhật mới:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Bước 5: Lưu tài liệu đã chỉnh sửa

Lưu tài liệu PDF đã sửa đổi:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu cho Di chuyển trường biểu mẫu bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Nhận một trường
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Sửa đổi vị trí trường
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Lưu tài liệu đã sửa đổi
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách di chuyển trường biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng điều hướng đến một trường cụ thể và thay đổi vị trí của nó nếu cần.


### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể di chuyển nhiều trường biểu mẫu trong một tài liệu PDF bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể di chuyển nhiều trường biểu mẫu trong một tài liệu PDF bằng Aspose.PDF cho .NET. Chỉ cần lặp lại quy trình cho từng trường biểu mẫu bạn muốn di chuyển.

#### Câu hỏi: Việc di chuyển trường biểu mẫu có ảnh hưởng đến dữ liệu hoặc chức năng liên quan của nó không?

Đáp: Không, việc di chuyển trường biểu mẫu không ảnh hưởng đến dữ liệu hoặc chức năng liên quan của nó. Trường biểu mẫu giữ lại tất cả các thuộc tính và giá trị của nó sau khi được di chuyển đến vị trí mới.

#### Câu hỏi: Làm cách nào tôi có thể xác định tọa độ chính xác cho vị trí mới của trường biểu mẫu?

 Đáp: Bạn có thể chỉ định vị trí mới bằng cách sử dụng`Aspose.Pdf.Rectangle` class, trong đó bạn xác định tọa độ X và Y của góc trên bên trái và tọa độ X và Y của góc dưới cùng bên phải của khu vực hình chữ nhật.

#### Câu hỏi: Aspose.PDF cho .NET có tương thích với cả môi trường Windows và Linux không?

Trả lời: Có, Aspose.PDF cho .NET tương thích với cả môi trường Windows và Linux, mang lại sự linh hoạt cho các nhà phát triển khi làm việc trong hệ điều hành ưa thích của họ.