---
title: Thêm dấu trang vào tệp PDF
linktitle: Thêm dấu trang vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng thêm dấu trang vào tệp PDF để cải thiện khả năng điều hướng với Aspose.PDF cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/add-bookmark/
---
Thêm dấu trang vào tệp PDF cho phép điều hướng dễ dàng và nhanh chóng. Với Aspose.PDF for .NET, bạn có thể dễ dàng thêm dấu trang vào tệp PDF bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF mà bạn muốn thêm dấu trang. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Mở tài liệu PDF

Bây giờ chúng tôi sẽ mở tài liệu PDF mà chúng tôi muốn thêm dấu trang bằng mã sau:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Bước 4: Tạo đối tượng đánh dấu

 Trong bước này, chúng ta sẽ tạo một đối tượng đánh dấu bằng cách sử dụng`OutlineItemCollection` class và đặt các thuộc tính của nó như tiêu đề, thuộc tính in nghiêng, thuộc tính in đậm và hành động sẽ thực hiện khi được nhấp vào. Đây là mã tương ứng:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Bước 5: Thêm dấu trang vào tài liệu

 Cuối cùng, chúng tôi thêm dấu trang đã tạo vào bộ sưu tập dấu trang của tài liệu bằng cách sử dụng`Add` phương pháp của`Outlines` tài sản. Đây là mã tương ứng:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Mã nguồn mẫu để Thêm dấu trang bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Tạo đối tượng đánh dấu
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Đặt số trang đích
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Thêm dấu trang vào bộ sưu tập phác thảo của tài liệu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Lưu đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để thêm dấu trang bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để cải thiện khả năng điều hướng trong tài liệu PDF của mình bằng cách thêm dấu trang tùy chỉnh.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng thao tác dấu trang nâng cao.


### Câu hỏi thường gặp về thêm dấu trang vào tệp PDF

#### Hỏi: Dấu trang trong tệp PDF là gì?

Đáp: Dấu trang, còn được gọi là đường viền, là các thành phần tương tác cung cấp khả năng điều hướng và cấu trúc trong tài liệu PDF. Chúng cho phép người dùng nhanh chóng chuyển đến các phần hoặc trang cụ thể.

#### Hỏi: Tại sao tôi cần thêm dấu trang vào tệp PDF?

Đáp: Việc thêm dấu trang vào tệp PDF sẽ cải thiện trải nghiệm người dùng và giúp người đọc điều hướng qua nội dung tài liệu dễ dàng hơn. Dấu trang có thể đóng vai trò là mục lục hoặc cung cấp quyền truy cập nhanh vào các phần quan trọng.

#### Câu hỏi: Làm cách nào để nhập các thư viện cần thiết cho dự án C# của tôi?

Đáp: Để nhập các thư viện cần thiết cho dự án C# của bạn, hãy bao gồm các lệnh nhập sau:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Những chỉ thị này cho phép bạn truy cập các lớp và phương thức cần thiết để làm việc với các tài liệu PDF và dấu trang.

#### Hỏi: Làm cách nào để chỉ định đường dẫn đến thư mục tài liệu?

 Đáp: Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã nguồn được cung cấp có đường dẫn thực tế đến thư mục chứa tệp PDF mà bạn muốn thêm dấu trang vào.

#### Hỏi: Làm cách nào để mở tài liệu PDF để thêm dấu trang?

Đáp: Để mở tài liệu PDF nhằm thêm dấu trang, hãy sử dụng mã sau:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Thay thế`"AddBookmark.pdf"` với tên tập tin thực tế.

#### Câu hỏi: Làm cách nào để tạo đối tượng dấu trang?

 Đáp: Để tạo một đối tượng đánh dấu, hãy sử dụng`OutlineItemCollection` lớp học. Tùy chỉnh các thuộc tính của nó như tiêu đề, kiểu in nghiêng, kiểu in đậm và hành động để thực hiện khi được nhấp vào.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  Hỏi: Mục đích của việc này là gì?`Action` property in a bookmark?

 Đáp: Cái`Action` thuộc tính chỉ định hành động được thực hiện khi nhấp vào dấu trang. Trong ví dụ này, chúng tôi sử dụng`GoToAction`class để điều hướng đến một trang cụ thể (trang 2 trong trường hợp này).

#### Hỏi: Làm cách nào để thêm dấu trang vào tài liệu?

 Đáp: Hãy sử dụng`Add` phương pháp của`Outlines` thuộc tính để thêm dấu trang đã tạo vào bộ sưu tập dấu trang của tài liệu.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### H: Tôi có thể thêm nhiều dấu trang bằng phương pháp này không?

Đáp: Có, bạn có thể lặp lại các bước từ 4 đến 8 để thêm nhiều dấu trang vào tài liệu. Tùy chỉnh các thuộc tính và hành động của từng dấu trang nếu cần.

#### Hỏi: Làm cách nào để lưu tệp PDF đã cập nhật?

 Đáp: Lưu tệp PDF đã cập nhật bằng cách sử dụng`Save` phương pháp của`pdfDocument` sự vật:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### Hỏi: Làm cách nào tôi có thể xác nhận rằng dấu trang đã được thêm vào?

Đáp: Mở tệp PDF được tạo để xác minh rằng các dấu trang được chỉ định đã được thêm vào tài liệu.

#### Hỏi: Có giới hạn về số lượng dấu trang tôi có thể thêm không?

Đáp: Nhìn chung không có giới hạn nghiêm ngặt về số lượng dấu trang bạn có thể thêm nhưng hãy cân nhắc kích thước và độ phức tạp của tài liệu để có hiệu suất tối ưu.

#### Hỏi: Tôi có thể tùy chỉnh giao diện của dấu trang không?

Trả lời: Có, bạn có thể tùy chỉnh thêm giao diện, màu sắc, kiểu dáng của dấu trang và các thuộc tính khác bằng cách sử dụng các tính năng Aspose.PDF.