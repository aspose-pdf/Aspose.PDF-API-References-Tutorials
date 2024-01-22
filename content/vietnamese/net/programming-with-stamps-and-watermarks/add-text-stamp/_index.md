---
title: Thêm dấu văn bản vào tệp PDF
linktitle: Thêm dấu văn bản vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách dễ dàng thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để thêm dấu văn bản tùy chỉnh vào một trang cụ thể của tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu PDF

Bước đầu tiên là tải tài liệu PDF hiện có vào dự án của bạn. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 3: Tạo bộ đệm văn bản

Bây giờ bạn đã tải lên tài liệu PDF, bạn có thể tạo dấu văn bản để thêm vào. Đây là cách thực hiện:

```csharp
// Tạo bộ đệm văn bản
TextStamp textStamp = new TextStamp("Example Stamp");
```

Đoạn mã trên tạo một bộ đệm văn bản mới chứa văn bản được chỉ định.

## Bước 4: Định cấu hình thuộc tính tem văn bản

Trước khi thêm dấu văn bản vào tài liệu PDF, bạn có thể định cấu hình các thuộc tính khác nhau của dấu, chẳng hạn như nền, vị trí, xoay, phông chữ, kích thước, v.v. Dưới đây là cách thực hiện:

```csharp
// Định cấu hình thuộc tính bộ đệm văn bản
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Bạn có thể điều chỉnh các thuộc tính này theo nhu cầu của bạn.

## Bước 5: Thêm dấu văn bản vào PDF

Bây giờ dấu văn bản đã sẵn sàng, bạn có thể thêm nó vào một trang cụ thể của tài liệu PDF. Đây là cách thực hiện:

```csharp
//Thêm bộ đệm văn bản vào trang cụ thể
pdfDocument.Pages[1].AddStamp(textStamp);
```

Đoạn mã trên thêm dấu văn bản vào trang đầu tiên của tài liệu PDF. Bạn có thể chỉ định một trang khác nếu cần.

## Bước 6: Lưu tài liệu đầu ra

Sau khi thêm dấu văn bản, bạn có thể lưu tài liệu PDF đã chỉnh sửa. Đây là cách thực hiện:

```csharp
// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
```

Đoạn mã trên lưu tài liệu PDF đã sửa đổi vào thư mục được chỉ định.

### Mã nguồn mẫu cho Thêm dấu văn bản bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Tạo dấu văn bản
TextStamp textStamp = new TextStamp("Sample Stamp");

// Đặt xem tem có phải là nền hay không
textStamp.Background = true;

// Đặt nguồn gốc
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Xoay tem
textStamp.Rotate = Rotation.on90;

// Đặt thuộc tính văn bản
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Thêm tem vào trang cụ thể
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm dấu văn bản bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể áp dụng kiến thức này cho các dự án của riêng mình để thêm dấu văn bản tùy chỉnh vào tài liệu PDF.

### Câu hỏi thường gặp về thêm dấu văn bản vào tệp PDF

#### Câu hỏi: Mục đích của việc thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET là gì?

Đáp: Việc thêm dấu văn bản cho phép bạn đặt văn bản tùy chỉnh trên một trang cụ thể của tài liệu PDF. Tính năng này hữu ích khi thêm nhãn, nhận xét, hình mờ hoặc bất kỳ thông tin văn bản nào khác nhằm nâng cao nội dung của tài liệu và cung cấp thêm ngữ cảnh.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của dấu văn bản, chẳng hạn như phông chữ, kích thước, màu sắc và cách xoay không?

 Trả lời: Có, bạn hoàn toàn có thể tùy chỉnh giao diện của tem văn bản. Mã nguồn C# được cung cấp minh họa cách thiết lập các thuộc tính khác nhau của`TextStamp` đối tượng, bao gồm phông chữ, cỡ chữ, kiểu phông chữ, màu văn bản, màu nền và xoay.

#### Hỏi: Có thể thêm nhiều dấu văn bản vào các trang khác nhau của cùng một tài liệu PDF không?

Đáp: Hoàn toàn có thể, bạn có thể thêm nhiều dấu văn bản vào các trang khác nhau của cùng một tài liệu PDF. Mã được cung cấp trong hướng dẫn cho phép bạn chỉ định trang đích để thêm dấu văn bản, làm cho nó trở nên linh hoạt cho các trang khác nhau trong tài liệu.

#### Hỏi: Làm cách nào để chỉ định vị trí của dấu văn bản trong tài liệu PDF?

 Đáp: Bạn có thể tùy chỉnh vị trí của dấu văn bản bằng cách sửa đổi`XIndent` Và`YIndent` thuộc tính của`TextStamp` sự vật. Các thuộc tính này xác định tọa độ góc trên bên trái của dấu so với điểm gốc của trang.

#### Hỏi: Tôi có thể áp dụng phương pháp này cho các tài liệu PDF hiện có để thêm dấu văn bản không?

Đáp: Có, bạn có thể áp dụng phương pháp này cho các tài liệu PDF hiện có để thêm dấu văn bản. Mã được cung cấp trong hướng dẫn này trình bày cách tải tài liệu PDF hiện có và thêm dấu văn bản vào một trang cụ thể.

#### Hỏi: Tôi có thể thêm cả màu nền và màu nền trước vào dấu văn bản không?

 Đáp: Có, bạn có thể thêm cả màu nền và màu nền trước vào dấu văn bản. Bằng cách thiết lập`Background` tài sản để`true` , bạn có thể cung cấp nền màu cho tem văn bản. Ngoài ra, bạn có thể thiết lập`TextState.ForegroundColor` thuộc tính để chỉ định màu của văn bản.

#### Hỏi: Làm cách nào tôi có thể đảm bảo rằng dấu văn bản không che khuất nội dung cơ bản của tài liệu PDF?

 Đáp: Khi thêm dấu văn bản, hãy lưu ý đến vị trí của dấu văn bản để đảm bảo rằng dấu không cản trở thông tin quan trọng hoặc ảnh hưởng tiêu cực đến khả năng đọc của tài liệu. Bạn có thể điều chỉnh`XIndent` Và`YIndent` Properties để định vị dấu văn bản một cách thích hợp.

#### Hỏi: Tôi có thể sử dụng phương pháp này để thêm tem không phải văn bản, chẳng hạn như hình ảnh hoặc logo không?

Đáp: Hướng dẫn cụ thể này tập trung vào việc thêm tem văn bản, nhưng bạn có thể thêm các loại tem khác theo cách tương tự, chẳng hạn như hình ảnh hoặc biểu trưng, bằng cách sử dụng Aspose.PDF cho .NET. Quá trình này bao gồm việc tạo đối tượng tem thích hợp và định cấu hình các thuộc tính của nó.

#### Hỏi: Làm cách nào tôi có thể tự động hóa quá trình thêm dấu văn bản vào nhiều tài liệu PDF?

Đáp: Bạn có thể tự động hóa quy trình thêm dấu văn bản vào nhiều tài liệu PDF bằng cách tạo tập lệnh hoặc chương trình lặp qua danh sách tài liệu và áp dụng cùng một quy trình đóng dấu văn bản cho từng tài liệu.