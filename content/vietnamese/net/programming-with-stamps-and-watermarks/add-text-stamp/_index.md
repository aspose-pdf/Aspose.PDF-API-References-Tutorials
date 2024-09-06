---
title: Thêm Dấu Văn Bản Vào Tệp PDF
linktitle: Thêm Dấu Văn Bản Vào Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách dễ dàng thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 50
url: /vi/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# được cung cấp để thêm dấu văn bản tùy chỉnh vào một trang cụ thể của tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu PDF

Bước đầu tiên là tải tài liệu PDF hiện có vào dự án của bạn. Thực hiện như sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 3: Tạo bộ đệm văn bản

Bây giờ bạn đã tải lên tài liệu PDF, bạn có thể tạo tem văn bản để thêm vào. Sau đây là cách thực hiện:

```csharp
// Tạo bộ đệm văn bản
TextStamp textStamp = new TextStamp("Example Stamp");
```

Đoạn mã trên tạo ra một bộ đệm văn bản mới chứa văn bản được chỉ định.

## Bước 4: Cấu hình Thuộc tính Dấu văn bản

Trước khi thêm dấu văn bản vào tài liệu PDF, bạn có thể cấu hình nhiều thuộc tính khác nhau của dấu, chẳng hạn như nền, vị trí, góc xoay, phông chữ, kích thước, v.v. Thực hiện như sau:

```csharp
// Cấu hình thuộc tính bộ đệm văn bản
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Bạn có thể điều chỉnh các thuộc tính này tùy theo nhu cầu của mình.

## Bước 5: Thêm Dấu Văn Bản vào PDF

Bây giờ con dấu văn bản đã sẵn sàng, bạn có thể thêm nó vào một trang cụ thể của tài liệu PDF. Thực hiện như sau:

```csharp
//Thêm vùng đệm văn bản vào trang cụ thể
pdfDocument.Pages[1].AddStamp(textStamp);
```

Mã ở trên thêm dấu văn bản vào trang đầu tiên của tài liệu PDF. Bạn có thể chỉ định trang khác nếu cần.

## Bước 6: Lưu tài liệu đầu ra

Sau khi thêm dấu văn bản, bạn có thể lưu tài liệu PDF đã chỉnh sửa. Thực hiện như sau:

```csharp
// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
```

Đoạn mã trên sẽ lưu tài liệu PDF đã chỉnh sửa vào thư mục được chỉ định.

### Mã nguồn mẫu cho Thêm Dấu Văn bản bằng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Tạo con dấu văn bản
TextStamp textStamp = new TextStamp("Sample Stamp");

// Thiết lập tem có phải là nền không
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

Xin chúc mừng! Bạn đã học được cách thêm tem văn bản bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng kiến thức này vào các dự án của riêng mình để thêm tem văn bản tùy chỉnh vào tài liệu PDF.

### Câu hỏi thường gặp về việc thêm dấu văn bản vào tệp PDF

#### H: Mục đích của việc thêm dấu văn bản vào tệp PDF bằng Aspose.PDF cho .NET là gì?

A: Thêm tem văn bản cho phép bạn đặt văn bản tùy chỉnh trên một trang cụ thể của tài liệu PDF. Tính năng này hữu ích để thêm nhãn, bình luận, hình mờ hoặc bất kỳ thông tin văn bản nào khác để nâng cao nội dung của tài liệu và cung cấp thêm ngữ cảnh.

#### H: Tôi có thể tùy chỉnh giao diện của con dấu văn bản như phông chữ, kích thước, màu sắc và cách xoay không?

 A: Có, bạn có thể tùy chỉnh hoàn toàn giao diện của tem văn bản. Mã nguồn C# được cung cấp sẽ trình bày cách thiết lập các thuộc tính khác nhau của`TextStamp` đối tượng, bao gồm phông chữ, cỡ chữ, kiểu phông chữ, màu chữ, màu nền và góc quay.

#### H: Có thể thêm nhiều dấu văn bản vào nhiều trang khác nhau của cùng một tài liệu PDF không?

A: Hoàn toàn có thể, bạn có thể thêm nhiều tem văn bản vào các trang khác nhau của cùng một tài liệu PDF. Mã được cung cấp trong hướng dẫn cho phép bạn chỉ định trang đích để thêm tem văn bản, giúp linh hoạt cho các trang khác nhau trong tài liệu.

#### H: Làm thế nào để xác định vị trí của dấu văn bản trong tài liệu PDF?

 A: Bạn có thể tùy chỉnh vị trí của dấu văn bản bằng cách sửa đổi`XIndent` Và`YIndent` tính chất của`TextStamp` đối tượng. Các thuộc tính này xác định tọa độ của góc trên bên trái của tem so với gốc của trang.

#### H: Tôi có thể áp dụng phương pháp này cho các tài liệu PDF hiện có để thêm dấu văn bản không?

A: Có, bạn có thể áp dụng phương pháp này cho các tài liệu PDF hiện có để thêm dấu văn bản. Mã được cung cấp trong hướng dẫn sẽ trình bày cách tải một tài liệu PDF hiện có và thêm dấu văn bản vào một trang cụ thể.

#### H: Tôi có thể thêm cả màu nền và màu tiền cảnh vào dấu văn bản không?

 A: Có, bạn có thể thêm cả màu nền và màu nền trước vào tem văn bản. Bằng cách thiết lập`Background` tài sản để`true` , bạn có thể cung cấp một nền màu cho con dấu văn bản. Ngoài ra, bạn có thể thiết lập`TextState.ForegroundColor` thuộc tính để chỉ định màu của chính văn bản.

#### H: Làm sao tôi có thể đảm bảo rằng dấu văn bản không che khuất nội dung cơ bản của tài liệu PDF?

A: Khi thêm dấu văn bản, hãy chú ý đến vị trí của nó để đảm bảo rằng nó không che khuất thông tin quan trọng hoặc ảnh hưởng tiêu cực đến khả năng đọc của tài liệu. Bạn có thể điều chỉnh`XIndent` Và`YIndent` thuộc tính để định vị dấu văn bản một cách thích hợp.

#### H: Tôi có thể sử dụng phương pháp này để thêm tem ngoài văn bản, chẳng hạn như hình ảnh hoặc logo không?

A: Hướng dẫn cụ thể này tập trung vào việc thêm tem văn bản, nhưng bạn cũng có thể thêm các loại tem khác, chẳng hạn như hình ảnh hoặc logo, bằng cách sử dụng Aspose.PDF cho .NET. Quá trình này bao gồm việc tạo đối tượng tem phù hợp và cấu hình các thuộc tính của nó.

#### H: Làm thế nào tôi có thể tự động hóa quá trình thêm dấu văn bản vào nhiều tài liệu PDF?

A: Bạn có thể tự động hóa quy trình thêm dấu văn bản vào nhiều tài liệu PDF bằng cách tạo một tập lệnh hoặc chương trình lặp qua danh sách các tài liệu và áp dụng cùng một quy trình đóng dấu văn bản cho từng tài liệu.