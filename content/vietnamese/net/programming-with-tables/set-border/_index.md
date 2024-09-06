---
title: Đặt đường viền trong PDF thành bảng
linktitle: Đặt đường viền trong PDF thành bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo đường viền trong PDF thành bảng bằng Aspose.PDF cho .NET.
type: docs
weight: 200
url: /vi/net/programming-with-tables/set-border/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để thiết lập đường viền trong bảng của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai.

## Bước 1: Khởi tạo đối tượng Document
Đầu tiên, chúng ta sẽ khởi tạo một đối tượng Document:

```csharp
Document doc = new Document();
```

## Bước 2: Thêm trang vào tài liệu PDF
Tiếp theo, chúng ta sẽ thêm một trang vào tài liệu PDF:

```csharp
Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng BorderInfo
Bây giờ chúng ta sẽ tạo một đối tượng BorderInfo để xác định đường viền của bảng:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Bước 4: Xác định đường viền trên và dưới
Chúng tôi sẽ chỉ định rằng đường viền trên và dưới sẽ là đường viền kép:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Bước 5: Khởi tạo đối tượng Table
Bây giờ chúng ta hãy khởi tạo một đối tượng Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Bước 6: Chỉ định độ rộng cột
Chúng ta sẽ chỉ định chiều rộng của các cột trong bảng:

```csharp
table. ColumnWidths = "100";
```

## Bước 7: Tạo đối tượng hàng
Chúng ta sẽ tạo một đối tượng Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Bước 8: Thêm một ô vào hàng
Tiếp theo, chúng ta sẽ thêm một ô vào hàng:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Bước 9: Thiết lập đường viền ô
Chúng ta sẽ xác định đường viền của ô (đường viền kép):

```csharp
cell. Border = border;
```

## Bước 10: Thêm bảng vào trang
Bây giờ chúng ta hãy thêm bảng vào trang tài liệu:

```csharp
page.Paragraphs.Add(table);
```

## Bước 11: Lưu tài liệu PDF
Cuối cùng, chúng ta sẽ lưu tài liệu PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Mã nguồn ví dụ cho Set Border sử dụng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Thêm trang vào tài liệu PDF
Page page = doc.Pages.Add();
// Tạo đối tượng BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Chỉ định rằng Đường viền trên sẽ là đường viền kép
border.Top.IsDoubled = true;
// Chỉ định rằng đường viền dưới sẽ là đường viền kép
border.Bottom.IsDoubled = true;
// Khởi tạo đối tượng Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Chỉ định thông tin chiều rộng cột
table.ColumnWidths = "100";
// Tạo đối tượng Row
Aspose.Pdf.Row row = table.Rows.Add();
// Thêm một ô Bảng vào bộ sưu tập ô của hàng
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Đặt đường viền cho đối tượng ô (đường viền kép)
cell.Border = border;
// Thêm bảng vào bộ sưu tập đoạn văn của Trang
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học cách thiết lập đường viền trong bảng của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách tạo tài liệu, thêm trang, cấu hình đường viền bảng và lưu tài liệu PDF. Bây giờ bạn có thể áp dụng kiến thức này vào các dự án của riêng mình.

### Câu hỏi thường gặp

#### H: Tôi có thể thiết lập các kiểu đường viền khác nhau (ví dụ: nét đứt hoặc chấm bi) cho đường viền trên cùng và dưới cùng của bảng không?

 A: Có, bạn có thể thiết lập các kiểu đường viền khác nhau cho đường viền trên cùng và dưới cùng của bảng bằng cách sửa đổi`border.Top.Style` Và`border.Bottom.Style`thuộc tính trong mã nguồn C# được cung cấp. Aspose.PDF cho .NET cho phép bạn chọn từ nhiều kiểu đường viền khác nhau, bao gồm Solid, Dashed, Dotted, Double, v.v.

#### H: Làm thế nào để thiết lập màu đường viền của bảng?

 A: Bạn có thể thiết lập màu của đường viền bảng bằng cách sửa đổi`border.Color` thuộc tính trong mã nguồn C#. Chỉ cần cung cấp màu mong muốn, chẳng hạn như`Aspose.Pdf.Color.Red` hoặc bất kỳ màu sắc hợp lệ nào khác để tùy chỉnh màu đường viền.

#### H: Có thể áp dụng đường viền cho từng ô trong bảng bằng các thiết lập khác nhau (ví dụ: màu sắc hoặc kiểu đường viền khác nhau) không?

 A: Có, bạn có thể áp dụng đường viền cho từng ô trong bảng với các thiết lập khác nhau bằng cách cấu hình`cell.Border` thuộc tính cho từng ô riêng lẻ. Điều này cho phép bạn có kiểu viền và màu sắc riêng cho từng ô dựa trên yêu cầu của bạn.

#### H: Tôi có thể xóa đường viền ở các cạnh cụ thể của bảng (ví dụ: đường viền trái và phải) không?

 A: Có, bạn có thể xóa đường viền khỏi các cạnh cụ thể của bảng bằng cách sửa đổi`border.Left`, `border.Right`, `border.Top` , Và`border.Bottom`thuộc tính trong mã nguồn C#. Thiết lập các thuộc tính này thành`null` sẽ xóa đường viền khỏi các cạnh tương ứng của bảng.

#### H: Làm thế nào để điều chỉnh độ dày của viền bảng?

 A: Bạn có thể điều chỉnh độ dày của đường viền bảng bằng cách sửa đổi`border.Width` thuộc tính trong mã nguồn C#. Chỉ cần đặt chiều rộng đường viền mong muốn (tính bằng điểm) để đạt được độ dày mong muốn.