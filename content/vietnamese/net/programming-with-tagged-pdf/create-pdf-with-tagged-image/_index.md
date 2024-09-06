---
title: Tạo PDF với hình ảnh được gắn thẻ
linktitle: Tạo PDF với hình ảnh được gắn thẻ
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để tạo PDF có gắn thẻ hình ảnh bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Trong hướng dẫn này, chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước về cách tạo tài liệu PDF có hình ảnh được gắn thẻ bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Sử dụng các tính năng cấu trúc nội dung được gắn thẻ của Aspose.PDF, bạn có thể thêm hình ảnh được gắn thẻ vào tài liệu PDF của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Visual Studio được cài đặt với .NET framework.
2. Thư viện Aspose.PDF dành cho .NET.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống thư viện từ trang web chính thức của Aspose và cài đặt trên máy của mình.

## Bước 2: Nhập các không gian tên cần thiết

Trong tệp mã C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Bước 3: Tạo tài liệu PDF có gắn thẻ hình ảnh

Sử dụng mã sau để tạo tài liệu PDF có gắn thẻ hình ảnh:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Mã này tạo một tài liệu PDF trống và thêm hình ảnh được gắn thẻ bằng các phương pháp do Aspose.PDF cung cấp. Hình ảnh được chỉ định bằng văn bản thay thế, tiêu đề và thẻ.

## Bước 4: Lưu tài liệu PDF

Sử dụng mã sau để lưu tài liệu PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Mã này lưu tài liệu PDF có gắn thẻ hình ảnh vào một tệp được chỉ định.

### Mã nguồn mẫu để tạo PDF với hình ảnh được gắn thẻ bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Thêm hình ảnh có độ phân giải 300 DPI (mặc định)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Lưu tài liệu PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo tài liệu PDF có hình ảnh được gắn thẻ bằng Aspose.PDF cho .NET. Hình ảnh được gắn thẻ sẽ thêm thông tin có cấu trúc bổ sung vào tài liệu PDF của bạn.

### Câu hỏi thường gặp

#### H: Mục đích của việc tạo tài liệu PDF có gắn thẻ hình ảnh bằng Aspose.PDF cho .NET là gì?

A: Tạo tài liệu PDF có hình ảnh được gắn thẻ bằng Aspose.PDF cho .NET cho phép bạn thêm hình ảnh được gắn thẻ vào nội dung tài liệu. Hình ảnh được gắn thẻ cung cấp thông tin có cấu trúc, chẳng hạn như văn bản thay thế và tiêu đề, tăng cường khả năng truy cập và tổ chức.

#### H: Thư viện Aspose.PDF hỗ trợ tạo tài liệu PDF có gắn thẻ hình ảnh như thế nào?

A: Aspose.PDF for .NET là một thư viện mạnh mẽ cung cấp các chức năng để tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Trong hướng dẫn này, các tính năng cấu trúc nội dung được gắn thẻ của thư viện được sử dụng để thêm hình ảnh được gắn thẻ vào tài liệu PDF.

#### H: Điều kiện tiên quyết để tạo tài liệu PDF có gắn thẻ hình ảnh bằng Aspose.PDF cho .NET là gì?

A: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt Visual Studio với .NET framework và có thư viện Aspose.PDF cho .NET được tham chiếu trong dự án của bạn.

#### H: Mã C# được cung cấp tạo ra tài liệu PDF có gắn thẻ hình ảnh như thế nào?

A: Mã này trình bày cách tạo tài liệu PDF, xác định phần tử hình ảnh được gắn thẻ và thêm vào nội dung của tài liệu. Hình ảnh được gắn thẻ bao gồm văn bản thay thế, tiêu đề và thẻ bằng các phương pháp do Aspose.PDF cung cấp.

#### H: Tôi có thể sử dụng các định dạng hình ảnh khác nhau cho hình ảnh được gắn thẻ không?

A: Có, bạn có thể sử dụng các định dạng hình ảnh khác nhau cho hình ảnh được gắn thẻ, chẳng hạn như JPEG, PNG, GIF, v.v. Mã ví dụ được cung cấp trong hướng dẫn sử dụng hình ảnh JPEG, nhưng bạn có thể thay thế bằng đường dẫn đến tệp hình ảnh ở định dạng bạn thích.

#### H: Văn bản thay thế (alt text) được sử dụng như thế nào trong hình ảnh được gắn thẻ?

 A: Văn bản thay thế cung cấp mô tả bằng văn bản về hình ảnh, được đọc to bằng trình đọc màn hình dành cho người dùng khiếm thị. Trong mã được cung cấp, văn bản thay thế được đặt bằng cách sử dụng`AlternativeText` tài sản của`IllustrationElement` đại diện cho hình ảnh được gắn thẻ.

####  Q: Làm thế nào để`SetTitle` method contribute to the PDF document's tagged image?

 A: Cái`SetTitle` phương pháp này đặt tiêu đề cho nội dung được gắn thẻ của tài liệu PDF, cung cấp ngữ cảnh bổ sung cho hình ảnh được gắn thẻ. Tiêu đề này có thể giúp xác định mục đích hoặc chủ đề của nội dung được gắn thẻ.

#### H: Tôi có thể tùy chỉnh thẻ và tiêu đề của hình ảnh được gắn thẻ không?

 A: Có, bạn có thể tùy chỉnh thẻ và tiêu đề của hình ảnh được gắn thẻ bằng cách sử dụng`SetTag` Và`Title` phương pháp của`IllustrationElement`. Ví dụ mã minh họa cách đặt thẻ thành "Hình" và tiêu đề thành "Hình ảnh 1".

#### H: Làm sao tôi có thể đảm bảo hình ảnh được gắn thẻ có thể truy cập được và tuân thủ các tiêu chuẩn về khả năng truy cập?

A: Bằng cách sử dụng các tính năng cấu trúc nội dung được gắn thẻ của Aspose.PDF và cung cấp văn bản thay thế và thông tin liên quan khác, bạn đóng góp vào khả năng truy cập của hình ảnh được gắn thẻ. Đảm bảo tuân thủ các tiêu chuẩn về khả năng truy cập bao gồm việc tuân theo các thông lệ tốt nhất cho văn bản thay thế và cấu trúc tài liệu.

#### H: Có thể thêm nhiều hình ảnh được gắn thẻ vào cùng một tài liệu PDF bằng các kỹ thuật tương tự không?

 A: Có, bạn có thể thêm nhiều hình ảnh được gắn thẻ vào cùng một tài liệu PDF bằng các kỹ thuật tương tự. Bạn sẽ tạo thêm`IllustrationElement` các trường hợp cho mỗi hình ảnh được gắn thẻ và tùy chỉnh các thuộc tính của chúng khi cần thiết.