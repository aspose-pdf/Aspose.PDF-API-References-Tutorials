---
title: Tìm kiếm văn bản và thêm siêu liên kết
linktitle: Tìm kiếm văn bản và thêm siêu liên kết
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm văn bản và thêm siêu liên kết vào tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước của chúng tôi.
type: docs
weight: 450
url: /vi/net/programming-with-text/search-text-and-add-hyperlink/
---
## Giới thiệu

Bạn đang tìm cách không chỉ để thao tác PDF mà còn cải thiện chúng bằng cách chèn siêu liên kết? Vâng, bạn đã đến đúng nơi rồi! Với thư viện Aspose.PDF mạnh mẽ cho .NET, bạn có thể tìm kiếm các mẫu văn bản trong tài liệu PDF của mình và thêm siêu liên kết một cách liền mạch. Hãy tưởng tượng có một tài liệu không chỉ truyền tải thông tin mà còn kết nối người đọc với các tài nguyên có liên quan chỉ bằng cách nhấp vào liên kết. Nghe có vẻ hay, phải không? Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách tìm kiếm văn bản bằng biểu thức chính quy và thêm siêu liên kết trong PDF của mình. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, bạn sẽ thấy quá trình này đơn giản và bổ ích.

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết, hãy đảm bảo rằng bạn có mọi thứ cần thiết để theo dõi. Sau đây là danh sách kiểm tra hữu ích:

- .NET Framework: Bạn phải cài đặt .NET Framework trên máy của mình (phiên bản 4.0 trở lên).
- Aspose.PDF cho Thư viện .NET: Đừng quên tải xuống và thêm tham chiếu đến thư viện Aspose.PDF trong dự án của bạn. Bạn có thể tìm thấy nó[đây](https://releases.aspose.com/pdf/net/).
- IDE: Bạn sẽ cần một Môi trường phát triển tích hợp (IDE) như Visual Studio để viết và chạy mã.
- Tệp PDF mẫu: Lấy tệp PDF mẫu mà bạn có thể kiểm tra mã. Bạn có thể tạo tệp PDF đơn giản hoặc sử dụng một trong các tài liệu hiện có của mình.

Sau khi bạn đã hoàn thành mọi mục trong danh sách này, chúng ta đã sẵn sàng bắt đầu!

## Nhập gói

Bước đầu tiên trong hành trình của chúng tôi là nhập các gói cần thiết. Đây là nơi chúng tôi cho dự án biết những công cụ nào chúng tôi sẽ sử dụng. Sau đây là cách bạn có thể thực hiện:

Trong tệp C# của bạn, hãy bắt đầu bằng cách thêm các không gian tên sau vào đầu:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Bằng cách nhập các không gian tên này, bạn cấp cho chương trình của mình quyền truy cập vào tất cả các tính năng thú vị mà Aspose.PDF cung cấp.

Bây giờ chúng ta đã thiết lập xong, đã đến lúc hành động. Chúng ta sẽ thực hiện theo một loạt các bước, vì vậy hãy theo dõi chặt chẽ nhé!

### Bước 1: Thiết lập thư mục tài liệu của bạn

Đầu tiên, bạn cần phải chỉ định nơi lưu trữ các tệp PDF của mình. Sửa đổi`dataDir` biến để trỏ đến thư mục tài liệu của bạn. Đây là cách bạn thực hiện:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Hãy chắc chắn thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế tới tài liệu của bạn.

### Bước 2: Tạo TextFragmentAbsorber

 Tiếp theo, chúng ta cần một công cụ để tìm văn bản chúng ta muốn liên kết. Nhập`TextFragmentAbsorber`. Anh chàng nhỏ bé này sẽ giúp chúng ta tìm kiếm mẫu văn bản cụ thể trong tệp PDF của mình.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Ở đây, chúng ta đang tìm kiếm một mẫu cụ thể: bốn chữ số, một dấu gạch ngang, theo sau là bốn chữ số khác (như số điện thoại hoặc năm).

### Bước 3: Bật Tìm kiếm biểu thức chính quy

 Chúng tôi đã sử dụng biểu thức chính quy để tìm mẫu văn bản của mình, nhưng chúng tôi cần đảm bảo`absorber` biết nó đã được bật. Điều này rất quan trọng để nó có thể tìm kiếm đúng cách.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Bước 4: Khởi tạo PdfContentEditor

 Bây giờ chúng ta đã có bộ hấp thụ sẵn sàng, chúng ta cần một`PdfContentEditor` để làm việc với tệp PDF của chúng tôi. Lớp này cho phép chúng tôi liên kết với PDF và thao tác với nó.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Bước 5: Liên kết tệp PDF nguồn của bạn

Sau khi trình chỉnh sửa nội dung đã sẵn sàng, đã đến lúc liên kết nó với tệp PDF thực tế mà chúng ta muốn làm việc.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Hãy chắc chắn thay thế`"SearchRegularExpressionPage.pdf"` bằng tên tệp PDF của bạn.

### Bước 6: Chấp nhận Absorber cho Trang

Chúng ta cần cho biên tập viên biết rằng chúng ta muốn tìm kiếm trên một trang cụ thể của tài liệu. Trong trường hợp này, hãy chọn Trang 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Bước 7: Chuẩn bị lặp qua các đoạn văn bản

Bây giờ, chúng ta đã sẵn sàng để lặp qua tất cả các đoạn văn bản được trình hấp thụ của chúng ta tìm thấy. Chúng ta sẽ tinh chỉnh giao diện của chúng và thiết lập siêu liên kết của chúng ta.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Ở đây, chúng ta thiết lập một số thông số, như màu của siêu liên kết.

### Bước 8: Lặp qua từng đoạn văn bản

Đối với mỗi đoạn văn bản khớp với tìm kiếm của chúng tôi, chúng tôi sẽ thay đổi màu sắc của nó và tạo một siêu liên kết. Sau đây là giao diện của nó:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, màu xanh, actionName);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Bước 9: Lưu PDF đã chỉnh sửa

Chúng ta sắp hoàn tất rồi! Bây giờ là lúc lưu những thay đổi vào một tệp PDF mới.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Bước 10: Đóng Trình chỉnh sửa

Cuối cùng, đừng quên đóng tài liệu để giải phóng tài nguyên!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Bây giờ, bạn vừa tạo một tệp PDF có siêu liên kết được tạo động dựa trên kết quả tìm kiếm. Thật tuyệt phải không?

## Phần kết luận

Và bạn đã có nó! Bằng cách làm theo các bước này, bạn đã học cách tìm kiếm trong PDF và thêm siêu liên kết bằng thư viện Aspose.PDF cho .NET. Điều này có thể mở ra một thế giới khả năng, đặc biệt nếu bạn đang làm việc với các tài liệu yêu cầu tính tương tác. Hãy tưởng tượng việc thêm liên kết đến các tài nguyên liên quan, trang web tham khảo hoặc thậm chí các trang nội bộ—tất cả chỉ với một vài dòng mã!
## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?  
Aspose.PDF for .NET là thư viện cho phép các nhà phát triển tạo, thao tác và quản lý tài liệu PDF trong các ứng dụng .NET.

### Làm thế nào tôi có thể tải xuống Aspose.PDF cho .NET?  
 Bạn có thể tải xuống thư viện[đây](https://releases.aspose.com/pdf/net/).

### Tôi có thể dùng thử Aspose.PDF miễn phí không?  
 Chắc chắn rồi! Bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Có hỗ trợ cho các sản phẩm Aspose không?  
 Có, bạn có thể tìm thấy sự hỗ trợ và thảo luận của cộng đồng[đây](https://forum.aspose.com/c/pdf/10).

### Làm thế nào tôi có thể xin được giấy phép tạm thời cho Aspose.PDF?  
 Bạn có thể yêu cầu giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).