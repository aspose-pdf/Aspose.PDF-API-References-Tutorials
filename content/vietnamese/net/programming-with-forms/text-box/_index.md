---
title: Hộp văn bản
linktitle: Hộp văn bản
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tạo trường văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 290
url: /vi/net/programming-with-forms/text-box/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng thư viện Aspose.PDF cho .NET để tạo trường văn bản trong tài liệu PDF. Chúng tôi sẽ chỉ cho bạn cách mở tài liệu, tạo trường văn bản, tùy chỉnh các thuộc tính của tài liệu và lưu tệp PDF đã chỉnh sửa.

## Bước 1: Cấu hình thư mục tài liệu

 Bước đầu tiên là định cấu hình thư mục tài liệu chứa tệp PDF bạn muốn làm việc. Bạn có thể dùng`dataDir` biến để chỉ định đường dẫn thư mục.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Mở tài liệu PDF

Trong bước này, chúng tôi sẽ mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Đảm bảo rằng tệp PDF có trong thư mục tài liệu được chỉ định.

## Bước 3: Tạo trường văn bản

 Chúng ta sẽ tạo một trường văn bản bằng cách sử dụng`TextBoxField` lớp học. Bạn có thể chỉ định tọa độ vị trí và kích thước trường bằng cách sử dụng`Rectangle` lớp học.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Tùy chỉnh tọa độ, kích thước, tên một phần và giá trị trường văn bản nếu cần.

## Bước 4: Tùy chỉnh thuộc tính trường văn bản

Ở bước này, chúng ta sẽ tùy chỉnh các thuộc tính của trường văn bản như đường viền, màu sắc, v.v.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Tùy chỉnh các thuộc tính của trường văn bản theo sở thích của bạn.

## Bước 5: Thêm trường vào tài liệu

Bây giờ chúng ta đã tạo và định cấu hình trường văn bản, chúng ta có thể thêm nó vào tài liệu PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Bước 6: Lưu tệp PDF đã sửa đổi

 Cuối cùng, chúng ta có thể lưu tệp PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Đảm bảo chỉ định đường dẫn và tên tệp đầy đủ cho tệp PDF đã chỉnh sửa.

### Mã nguồn mẫu cho Hộp văn bản sử dụng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Tạo một trường
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = Đường viền mới(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Thêm trường vào tài liệu
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Lưu bản PDF đã sửa đổi
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã tìm hiểu cách sử dụng thư viện Aspose.PDF cho .NET để tạo trường văn bản trong tài liệu PDF. Bằng cách làm theo các bước được mô tả, bạn có thể tùy chỉnh các thuộc tính của trường văn bản và thêm nó vào tài liệu nếu cần. Vui lòng khám phá thêm các tính năng của Aspose.PDF cho .NET để mở rộng khả năng thao tác với tệp PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET để tạo nhiều trường văn bản trong một tài liệu PDF không?

Trả lời: Có, bạn có thể tạo nhiều trường văn bản trong một tài liệu PDF bằng Aspose.PDF cho .NET. Chỉ cần lặp lại quy trình tạo và tùy chỉnh các trường văn bản cho từng vị trí mong muốn trong tài liệu.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh giao diện của trường văn bản, chẳng hạn như cỡ chữ và màu sắc?

Trả lời: Bạn có thể tùy chỉnh giao diện của trường văn bản bằng cách điều chỉnh các thuộc tính của nó, chẳng hạn như kích thước phông chữ, kiểu phông chữ, màu sắc, kiểu đường viền, màu nền, v.v. Trong mã nguồn mẫu được cung cấp, độ rộng đường viền, mẫu gạch ngang đường viền và màu văn bản được tùy chỉnh.

#### Hỏi: Có thể trích xuất văn bản do người dùng nhập từ trường văn bản đã tạo không?

Trả lời: Có, bạn có thể trích xuất văn bản do người dùng nhập từ trường văn bản đã tạo. Sau khi người dùng điền vào trường văn bản trong tài liệu PDF, bạn có thể truy xuất giá trị trường theo chương trình bằng cách sử dụng Aspose.PDF cho .NET.

#### Hỏi: Tôi có thể thêm trường văn bản vào tài liệu PDF hiện có mà không cần tạo tài liệu mới không?

Đáp: Có, bạn có thể thêm trường văn bản vào tài liệu PDF hiện có mà không cần tạo tài liệu mới. Aspose.PDF for .NET cung cấp khả năng sửa đổi các tài liệu PDF hiện có, bao gồm thêm trường văn bản, hộp kiểm và các thành phần biểu mẫu khác.

#### Câu hỏi: Aspose.PDF cho .NET có hỗ trợ các loại trường biểu mẫu khác, chẳng hạn như hộp kiểm và nút radio không?

Trả lời: Có, Aspose.PDF cho .NET hỗ trợ nhiều loại trường biểu mẫu khác nhau, bao gồm hộp kiểm, nút radio, danh sách thả xuống, v.v. Bạn có thể sử dụng thư viện để làm việc với các loại thành phần biểu mẫu khác nhau trong tài liệu PDF.