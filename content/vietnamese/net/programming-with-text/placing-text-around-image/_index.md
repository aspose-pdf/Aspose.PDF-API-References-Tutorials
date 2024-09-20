---
title: Đặt Văn Bản Xung Quanh Hình Ảnh Trong Tệp PDF
linktitle: Đặt Văn Bản Xung Quanh Hình Ảnh Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách đặt văn bản xung quanh hình ảnh trong PDF bằng Aspose.PDF cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để tạo PDF chuyên nghiệp với hình ảnh và văn bản cạnh nhau.
type: docs
weight: 260
url: /vi/net/programming-with-text/placing-text-around-image/
---
## Giới thiệu

Bạn đã bao giờ thử đặt văn bản xung quanh hình ảnh trong tệp PDF nhưng thấy khó chưa? Nếu vậy, bạn đã đến đúng nơi rồi! Aspose.PDF cho .NET giúp quá trình này trở nên đơn giản, cho phép bạn đặt văn bản bên cạnh hình ảnh chỉ bằng một vài dòng mã. Cho dù bạn đang tạo báo cáo, tài liệu hay bản trình bày, tính năng này là một cách tuyệt vời để cải thiện bố cục nội dung của bạn và làm cho nó hấp dẫn hơn về mặt thị giác. Hôm nay, chúng ta sẽ hướng dẫn cách sử dụng Aspose.PDF cho .NET để đặt văn bản xung quanh hình ảnh trong tài liệu PDF.

## Điều kiện tiên quyết

Trước khi bắt đầu vào mã, hãy đảm bảo rằng chúng ta đã thiết lập mọi thứ. Sau đây là những gì bạn cần:

-  Aspose.PDF cho .NET: Bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/net/).
- Visual Studio: Đảm bảo bạn đã cài đặt phiên bản mới nhất để thực hiện dễ dàng.
- .NET Framework: Ví dụ này sử dụng .NET, vì vậy hãy đảm bảo môi trường của bạn được thiết lập để phát triển .NET.
-  Giấy phép tạm thời: Bạn có thể yêu cầu giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) nếu bạn đang đánh giá sản phẩm.

Nếu bạn chưa thiết lập Aspose.PDF cho .NET, hãy làm theo hướng dẫn cài đặt trong[tài liệu](https://reference.aspose.com/pdf/net/).

## Nhập không gian tên

Trước khi bắt đầu mã hóa, chúng ta cần nhập các không gian tên cần thiết. Sau đây là đoạn mã để thực hiện việc đó:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Các không gian tên này rất cần thiết vì chúng cung cấp quyền truy cập vào các lớp như`Document`, `Page`, `Image` , Và`HtmlFragment`, chúng ta sẽ sử dụng để tạo và thao tác với PDF.

Bây giờ chúng ta đã thiết lập xong bối cảnh, hãy cùng tìm hiểu cách đặt văn bản xung quanh hình ảnh trong tệp PDF của bạn bằng Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn bạn từng bước.

## Bước 1: Khởi tạo đối tượng tài liệu

 Đầu tiên, bạn cần tạo một tài liệu PDF. Trong Aspose.PDF, điều này được thực hiện bằng cách tạo một`Document` đối tượng. Đối tượng này sẽ đóng vai trò là nền tảng cho toàn bộ nội dung chúng ta sẽ thêm vào.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Ở đây, chúng tôi đã tạo một tài liệu PDF trống. Tài liệu này chưa có trang nào, nhưng đừng lo, chúng tôi sẽ thêm một trang ở bước tiếp theo.

## Bước 2: Thêm Trang vào Tài liệu

Bây giờ chúng ta đã có tài liệu, đã đến lúc thêm một trang. Hãy nghĩ về điều này như việc tạo một tờ giấy trắng nơi bạn sẽ thêm nội dung của mình.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Mã này thêm một trang mới vào tài liệu. Theo mặc định, trang này trống, nhưng chúng tôi sắp thay đổi điều đó.

## Bước 3: Tạo bảng để sắp xếp nội dung

Để giữ cho hình ảnh và văn bản được căn chỉnh đúng, chúng ta sẽ sử dụng bảng. Bảng trong PDF có thể giúp cấu trúc bố cục của bạn, giống như trong tài liệu Word hoặc HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Đoạn mã này tạo một bảng và thêm vào trang. Hãy nghĩ về bảng như một khuôn khổ để căn chỉnh hình ảnh và văn bản của bạn.

## Bước 4: Thiết lập độ rộng cột cho bảng

Bây giờ chúng ta đã thêm một bảng, chúng ta cần xác định độ rộng của các cột. Điều này đảm bảo rằng hình ảnh và văn bản có kích thước phù hợp trên trang.

```csharp
table1.ColumnWidths = "120 270";
```

Dòng này thiết lập chiều rộng của hai cột—một cho hình ảnh và một cho văn bản. Điều chỉnh các giá trị này nếu hình ảnh hoặc văn bản của bạn cần nhiều hoặc ít không gian hơn.

## Bước 5: Xác định lề và khoảng đệm

Để đảm bảo mọi thứ trông gọn gàng, hãy thêm một số lề và phần đệm vào bảng.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Những thiết lập này đảm bảo rằng bảng của bạn có khoảng cách nhất quán, làm cho nội dung hấp dẫn về mặt thị giác.

## Bước 6: Chèn hình ảnh vào bảng

Bây giờ, chúng ta hãy đến với phần thú vị—thêm hình ảnh. Trong trường hợp này, chúng ta sẽ thêm logo Aspose, nhưng bạn có thể thoải mái sử dụng bất kỳ hình ảnh nào bạn thích.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Sau đây là những gì đang xảy ra:
- Chúng tôi tải hình ảnh từ thư mục bạn chỉ định.
- Chúng tôi thiết lập chiều cao và chiều rộng của hình ảnh.
- Cuối cùng, chúng ta thêm hình ảnh vào ô đầu tiên trong bảng.

## Bước 7: Thêm văn bản bên cạnh hình ảnh

Bây giờ hình ảnh đã vào đúng vị trí, hãy thêm một số văn bản bên cạnh hình ảnh. Đối với ví dụ này, chúng ta sẽ sử dụng văn bản định dạng HTML để định dạng nội dung.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Khối này thêm tiêu đề và mô tả theo kiểu vào ô bên cạnh hình ảnh. Bạn có thể định dạng văn bản bằng thẻ HTML để tùy chỉnh nhiều hơn.

## Bước 8: Điều chỉnh căn chỉnh theo chiều dọc

Theo mặc định, nội dung trong các ô của bảng có thể không căn chỉnh theo cách bạn muốn. Trong trường hợp này, chúng tôi muốn đảm bảo văn bản được căn chỉnh với đầu ô.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Điều này đảm bảo rằng văn bản nằm ở đầu ô, giữ cho bố cục gọn gàng và chuyên nghiệp.

## Bước 9: Thêm văn bản bên dưới hình ảnh và mô tả

Bạn có thể muốn đưa thêm nội dung bên dưới hình ảnh và văn bản. Hãy thêm một hàng khác vào bảng cho mục đích này.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Ở đây, chúng tôi đã thêm một hàng có văn bản bổ sung, trải dài trên cả hai cột để duy trì sự cân bằng trong bố cục.

## Bước 10: Lưu tài liệu PDF

Cuối cùng, chúng ta cần lưu tài liệu để bạn có thể xem những thay đổi.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Thao tác này sẽ lưu tệp PDF với hình ảnh và văn bản được định dạng theo đúng ý muốn của chúng ta.

## Phần kết luận

Đặt văn bản xung quanh hình ảnh trong PDF có vẻ là một nhiệm vụ khó khăn, nhưng Aspose.PDF cho .NET đơn giản hóa quy trình. Bằng cách tận dụng các bảng, hình ảnh và văn bản được định dạng, bạn có thể tạo PDF trông chuyên nghiệp với nỗ lực tối thiểu. Chỉ với một vài dòng mã, bạn có thể định vị nội dung chính xác ở nơi bạn muốn, mang lại cho tài liệu của bạn vẻ ngoài bóng bẩy và được sắp xếp tốt.

## Câu hỏi thường gặp

### Tôi có thể sử dụng phương pháp này để chèn nhiều hình ảnh có văn bản không?
Có, bạn chỉ cần thêm nhiều hàng và ô vào bảng để thêm hình ảnh và văn bản.

### Tôi có thể thay đổi cách căn chỉnh hình ảnh không?
Hoàn toàn có thể! Bạn có thể thay đổi cách căn chỉnh hình ảnh bằng cách điều chỉnh thuộc tính căn chỉnh của ô.

### Tôi có thể định dạng văn bản thêm như thế nào?
 Bạn có thể sử dụng thẻ HTML trong`HtmlFragment` đối tượng áp dụng nhiều kiểu chữ khác nhau như in đậm, in nghiêng hoặc phông chữ khác nhau.

### Tôi có thể kiểm soát khoảng cách giữa văn bản và hình ảnh không?
 Có, sử dụng`MarginInfo` đối tượng cho phép bạn kiểm soát khoảng đệm và lề giữa các phần tử.

### Có thể thêm liên kết vào văn bản không?
 Chắc chắn rồi! Bạn có thể nhúng siêu liên kết vào văn bản định dạng HTML bằng cách sử dụng`<a>` nhãn.