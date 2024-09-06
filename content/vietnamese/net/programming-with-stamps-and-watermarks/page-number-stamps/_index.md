---
title: Con dấu số trang trong tệp PDF
linktitle: Con dấu số trang trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm dấu số trang vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 160
url: /vi/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm dấu số trang vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để mở một tài liệu PDF hiện có, tạo dấu số trang, thiết lập thuộc tính của nó và thêm nó vào một trang cụ thể trong tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Môi trường phát triển .NET đã được cài đặt.
- Thư viện Aspose.PDF dành cho .NET đã được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu PDF hiện có

Bước đầu tiên là tải tài liệu PDF hiện có vào dự án của bạn. Thực hiện như sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu PDF hiện có
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 3: Tạo và cấu hình con dấu đánh số trang

Bây giờ tài liệu PDF đã được tải, chúng ta có thể tạo bộ đệm đánh số trang và cấu hình nó theo nhu cầu của mình. Sau đây là cách thực hiện:

```csharp
// Tạo bộ đệm số trang
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Xác định xem bộ đệm có ở chế độ nền hay không
pageNumberStamp.Background = false;

// Định dạng của bộ đệm đánh số trang
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Lề dưới của bộ đệm đánh số trang
pageNumberStamp.BottomMargin = 10;

// Căn chỉnh theo chiều ngang của bộ đệm đánh số trang
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Bắt đầu số trang đánh số
pageNumberStamp.StartingNumber = 1;

// Đặt thuộc tính văn bản đệm số trang
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Đoạn mã trên tạo ra một con dấu số trang với các thuộc tính như định dạng số trang, lề dưới, căn chỉnh theo chiều ngang, số bắt đầu và các thuộc tính văn bản.

## Bước 4: Thêm dấu số trang vào một trang cụ thể

Sau khi cấu hình xong con dấu số trang, chúng ta có thể thêm nó vào một trang cụ thể của tài liệu PDF. Thực hiện như sau:

```csharp
// Thêm bộ đệm số trang vào một trang cụ thể
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Mã trên thêm dấu số trang vào trang đầu tiên của tài liệu PDF. Bạn có thể thay đổi số trang khi cần.

## Bước 5: Lưu tài liệu PDF đã sửa đổi

Sau khi thêm dấu số trang vào tài liệu PDF, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Thực hiện như sau:

```csharp
// Lưu tài liệu PDF đã sửa đổi
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Hãy nhớ thay thế "YOUR DOCUMENTS DIRECTORY" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF đã chỉnh sửa.

### Mã nguồn mẫu cho Dấu số trang sử dụng Aspose.PDF cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Tạo dấu số trang
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Con tem có phải là nền không
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Đặt thuộc tính văn bản
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Thêm tem vào trang cụ thể
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Lưu tài liệu đầu ra
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thêm dấu số trang vào tài liệu PDF bằng Aspose.PDF cho .NET. Bây giờ bạn có thể cá nhân hóa tài liệu PDF của mình bằng cách thêm số trang rõ ràng và nhiều thông tin.

### Câu hỏi thường gặp về dấu số trang trong tệp PDF

#### H: Con dấu số trang là gì và nó được sử dụng như thế nào để thêm số trang vào tệp PDF?

A: Page Number Stamp là một tính năng trong Aspose.PDF cho phép bạn thêm số trang động vào các trang cụ thể của tài liệu PDF. Trong hướng dẫn này, bạn có thể thực hiện bằng cách tạo đối tượng PageNumberStamp, cấu hình thuộc tính của đối tượng và thêm vào trang được chỉ định.

#### H: Mã nguồn C# được cung cấp thực hiện việc thêm dấu số trang vào tệp PDF như thế nào?

A: Mã này trình bày cách tải một tài liệu PDF hiện có, tạo PageNumberStamp, thiết lập nhiều thuộc tính khác nhau (như định dạng, phông chữ, căn chỉnh, v.v.), sau đó thêm con dấu vào một trang cụ thể. Con dấu tự động tính tổng số trang và chèn số trang chính xác.

#### H: Tôi có thể tùy chỉnh giao diện của số trang như kiểu phông chữ, màu sắc và kích thước không?

A: Hoàn toàn có thể, bạn có thể tùy chỉnh giao diện của dấu số trang bằng cách điều chỉnh các thuộc tính như phông chữ, cỡ chữ, kiểu phông chữ (đậm, nghiêng, v.v.) và màu chữ.

#### H: Có thể thêm dấu số trang vào nhiều trang trong một tài liệu PDF không?

A: Có, bạn có thể thêm dấu số trang vào nhiều trang bằng cách tạo nhiều đối tượng PageNumberStamp và thêm từng đối tượng vào các trang mong muốn.

#### H: Tôi có thể chọn hiển thị số trang như một phần của nội dung trang hay như một phần nền không?

 A: Có, bạn có thể kiểm soát việc con dấu số trang xuất hiện như một phần của nội dung trang hay như một phần tử nền bằng cách thiết lập`Background` thuộc tính của PageNumberStamp.

#### H: Làm thế nào để chỉ định định dạng số trang, bao gồm tổng số trang?

 A: Mã sử dụng`Format`thuộc tính của PageNumberStamp để chỉ định định dạng của số trang. Macro "# of" được sử dụng để biểu thị tổng số trang.

#### H: Điều gì xảy ra nếu tôi thêm cùng một con dấu số trang vào nhiều trang?

A: Thêm cùng một trường hợp PageNumberStamp vào nhiều trang sẽ hiển thị đúng số trang cho từng trang. Con dấu tự động điều chỉnh số trang và tổng số trang.

#### H: Tôi có thể thêm dấu số trang vào phần đầu trang hoặc chân trang của tài liệu PDF không?

A: Trong khi PageNumberStamp thường được thêm trực tiếp vào nội dung của trang, bạn có thể sử dụng FloatingBox hoặc các kỹ thuật khác để định vị chúng trong phần đầu trang hoặc chân trang.

#### H: Làm thế nào để xác định vị trí đóng dấu số trang trên trang?

 A: Cái`BottomMargin` Và`HorizontalAlignment` Thuộc tính của PageNumberStamp cho phép bạn kiểm soát vị trí của con dấu trong trang.

#### H: Tôi phải làm sao nếu muốn bắt đầu đánh số trang từ một số khác thay vì 1?

 A: Bạn có thể thiết lập`StartingNumber`thuộc tính của PageNumberStamp để chỉ định số trang bắt đầu.