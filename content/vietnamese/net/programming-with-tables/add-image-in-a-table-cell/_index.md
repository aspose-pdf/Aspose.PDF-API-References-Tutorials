---
title: Thêm hình ảnh vào ô bảng
linktitle: Thêm hình ảnh vào ô bảng
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Thêm hình ảnh vào ô bảng với Aspose.PDF cho .NET hướng dẫn từng bước để thao tác chính xác với hình ảnh trong tài liệu PDF.
type: docs
weight: 10
url: /vi/net/programming-with-tables/add-image-in-a-table-cell/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp minh họa cách đạt được chức năng này. Bằng cách làm theo các bước được nêu bên dưới, bạn sẽ có thể kết hợp hình ảnh vào các ô trong bảng của mình một cách hiệu quả.

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn đã cài đặt và tham chiếu thư viện Aspose.PDF cho .NET trong dự án của mình.

## Bước 1: Thiết lập tài liệu

 Để bắt đầu, chúng ta cần tạo một phiên bản mới của`Document` lớp từ không gian tên Aspose.Pdf. Lớp này đại diện cho một tài liệu PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một đối tượng Tài liệu
Document pdfDocument = new Document();
```

## Bước 2: Tạo trang

Tiếp theo, chúng ta cần thêm một trang vào tài liệu PDF. Một trang đóng vai trò là nơi chứa bảng và các phần tử khác.

```csharp
// Tạo một trang trong tài liệu pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Bước 3: Thêm bảng

 Trong bước này, chúng ta sẽ tạo một bảng bằng cách khởi tạo`Table` lớp từ không gian tên Aspose.Pdf.

```csharp
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Bước 4: Đặt viền ô mặc định

 Để đảm bảo tính nhất quán, chúng ta có thể đặt đường viền ô mặc định bằng cách sử dụng`DefaultCellBorder`thuộc tính của bảng`BorderInfo` sự vật.

```csharp
// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Bước 5: Đặt độ rộng cột

 Để xác định độ rộng của mỗi cột trong bảng, chúng ta có thể đặt`ColumnWidths` tài sản. Chỉ định độ rộng dưới dạng một chuỗi có các giá trị được phân tách bằng dấu cách.

```csharp
// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "100 100 120";
```

## Bước 6: Thêm hình ảnh vào ô bảng

Bây giờ đến phần thú vị, thêm hình ảnh vào ô trong bảng. Để làm điều này, chúng tôi sẽ làm theo các bước phụ sau:

## Bước 6.1: Tạo đối tượng hình ảnh

 Tạo một thể hiện của`Image` lớp từ không gian tên Aspose.Pdf. Đặt`File` thuộc tính vào đường dẫn của tệp hình ảnh bạn muốn thêm.

```csharp
// Tạo một đối tượng Hình ảnh
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Bước 6.2: Tạo hàng và ô

Để thêm hình ảnh vào bảng, trước tiên chúng ta cần tạo một hàng và các ô cần thiết.

```csharp
// Tạo một hàng trong bảng
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Thêm một ô văn bản vào hàng
row1.Cells.Add("Sample text in cell");

// Thêm ô chứa hình ảnh
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Bước 6.3: Thêm hình ảnh vào ô bảng

Cuối cùng, chúng ta có thể thêm hình ảnh vào ô của bảng bằng cách thêm nó dưới dạng một đoạn văn trong ô.

```csharp
// Thêm hình ảnh vào ô bảng
cell2.Paragraphs.Add(img);
```

## Bước 6.4: Thêm ô bổ sung

Sau khi thêm ô hình ảnh, chúng ta có thể thêm nhiều ô vào hàng nếu cần.

```csharp
//Thêm một ô khác vào hàng
row1.Cells.Add("Previous cell with image");

// Điều chỉnh căn chỉnh theo chiều dọc của ô thứ ba
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Bước 7: Lưu tài liệu

 Cuối cùng, chúng ta có thể lưu tài liệu đã sửa đổi vào một vị trí được chỉ định bằng cách sử dụng`Save` phương pháp.

```csharp
// Lưu tài liệu
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Chúc mừng! Bạn đã học thành công cách thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET. Vui lòng khám phá các tùy chọn tùy chỉnh khác và tích hợp chức năng này vào các dự án của bạn.

### Mã nguồn ví dụ để thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một đối tượng Tài liệu
Document pdfDocument = new Document();
// Tạo một trang trong tài liệu pdf
Page sec1 = pdfDocument.Pages.Add();
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của trang mong muốn
sec1.Paragraphs.Add(tab1);
// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Thêm ô chứa hình ảnh
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Thêm hình ảnh vào ô bảng
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Lưu tài liệu
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày hướng dẫn từng bước về cách thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET. Chúng tôi bắt đầu bằng cách thiết lập tài liệu, tạo trang và thêm bảng. Sau đó, chúng tôi đặt đường viền ô và độ rộng cột mặc định. Chúng tôi đã trình bày cách thêm hình ảnh vào một ô trong bảng và điều chỉnh căn chỉnh theo chiều dọc của ô. Cuối cùng, chúng tôi đã lưu tài liệu đã sửa đổi. Bằng cách làm theo các bước này, bạn có thể nâng cao tài liệu PDF của mình bằng hình ảnh trong các ô bảng một cách hiệu quả.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể thêm nhiều hình ảnh vào các ô khác nhau trong cùng một bảng bằng Aspose.PDF cho .NET không?

Đáp: Có, bạn có thể thêm nhiều hình ảnh vào các ô khác nhau trong cùng một bảng bằng Aspose.PDF for .NET. Chỉ cần làm theo quy trình tương tự được trình bày trong hướng dẫn cho từng hình ảnh bạn muốn thêm vào bảng.

#### Câu hỏi: Tôi có thể tùy chỉnh kích thước và vị trí hình ảnh trong ô bảng không?

 Trả lời: Có, bạn có thể tùy chỉnh kích thước và vị trí hình ảnh trong ô bảng bằng cách điều chỉnh các thuộc tính của`Image`sự vật. Bạn có thể đặt chiều rộng và chiều cao của hình ảnh cũng như căn chỉnh trong ô.

#### Câu hỏi: Tôi có thể thêm hình ảnh vào một bảng có số hàng và cột động không?

Đáp: Có, bạn có thể thêm hình ảnh vào một bảng có số lượng hàng và cột động. Aspose.PDF for .NET cung cấp tính linh hoạt trong việc tạo các bảng có kích thước khác nhau. Bạn có thể thêm hàng và ô nếu cần, sau đó thêm hình ảnh vào các ô cụ thể tương ứng.

#### Câu hỏi: Aspose.PDF hỗ trợ những định dạng hình ảnh nào cho .NET để thêm hình ảnh vào ô bảng?

Đáp: Aspose.PDF for .NET hỗ trợ nhiều định dạng hình ảnh, bao gồm JPEG, PNG, GIF, BMP và TIFF. Bạn có thể sử dụng hình ảnh thuộc bất kỳ định dạng nào trong số này để thêm chúng vào ô bảng.

#### Câu hỏi: Tôi có thể thêm hình ảnh vào bảng trong tài liệu PDF hiện có không?

Trả lời: Có, bạn có thể thêm hình ảnh vào bảng trong tài liệu PDF hiện có bằng Aspose.PDF cho .NET. Chỉ cần tải tài liệu hiện có và làm theo các bước tương tự để thêm hình ảnh vào bảng như được minh họa trong hướng dẫn.