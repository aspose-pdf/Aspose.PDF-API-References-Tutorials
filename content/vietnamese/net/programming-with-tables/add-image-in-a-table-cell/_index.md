---
title: Thêm hình ảnh vào ô bảng
linktitle: Thêm hình ảnh vào ô bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET - hướng dẫn từng bước để thao tác chính xác hình ảnh trong tài liệu PDF.
type: docs
weight: 10
url: /vi/net/programming-with-tables/add-image-in-a-table-cell/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày cách thực hiện chức năng này. Bằng cách làm theo các bước được nêu dưới đây, bạn sẽ có thể kết hợp hình ảnh vào ô bảng của mình một cách hiệu quả.

Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn đã cài đặt và tham chiếu thư viện Aspose.PDF cho .NET trong dự án của mình.

## Bước 1: Thiết lập Tài liệu

 Để bắt đầu, chúng ta cần tạo một phiên bản mới của`Document` lớp từ không gian tên Aspose.Pdf. Lớp này biểu diễn một tài liệu PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một đối tượng Tài liệu
Document pdfDocument = new Document();
```

## Bước 2: Tạo trang

Tiếp theo, chúng ta cần thêm một trang vào tài liệu PDF. Một trang đóng vai trò là nơi chứa bảng và các thành phần khác.

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

## Bước 4: Thiết lập đường viền ô mặc định

 Để đảm bảo tính nhất quán, chúng ta có thể thiết lập đường viền ô mặc định bằng cách sử dụng`DefaultCellBorder`tính chất của bảng`BorderInfo` sự vật.

```csharp
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Bước 5: Thiết lập độ rộng cột

 Để xác định chiều rộng của mỗi cột trong bảng, chúng ta có thể thiết lập`ColumnWidths` thuộc tính. Chỉ định chiều rộng dưới dạng chuỗi với các giá trị được phân tách bằng dấu cách.

```csharp
// Thiết lập với chiều rộng cột của bảng
tab1.ColumnWidths = "100 100 120";
```

## Bước 6: Thêm hình ảnh vào ô bảng

Bây giờ đến phần thú vị, thêm hình ảnh vào ô bảng. Để thực hiện việc này, chúng ta sẽ làm theo các bước phụ sau:

## Bước 6.1: Tạo đối tượng hình ảnh

 Tạo một phiên bản của`Image` lớp từ không gian tên Aspose.Pdf. Đặt`File` thuộc tính vào đường dẫn đến tệp hình ảnh bạn muốn thêm.

```csharp
// Tạo một đối tượng hình ảnh
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

## Bước 6.4: Thêm các ô bổ sung

Sau khi thêm ô hình ảnh, chúng ta có thể thêm nhiều ô vào hàng nếu cần.

```csharp
//Thêm một ô nữa vào hàng
row1.Cells.Add("Previous cell with image");

// Điều chỉnh căn chỉnh theo chiều dọc của ô thứ ba
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Bước 7: Lưu tài liệu

 Cuối cùng, chúng ta có thể lưu tài liệu đã sửa đổi vào một vị trí đã chỉ định bằng cách sử dụng`Save` phương pháp.

```csharp
// Lưu tài liệu
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Xin chúc mừng! Bạn đã học thành công cách thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET. Hãy thoải mái khám phá thêm các tùy chọn tùy chỉnh và tích hợp chức năng này vào các dự án của bạn.

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
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Thiết lập với chiều rộng cột của bảng
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

Trong hướng dẫn này, chúng tôi đã trình bày hướng dẫn từng bước về cách thêm hình ảnh vào ô bảng bằng Aspose.PDF cho .NET. Chúng tôi bắt đầu bằng cách thiết lập tài liệu, tạo trang và thêm bảng. Sau đó, chúng tôi đặt đường viền ô và độ rộng cột mặc định. Chúng tôi đã trình bày cách thêm hình ảnh vào ô bảng và điều chỉnh căn chỉnh theo chiều dọc của ô. Cuối cùng, chúng tôi đã lưu tài liệu đã sửa đổi. Bằng cách làm theo các bước này, bạn có thể cải thiện tài liệu PDF của mình bằng hình ảnh trong ô bảng một cách hiệu quả.

### Câu hỏi thường gặp

#### H: Tôi có thể thêm nhiều hình ảnh vào các ô khác nhau trong cùng một bảng bằng Aspose.PDF cho .NET không?

A: Có, bạn có thể thêm nhiều hình ảnh vào các ô khác nhau trong cùng một bảng bằng Aspose.PDF cho .NET. Chỉ cần làm theo cùng một quy trình được trình bày trong hướng dẫn cho mỗi hình ảnh bạn muốn thêm vào bảng.

#### H: Tôi có thể tùy chỉnh kích thước và vị trí hình ảnh trong ô bảng không?

 A: Có, bạn có thể tùy chỉnh kích thước và vị trí hình ảnh trong ô bảng bằng cách điều chỉnh các thuộc tính của`Image`đối tượng. Bạn có thể thiết lập chiều rộng và chiều cao của hình ảnh, cũng như căn chỉnh trong ô.

#### H: Tôi có thể thêm hình ảnh vào bảng có số lượng hàng và cột động không?

A: Có, bạn có thể thêm hình ảnh vào bảng với số lượng hàng và cột động. Aspose.PDF cho .NET cung cấp tính linh hoạt trong việc tạo bảng với nhiều kích thước khác nhau. Bạn có thể thêm hàng và ô khi cần, sau đó thêm hình ảnh vào các ô cụ thể theo đó.

#### H: Aspose.PDF hỗ trợ những định dạng hình ảnh nào cho .NET để thêm hình ảnh vào ô bảng?

A: Aspose.PDF for .NET hỗ trợ nhiều định dạng hình ảnh, bao gồm JPEG, PNG, GIF, BMP và TIFF. Bạn có thể sử dụng hình ảnh ở bất kỳ định dạng nào trong số này để thêm vào ô bảng.

#### H: Tôi có thể thêm hình ảnh vào bảng trong tài liệu PDF hiện có không?

A: Có, bạn có thể thêm hình ảnh vào bảng trong tài liệu PDF hiện có bằng Aspose.PDF cho .NET. Chỉ cần tải tài liệu hiện có và làm theo các bước tương tự để thêm hình ảnh vào bảng như được trình bày trong hướng dẫn.