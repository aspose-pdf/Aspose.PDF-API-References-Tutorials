---
title: Điền nét văn bản vào tệp PDF
linktitle: Điền nét văn bản vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách dễ dàng điền và phác thảo văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 90
url: /vi/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách điền và phác thảo văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để áp dụng màu tô và đường viền cho văn bản trong tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tạo đối tượng TextState

Bước đầu tiên là tạo một đối tượng TextState để chuyển các thuộc tính nâng cao. Đây là cách thực hiện:

```csharp
// Tạo đối tượng TextState để chuyển các thuộc tính nâng cao
TextState ts = new TextState();

// Đặt màu đường viền
ts.StrokingColor = Color.Gray;

// Xác định chế độ hiển thị văn bản
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Đoạn mã trên tạo một đối tượng TextState mới và đặt màu đường viền cũng như cách hiển thị văn bản.

## Bước 3: Tải tài liệu PDF

Bây giờ đối tượng TextState đã sẵn sàng, chúng ta có thể tải tài liệu PDF vào nơi chúng ta muốn áp dụng phần điền và phác thảo văn bản. Đây là cách thực hiện:

```csharp
// Tải tài liệu PDF làm đầu vào
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Đoạn mã trên tải tài liệu PDF hiện có bằng lớp PdfFileStamp từ thư viện Aspose.PDF.Facades.

## Bước 4: Thêm màu tô và nét vào văn bản

Bây giờ tài liệu PDF đã được tải, chúng ta có thể thêm phần điền và phác thảo vào văn bản. Đây là cách thực hiện:

```csharp
// Tạo tem (Stamp) với văn bản và thuộc tính được xác định
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Liên kết đối tượng TextState
stamp.BindTextState(ts);

// Đặt điểm gốc X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Thêm tem vào tài liệu
fileStamp.AddStamp(stamp);
```

Đoạn mã trên tạo một Dấu với văn bản được chỉ định và các thuộc tính Điền và Nét được xác định.

## Bước 5: Lưu tài liệu đầu ra

Sau khi thêm dấu văn bản, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Đây là cách thực hiện:

```csharp
// Lưu tài liệu đã sửa đổi
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Đoạn mã trên lưu tài liệu PDF đã chỉnh sửa vào thư mục được chỉ định.

### Mã nguồn mẫu cho Văn bản điền nét bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo đối tượng TextState để chuyển các thuộc tính nâng cao
TextState ts = new TextState();

// Đặt màu cho nét vẽ
ts.StrokingColor = Color.Gray;

// Đặt chế độ hiển thị văn bản
ts.RenderingMode = TextRenderingMode.StrokeText;

// Tải tài liệu PDF đầu vào
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Liên kết trạng thái văn bản
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

Xin chúc mừng! Bạn đã học cách điền và phác thảo văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể áp dụng kiến thức này để tùy chỉnh màu tô và đường viền trong tài liệu PDF của mình.

### Câu hỏi thường gặp về điền nét văn bản trong tệp PDF

#### Hỏi: Việc điền và phác thảo văn bản trong tài liệu PDF có ý nghĩa gì và khi nào tôi có thể cần phải làm như vậy?

Đáp: Việc tô và viền văn bản trong tài liệu PDF liên quan đến việc áp dụng màu sắc cho phần bên trong của các ký tự văn bản (tô) và cho các đường viền xung quanh văn bản (viền). Điều này có thể được sử dụng để nâng cao hình thức trực quan của văn bản, tạo điểm nhấn hoặc làm nổi bật nội dung cụ thể trong tệp PDF.

#### Câu hỏi: Mã nguồn C# được cung cấp thực hiện việc điền và dàn văn bản trong tệp PDF như thế nào?

 Đáp: Mã nguồn được cung cấp minh họa cách tạo một`TextState` đối tượng để xác định các thuộc tính văn bản nâng cao, chẳng hạn như màu đường viền và chế độ hiển thị. Sau đó, nó sử dụng Aspose.PDF.Facades để tải tài liệu PDF hiện có, tạo tem chứa văn bản với các thuộc tính tô và nét được chỉ định, đồng thời thêm tem vào tài liệu.

####  Hỏi: Mục đích của việc này là gì?`TextState` object in the code?

 Đáp: Cái`TextState`đối tượng được sử dụng để xác định các thuộc tính văn bản nâng cao, bao gồm màu của đường viền văn bản (nét) và chế độ hiển thị. Nó cho phép bạn tùy chỉnh cách văn bản xuất hiện về nét và tô.

#### Hỏi: Tôi có thể áp dụng các màu tô và đường viền khác nhau cho các phần khác nhau của cùng một văn bản không?

 Trả lời: Có, bạn có thể sửa đổi mã để tạo các mã khác nhau`TextState` đối tượng có màu tô và đường viền riêng biệt rồi áp dụng chúng cho các phần cụ thể của văn bản bằng cách sử dụng các màu riêng biệt`Stamp` các đối tượng.

#### Câu hỏi: Tôi có thể áp dụng màu tô và đường viền cho văn bản đã có trong tài liệu PDF không?

 Đáp: Có, bạn có thể sử dụng các nguyên tắc tương tự để áp dụng màu tô và đường viền cho văn bản hiện có trong tài liệu PDF bằng cách chọn các đối tượng văn bản thích hợp và thêm chúng dưới dạng dấu với các thuộc tính mong muốn.`TextState` của cải.

#### Câu hỏi: Làm cách nào tôi có thể điều chỉnh độ mờ và hòa trộn của văn bản được tô màu và có đường viền?

 Trả lời: Mã được cung cấp cho phép bạn đặt thuộc tính độ mờ và hòa trộn của tem bằng cách sử dụng`Opacity` Và`BlendingSpace`các thuộc tính tương ứng. Bạn có thể điều chỉnh các giá trị này để đạt được hiệu ứng hình ảnh mong muốn.

#### Hỏi: Làm cách nào tôi có thể áp dụng các màu tô và đường viền khác nhau cho nhiều tem trong cùng một tài liệu PDF?

 Đáp: Bạn có thể tạo nhiều`TextState` các đối tượng có màu tô và đường viền khác nhau, sau đó tạo các đối tượng riêng biệt`Stamp` các đối tượng cho mỗi bộ văn bản với màu sắc riêng biệt. Thêm các dấu này vào cùng một tài liệu PDF bằng cách sử dụng`PdfFileStamp` lớp học.

#### Câu hỏi: Tôi có thể sử dụng các phông chữ khác ngoài Arial cho văn bản có viền và được điền không?

 Đ: Có, bạn có thể thay đổi phông chữ bằng cách sửa đổi tham số tên phông chữ trong`FormattedText` hàm tạo khi tạo tem. Bạn có thể sử dụng bất kỳ phông chữ nào có sẵn trên hệ thống của bạn.

#### Câu hỏi: Làm cách nào tôi có thể sửa đổi góc xoay của văn bản được viền và tô màu?

 Đáp: Mã được cung cấp cho phép bạn đặt góc xoay của tem bằng cách sử dụng`Rotation` tài sản. Bạn có thể điều chỉnh thuộc tính này để chỉ định góc xoay mong muốn cho văn bản.

#### Hỏi: Làm cách nào tôi có thể kiểm soát vị trí và kích thước của văn bản có viền và được điền trên trang?

Đáp: Bạn có thể sử dụng`SetOrigin` phương pháp của`Stamp` đối tượng để đặt tọa độ X và Y của vị trí tem trên trang. Ngoài ra, bạn có thể điều chỉnh kích thước phông chữ trong`FormattedText` hàm tạo để kiểm soát kích thước của văn bản.