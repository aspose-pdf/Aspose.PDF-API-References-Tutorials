---
title: Tự động phù hợp với cửa sổ
linktitle: Tự động phù hợp với cửa sổ
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tự động điều chỉnh bảng vào cửa sổ bằng Aspose.PDF cho .NET trong hướng dẫn từng bước chi tiết này. Hoàn hảo để tạo các bảng được trau chuốt và vừa vặn trong PDF.
type: docs
weight: 50
url: /vi/net/programming-with-tables/auto-fit-to-window/
---
## Giới thiệu

Khi làm việc với PDF, việc xử lý bảng là điều thường gặp và có những lúc bạn cần những bảng đó vừa khít với chiều rộng của một trang. Trong hướng dẫn này, chúng ta sẽ khám phá cách tự động điều chỉnh bảng cho vừa với cửa sổ bằng Aspose.PDF cho .NET. Điều này có thể giúp bảng của bạn trông bóng bẩy và có tổ chức, ngăn ngừa các sự cố như tràn hoặc cột không đều. Sẵn sàng học chưa? Hãy cùng tìm hiểu nhé!

## Điều kiện tiên quyết

Trước khi đi vào hướng dẫn từng bước, bạn cần chuẩn bị một số thứ sau:

1. Aspose.PDF cho .NET được cài đặt trong dự án của bạn. Nếu bạn chưa có, bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/) hoặc khám phá của họ[phiên bản dùng thử miễn phí](https://releases.aspose.com/).
2. Hiểu biết cơ bản về lập trình .NET.
3. Visual Studio hoặc bất kỳ IDE nào hỗ trợ .NET được cài đặt trên hệ thống của bạn.

>  PS Đừng quên bạn sẽ cần giấy phép để sử dụng Aspose.PDF mà không có giới hạn. Bạn có thể mua một[đây](https://purchase.aspose.com/buy) hoặc nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để thử tất cả các tính năng.

## Nhập gói

Trước khi đi sâu vào mã, bạn sẽ cần nhập các không gian tên cần thiết:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bây giờ chúng ta đã thiết lập xong, hãy chia nhỏ thành các bước đơn giản, dễ hiểu để hiểu cách bạn có thể tự động điều chỉnh bảng vào cửa sổ bằng Aspose.PDF cho .NET.

## Bước 1: Khởi tạo đối tượng tài liệu

Trước tiên, bạn cần tạo một tài liệu PDF. Hãy nghĩ về tài liệu này như một tờ giấy trắng mà bạn sẽ thêm các trang và bảng.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Pdf bằng cách gọi hàm tạo rỗng của nó
Document doc = new Document();
```
  
 Ở đây, chúng tôi tạo một tài liệu mới bằng cách sử dụng`Document` lớp từ Aspose.PDF.`dataDir` là vị trí mà tệp PDF của bạn sẽ được lưu sau khi hoàn tất.

## Bước 2: Thêm Trang vào Tài liệu

Một tài liệu PDF cần nhiều trang, đúng không? Hãy thêm một trang.

```csharp
// Tạo một phần (trang) trong đối tượng Pdf
Page sec1 = doc.Pages.Add();
```
  
 Chúng tôi đã thêm một trang mới vào tài liệu bằng cách sử dụng`Pages.Add()` phương pháp. Bạn có thể nghĩ về điều này như việc thêm một trang tính mới vào tài liệu của mình để đặt bảng.

## Bước 3: Tạo và cấu hình bảng

Bây giờ là lúc tạo một bảng và điều chỉnh cho vừa với cửa sổ.

```csharp
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
sec1.Paragraphs.Add(tab1);
```
  
 Chúng tôi đã khởi tạo một cái mới`Table` đối tượng và thêm nó vào bộ sưu tập đoạn văn của trang. Mỗi trang PDF có thể có các đoạn văn khác nhau và ở đây chúng tôi coi bảng như một đoạn văn.

## Bước 4: Xác định chiều rộng cột và tự động điều chỉnh cho vừa với cửa sổ

Tiếp theo, chúng ta thiết lập độ rộng cột và đảm bảo rằng bảng có thể tự điều chỉnh để vừa với cửa sổ.

```csharp
// Đặt độ rộng cột cho bảng
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Chúng tôi thiết lập chiều rộng cột cố định cho bảng nhưng cũng đã thêm`ColumnAdjustment.AutoFitToWindow`, đảm bảo rằng bảng sẽ điều chỉnh kích thước sao cho vừa với cửa sổ có sẵn.

## Bước 5: Thiết lập đường viền và lề cho bảng và ô

Bảng không có đường viền thường khó đọc. Hãy xác định đường viền và lề để trông gọn gàng.

```csharp
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// Tạo đối tượng MarginInfo và thiết lập lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Đặt khoảng đệm ô mặc định thành đối tượng MarginInfo
tab1.DefaultCellPadding = margin;
```
  
 Đường viền được thêm vào cả bảng và ô bằng cách sử dụng`BorderInfo` lớp, nơi bạn xác định độ dày. Lề được thiết lập để cung cấp cho các ô một số khoảng đệm.

## Bước 6: Thêm Hàng và Ô vào Bảng

Một bảng không có nội dung? Không ổn chút nào! Hãy thêm một số hàng và ô.

```csharp
//Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Chúng tôi đang tạo hai hàng và thêm ba ô vào mỗi hàng. Đây là nơi bạn sẽ nhập dữ liệu thực tế của mình (có thể là bất kỳ thứ gì từ chuỗi đến các phần tử phức tạp hơn).

## Bước 7: Lưu tài liệu

Khi mọi thứ đã hoàn tất, bạn sẽ muốn lưu tài liệu PDF mới tạo.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Lưu tài liệu cập nhật có chứa đối tượng bảng
doc.Save(dataDir);
```
  
 Các`doc.Save()` phương pháp lưu PDF vào thư mục được chỉ định. Trong trường hợp này, tài liệu sẽ được lưu dưới dạng`AutoFitToWindow_out.pdf` trong thư mục bạn đã xác định.

## Phần kết luận

Và bạn đã có nó! Bạn vừa tạo một bảng tự động vừa với cửa sổ bằng Aspose.PDF cho .NET. Điều này không chỉ đảm bảo bảng của bạn trông chuyên nghiệp và vừa vặn mà còn mang lại cho bạn sự linh hoạt khi làm việc với các kích thước dữ liệu khác nhau. Cho dù bạn đang tạo báo cáo, hóa đơn hay bất kỳ tài liệu nào yêu cầu bảng, phương pháp này là một cách tuyệt vời để duy trì bố cục sạch sẽ và dễ đọc.

## Câu hỏi thường gặp

### Tôi có thể thêm nhiều hàng một cách động không?  
 Có, bạn có thể tiếp tục thêm hàng bằng cách sử dụng`tab1.Rows.Add()` phương pháp, dựa trên nội dung một cách năng động.

### Tôi phải điều chỉnh bàn như thế nào nếu tôi không muốn nó tự động vừa khít?  
 Bạn có thể thiết lập thủ công`ColumnWidths` không sử dụng`ColumnAdjustment.AutoFitToWindow` để duy trì chiều rộng cố định của bảng.

### Tôi có thể thêm hình ảnh hoặc nội dung khác vào ô không?  
Có, Aspose.PDF cho phép bạn thêm hình ảnh, văn bản và thậm chí cả các bảng khác vào trong ô!

### Tôi phải làm sao nếu cần kiểu bảng phức tạp hơn?  
Bạn có thể tùy chỉnh thêm kiểu bảng và ô bằng cách sử dụng các thuộc tính như màu nền, căn chỉnh văn bản và cài đặt phông chữ.

### Có thể xuất bảng này sang các định dạng khác ngoài PDF không?  
Chắc chắn rồi! Aspose.PDF hỗ trợ xuất sang nhiều định dạng khác nhau như HTML, DOCX, v.v.