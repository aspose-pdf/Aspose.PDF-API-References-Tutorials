---
title: Khối văn bản ẩn trong tệp PDF
linktitle: Khối văn bản ẩn trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo khối văn bản ẩn trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 230
url: /vi/net/programming-with-text/hidden-text-block/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách tạo khối văn bản ẩn trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Khối văn bản ẩn là văn bản nổi sẽ hiển thị khi con trỏ chuột di chuyển qua một vùng cụ thể. Chúng tôi sẽ hướng dẫn từng bước để tạo khối văn bản ẩn bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục bạn mong muốn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu mẫu

Trong bước này, chúng tôi tạo một tài liệu PDF mẫu và thêm một đoạn văn bản vào đó. Đoạn văn bản sẽ đóng vai trò là trình kích hoạt để hiển thị khối văn bản ẩn.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Bước 3: Mở Tài liệu

 Bây giờ, chúng ta mở tài liệu đã tạo trước đó bằng cách sử dụng`Document` lớp học.

```csharp
Document document = new Document(outputFile);
```

## Bước 4: Tìm đoạn văn bản

 Chúng tôi sử dụng một`TextFragmentAbsorber`đối tượng để tìm đoạn văn bản sẽ kích hoạt hiển thị khối văn bản ẩn. Trong trường hợp này, chúng tôi đang tìm kiếm văn bản chính xác "Di chuyển con trỏ chuột đến đây để hiển thị văn bản nổi".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Bước 5: Tạo trường văn bản ẩn

 Chúng tôi tạo ra một`TextBoxField` đối tượng để biểu diễn trường văn bản ẩn. Trường này sẽ chứa văn bản hiển thị khi con trỏ chuột di qua văn bản kích hoạt.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Bước 6: Thêm trường văn bản ẩn vào tài liệu

Chúng tôi thêm trường văn bản ẩn vào bộ sưu tập biểu mẫu của tài liệu.

```csharp
document.Form.Add(floatingField);
```

## Bước 7: Tạo nút vô hình

Chúng tôi tạo một trường nút vô hình sẽ được định vị trên đầu đoạn văn bản kích hoạt. Trường nút này sẽ có các hành động liên quan đến sự kiện nhập và thoát chuột.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Bước 8: Lưu tài liệu

Cuối cùng, chúng ta lưu tài liệu đã chỉnh sửa với khối văn bản ẩn.

```csharp
document. Save(outputFile);
```

### Mã nguồn mẫu cho Hidden Text Block sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Tạo tài liệu mẫu có văn bản
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Mở tài liệu có văn bản
Document document = new Document(outputFile);
// Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Chấp nhận bộ hấp thụ cho các trang tài liệu
document.Pages.Accept(absorber);
// Nhận đoạn văn bản được trích xuất đầu tiên
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Tạo trường văn bản ẩn cho văn bản nổi trong hình chữ nhật được chỉ định của trang
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Đặt văn bản được hiển thị dưới dạng giá trị trường
floatingField.Value = "This is the \"floating text field\".";
// Chúng tôi khuyên bạn nên tạo trường 'chỉ đọc' cho trường hợp này
floatingField.ReadOnly = true;
// Đặt cờ 'ẩn' để làm cho trường vô hình khi mở tài liệu
floatingField.Flags |= AnnotationFlags.Hidden;
// Việc đặt tên trường duy nhất không cần thiết nhưng được phép
floatingField.PartialName = "FloatingField_1";
// Thiết lập các đặc điểm của giao diện trường không cần thiết nhưng làm cho nó tốt hơn
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Thêm trường văn bản vào tài liệu
document.Form.Add(floatingField);
// Tạo nút vô hình trên vị trí đoạn văn bản
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Tạo hành động ẩn mới cho trường được chỉ định (chú thích) và cờ ẩn.
// (Bạn cũng có thể tham chiếu trường nổi theo tên nếu bạn đã chỉ định ở trên.)
// Thêm hành động vào/ra chuột tại trường nút vô hình
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Thêm trường nút vào tài liệu
document.Form.Add(buttonField);
// Lưu tài liệu
document.Save(outputFile);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo khối văn bản ẩn bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tạo tài liệu PDF có trường văn bản ẩn hiển thị khi con trỏ chuột di chuột qua một vùng cụ thể. Bạn có thể tùy chỉnh giao diện và hành vi của khối văn bản ẩn theo yêu cầu của mình.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Khối văn bản ẩn trong tệp PDF" là gì?

A: Hướng dẫn "Hidden Text Block In PDF File" giải thích cách tạo một khối văn bản ẩn trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Khối văn bản ẩn là một văn bản nổi sẽ hiển thị khi con trỏ chuột di chuột qua một vùng cụ thể. Hướng dẫn này cung cấp hướng dẫn từng bước bằng cách sử dụng mã nguồn C#.

#### H: Tại sao tôi lại muốn tạo khối văn bản ẩn trong tệp PDF?

A: Việc tạo khối văn bản ẩn có thể hữu ích cho các tài liệu PDF tương tác khi bạn muốn cung cấp thêm thông tin hoặc ngữ cảnh mà chỉ hiển thị khi người dùng di con trỏ chuột qua một vùng được chỉ định.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục mà bạn muốn lưu tệp PDF đã tạo.

#### H: Làm thế nào để tạo một tài liệu mẫu và thêm đoạn văn bản vào đó?

 A: Trong hướng dẫn, bạn sử dụng`Document` lớp để tạo một tài liệu PDF mẫu và thêm một đoạn văn bản. Đoạn văn bản này đóng vai trò là trình kích hoạt để hiển thị khối văn bản ẩn.

#### H: Làm thế nào để tìm đoạn văn bản kích hoạt khối văn bản ẩn?

 A: Hướng dẫn này trình bày cách sử dụng`TextFragmentAbsorber` đối tượng để tìm đoạn văn bản kích hoạt hiển thị khối văn bản ẩn. Nó tìm kiếm một chuỗi văn bản cụ thể trong tài liệu PDF.

#### H: Làm thế nào để tạo và tùy chỉnh trường văn bản ẩn?

 A: Bạn tạo ra một`TextBoxField`đối tượng để biểu diễn trường văn bản ẩn. Hướng dẫn cung cấp mã để thiết lập nhiều thuộc tính khác nhau như vị trí, giá trị, giao diện và hành vi của trường văn bản ẩn.

#### H: Làm thế nào để tạo nút vô hình liên kết với khối văn bản ẩn?

 A: Một trường nút vô hình được tạo ra bằng cách sử dụng`ButtonField` lớp. Trường nút này được định vị trên đầu đoạn văn bản kích hoạt và có các hành động liên quan đến sự kiện nhập và thoát của chuột. Các hành động này kiểm soát khả năng hiển thị của khối văn bản ẩn.

#### H: Tôi có thể tùy chỉnh giao diện của khối văn bản ẩn và vùng kích hoạt không?

A: Có, bạn có thể tùy chỉnh nhiều thuộc tính khác nhau của cả trường văn bản ẩn và nút vô hình, bao gồm phông chữ, màu sắc, kích thước và vị trí.

#### H: Làm thế nào để lưu tài liệu đã chỉnh sửa với khối văn bản ẩn?

 A: Hướng dẫn này trình bày cách lưu tài liệu đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp học.