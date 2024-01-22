---
title: Tem số trang trong file PDF
linktitle: Tem số trang trong file PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm tem số trang trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 160
url: /vi/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách thêm tem số trang vào tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để mở tài liệu PDF hiện có, tạo tem số trang, đặt thuộc tính của nó và thêm nó vào một trang cụ thể trong tệp PDF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Một môi trường phát triển .NET được cài đặt.
- Thư viện Aspose.PDF dành cho .NET được tải xuống và tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu PDF hiện có

Bước đầu tiên là tải tài liệu PDF hiện có vào dự án của bạn. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mở tài liệu PDF hiện có
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 3: Tạo và cấu hình tem đánh số trang

Bây giờ tài liệu PDF đã được tải, chúng ta có thể tạo bộ đệm đánh số trang và định cấu hình nó theo nhu cầu của mình. Đây là cách thực hiện:

```csharp
// Tạo bộ đệm số trang
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Xác định xem bộ đệm có ở chế độ nền hay không
pageNumberStamp.Background = false;

// Định dạng của bộ đệm đánh số trang
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Lề dưới của vùng đệm đánh số trang
pageNumberStamp.BottomMargin = 10;

// Căn chỉnh theo chiều ngang của bộ đệm đánh số trang
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Số bắt đầu đánh số trang
pageNumberStamp.StartingNumber = 1;

// Đặt thuộc tính văn bản đệm số trang
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Đoạn mã trên tạo dấu số trang với các thuộc tính như định dạng số trang, lề dưới, căn chỉnh theo chiều ngang, số bắt đầu và thuộc tính văn bản.

## Bước 4: Thêm tem số trang vào một trang cụ thể

Sau khi định cấu hình dấu số trang, chúng ta có thể thêm dấu này vào một trang cụ thể của tài liệu PDF. Đây là cách thực hiện:

```csharp
// Thêm bộ đệm số trang vào một trang cụ thể
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Đoạn mã trên thêm dấu số trang vào trang đầu tiên của tài liệu PDF. Bạn có thể thay đổi số trang nếu cần.

## Bước 5: Lưu tài liệu PDF đã sửa đổi

Sau khi thêm dấu số trang vào tài liệu PDF, chúng ta có thể lưu tài liệu PDF đã sửa đổi. Đây là cách thực hiện:

```csharp
// Lưu tài liệu PDF đã sửa đổi
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu PDF đã chỉnh sửa.

### Mã nguồn mẫu cho Tem số trang bằng Aspose.PDF for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Tạo tem đánh số trang
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Liệu con tem có phải là nền không
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

Xin chúc mừng! Bạn đã học cách thêm tem số trang vào tài liệu PDF bằng Aspose.PDF cho .NET. Giờ đây, bạn có thể cá nhân hóa tài liệu PDF của mình bằng cách thêm số trang rõ ràng và giàu thông tin.

### Câu hỏi thường gặp về tem số trang trong file PDF

#### Hỏi: Tem số trang là gì và nó được sử dụng như thế nào để thêm số trang vào tệp PDF?

Trả lời: Dấu số trang là một tính năng trong Aspose.PDF cho phép bạn thêm số trang động vào các trang cụ thể của tài liệu PDF. Trong hướng dẫn này, điều đó đạt được bằng cách tạo một đối tượng PageNumberStamp, định cấu hình các thuộc tính của nó và thêm nó vào một trang được chỉ định.

#### Câu hỏi: Mã nguồn C# được cung cấp thực hiện việc thêm tem số trang vào tệp PDF như thế nào?

Đáp: Mã này trình bày cách tải tài liệu PDF hiện có, tạo PageNumberStamp, đặt các thuộc tính khác nhau (chẳng hạn như định dạng, phông chữ, căn chỉnh, v.v.), sau đó thêm dấu vào một trang cụ thể. Con tem tự động tính toán tổng số trang và chèn số trang chính xác.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của số trang, chẳng hạn như kiểu phông chữ, màu sắc và kích thước không?

Trả lời: Hoàn toàn có thể, bạn có thể tùy chỉnh giao diện của tem số trang bằng cách điều chỉnh các thuộc tính như phông chữ, cỡ chữ, kiểu phông chữ (đậm, in nghiêng, v.v.) và màu văn bản.

#### Hỏi: Có thể thêm tem số trang vào nhiều trang trong tài liệu PDF không?

Trả lời: Có, bạn có thể thêm tem số trang vào nhiều trang bằng cách tạo nhiều đối tượng PageNumberStamp và thêm từng đối tượng vào các trang mong muốn.

#### Hỏi: Tôi có thể chọn dấu số trang xuất hiện như một phần nội dung của trang hay dưới dạng phần tử nền không?

 Đáp: Có, bạn có thể kiểm soát xem tem số trang xuất hiện như một phần nội dung của trang hay dưới dạng thành phần nền bằng cách đặt`Background` thuộc tính của PageNumberStamp.

#### Hỏi: Làm cách nào để chỉ định định dạng số trang, bao gồm tổng số trang?

 A: Mã sử dụng`Format`thuộc tính của PageNumberStamp để chỉ định định dạng số trang. Macro "# of" được sử dụng để biểu thị tổng số trang.

#### Hỏi: Điều gì xảy ra nếu tôi thêm cùng một dấu số trang vào nhiều trang?

Trả lời: Việc thêm cùng một phiên bản PageNumberStamp vào nhiều trang sẽ hiển thị số trang chính xác cho mỗi trang. Tem tự động điều chỉnh số trang và tổng số trang.

#### Hỏi: Tôi có thể thêm tem số trang vào phần đầu trang hoặc chân trang của tài liệu PDF không?

Trả lời: Mặc dù PageNumberStamp thường được thêm trực tiếp vào nội dung của trang nhưng bạn có thể sử dụng FloatBox hoặc các kỹ thuật khác để định vị chúng trong phần đầu trang hoặc chân trang.

#### Hỏi: Làm cách nào để xác định vị trí của dấu số trang trên trang?

 Đáp: Cái`BottomMargin` Và`HorizontalAlignment` thuộc tính của PageNumberStamp cho phép bạn kiểm soát vị trí của dấu trong trang.

#### Hỏi: Nếu tôi muốn bắt đầu đánh số trang từ một số khác thay vì 1 thì sao?

 Trả lời: Bạn có thể đặt`StartingNumber`thuộc tính của PageNumberStamp để chỉ định số trang bắt đầu.