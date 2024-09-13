---
title: Ẩn số trang trong mục lục
linktitle: Ẩn số trang trong mục lục
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách ẩn số trang trong Mục lục bằng Aspose.PDF cho .NET. Thực hiện theo hướng dẫn chi tiết này với các ví dụ mã để tạo PDF chuyên nghiệp.
type: docs
weight: 220
url: /vi/net/programming-with-document/hidepagenumbersintoc/
---
## Giới thiệu

Khi làm việc với PDF, đôi khi bạn có thể muốn tạo Mục lục (TOC) nhưng vẫn giữ mọi thứ gọn gàng bằng cách ẩn số trang. Có thể tài liệu sẽ trôi chảy hơn khi không có chúng hoặc có thể đó là lựa chọn thẩm mỹ. Dù lý do của bạn là gì, nếu bạn đang làm việc với Aspose.PDF cho .NET, hướng dẫn này sẽ chỉ cho bạn chính xác cách ẩn số trang trong TOC của bạn.

## Điều kiện tiên quyết

Trước khi bắt đầu, có một số điều bạn cần chuẩn bị. Sau đây là danh sách kiểm tra nhanh:

- Đã cài đặt Visual Studio: Bạn sẽ cần phiên bản Visual Studio đang hoạt động để viết mã.
- Thư viện Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF cho .NET.
  -  Liên kết tải xuống:[Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/)
- Giấy phép tạm thời: Nếu bạn đang thử nghiệm các tính năng, việc có giấy phép tạm thời sẽ rất hữu ích.
  -  Giấy phép tạm thời:[Nhận nó ở đây](https://purchase.aspose.com/temporary-license/)

## Nhập gói

Trước khi bắt đầu code, hãy đảm bảo bạn nhập các namespace sau vào dự án C# của mình. Chúng sẽ cung cấp các lớp và phương thức cần thiết để làm việc với tài liệu PDF và tạo Mục lục (TOC) của bạn.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Bây giờ môi trường của bạn đã sẵn sàng và các gói đã được nhập, hãy cùng phân tích từng bước của quy trình. Chúng tôi sẽ đề cập đến mọi phần của mã để đảm bảo tính rõ ràng, để bạn có thể dễ dàng theo dõi.

## Bước 1: Khởi tạo tài liệu PDF của bạn

Điều đầu tiên chúng ta cần làm là tạo một tài liệu PDF mới và thêm một trang cho Mục lục (TOC).


```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Đây là thư mục nơi tập tin đầu ra của bạn sẽ được lưu.
- Document(): Khởi tạo một tài liệu PDF mới.
- Pages.Add(): Thêm một trang trống mới vào tài liệu, sau đó sẽ lưu mục lục của bạn.

## Bước 2: Thiết lập thông tin mục lục và tiêu đề

Tiếp theo, chúng ta sẽ xác định thông tin Mục lục, bao gồm việc thiết lập tiêu đề sẽ xuất hiện ở đầu Mục lục.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Đối tượng này lưu trữ tất cả thông tin về TOC.
- TextFragment: Biểu thị văn bản của tiêu đề mục lục, ở đây chúng tôi đặt nó là "Mục lục".
- FontStyle: Chúng tôi định dạng tiêu đề mục lục bằng cách đặt kích thước của nó thành 20 và in đậm.
- tocPage.TocInfo: Chúng tôi gán thông tin mục lục cho trang sẽ hiển thị mục lục.

## Bước 3: Ẩn số trang trong mục lục

Bây giờ đến phần thú vị! Đây là nơi chúng ta cấu hình TOC để ẩn số trang.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Đây là công tắc ma thuật ẩn số trang. Đặt thành`false`và số trang sẽ không xuất hiện trong Mục lục.
- FormatArrayLength: Chúng tôi đặt thành 4, cho biết chúng tôi muốn xác định định dạng cho bốn cấp tiêu đề mục lục.

## Bước 4: Tùy chỉnh định dạng mục lục

Để thêm phong cách cho mục lục, chúng ta sẽ xác định định dạng cho các cấp tiêu đề khác nhau.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Mảng này kiểm soát định dạng của mục lục. Mỗi chỉ mục biểu thị một cấp độ tiêu đề khác nhau.
- Lề và Kiểu văn bản: Chúng tôi thiết lập lề và áp dụng các kiểu phông chữ như in đậm, in nghiêng và gạch chân cho từng cấp tiêu đề.

## Bước 5: Thêm Tiêu đề vào Tài liệu

Cuối cùng, chúng ta hãy thêm các tiêu đề thực tế sẽ là một phần của Mục lục.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Tiêu đề và TextSegment: Đây là các tiêu đề sẽ xuất hiện trong mục lục của bạn. Mỗi cấp độ có tiêu đề riêng.
- IsAutoSequence: Tự động đánh số các tiêu đề.
- IsInList: Đảm bảo mỗi tiêu đề xuất hiện trong mục lục.

## Bước 6: Lưu tài liệu

Khi mọi thứ đã hoàn tất, hãy lưu tài liệu PDF vào tệp đầu ra đã chỉ định.

```csharp
doc.Save(outFile);
```

Và thế là xong! Bạn đã tạo thành công tệp PDF có Mục lục và số trang đã được ẩn!

## Phần kết luận

Tạo Mục lục trong PDF và ẩn số trang có vẻ phức tạp, nhưng với Aspose.PDF cho .NET, việc này trở nên dễ dàng. Bằng cách làm theo hướng dẫn từng bước này, bạn đã biết cách tùy chỉnh định dạng Mục lục, ẩn số trang và áp dụng các kiểu khác nhau cho tiêu đề của mình. Bây giờ bạn có thể tạo PDF chuyên nghiệp phù hợp với nhu cầu chính xác của mình.

## Câu hỏi thường gặp

### Tôi có thể hiển thị số trang cho các tiêu đề cụ thể trong Mục lục không?
Không, Aspose.PDF ẩn hoặc hiển thị số trang cho toàn bộ mục lục. Bạn không thể ẩn chúng một cách có chọn lọc đối với các mục cụ thể.

### Có thể thêm nhiều cấp độ hơn vào mục lục không?
 Vâng, bạn có thể tăng`FormatArrayLength` để xác định nhiều cấp độ tiêu đề mục lục hơn.

### Làm thế nào tôi có thể thay đổi phông chữ cho tất cả các mục lục?
 Bạn có thể thay đổi phông chữ bằng cách sửa đổi`TextState.Font` tài sản cho mỗi cấp độ trong`FormatArray`.

### Tôi có thể chèn siêu liên kết vào mục lục không?
 Có, bạn có thể liên kết từng mục lục với một phần cụ thể trong tài liệu bằng cách sử dụng`Heading.TocPage` tài sản.

### Tôi có cần giấy phép sử dụng Aspose.PDF không?
Có, cần có giấy phép hợp lệ để sử dụng sản xuất. Bạn có thể xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) để kiểm tra các tính năng.