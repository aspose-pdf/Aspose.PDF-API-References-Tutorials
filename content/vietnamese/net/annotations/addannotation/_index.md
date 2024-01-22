---
title: Thêm chú thích PDF
linktitle: Thêm chú thích
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm chú thích văn bản PDF bằng Aspose.PDF cho .NET bằng mã nguồn C# này. Tùy chỉnh chú thích của bạn với các chi tiết và biểu tượng cụ thể.
type: docs
weight: 10
url: /vi/net/annotations/addannotation/
---
Thêm chú thích vào tài liệu PDF là một tính năng mạnh mẽ có thể nâng cao quá trình cộng tác và đánh giá. Aspose.PDF for .NET giúp dễ dàng thêm chú thích theo chương trình vào tài liệu PDF bằng C#. Trong hướng dẫn này, chúng tôi sẽ giải thích từng bước cách sử dụng Aspose.PDF cho .NET để thêm chú thích vào tài liệu PDF.

## Bước 1: Tạo dự án mới và cài đặt Aspose.PDF cho .NET

Trước khi bắt đầu viết mã để thêm chú thích, chúng ta cần tạo một dự án mới và cài đặt Aspose.PDF cho .NET. Để cài đặt Aspose.PDF cho .NET, hãy làm theo các bước sau:

1. Mở Visual Studio và tạo một dự án C# mới.
2. Nhấp chuột phải vào dự án trong Solution Explorer và chọn "Quản lý gói NuGet".
3. Tìm kiếm "Aspose.PDF" và chọn "Cài đặt".

Sau khi cài đặt hoàn tất, chúng ta có thể bắt đầu viết mã.

## Bước 2: Mở tài liệu PDF

Bước đầu tiên trong việc thêm chú thích là mở tài liệu PDF. Chúng ta có thể sử dụng đoạn mã sau để mở tài liệu:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Trong mã này, chúng tôi chỉ định đường dẫn đến tài liệu PDF mà chúng tôi muốn mở. Đảm bảo thay thế "THƯ MỤC DỮ LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục dữ liệu của bạn.

## Bước 3: Tạo chú thích

 Để thêm chú thích, chúng ta cần tạo một phiên bản mới của`TextAnnotation` lớp học. Chúng ta có thể sử dụng đoạn mã sau để tạo chú thích văn bản mới:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Trong mã này, chúng tôi tạo chú thích văn bản mới trên trang thứ hai của tài liệu PDF. Chúng tôi cũng đặt các thuộc tính tiêu đề, chủ đề, trạng thái, nội dung, mở và biểu tượng của chú thích.

## Bước 4: Tùy chỉnh chú thích

 Chúng ta có thể tùy chỉnh giao diện của chú thích bằng cách sử dụng`Border` lớp học. Chúng ta có thể sử dụng đoạn mã sau để tùy chỉnh đường viền của chú thích:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Trong mã này, chúng tôi tạo một mới`Border`đối tượng và đặt thuộc tính chiều rộng và dấu gạch ngang của nó. Sau đó chúng tôi thiết lập`Border` thuộc tính của chú thích sang cái mới`Border` sự vật. Cuối cùng, chúng tôi thiết lập`Rect` thuộc tính của chú thích để xác định vị trí và kích thước của nó.

## Bước 5: Thêm chú thích vào tài liệu PDF

Sau khi tạo và tùy chỉnh chú thích, chúng ta cần thêm chú thích đó vào tài liệu PDF. Chúng ta có thể sử dụng đoạn mã sau để thêm chú thích vào tài liệu PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Trong mã này, chúng tôi thêm chú thích vào bộ sưu tập chú thích của trang thứ hai của tài liệu PDF.

## Bước 6: Lưu tệp đầu ra

Cuối cùng, chúng ta cần lưu tài liệu PDF có thêm chú thích. Chúng ta có thể sử dụng đoạn mã sau để lưu tệp đầu ra:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Mã nguồn ví dụ về Thêm chú thích bằng Aspose.PDF cho .NET


```csharp   
 // Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DATA DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Tạo chú thích
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Thêm chú thích vào bộ sưu tập chú thích của trang
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Lưu tập tin đầu ra
pdfDocument.Save(dataDir);
```
Mã này trình bày cách thêm chú thích văn bản với tiêu đề, chủ đề, trạng thái, nội dung và biểu tượng cụ thể vào trang PDF bằng Aspose.PDF cho .NET. Bạn có thể sửa đổi mã này theo yêu cầu của mình để thêm chú thích vào tài liệu PDF. Chỉ cần nhớ thay thế THƯ MỤC DỮ LIỆU CỦA BẠN bằng đường dẫn thư mục thực nơi đặt tệp PDF của bạn và nơi bạn muốn lưu tệp đầu ra.

## Phần kết luận

Thêm chú thích vào tài liệu PDF bằng Aspose.PDF cho .NET cung cấp một công cụ có giá trị để nâng cao quy trình đánh giá và cộng tác tài liệu. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong bài viết này, nhà phát triển có thể tích hợp liền mạch khả năng chú thích vào ứng dụng C# của họ.

### Câu hỏi thường gặp

#### Câu hỏi: Những loại chú thích nào có thể được thêm bằng Aspose.PDF cho .NET?

Đáp: Aspose.PDF for .NET hỗ trợ nhiều loại chú thích khác nhau, bao gồm chú thích văn bản, tem, liên kết, hình dạng, v.v. Nhà phát triển có thể tùy chỉnh giao diện và thuộc tính của các chú thích này cho phù hợp với nhu cầu cụ thể của họ.

#### Hỏi: Tôi có thể thêm chú thích vào các trang cụ thể trong tài liệu PDF nhiều trang không?

Đáp: Có, Aspose.PDF for .NET cho phép bạn chỉ định trang mà bạn muốn thêm chú thích. Bạn có thể chọn một trang cụ thể hoặc thêm chú thích vào nhiều trang nếu cần.

#### Câu hỏi: Làm cách nào để tùy chỉnh hình thức của chú thích?

Đáp: Bạn có thể tùy chỉnh chú thích bằng cách sử dụng các thuộc tính như độ rộng đường viền, màu sắc, kiểu gạch ngang, kiểu văn bản, v.v. Aspose.PDF for .NET cung cấp một bộ tùy chọn phong phú để điều chỉnh giao diện của chú thích.

#### Câu hỏi: Có thể thêm siêu liên kết làm chú thích bằng Aspose.PDF cho .NET không?

Trả lời: Có, bạn có thể thêm siêu liên kết dưới dạng chú thích vào tài liệu PDF bằng Aspose.PDF cho .NET. Chú thích siêu liên kết có thể được sử dụng để liên kết đến các URL bên ngoài hoặc các vị trí cụ thể trong cùng một tài liệu.

#### Hỏi: Có thể thêm chú thích vào tài liệu PDF hiện có mà không làm thay đổi nội dung gốc không?

Trả lời: Có, Aspose.PDF cho .NET thêm chú thích dưới dạng thành phần bổ sung mà không làm thay đổi nội dung gốc của tài liệu PDF. Nội dung PDF gốc vẫn còn nguyên.