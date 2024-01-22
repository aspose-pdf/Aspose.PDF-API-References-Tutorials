---
title: Thêm dấu ngày giờ vào tệp PDF
linktitle: Thêm dấu ngày giờ vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách dễ dàng thêm dấu ngày và giờ trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Trong bài viết này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm dấu ngày và giờ trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để thêm dấu ngày và giờ vào tệp PDF hiện có.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 1: Thiết lập môi trường

Trước khi có thể thêm dấu ngày và giờ vào tài liệu PDF, bạn cần thiết lập môi trường phát triển của mình. Dưới đây là các bước để làm theo:

1. Mở IDE (Môi trường phát triển tích hợp) yêu thích của bạn.
2. Tạo một dự án C# mới.
3. Đảm bảo bạn đã thêm tham chiếu vào thư viện Aspose.PDF cho .NET.

## Bước 2: Thêm thư viện Aspose.PDF

Cần có thư viện Aspose.PDF cho .NET để hoạt động với các tài liệu PDF trong dự án của bạn.

## Bước 3: Tải tài liệu PDF

Bước đầu tiên để thêm dấu ngày và giờ là tải tài liệu PDF hiện có vào dự án của bạn. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 4: Tạo tem ngày giờ

Bây giờ bạn đã tải lên tài liệu

  PDF, bạn có thể tạo dấu ngày và thời gian để thêm. Đây là cách thực hiện:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Tạo bộ đệm văn bản
TextStamp textStamp = new TextStamp(annotationText);
```

Đoạn mã trên tạo một bộ đệm văn bản mới chứa ngày và giờ hiện tại.

## Bước 5: Cấu hình thuộc tính tem

Trước khi thêm dấu vào tài liệu PDF, bạn có thể định cấu hình các thuộc tính khác nhau của dấu, chẳng hạn như lề, căn chỉnh ngang và dọc, v.v. Dưới đây là cách thực hiện:

```csharp
// Đặt thuộc tính bộ đệm
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Bạn có thể điều chỉnh các thuộc tính này theo nhu cầu của bạn.

## Bước 6: Thêm tem vào PDF

Bây giờ dấu ngày và giờ đã sẵn sàng, bạn có thể thêm nó vào một trang cụ thể của tài liệu PDF. Đây là cách thực hiện:

```csharp
// Thêm tem vào bộ sưu tập tem của trang
pdfDocument.Pages[1].AddStamp(textStamp);
```

Đoạn mã trên thêm dấu vào trang đầu tiên của tài liệu PDF. Bạn có thể chỉ định một trang khác nếu cần.

## Bước 7: Lưu tài liệu đầu ra

Khi bạn đã thêm dấu ngày và giờ, bạn có thể lưu tài liệu PDF đã sửa đổi. Đây là cách thực hiện:

```csharp
// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
```

Đoạn mã trên lưu tài liệu PDF đã chỉnh sửa vào thư mục được chỉ định.

### Mã nguồn mẫu cho Thêm dấu thời gian ngày bằng cách sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Tạo dấu văn bản
TextStamp textStamp = new TextStamp(annotationText);

// Đặt thuộc tính của tem
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

Xin chúc mừng! Bạn đã học cách thêm dấu ngày và giờ bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể áp dụng kiến thức này cho các dự án của riêng mình để thêm dấu ngày và giờ vào tài liệu PDF.

### Câu hỏi thường gặp về thêm dấu ngày giờ vào tệp PDF

#### Câu hỏi: Mục đích của việc thêm dấu ngày và giờ vào tài liệu PDF bằng Aspose.PDF cho .NET là gì?

Đáp: Việc thêm dấu ngày và giờ vào tài liệu PDF sẽ nâng cao giá trị thông tin của nó bằng cách cho biết thời điểm tài liệu được sửa đổi hoặc tạo. Tính năng này hữu ích để theo dõi các thay đổi của tài liệu và cung cấp điểm tham chiếu cho lịch sử tài liệu.

#### Câu hỏi: Tôi có thể tùy chỉnh định dạng của dấu ngày và giờ để phù hợp với yêu cầu cụ thể không?

 Trả lời: Có, bạn có thể tùy chỉnh định dạng của dấu ngày và giờ theo sở thích của mình. Mã nguồn C# được cung cấp sử dụng`DateTime.Now.ToString()` phương pháp để tạo dấu thời gian ở một định dạng cụ thể. Bạn có thể sửa đổi mã này để định dạng dấu thời gian nếu cần.

#### Câu hỏi: Có thể thêm dấu ngày và giờ vào một vị trí cụ thể trên trang PDF không?

 Đáp: Hoàn toàn có thể, bạn có thể điều chỉnh vị trí của dấu ngày và giờ trên trang PDF bằng cách sửa đổi các thuộc tính của`TextStamp` sự vật. Mã được cung cấp trong hướng dẫn này trình bày cách đặt các thuộc tính như lề, căn chỉnh và định vị theo chiều dọc.

#### Hỏi: Tôi có thể thêm nhiều dấu ngày và giờ vào các trang khác nhau của cùng một tài liệu PDF không?

 Đáp: Có, bạn có thể thêm nhiều dấu ngày và giờ vào các trang khác nhau của cùng một tài liệu PDF. Đơn giản chỉ cần lặp lại quá trình tạo một`TextStamp` đối tượng và định cấu hình các thuộc tính của nó cho từng trang mong muốn.

#### Hỏi: Làm cách nào tôi có thể thay đổi phông chữ, kích thước hoặc màu sắc của văn bản dấu ngày và giờ?

 Trả lời: Để sửa đổi phông chữ, kích thước hoặc màu sắc của văn bản tem ngày và giờ, bạn có thể tùy chỉnh các thuộc tính của`DefaultAppearance` đối tượng được sử dụng để tạo ra`TextStamp`. Điều chỉnh tên phông chữ, kích thước và giá trị màu sắc để đạt được giao diện mong muốn.

#### Câu hỏi: Có thể thêm các loại chú thích hoặc tem khác vào tài liệu PDF bằng Aspose.PDF cho .NET không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp nhiều loại chú thích mà bạn có thể thêm vào tài liệu PDF, bao gồm chú thích văn bản, dấu, đường, hình dạng, v.v. Bạn có thể khám phá tài liệu Aspose.PDF để biết thêm chi tiết về cách làm việc với chú thích.

#### Câu hỏi: Có bất kỳ hạn chế hoặc cân nhắc nào khi thêm dấu ngày và giờ vào tài liệu PDF không?

Đáp: Mặc dù việc thêm dấu ngày và thời gian rất đơn giản nhưng hãy xem xét các yếu tố như bố cục của tài liệu và nội dung hiện có. Đảm bảo vị trí dán tem không che khuất những thông tin quan trọng hoặc ảnh hưởng đến khả năng đọc của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tích hợp phương pháp này vào các dự án của riêng mình để thêm dấu ngày và giờ vào tài liệu PDF?

Đáp: Để tích hợp phương pháp này, hãy làm theo các bước được cung cấp và điều chỉnh mã cho phù hợp với cấu trúc dự án của bạn. Bạn có thể thêm dấu ngày và giờ vào các tài liệu PDF hiện có để nâng cao tính hữu dụng của chúng và cung cấp dòng thời gian thay đổi rõ ràng.

#### Hỏi: Tôi có thể tự động hóa quá trình thêm dấu ngày và giờ vào nhiều tài liệu PDF không?

Trả lời: Có, bạn có thể tự động hóa quy trình thêm dấu ngày và giờ vào nhiều tài liệu PDF bằng cách tạo tập lệnh hoặc chương trình lặp qua danh sách tài liệu và áp dụng cùng một quy trình đóng dấu cho từng tài liệu.