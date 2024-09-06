---
title: Hộp văn bản
linktitle: Hộp văn bản
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo trường văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 290
url: /vi/net/programming-with-forms/text-box/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng thư viện Aspose.PDF cho .NET để tạo trường văn bản trong tài liệu PDF. Chúng tôi sẽ chỉ cho bạn cách mở tài liệu, tạo trường văn bản, tùy chỉnh thuộc tính của trường và lưu PDF đã chỉnh sửa.

## Bước 1: Cấu hình thư mục tài liệu

 Bước đầu tiên là cấu hình thư mục tài liệu nơi tệp PDF bạn muốn làm việc được đặt. Bạn có thể sử dụng`dataDir` biến để chỉ định đường dẫn thư mục.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Mở tài liệu PDF

 Trong bước này, chúng ta sẽ mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Đảm bảo rằng tệp PDF có trong thư mục tài liệu được chỉ định.

## Bước 3: Tạo trường văn bản

 Chúng tôi sẽ tạo một trường văn bản bằng cách sử dụng`TextBoxField` lớp. Bạn có thể chỉ định tọa độ vị trí và kích thước trường bằng cách sử dụng`Rectangle` lớp học.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Tùy chỉnh tọa độ, kích thước, tên một phần và giá trị trường văn bản theo nhu cầu.

## Bước 4: Tùy chỉnh thuộc tính trường văn bản

Ở bước này, chúng ta sẽ tùy chỉnh các thuộc tính của trường văn bản như đường viền, màu sắc, v.v.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Tùy chỉnh thuộc tính trường văn bản theo sở thích của bạn.

## Bước 5: Thêm trường vào tài liệu

Bây giờ chúng ta đã tạo và cấu hình trường văn bản, chúng ta có thể thêm nó vào tài liệu PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Bước 6: Lưu tệp PDF đã sửa đổi

 Cuối cùng, chúng ta có thể lưu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Hãy chắc chắn chỉ định đường dẫn đầy đủ và tên tệp cho tệp PDF đã chỉnh sửa.

### Mã nguồn mẫu cho Text Box sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//Tạo một trường
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = Đường viền mới(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Thêm trường vào tài liệu
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Lưu PDF đã sửa đổi
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng thư viện Aspose.PDF cho .NET để tạo trường văn bản trong tài liệu PDF. Bằng cách làm theo các bước được mô tả, bạn có thể tùy chỉnh các thuộc tính của trường văn bản và thêm trường này vào tài liệu khi cần. Hãy thoải mái khám phá thêm các tính năng của Aspose.PDF cho .NET để mở rộng khả năng thao tác với các tệp PDF.

### Câu hỏi thường gặp

#### H: Tôi có thể sử dụng Aspose.PDF cho .NET để tạo nhiều trường văn bản trong một tài liệu PDF không?

A: Có, bạn có thể tạo nhiều trường văn bản trong một tài liệu PDF bằng Aspose.PDF cho .NET. Chỉ cần lặp lại quy trình tạo và tùy chỉnh các trường văn bản cho từng vị trí mong muốn trong tài liệu.

#### H: Làm thế nào để tùy chỉnh giao diện của trường văn bản, chẳng hạn như kích thước phông chữ và màu sắc?

A: Bạn có thể tùy chỉnh giao diện của trường văn bản bằng cách điều chỉnh các thuộc tính của trường, chẳng hạn như kích thước phông chữ, kiểu phông chữ, màu sắc, kiểu đường viền, màu nền, v.v. Trong mã nguồn mẫu được cung cấp, chiều rộng đường viền, kiểu gạch ngang đường viền và màu văn bản được tùy chỉnh.

#### H: Có thể trích xuất văn bản do người dùng nhập từ trường văn bản đã tạo không?

A: Có, bạn có thể trích xuất văn bản do người dùng nhập từ trường văn bản đã tạo. Sau khi người dùng điền vào trường văn bản trong tài liệu PDF, bạn có thể lập trình để lấy giá trị trường bằng Aspose.PDF cho .NET.

#### H: Tôi có thể thêm trường văn bản vào tài liệu PDF hiện có mà không cần tạo tài liệu mới không?

A: Có, bạn có thể thêm trường văn bản vào tài liệu PDF hiện có mà không cần tạo tài liệu mới. Aspose.PDF for .NET cung cấp khả năng sửa đổi tài liệu PDF hiện có, bao gồm thêm trường văn bản, hộp kiểm và các thành phần biểu mẫu khác.

#### H: Aspose.PDF cho .NET có hỗ trợ các loại trường biểu mẫu khác như hộp kiểm và nút radio không?

A: Có, Aspose.PDF for .NET hỗ trợ nhiều loại trường biểu mẫu, bao gồm hộp kiểm, nút radio, danh sách thả xuống, v.v. Bạn có thể sử dụng thư viện để làm việc với nhiều loại phần tử biểu mẫu khác nhau trong tài liệu PDF.