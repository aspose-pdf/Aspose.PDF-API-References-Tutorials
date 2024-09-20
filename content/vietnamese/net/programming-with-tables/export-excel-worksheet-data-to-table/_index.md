---
title: Xuất dữ liệu bảng tính Excel sang bảng
linktitle: Xuất dữ liệu bảng tính Excel sang bảng
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xuất dữ liệu bảng tính Excel sang bảng PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với các ví dụ về mã, điều kiện tiên quyết và mẹo hữu ích.
type: docs
weight: 70
url: /vi/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Giới thiệu

Bạn đã bao giờ cần xuất dữ liệu từ bảng tính Excel sang tệp PDF, được sắp xếp gọn gàng theo định dạng bảng chưa? Hãy tưởng tượng bạn có một loạt dữ liệu trong Excel, nhưng cần chia sẻ dưới dạng PDF trông chuyên nghiệp. Nghe có vẻ phức tạp, phải không? Nhưng với Aspose.PDF cho .NET, bạn có thể biến nhiệm vụ này thành chuyện dễ dàng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình xuất dữ liệu bảng tính Excel thành bảng bên trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn bạn từng bước, phân tích mọi thứ để ngay cả khi bạn mới làm quen với việc này, bạn vẫn sẽ cảm thấy mình như một chuyên gia khi hoàn thành.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã hóa, chúng ta hãy thiết lập một vài thứ:

1.  Aspose.PDF cho Thư viện .NET – Đảm bảo bạn đã cài đặt phiên bản mới nhất. Bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells cho Thư viện .NET – Bạn sẽ cần thư viện này để xử lý các hoạt động của Excel. Tải xuống từ[đây](https://releases.aspose.com/cells/net/).
3. Môi trường phát triển .NET – Một công cụ như Visual Studio sẽ hoạt động hoàn hảo để mã hóa.
4. Tệp Excel – Chuẩn bị sẵn tệp Excel chứa dữ liệu bạn muốn xuất.

 Nếu bạn không có thư viện Aspose.PDF và Aspose.Cells, bạn có thể bắt đầu bằng[dùng thử miễn phí](https://releases.aspose.com/).

## Nhập gói

Để bắt đầu, hãy đảm bảo bạn đã cài đặt cả thư viện Aspose.PDF và Aspose.Cells trong dự án của mình. Bạn có thể cài đặt chúng bằng NuGet Package Manager trong Visual Studio.

Sau đây là cách nhập các gói cần thiết vào mã C# của bạn:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Bây giờ các điều kiện tiên quyết đã được thiết lập, chúng ta hãy cùng tìm hiểu quy trình xuất dữ liệu từ bảng tính Excel sang bảng trong tài liệu PDF.

## Bước 1: Tải sổ làm việc Excel

Để bắt đầu, bạn cần tải sổ làm việc Excel của mình vào chương trình. Trong bước này, chúng ta sẽ sử dụng Aspose.Cells để mở tệp Excel.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải bảng tính Excel
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Giải thích: Ở đây, chúng tôi chỉ định đường dẫn thư mục nơi tệp Excel của chúng tôi được đặt và tải sổ làm việc bằng cách sử dụng`Aspose.Cells.Workbook` . Hãy chắc chắn điều chỉnh`"YOUR DOCUMENT DIRECTORY"` để trỏ đến vị trí tệp của bạn.

## Bước 2: Truy cập vào Bảng tính đầu tiên

Sau khi tải bảng tính, chúng ta cần truy cập vào bảng tính đầu tiên nơi dữ liệu của chúng ta được lưu trữ.

```csharp
// Truy cập vào trang tính đầu tiên trong tệp Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Giải thích: Bước này khá đơn giản, chúng ta lấy bảng tính đầu tiên từ sổ làm việc có chứa dữ liệu cần xuất.

## Bước 3: Xuất dữ liệu vào DataTable

Bây giờ, chúng ta hãy xuất dữ liệu từ bảng tính Excel sang đối tượng DataTable, đối tượng này sẽ đóng vai trò trung gian để chuyển dữ liệu sang PDF.

```csharp
// Xuất nội dung của 7 hàng và 2 cột bắt đầu từ ô thứ 1 vào DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Giải thích:`ExportDataTable` phương pháp trích xuất dữ liệu bắt đầu từ ô đầu tiên của bảng tính và trải dài tất cả các hàng và cột. Dữ liệu này sau đó được lưu trữ trong`DataTable` để sử dụng sau này.

## Bước 4: Tạo một tài liệu PDF mới

Tiếp theo, chúng ta cần tạo một tài liệu PDF mới bằng Aspose.PDF.

```csharp
// Khởi tạo một phiên bản Tài liệu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Tạo một trang trong phiên bản tài liệu
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Giải thích: Ở đây, chúng ta khởi tạo một`Aspose.Pdf.Document`và thêm một trang vào đó. Trang này sau đó sẽ chứa bảng chúng ta tạo từ dữ liệu Excel.

## Bước 5: Tạo đối tượng bảng trong PDF

Chúng ta hãy chuyển sang tạo bảng bên trong tài liệu PDF.

```csharp
// Tạo một đối tượng Bảng
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Thêm đối tượng Bảng vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(table);
```

 Giải thích: Chúng tôi tạo ra một`Aspose.Pdf.Table` đối tượng và thêm nó vào bộ sưu tập đoạn văn của trang, đảm bảo rằng bảng được hiển thị trên trang.

## Bước 6: Thiết lập độ rộng cột và đường viền

Các bảng trong PDF cần có chiều rộng cột được xác định. Chúng tôi cũng sẽ thêm đường viền để làm cho bảng dễ đọc hơn.

```csharp
// Đặt độ rộng cột của bảng
table.ColumnWidths = "40 100 100";

// Đặt đường viền ô mặc định
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Giải thích: Chúng tôi thiết lập chiều rộng của ba cột và cung cấp cho tất cả các ô một đường viền mặc định có độ dày là`0.1F`.

## Bước 7: Nhập dữ liệu từ DataTable vào bảng PDF

Bây giờ là lúc nhập dữ liệu từ DataTable vào bảng PDF của chúng ta.

```csharp
// Nhập dữ liệu vào đối tượng Table từ DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Giải thích:`ImportDataTable`phương pháp chuyển tất cả dữ liệu từ`DataTable` vào bảng PDF. Thao tác này sẽ điền dữ liệu từ bảng tính Excel của bạn vào bảng.

## Bước 8: Định dạng hàng tiêu đề

Hãy định dạng hàng tiêu đề của bảng bằng cách thay đổi màu nền, phông chữ và căn chỉnh.

```csharp
// Lấy hàng đầu tiên từ bảng
Aspose.Pdf.Row headerRow = table.Rows[0];

// Đặt kiểu cho hàng tiêu đề
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Giải thích: Chúng ta lặp qua tất cả các ô ở hàng đầu tiên (tiêu đề) và đặt màu nền của chúng thành màu xanh, màu văn bản thành màu vàng và căn chỉnh văn bản vào giữa.

## Bước 9: Tạo kiểu cho các hàng còn lại

Để phân biệt giữa tiêu đề và các hàng còn lại, hãy thêm một kiểu khác cho các hàng còn lại.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Giải thích: Đối với tất cả các hàng ngoại trừ tiêu đề, chúng tôi đặt nền màu xám và màu văn bản màu trắng.

## Bước 10: Lưu tài liệu PDF

Cuối cùng, lưu tài liệu PDF có bảng.

```csharp
// Lưu tệp PDF
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Giải thích: Chúng tôi lưu PDF vào thư mục đã chỉ định. Voilà! Dữ liệu Excel của bạn hiện nằm trong bảng PDF được định dạng đẹp mắt.

## Phần kết luận

Và bạn đã có nó! Chỉ trong vài bước, bạn đã xuất dữ liệu từ một bảng tính Excel vào một bảng bên trong PDF bằng Aspose.PDF cho .NET. Bằng cách chia nhỏ quy trình và định dạng trong quá trình thực hiện, bạn có thể tùy chỉnh đầu ra của mình và đảm bảo dữ liệu của bạn trông sạch sẽ và chuyên nghiệp. Vì vậy, lần tới khi ai đó đưa cho bạn một tệp Excel và yêu cầu báo cáo PDF, bạn biết chính xác phải làm gì.

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh bảng nhiều hơn không?
Hoàn toàn có thể! Bạn có thể chỉnh sửa màu sắc, phông chữ, căn chỉnh và thậm chí thêm đường viền vào các ô cụ thể.

### Aspose.PDF cho .NET có miễn phí không?
 Nó cung cấp bản dùng thử miễn phí, nhưng để sử dụng lâu dài, bạn sẽ cần giấy phép. Bạn có thể[mua nó ở đây](https://purchase.aspose.com/buy).

### Tôi có thể chỉ xuất những hàng và cột cụ thể không?
 Có, bạn có thể sửa đổi các thông số trong`ExportDataTable` phương pháp xuất các phạm vi cụ thể.

### Cách này có hiệu quả với các file Excel lớn không?
Có, Aspose.Cells được thiết kế để xử lý các tệp Excel lớn một cách hiệu quả.

### Làm thế nào để tôi có thể thêm nhiều trang vào PDF?
 Bạn có thể sử dụng`pdfDocument.Pages.Add()` để thêm nhiều trang tùy theo nhu cầu của bạn.