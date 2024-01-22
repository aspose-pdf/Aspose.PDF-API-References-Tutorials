---
title: Đặt đường viền trong PDF thành bảng
linktitle: Đặt đường viền trong PDF thành bảng
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt đường viền trong PDF thành bảng bằng Aspose.PDF cho .NET.
type: docs
weight: 200
url: /vi/net/programming-with-tables/set-border/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách đặt đường viền trong bảng của tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai mã đó.

## Bước 1: Khởi tạo đối tượng Document
Đầu tiên, chúng ta sẽ khởi tạo một đối tượng Document:

```csharp
Document doc = new Document();
```

## Bước 2: Thêm trang vào tài liệu PDF
Tiếp theo, chúng tôi sẽ thêm một trang vào tài liệu PDF:

```csharp
Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng BorderInfo
Bây giờ chúng ta sẽ tạo một đối tượng BorderInfo để xác định đường viền của bảng:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Bước 4: Xác định đường viền trên và dưới
Chúng tôi sẽ chỉ định rằng đường viền trên và dưới sẽ gấp đôi:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Bước 5: Khởi tạo đối tượng Table
Bây giờ hãy khởi tạo một đối tượng Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Bước 6: Chỉ định độ rộng cột
Chúng ta sẽ chỉ định độ rộng của các cột trong bảng:

```csharp
table. ColumnWidths = "100";
```

## Bước 7: Tạo đối tượng hàng
Chúng ta sẽ tạo một đối tượng Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Bước 8: Thêm ô vào hàng
Tiếp theo, chúng ta sẽ thêm một ô vào hàng:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Bước 9: Thiết lập viền ô
Chúng ta sẽ xác định đường viền của ô (đường viền kép):

```csharp
cell. Border = border;
```

## Bước 10: Thêm bảng vào trang
Bây giờ hãy thêm bảng vào trang tài liệu:

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

### Mã nguồn ví dụ cho Đặt đường viền bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu
Document doc = new Document();
// Thêm trang vào tài liệu PDF
Page page = doc.Pages.Add();
// Tạo đối tượng BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Chỉ định rằng đường viền trên cùng sẽ gấp đôi
border.Top.IsDoubled = true;
// Chỉ định rằng đường viền dưới cùng sẽ gấp đôi
border.Bottom.IsDoubled = true;
// Khởi tạo đối tượng Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Chỉ định thông tin chiều rộng cột
table.ColumnWidths = "100";
// Tạo đối tượng Hàng
Aspose.Pdf.Row row = table.Rows.Add();
// Thêm một ô Bảng vào bộ sưu tập ô của hàng
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Đặt đường viền cho đối tượng ô (viền đôi)
cell.Border = border;
// Thêm bảng vào bộ sưu tập đoạn văn của Trang
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học cách đặt đường viền trong bảng của tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách tạo tài liệu, thêm trang, định cấu hình đường viền bảng và lưu tài liệu PDF. Bây giờ bạn có thể áp dụng kiến thức này vào dự án của riêng mình.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể đặt các kiểu đường viền khác nhau (ví dụ: nét đứt hoặc chấm) cho đường viền trên và dưới của bảng không?

 Đáp: Có, bạn có thể đặt các kiểu đường viền khác nhau cho đường viền trên và dưới của bảng bằng cách sửa đổi`border.Top.Style` Và`border.Bottom.Style`thuộc tính trong mã nguồn C# được cung cấp. Aspose.PDF for .NET cho phép bạn chọn từ nhiều kiểu đường viền khác nhau, bao gồm Solid, Dashed, Dotted, Double, v.v.

#### Câu hỏi: Làm cách nào để đặt màu đường viền của bảng?

 Đáp: Bạn có thể đặt màu đường viền của bảng bằng cách sửa đổi`border.Color` thuộc tính trong mã nguồn C#. Đơn giản chỉ cần cung cấp màu sắc mong muốn, chẳng hạn như`Aspose.Pdf.Color.Red` hoặc bất kỳ cách thể hiện màu hợp lệ nào khác, để tùy chỉnh màu đường viền.

#### Câu hỏi: Có thể áp dụng đường viền cho từng ô trong bảng với các cài đặt khác nhau (ví dụ: màu sắc hoặc kiểu đường viền khác nhau) không?

 Đáp: Có, bạn có thể áp dụng đường viền cho từng ô trong bảng với các cài đặt khác nhau bằng cách định cấu hình`cell.Border` thuộc tính cho từng ô riêng lẻ. Điều này cho phép bạn có các kiểu và màu sắc đường viền dành riêng cho ô dựa trên yêu cầu của bạn.

#### Hỏi: Tôi có thể xóa đường viền khỏi các cạnh cụ thể của bảng (ví dụ: viền trái và phải) không?

 Đáp: Có, bạn có thể xóa đường viền khỏi các cạnh cụ thể của bảng bằng cách sửa đổi`border.Left`, `border.Right`, `border.Top` , Và`border.Bottom`thuộc tính trong mã nguồn C#. Đặt các thuộc tính này thành`null` sẽ xóa đường viền khỏi các cạnh tương ứng của bảng.

#### Hỏi: Làm cách nào để điều chỉnh độ dày đường viền của bảng?

 Đáp: Bạn có thể điều chỉnh độ dày của đường viền bảng bằng cách sửa đổi`border.Width` thuộc tính trong mã nguồn C#. Chỉ cần đặt độ rộng đường viền mong muốn (tính bằng điểm) để đạt được độ dày mong muốn.