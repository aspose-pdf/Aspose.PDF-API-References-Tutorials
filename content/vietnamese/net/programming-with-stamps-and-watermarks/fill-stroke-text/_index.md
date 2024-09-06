---
title: Điền nét chữ vào tệp PDF
linktitle: Điền nét chữ vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách dễ dàng điền và phác thảo văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 90
url: /vi/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách tô và phác thảo văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để áp dụng màu tô và phác thảo cho văn bản trong tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo đối tượng TextState

Bước đầu tiên là tạo một đối tượng TextState để truyền các thuộc tính nâng cao. Thực hiện như sau:

```csharp
// Tạo đối tượng TextState để chuyển các thuộc tính nâng cao
TextState ts = new TextState();

// Đặt màu phác thảo
ts.StrokingColor = Color.Gray;

// Xác định chế độ hiển thị văn bản
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Đoạn mã trên tạo một đối tượng TextState mới và thiết lập màu viền cũng như cách hiển thị văn bản.

## Bước 3: Tải tài liệu PDF

Bây giờ đối tượng TextState đã sẵn sàng, chúng ta có thể tải tài liệu PDF vào nơi chúng ta muốn áp dụng phần tô và phác thảo văn bản. Thực hiện như sau:

```csharp
// Tải tài liệu PDF làm đầu vào
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Đoạn mã trên tải tài liệu PDF hiện có bằng cách sử dụng lớp PdfFileStamp từ thư viện Aspose.PDF.Facades.

## Bước 4: Thêm Tô và Nét vào Văn bản

Bây giờ tài liệu PDF đã được tải, chúng ta có thể thêm phần tô và phác thảo vào văn bản. Thực hiện như sau:

```csharp
// Tạo một con dấu (Stamp) với văn bản và thuộc tính đã xác định
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Liên kết đối tượng TextState
stamp.BindTextState(ts);

// Đặt gốc X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Thêm tem vào tài liệu
fileStamp.AddStamp(stamp);
```

Đoạn mã trên tạo ra một Con dấu với văn bản được chỉ định và các thuộc tính Tô và Nét được xác định.

## Bước 5: Lưu tài liệu đầu ra

Sau khi thêm dấu văn bản, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Thực hiện như sau:

```csharp
// Lưu tài liệu đã sửa đổi
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục đã chỉ định.

### Mã nguồn mẫu cho Fill Stroke Text sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo đối tượng TextState để chuyển các thuộc tính nâng cao
TextState ts = new TextState();

// Đặt màu cho nét vẽ
ts.StrokingColor = Color.Gray;

// Đặt chế độ hiển thị văn bản
ts.RenderingMode = TextRenderingMode.StrokeText;

// Tải một tài liệu PDF đầu vào
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Liên kết TextState
stamp.BindTextState(ts);

// Đặt gốc X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Thêm tem
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách tô và phác thảo văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng kiến thức này để tùy chỉnh màu tô và phác thảo trong tài liệu PDF của mình.

### Câu hỏi thường gặp về tô nét chữ trong tệp PDF

#### H: Điền và phác thảo văn bản trong tài liệu PDF có nghĩa là gì và khi nào tôi cần phải làm như vậy?

A: Việc tô và phác thảo văn bản trong tài liệu PDF bao gồm việc áp dụng màu vào bên trong các ký tự văn bản (tô) và vào các đường viền xung quanh văn bản (phác thảo). Điều này có thể được sử dụng để tăng cường hình thức trực quan của văn bản, tạo điểm nhấn hoặc làm nổi bật nội dung cụ thể trong PDF.

#### H: Mã nguồn C# được cung cấp thực hiện việc điền và phác thảo văn bản trong tệp PDF như thế nào?

 A: Mã nguồn được cung cấp chứng minh cách tạo ra một`TextState` đối tượng để xác định các thuộc tính văn bản nâng cao, chẳng hạn như màu phác thảo và chế độ hiển thị. Sau đó, nó sử dụng Aspose.PDF.Facades để tải một tài liệu PDF hiện có, tạo một con dấu chứa văn bản với các thuộc tính tô và nét được chỉ định và thêm con dấu vào tài liệu.

####  Q: Mục đích của việc này là gì?`TextState` object in the code?

 A: Cái`TextState`đối tượng được sử dụng để xác định các thuộc tính văn bản nâng cao, bao gồm màu của đường viền văn bản (nét) và chế độ hiển thị. Nó cho phép bạn tùy chỉnh cách văn bản xuất hiện theo nét và màu tô.

#### H: Tôi có thể áp dụng màu tô và màu viền khác nhau cho các phần khác nhau của cùng một văn bản không?

 A: Có, bạn có thể sửa đổi mã để tạo ra các`TextState` các đối tượng có màu tô và viền riêng biệt và áp dụng chúng vào các phần cụ thể của văn bản bằng cách sử dụng riêng biệt`Stamp` đồ vật.

#### H: Tôi có thể áp dụng màu tô và viền cho văn bản đã có trong tài liệu PDF không?

 A: Có, bạn có thể sử dụng các nguyên tắc tương tự để áp dụng màu tô và viền cho văn bản hiện có trong tài liệu PDF bằng cách chọn các đối tượng văn bản thích hợp và thêm chúng dưới dạng tem có nội dung mong muốn.`TextState` của cải.

#### H: Làm thế nào để điều chỉnh độ mờ đục và độ hòa trộn của văn bản được tô và phác thảo?

 A: Mã được cung cấp cho phép bạn thiết lập độ mờ đục và các thuộc tính pha trộn của tem bằng cách sử dụng`Opacity` Và`BlendingSpace`thuộc tính tương ứng. Bạn có thể điều chỉnh các giá trị này để đạt được hiệu ứng hình ảnh mong muốn.

#### H: Làm thế nào tôi có thể áp dụng nhiều màu tô và viền khác nhau cho nhiều con dấu trong cùng một tài liệu PDF?

 A: Bạn có thể tạo nhiều`TextState` các đối tượng có màu tô và màu viền khác nhau, sau đó tạo các đối tượng riêng biệt`Stamp` đối tượng cho mỗi bộ văn bản có màu sắc riêng biệt. Thêm các tem này vào cùng một tài liệu PDF bằng cách sử dụng`PdfFileStamp` lớp học.

#### H: Tôi có thể sử dụng phông chữ khác ngoài Arial cho văn bản được phác thảo và tô màu không?

 A: Có, bạn có thể thay đổi phông chữ bằng cách sửa đổi tham số tên phông chữ trong`FormattedText` constructor khi tạo tem. Bạn có thể sử dụng bất kỳ phông chữ nào có sẵn trên hệ thống của bạn.

#### H: Làm thế nào để tôi có thể thay đổi góc xoay của văn bản được viền và tô màu?

 A: Mã được cung cấp cho phép bạn thiết lập góc quay của tem bằng cách sử dụng`Rotation` thuộc tính. Bạn có thể điều chỉnh thuộc tính này để chỉ định góc xoay mong muốn cho văn bản.

#### H: Làm thế nào tôi có thể kiểm soát vị trí và kích thước của văn bản được phác thảo và tô màu trên trang?

 A: Bạn có thể sử dụng`SetOrigin` phương pháp của`Stamp` đối tượng để thiết lập tọa độ X và Y của vị trí con dấu trên trang. Ngoài ra, bạn có thể điều chỉnh kích thước phông chữ trong`FormattedText` hàm tạo để kiểm soát kích thước của văn bản.