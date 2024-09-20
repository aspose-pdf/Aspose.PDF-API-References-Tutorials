---
title: Thêm cột lặp lại trong tài liệu PDF
linktitle: Thêm cột lặp lại trong tài liệu PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm các cột lặp lại vào tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với ví dụ và mã. Hoàn hảo cho các nhà phát triển.
type: docs
weight: 20
url: /vi/net/programming-with-tables/add-repeating-column/
---
## Giới thiệu

Nếu bạn đang làm việc với các tài liệu PDF và cần thêm các cột lặp lại, bạn đã đến đúng nơi rồi! Sử dụng Aspose.PDF cho .NET, bạn có thể dễ dàng quản lý các bảng và nội dung trong PDF. Cho dù bạn đang xây dựng các báo cáo động, hóa đơn hay bất kỳ tài liệu có cấu trúc nào khác, các cột lặp lại có thể là một công cụ thay đổi cuộc chơi trong việc sắp xếp dữ liệu. Hãy cùng tìm hiểu hướng dẫn từng bước về cách thêm các cột lặp lại vào tài liệu PDF.

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, hãy đảm bảo rằng bạn đã thiết lập mọi thứ:

- Aspose.PDF cho .NET: Bạn cần cài đặt thư viện Aspose.PDF cho .NET trong dự án của mình.
- [Tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/)
- [Dùng thử miễn phí](https://releases.aspose.com/)
- Môi trường phát triển: Đảm bảo bạn đã cài đặt IDE tương thích với .NET như Visual Studio.
- Hiểu biết cơ bản về C#: Mặc dù chúng tôi sẽ phân tích chi tiết mọi thứ, nhưng hiểu biết cơ bản về C# sẽ giúp bạn theo dõi dễ dàng hơn.
  
 Nếu bạn chưa có Aspose.PDF cho .NET, bạn có thể tải xuống[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để bắt đầu khám phá các tính năng của nó.

## Nhập gói

Để bắt đầu, bạn cần nhập các không gian tên cần thiết từ Aspose.PDF cho .NET. Sau đây là cách thực hiện:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Các gói này cung cấp các lớp và phương thức thiết yếu để làm việc với tài liệu PDF và thao tác với bảng.

Bây giờ, chúng ta hãy chia nhỏ quy trình thành nhiều bước để thêm các cột lặp lại vào tài liệu PDF. Hãy làm theo nhé!

## Bước 1: Thiết lập đường dẫn đến thư mục tài liệu của bạn

Trước khi tạo hoặc thao tác bất kỳ tệp nào, chúng ta cần xác định đường dẫn nơi tệp PDF được tạo sẽ được lưu. Trong dự án C# của bạn, hãy đặt đường dẫn thư mục đến nơi các tệp của bạn sẽ được lưu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Đường dẫn này trỏ đến thư mục nơi tệp PDF đầu ra sẽ được lưu. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế trên máy của bạn.

## Bước 2: Tạo một tài liệu PDF mới

 Để bắt đầu, hãy tạo một cái mới`Document` đối tượng. Phần này sẽ đóng vai trò là vùng chứa cho tất cả các trang và nội dung trong PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Ở đây, chúng tôi đã tạo một tài liệu PDF mới và thêm một trang trống vào đó.`doc.Pages.Add()` phương pháp này chèn một trang mới vào tài liệu.

## Bước 3: Khởi tạo Bảng bên ngoài

Tiếp theo, chúng ta tạo một bảng bên ngoài. Bảng này sẽ trải dài toàn bộ chiều rộng của trang và đóng vai trò là vùng chứa cho các bảng khác, bao gồm cả bảng chứa các cột lặp lại.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Chúng tôi đã thiết lập`ColumnWidths` thuộc tính thành "100%", nghĩa là bảng sẽ trải dài trên toàn bộ chiều rộng của trang.

## Bước 4: Tạo Bảng bên trong

 Bây giờ, chúng ta hãy tạo bảng bên trong, bảng này sẽ có các cột lặp lại. Các thuộc tính chính ở đây là`Broken` , cho phép bảng tiếp tục trên cùng một trang và`ColumnAdjustment`, tự động điều chỉnh độ rộng của cột cho phù hợp với nội dung.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Bảng bên trong này sẽ được lồng vào bảng bên ngoài.

## Bước 5: Thêm Bảng vào Trang

Bây giờ chúng ta đã chuẩn bị xong cả bảng bên ngoài và bên trong, hãy thêm chúng vào trang. Bước này đảm bảo rằng các bảng được đưa vào cấu trúc của tài liệu.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Ở đây, chúng tôi đã thêm`outerTable` vào trang, và sau đó trong bảng bên ngoài, chúng tôi lồng nhau`mytable` . Ngoài ra, chúng tôi thiết lập`RepeatingColumnsCount`đến 5, chỉ định số cột sẽ lặp lại khi dữ liệu được thêm vào.

## Bước 6: Thêm hàng tiêu đề

Bây giờ là lúc thêm tiêu đề vào bảng. Hàng tiêu đề cung cấp ngữ cảnh cho dữ liệu và giúp cấu trúc các cột. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Đoạn mã này thêm hàng đầu tiên (chúng ta sẽ sử dụng làm tiêu đề) và điền vào các ô có chứa văn bản như "tiêu đề 1", "tiêu đề 2", v.v.

## Bước 7: Thêm hàng dữ liệu

Cuối cùng, chúng ta có thể thêm một số dữ liệu vào bảng. Vòng lặp này tạo các hàng động và điền nội dung vào các ô:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

Vòng lặp này lặp lại sáu lần, thêm các hàng và điền dữ liệu cột tương ứng vào mỗi ô (ví dụ: “cột 1, 1”, “cột 2, 2”, v.v.).

## Bước 8: Lưu tài liệu

Sau khi đã thêm tất cả các hàng và cột, bước cuối cùng là lưu tài liệu vào đường dẫn tệp đã chỉ định.

```csharp
doc.Save(outFile);
```

Tài liệu của bạn hiện đã được lưu với các cột lặp lại!

## Phần kết luận

Vậy là xong! Với các bước đơn giản này, bạn có thể tạo một tài liệu PDF với các cột lặp lại bằng Aspose.PDF cho .NET. Bằng cách tận dụng tính linh hoạt của các bảng lồng nhau, bạn có thể đạt được các bố cục phức tạp giúp PDF của bạn trông chuyên nghiệp và có tổ chức. Hãy thử điều này cho dự án tiếp theo của bạn và khám phá toàn bộ tiềm năng của Aspose.PDF để xử lý nhu cầu tạo PDF của bạn.

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và quản lý tài liệu PDF theo chương trình.

### Tôi có thể điều chỉnh số lượng cột lặp lại một cách linh hoạt không?
 Có, bạn có thể thay đổi số lượng cột lặp lại bằng cách sửa đổi`RepeatingColumnsCount` tài sản.

### Làm thế nào tôi có thể áp dụng giấy phép cho Aspose.PDF cho .NET?
 Bạn có thể áp dụng giấy phép từ một tệp hoặc luồng bằng cách làm theo[tài liệu](https://reference.aspose.com/pdf/net/).

### Có thể thêm hình ảnh vào ô trong bảng không?
Có, Aspose.PDF cho .NET hỗ trợ thêm nhiều loại nội dung khác nhau, bao gồm hình ảnh, vào các ô bảng.

### Tôi có thể tùy chỉnh thêm cách bố trí bảng không?
Chắc chắn rồi! Aspose.PDF cung cấp các tính năng mở rộng để tùy chỉnh kiểu bảng, bao gồm đường viền, khoảng đệm, căn chỉnh và nhiều tính năng khác.