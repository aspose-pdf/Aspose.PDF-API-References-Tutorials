---
title: Đặt định dạng chú thích văn bản miễn phí
linktitle: Đặt định dạng chú thích văn bản miễn phí
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Bài viết này cung cấp hướng dẫn từng bước về cách tạo chú thích văn bản miễn phí và chỉ định nội dung của nó bằng Aspose.PDF cho .NET
type: docs
weight: 140
url: /vi/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF for .NET là API thao tác tài liệu PDF mạnh mẽ và dễ sử dụng, cho phép bạn làm việc với các tệp PDF theo chương trình trong các ứng dụng .NET của mình. Một trong những tính năng được Aspose.PDF cung cấp cho .NET là khả năng đặt định dạng chú thích văn bản miễn phí trong tài liệu PDF. Trong bài viết này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước thiết lập định dạng chú thích văn bản miễn phí bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Microsoft Visual Studio 2010 trở lên
- Aspose.PDF cho .NET
- Kiến thức cơ bản về C#



## Bước 1: Tạo ứng dụng bảng điều khiển C# mới

Đầu tiên, tạo ứng dụng bảng điều khiển C# mới trong Microsoft Visual Studio. Để tạo một ứng dụng bảng điều khiển mới, chọn "Tệp"> "Mới" > "Dự án" > "Visual C#"> "Ứng dụng bảng điều khiển" từ menu chính.

## Bước 2: Thêm tham chiếu vào Aspose.PDF cho .NET

Tiếp theo, thêm tham chiếu đến Aspose.PDF cho .NET trong dự án của bạn. Để thực hiện việc này, hãy nhấp chuột phải vào dự án của bạn trong ngăn "Solution Explorer", chọn "Thêm" > "Tham khảo", sau đó duyệt đến vị trí bạn đã lưu tệp Aspose.PDF cho .NET DLL. Chọn tệp DLL và nhấp vào "OK" để thêm tham chiếu vào dự án của bạn.

## Bước 3: Thiết lập môi trường

Sau khi thêm tham chiếu vào Aspose.PDF cho .NET, bạn cần thiết lập môi trường. Để thực hiện việc này, hãy tạo một biến chuỗi mới có tên là "dataDir" và đặt nó vào đường dẫn của thư mục chứa tài liệu PDF của bạn. Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" trong mã bên dưới bằng đường dẫn thực tế của thư mục tài liệu của bạn:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 4: Mở tài liệu PDF

Khi bạn đã thiết lập môi trường, bạn có thể mở tài liệu PDF bằng mã sau:

```csharp
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Thay thế "SetFreeTextAnnotationFormatting.pdf" bằng tên thực của tài liệu PDF của bạn.

## Bước 5: Thiết lập giao diện mặc định

Để thiết lập giao diện mặc định của chú thích văn bản miễn phí, bạn cần khởi tạo đối tượng DefaultAppearance với phông chữ, cỡ chữ và màu sắc mong muốn. Trong hướng dẫn này, chúng tôi đặt phông chữ thành "Arial", cỡ chữ thành 28 và màu thành màu đỏ.

```csharp
// Khởi tạo đối tượng DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Bước 6: Tạo chú thích văn bản miễn phí

Bây giờ bạn đã thiết lập giao diện mặc định, bạn có thể tạo chú thích văn bản miễn phí bằng mã sau:

```csharp
// Tạo chú thích
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Đoạn mã trên tạo một chú thích văn bản miễn phí mới trên trang thứ hai của tài liệu PDF. Chú thích sẽ được đặt ở vị trí (200, 400) và có chiều rộng là 400 và chiều cao là 600.

## Bước 7: Xác định nội dung chú thích

Sau khi tạo chú thích văn bản miễn phí, bạn có thể chỉ định nội dung của chú thích bằng mã sau:

```csharp
// Xác định nội dung chú thích
freetext.Contents = "Free Text
```

### Mã nguồn mẫu cho Đặt định dạng chú thích văn bản miễn phí bằng Aspose.PDF cho .NET
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Khởi tạo đối tượng DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Tạo chú thích
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Xác định nội dung chú thích
freetext.Contents = "Free Text";
// Thêm chú thích vào bộ sưu tập chú thích của trang
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir);            
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã tìm hiểu cách đặt định dạng chú thích văn bản miễn phí trong tài liệu PDF bằng Aspose.PDF cho .NET. Thư viện cung cấp một cách đơn giản và hiệu quả để làm việc với các tài liệu PDF theo chương trình, cho phép các nhà phát triển tạo và tùy chỉnh nhiều loại chú thích khác nhau, bao gồm cả chú thích văn bản miễn phí. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng thiết lập môi trường, mở tài liệu PDF và tạo chú thích văn bản miễn phí với định dạng tùy chỉnh. Aspose.PDF for .NET là một API mạnh mẽ và đáng tin cậy giúp đơn giản hóa các tác vụ thao tác tài liệu PDF, khiến nó trở thành một công cụ có giá trị cho các nhà phát triển .NET làm việc với các tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Chú thích văn bản miễn phí trong tài liệu PDF là gì?

Đáp: Chú thích văn bản miễn phí trong tài liệu PDF là một loại chú thích cho phép bạn thêm văn bản vào tài liệu mà không bị ràng buộc với một vị trí hoặc cấu trúc cụ thể. Nó thường được sử dụng để cung cấp nhận xét, ghi chú hoặc thông tin bổ sung khác trong tài liệu.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của chú thích văn bản miễn phí bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của chú thích văn bản miễn phí, chẳng hạn như phông chữ, cỡ chữ, màu sắc, vị trí, v.v.

#### Hỏi: Làm cách nào để chỉ định nội dung của chú thích văn bản miễn phí?

 Đáp: Để chỉ định nội dung của chú thích văn bản tự do, bạn có thể đặt`Contents` tài sản của`FreeTextAnnotation` phản đối văn bản mong muốn.

#### Câu hỏi: Tôi có thể thêm nhiều chú thích văn bản miễn phí vào tài liệu PDF bằng Aspose.PDF cho .NET không?

 Đáp: Có, bạn có thể tạo nhiều chú thích văn bản miễn phí trong tài liệu PDF bằng cách tạo nhiều phiên bản của`FreeTextAnnotation`đối tượng và thêm chúng vào các trang hoặc vị trí khác nhau trong tài liệu.