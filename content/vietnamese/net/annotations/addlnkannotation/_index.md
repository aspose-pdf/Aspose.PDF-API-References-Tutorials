---
title: Thêm chú thích lnk
linktitle: Thêm chú thích lnk
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm tính năng Ink Annotation vào tài liệu PDF trong C# bằng Aspose.PDF for .NET với hướng dẫn từng bước và mã nguồn đầy đủ.
type: docs
weight: 20
url: /vi/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển thực hiện nhiều thao tác PDF khác nhau. Một thao tác như vậy là thêm Chú thích bằng mực vào tài liệu PDF. Trong bài viết này, chúng tôi sẽ cung cấp hướng dẫn từng bước để giải thích mã nguồn C# để thêm Chú thích mực bằng Aspose.PDF cho .NET. Bắt đầu nào!

## Tìm hiểu tính năng chú thích mực của Aspose.PDF cho .NET

Trước khi đi sâu vào mã nguồn C#, trước tiên chúng ta hãy hiểu Ink Annotation là gì và cách sử dụng của nó.

Chú thích bằng mực là một cách để vẽ các chú thích bằng mực dạng tự do trên tài liệu PDF. Nó cho phép bạn tạo chú thích bằng bút stylus hoặc chuột. Tính năng này hữu ích trong những trường hợp bạn cần vẽ sơ đồ, bản phác thảo hoặc các loại chú thích khác.

## Bước 1: Tạo một tài liệu mới

Bước đầu tiên trong việc thêm Chú thích Mực vào tài liệu PDF là tạo một phiên bản mới của lớp Tài liệu. Điều này đạt được bằng cách sử dụng đoạn mã sau:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Ở đây, chúng ta tạo một phiên bản mới của lớp Document và thêm một trang mới vào đó.

## Bước 2: Tạo chú thích viết tay

Bước tiếp theo là tạo một phiên bản của lớp InkAnnotation. Điều này được thực hiện bằng cách sử dụng đoạn mã sau:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(đột quỵ.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Ở đây, trước tiên chúng ta tạo một hình chữ nhật bằng lớp System.draw.Rectangle và chuyển đổi nó thành Aspose.Pdf.Rectangle bằng phương thức FromRect. Sau đó, chúng tôi tạo một phiên bản của lớp InkAnnotation bằng cách sử dụng hình chữ nhật, danh sách các điểm và trang nơi chú thích được thêm vào.

Sau đó, chúng tôi đặt các thuộc tính khác nhau của InkAnnotation, chẳng hạn như tiêu đề, màu sắc, kiểu chữ hoa, đường viền và độ mờ. Cuối cùng, chúng ta thêm chú thích vào trang bằng phương thức Annotations.Add.

## Bước 3: Lưu tài liệu

Bước cuối cùng là lưu tài liệu PDF có thêm Chú thích mực. Điều này đạt được bằng cách sử dụng đoạn mã sau:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Ở đây, chúng tôi ghép tên tệp đầu ra vào thư mục dữ liệu và lưu tài liệu bằng phương thức Lưu.

### Mã nguồn ví dụ về Thêm chú thích viết tay bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(đột quỵ.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Lưu tập tin đầu ra
doc.Save(dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách thêm Chú thích viết tay vào tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng triển khai chức năng Chú thích bằng mực trong các ứng dụng xử lý PDF của họ.

### Câu hỏi thường gặp

#### Hỏi: Chú thích viết tay trong tài liệu PDF là gì?

Đáp: Chú thích bằng mực trong tài liệu PDF cho phép người dùng vẽ chú thích bằng mực dạng tự do bằng bút cảm ứng hoặc chuột. Nó thường được sử dụng để thêm các bản phác thảo, sơ đồ vẽ tay hoặc các chú thích tự do khác vào tệp PDF.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của Chú thích bằng mực không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp nhiều thuộc tính khác nhau để tùy chỉnh giao diện của Chú thích mực, chẳng hạn như màu sắc, độ mờ, kiểu chữ hoa, độ rộng đường viền, v.v. Nhà phát triển có thể điều chỉnh các thuộc tính này để đáp ứng các yêu cầu cụ thể của họ.

#### Hỏi: Có thể thêm nhiều Chú thích viết tay vào một trang PDF không?

Trả lời: Có, bạn có thể thêm nhiều Chú thích viết tay vào một trang PDF bằng Aspose.PDF cho .NET. Mỗi Chú thích Viết tay có thể có tập hợp các điểm riêng và hình thức tùy chỉnh.

#### Câu hỏi: Tôi có thể thêm Chú thích Viết tay vào tài liệu PDF hiện có không?

Trả lời: Có, Aspose.PDF cho .NET cho phép bạn thêm Chú thích bằng mực vào cả tài liệu PDF mới được tạo và tệp PDF hiện có. Bạn có thể mở tệp PDF hiện có, thêm Chú thích viết tay và lưu tài liệu đã cập nhật.

#### Câu hỏi: Một số trường hợp sử dụng phổ biến cho Chú thích viết tay trong tài liệu PDF là gì?

Đáp: Chú thích bằng mực rất hữu ích cho nhiều ứng dụng, bao gồm thêm chữ ký hoặc ghi chú viết tay vào biểu mẫu PDF, chú thích bản thiết kế kiến trúc hoặc bản vẽ kỹ thuật cũng như đánh dấu tài liệu để cộng tác đánh giá.