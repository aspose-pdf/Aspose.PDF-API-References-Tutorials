---
title: Thêm Ngày Giờ Vào Tệp PDF
linktitle: Thêm Ngày Giờ Vào Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách dễ dàng thêm dấu ngày tháng và thời gian vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Trong bài viết này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm dấu ngày và giờ vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để thêm dấu ngày và giờ vào tệp PDF hiện có.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 1: Thiết lập môi trường

Trước khi bạn có thể thêm ngày và dấu thời gian vào tài liệu PDF, bạn cần thiết lập môi trường phát triển của mình. Sau đây là các bước cần thực hiện:

1. Mở IDE (Môi trường phát triển tích hợp) yêu thích của bạn.
2. Tạo một dự án C# mới.
3. Hãy đảm bảo rằng bạn đã thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Thêm thư viện Aspose.PDF

Thư viện Aspose.PDF dành cho .NET là cần thiết để làm việc với các tài liệu PDF trong dự án của bạn.

## Bước 3: Tải tài liệu PDF

Bước đầu tiên để thêm ngày và dấu thời gian là tải tài liệu PDF hiện có vào dự án của bạn. Thực hiện như sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 4: Tạo dấu ngày và giờ

Bây giờ bạn đã tải tài liệu lên

  PDF, bạn có thể tạo ngày và dấu thời gian để thêm. Sau đây là cách thực hiện:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Tạo vùng đệm văn bản
TextStamp textStamp = new TextStamp(annotationText);
```

Đoạn mã trên tạo ra một vùng đệm văn bản mới chứa ngày và giờ hiện tại.

## Bước 5: Cấu hình Thuộc tính tem

Trước khi thêm dấu vào tài liệu PDF, bạn có thể cấu hình nhiều thuộc tính khác nhau của dấu, chẳng hạn như lề, căn chỉnh theo chiều ngang và chiều dọc, v.v. Thực hiện như sau:

```csharp
// Đặt thuộc tính bộ đệm
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Bạn có thể điều chỉnh các thuộc tính này tùy theo nhu cầu của mình.

## Bước 6: Thêm tem vào PDF

Bây giờ ngày và giờ đã sẵn sàng, bạn có thể thêm nó vào một trang cụ thể của tài liệu PDF. Thực hiện như sau:

```csharp
// Thêm tem vào bộ sưu tập tem của trang
pdfDocument.Pages[1].AddStamp(textStamp);
```

Mã ở trên thêm dấu vào trang đầu tiên của tài liệu PDF. Bạn có thể chỉ định trang khác nếu cần.

## Bước 7: Lưu tài liệu đầu ra

Sau khi thêm ngày và dấu thời gian, bạn có thể lưu tài liệu PDF đã sửa đổi. Thực hiện như sau:

```csharp
// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu để Thêm Dấu thời gian Ngày tháng bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Tạo con dấu văn bản
TextStamp textStamp = new TextStamp(annotationText);

// Thiết lập thuộc tính của tem
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Thêm tem vào bộ sưu tập tem
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Phần kết luận

Xin chúc mừng! Bạn đã học được cách thêm dấu ngày và giờ bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng kiến thức này vào các dự án của riêng mình để thêm dấu ngày và giờ vào tài liệu PDF.

### Câu hỏi thường gặp về việc thêm dấu thời gian ngày tháng vào tệp PDF

#### H: Mục đích của việc thêm ngày tháng và thời gian vào tài liệu PDF bằng Aspose.PDF cho .NET là gì?

A: Thêm dấu ngày tháng và thời gian vào tài liệu PDF sẽ tăng giá trị thông tin của tài liệu bằng cách chỉ ra thời điểm tài liệu được sửa đổi hoặc tạo. Tính năng này hữu ích để theo dõi các thay đổi của tài liệu và cung cấp điểm tham chiếu cho lịch sử tài liệu.

#### H: Tôi có thể tùy chỉnh định dạng ngày tháng và thời gian để phù hợp với các yêu cầu cụ thể không?

 A: Có, bạn có thể tùy chỉnh định dạng của ngày và dấu thời gian theo sở thích của bạn. Mã nguồn C# được cung cấp sử dụng`DateTime.Now.ToString()` phương pháp tạo dấu thời gian theo định dạng cụ thể. Bạn có thể sửa đổi mã này để định dạng dấu thời gian theo nhu cầu.

#### H: Có thể thêm ngày tháng và dấu thời gian vào một vị trí cụ thể trên trang PDF không?

 A: Hoàn toàn có thể, bạn có thể điều chỉnh vị trí của dấu ngày và giờ trên trang PDF bằng cách sửa đổi các thuộc tính của`TextStamp` đối tượng. Mã được cung cấp trong hướng dẫn trình bày cách thiết lập các thuộc tính như lề, căn chỉnh và định vị theo chiều dọc.

#### H: Tôi có thể thêm nhiều dấu ngày tháng và thời gian vào nhiều trang khác nhau của cùng một tài liệu PDF không?

 A: Có, bạn có thể thêm nhiều dấu ngày tháng và thời gian vào các trang khác nhau của cùng một tài liệu PDF. Chỉ cần lặp lại quy trình tạo`TextStamp` đối tượng và cấu hình các thuộc tính của nó cho mỗi trang mong muốn.

#### H: Làm thế nào để thay đổi phông chữ, kích thước hoặc màu sắc của văn bản ngày tháng và thời gian?

 A: Để sửa đổi phông chữ, kích thước hoặc màu sắc của văn bản ngày tháng và dấu thời gian, bạn có thể tùy chỉnh các thuộc tính của`DefaultAppearance` đối tượng được sử dụng để tạo ra`TextStamp`. Điều chỉnh tên phông chữ, kích thước và giá trị màu sắc để đạt được giao diện mong muốn.

#### H: Có thể thêm các loại chú thích hoặc dấu khác vào tài liệu PDF bằng Aspose.PDF cho .NET không?

A: Có, Aspose.PDF for .NET cung cấp nhiều loại chú thích mà bạn có thể thêm vào tài liệu PDF, bao gồm chú thích văn bản, tem, đường kẻ, hình dạng, v.v. Bạn có thể khám phá tài liệu Aspose.PDF để biết thêm chi tiết về cách làm việc với chú thích.

#### H: Có hạn chế hoặc lưu ý nào khi thêm dấu ngày tháng và thời gian vào tài liệu PDF không?

A: Mặc dù việc thêm dấu ngày tháng và thời gian rất đơn giản, hãy cân nhắc các yếu tố như bố cục của tài liệu và nội dung hiện có. Đảm bảo vị trí đóng dấu không che khuất thông tin quan trọng hoặc ảnh hưởng đến khả năng đọc của tài liệu.

#### H: Làm thế nào tôi có thể tích hợp phương pháp này vào các dự án của mình để thêm dấu ngày tháng và thời gian vào tài liệu PDF?

A: Để tích hợp phương pháp này, hãy làm theo các bước được cung cấp và điều chỉnh mã cho phù hợp với cấu trúc dự án của bạn. Bạn có thể thêm dấu ngày và giờ vào các tài liệu PDF hiện có để tăng tính hữu ích của chúng và cung cấp mốc thời gian rõ ràng về các thay đổi.

#### H: Tôi có thể tự động hóa quy trình thêm dấu ngày tháng và thời gian vào nhiều tài liệu PDF không?

A: Có, bạn có thể tự động hóa quy trình thêm dấu ngày tháng và thời gian vào nhiều tài liệu PDF bằng cách tạo một tập lệnh hoặc chương trình lặp qua danh sách các tài liệu và áp dụng cùng một quy trình đóng dấu cho từng tài liệu.