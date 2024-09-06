---
title: Gạch bỏ các từ
linktitle: Gạch bỏ các từ
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách gạch bỏ các từ trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước toàn diện này. Nâng cao kỹ năng chỉnh sửa tài liệu của bạn.
type: docs
weight: 150
url: /vi/net/annotations/strikeoutwords/
---
## Giới thiệu

Bạn đã bao giờ thấy mình cần nhấn mạnh một đoạn văn bản cụ thể trong PDF bằng cách gạch bỏ nó chưa? Cho dù bạn đang xem lại tài liệu, đánh dấu văn bản hay chỉ cần làm nổi bật một số phần nhất định, thì việc gạch bỏ các từ có thể là một công cụ hữu ích. Trong hướng dẫn này, chúng ta sẽ khám phá cách thực hiện điều đó bằng Aspose.PDF cho .NET. Hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước, đảm bảo bạn có tất cả thông tin cần thiết để triển khai hiệu quả tính năng này trong các ứng dụng .NET của mình. 

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, bạn cần đáp ứng một số điều kiện tiên quyết để có thể làm theo hướng dẫn này:

1.  Aspose.PDF cho Thư viện .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Đảm bảo rằng bạn đã cài đặt .NET Framework trên máy của mình. Hướng dẫn này được thiết kế cho các ứng dụng .NET.

3. Môi trường phát triển: Bạn sẽ cần một IDE như Visual Studio để viết và chạy mã của mình.

4. Tài liệu PDF: Chuẩn bị sẵn tệp PDF mẫu mà bạn muốn sử dụng. Đây sẽ là tài liệu mà chúng tôi sẽ gạch bỏ văn bản.

5. Kiến thức cơ bản về C#: Cần phải quen thuộc với lập trình C# để hiểu và thực hiện các bước trong hướng dẫn này.

## Nhập gói

Trước khi chúng ta có thể bắt đầu mã hóa, chúng ta cần nhập các không gian tên cần thiết vào dự án .NET của mình. Điều này sẽ cho phép chúng ta truy cập vào các lớp và phương thức cần thiết để thao tác các tệp PDF bằng Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Các không gian tên này rất cần thiết khi làm việc với tài liệu PDF, xử lý văn bản và thêm chú thích như gạch bỏ.

Trong phần này, chúng tôi sẽ chia nhỏ quy trình gạch bỏ các từ trong tài liệu PDF thành các bước đơn giản, dễ quản lý. Mỗi bước sẽ đi kèm với giải thích chi tiết để đảm bảo bạn hiểu cách mọi thứ hoạt động.

## Bước 1: Tải Tài liệu PDF

Bước đầu tiên là tải tài liệu PDF mà bạn muốn chỉnh sửa. Đây sẽ là tài liệu mà bạn sẽ gạch bỏ các từ hoặc cụm từ cụ thể.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Biến này giữ đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi lưu trữ tệp PDF của bạn.
- `Document` : Các`Document` lớp biểu diễn một tài liệu PDF. Bằng cách truyền đường dẫn tệp đến hàm tạo của nó, chúng ta mở tệp PDF để xử lý.

## Bước 2: Tạo TextFragment Absorber để tìm văn bản cụ thể

 Tiếp theo, chúng ta sẽ tạo một thể hiện của`TextFragmentAbsorber` để tìm kiếm một đoạn văn bản cụ thể trong tài liệu PDF. Điều này cho phép chúng tôi xác định vị trí đoạn văn bản mà chúng tôi muốn gạch bỏ.

```csharp
// Tạo phiên bản TextFragment Absorber để tìm kiếm một đoạn văn bản cụ thể
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Lớp này được sử dụng để tìm và làm việc với các đoạn văn bản cụ thể trong tài liệu PDF. Trong ví dụ này, chúng tôi đang tìm kiếm từ "Estoque". Thay thế "Estoque" bằng từ hoặc cụm từ bạn muốn tìm trong tài liệu của mình.

## Bước 3: Lặp lại qua các trang của tài liệu PDF

 Bây giờ chúng ta đã có`TextFragmentAbsorber`, chúng ta cần lặp lại từng trang của tài liệu PDF để tìm văn bản được chỉ định.

```csharp
// Lặp lại qua các trang của tài liệu PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Lấy trang hiện tại của tài liệu PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Vòng lặp này lặp lại qua từng trang của tài liệu PDF.
- `document.Pages[i]`: Truy xuất trang hiện tại đang được xử lý.
- `page.Accept(textFragmentAbsorber)` : Phương pháp này áp dụng`TextFragmentAbsorber` đến trang hiện tại, tìm kiếm văn bản đã chỉ định.

## Bước 4: Thu thập và xử lý các đoạn văn bản

Sau khi duyệt qua các trang, chúng tôi sẽ thu thập các đoạn văn bản tìm thấy và chuẩn bị chúng để xử lý thêm.

```csharp
// Tạo một bộ sưu tập các đoạn văn bản được hấp thụ
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Bộ sưu tập này lưu trữ tất cả các đoạn văn bản được tìm thấy trong tài liệu. Chúng tôi sẽ sử dụng bộ sưu tập này trong bước tiếp theo để gạch bỏ văn bản.

## Bước 5: Lặp lại các đoạn văn bản và gạch bỏ chúng

Ở bước này, chúng ta sẽ lặp qua từng đoạn văn bản trong bộ sưu tập và áp dụng chú thích gạch bỏ vào đó.

```csharp
// Lặp lại qua bộ sưu tập các đoạn văn bản
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Lấy kích thước hình chữ nhật của đối tượng TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Khởi tạo phiên bản chú thích StrikeOut
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Đặt thuộc tính của chú thích gạch bỏ
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Thêm chú thích vào bộ sưu tập chú thích của trang đoạn văn bản
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Dòng này lấy đoạn văn bản hiện tại.
- `Aspose.Pdf.Rectangle`:Chúng tôi tính toán kích thước hình chữ nhật của đoạn văn bản để xác định vị trí áp dụng gạch ngang.
- `StrikeOutAnnotation`: Lớp này biểu diễn chú thích gạch bỏ. Chúng tôi khởi tạo nó bằng hình chữ nhật được tính toán và trang hiện tại.
- `strikeOut.Opacity`: Thuộc tính này thiết lập độ mờ đục của phần gạch bỏ, làm cho phần này hiển thị ở mức 80%.
- `strikeOut.Color`Chúng tôi đặt màu của gạch bỏ là đỏ. Bạn có thể thay đổi thành bất kỳ màu nào bạn thích.
- `textFragment.Page.Annotations.Add(strikeOut)`: Thao tác này sẽ thêm chú thích gạch bỏ vào trang.

## Bước 6: Lưu tài liệu PDF đã sửa đổi

Bước cuối cùng là lưu tài liệu PDF đã chỉnh sửa với các gạch bỏ được áp dụng.

```csharp
// Lưu tài liệu PDF đã cập nhật
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Thao tác này tạo tên tệp mới cho tài liệu đã sửa đổi. Tệp gốc vẫn không thay đổi.
- `document.Save(dataDir)`: Lưu tài liệu PDF có gạch bỏ chữ vào vị trí đã chỉ định.

## Phần kết luận

Xin chúc mừng! Bạn đã gạch bỏ thành công các từ cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước này, giờ đây bạn có thể tùy chỉnh tài liệu PDF bằng cách tô sáng hoặc gạch bỏ văn bản, giúp chúng trở nên năng động hơn và phù hợp với nhu cầu của bạn. Cho dù bạn đang chú thích tài liệu pháp lý, chuẩn bị báo cáo hay chỉ đánh dấu văn bản để xem lại, hướng dẫn này đã trang bị cho bạn các kỹ năng để thực hiện hiệu quả.

## Câu hỏi thường gặp

### Tôi có thể thay đổi màu của phần gạch ngang không?

 Có, bạn có thể thay đổi màu sắc bằng cách sửa đổi`strikeOut.Color`thuộc tính. Ví dụ, bạn có thể đặt nó thành`Aspose.Pdf.Color.Blue` để đánh bóng màu xanh.

### Có thể gạch bỏ nhiều từ cùng một lúc không?

 Chắc chắn rồi!`TextFragmentAbsorber` có thể được sử dụng để tìm kiếm bất kỳ từ hoặc cụm từ nào trong tài liệu. Bạn có thể áp dụng gạch bỏ cho nhiều trường hợp bằng cách lặp lại qua`TextFragmentCollection`.

### Tôi phải làm sao nếu chỉ muốn gạch bỏ văn bản trên một số trang cụ thể?

 Bạn có thể sửa đổi vòng lặp lặp qua các trang để chỉ bao gồm các trang bạn muốn sửa đổi. Ví dụ:`for (int i = 1; i <= 3; i++)` sẽ chỉ áp dụng lệnh gạch bỏ cho ba trang đầu tiên.

### Tôi có thể điều chỉnh độ dày của đường gạch ngang như thế nào?

 Bạn có thể điều chỉnh độ dày của đường gạch ngang bằng cách sửa đổi`Border` tài sản của`StrikeOutAnnotation`. Điều này cho phép tùy chỉnh giao diện gạch ngang.

### Có cách nào để hoàn tác lệnh gạch bỏ sau khi lưu tài liệu không?

Sau khi tài liệu được lưu, gạch bỏ sẽ có hiệu lực vĩnh viễn. Nếu bạn cần giữ nguyên văn bản gốc mà không có gạch bỏ, hãy cân nhắc lưu bản sao lưu của tài liệu gốc trước khi áp dụng bất kỳ sửa đổi nào.