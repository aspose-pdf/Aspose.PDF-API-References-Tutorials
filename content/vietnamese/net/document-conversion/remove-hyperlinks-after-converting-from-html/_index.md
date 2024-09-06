---
title: Xóa siêu liên kết sau khi chuyển đổi từ HTML
linktitle: Xóa siêu liên kết sau khi chuyển đổi từ HTML
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xóa siêu liên kết khỏi tài liệu HTML sau khi chuyển đổi sang PDF bằng Aspose.PDF cho .NET trong hướng dẫn từng bước này.
type: docs
weight: 250
url: /vi/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Giới thiệu

Trong thời đại kỹ thuật số, việc chuyển đổi tài liệu HTML sang PDF là một nhiệm vụ phổ biến. Tuy nhiên, đôi khi bạn có thể muốn xóa siêu liên kết khỏi PDF đã chuyển đổi vì nhiều lý do, chẳng hạn như tăng khả năng đọc hoặc ngăn chặn điều hướng không mong muốn. Trong hướng dẫn này, chúng ta sẽ khám phá cách thực hiện điều này bằng Aspose.PDF cho .NET. 

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Đây sẽ là môi trường phát triển của bạn.
2.  Aspose.PDF cho .NET: Bạn cần có thư viện Aspose.PDF. Bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu mã tốt hơn.

## Nhập gói

Để bắt đầu, bạn cần nhập các gói cần thiết vào dự án C# của mình. Sau đây là cách bạn có thể thực hiện:

1. Mở dự án Visual Studio của bạn.
2. Nhấp chuột phải vào dự án của bạn trong Solution Explorer và chọn "Quản lý gói NuGet".
3.  Tìm kiếm`Aspose.PDF` và cài đặt nó.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Bây giờ bạn đã thiết lập mọi thứ, chúng ta hãy cùng tìm hiểu quy trình xóa siêu liên kết khỏi tệp HTML sau khi chuyển đổi tệp đó sang PDF.

## Bước 1: Thiết lập thư mục tài liệu

Trước tiên, bạn cần chỉ định đường dẫn đến thư mục tài liệu của mình. Đây là nơi tệp HTML của bạn nằm và nơi tệp PDF đầu ra sẽ được lưu.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tệp HTML của bạn được lưu trữ.

## Bước 2: Tải tài liệu HTML

 Tiếp theo, bạn sẽ tải tài liệu HTML bằng cách sử dụng`Document` lớp từ Aspose.PDF. Lớp này cho phép bạn làm việc với các tài liệu PDF dễ dàng.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Ở đây, chúng tôi đang tải tệp HTML có tên`SampleHtmlFile.html`. Đảm bảo rằng tập tin này tồn tại trong thư mục bạn chỉ định.

## Bước 3: Lưu tài liệu vào Memory Stream

Trước khi bắt đầu xử lý chú thích, chúng ta cần lưu tài liệu vào luồng bộ nhớ. Bước này rất quan trọng vì nó chuẩn bị tài liệu cho thao tác tiếp theo.

```csharp
doc.Save(new MemoryStream());
```

Dòng này lưu tài liệu vào bộ nhớ, cho phép chúng ta làm việc với tài liệu mà không cần ghi vào đĩa ngay.

## Bước 4: Lặp lại qua các chú thích

Bây giờ, chúng ta sẽ lặp lại các chú thích trong tài liệu. Chú thích là các thành phần như liên kết, bình luận và điểm nổi bật. Chúng tôi đặc biệt quan tâm đến chú thích liên kết.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Xử lý chú thích liên kết
    }
}
```

Trong vòng lặp này, chúng ta kiểm tra xem loại chú thích có phải là liên kết không. Nếu có, chúng ta sẽ tiến hành các bước tiếp theo.

## Bước 5: Xóa hành động siêu liên kết

Đối với mỗi chú thích liên kết, chúng ta cần kiểm tra xem nó có hành động siêu liên kết hay không. Nếu có, chúng ta sẽ xóa siêu liên kết bằng cách đặt URI của nó thành một chuỗi rỗng.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Đoạn mã này đảm bảo rằng hành động siêu liên kết được loại bỏ hiệu quả.

## Bước 6: Hấp thụ các đoạn văn bản

Tiếp theo, chúng ta sẽ hấp thụ các đoạn văn bản liên quan đến chú thích liên kết. Điều này cho phép chúng ta thao tác giao diện văn bản.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Ở đây, chúng tôi tạo ra một`TextFragmentAbsorber` và đặt tùy chọn tìm kiếm của nó vào hình chữ nhật của chú thích. Điều này giúp chúng tôi tìm thấy văn bản được liên kết.

## Bước 7: Sửa đổi giao diện văn bản

Khi đã có các đoạn văn bản, chúng ta có thể thay đổi giao diện của chúng. Trong trường hợp này, chúng ta sẽ xóa phần gạch chân và đổi màu văn bản thành màu đen.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Bước này giúp tăng khả năng đọc của văn bản bằng cách loại bỏ kiểu siêu liên kết.

## Bước 8: Xóa chú thích

Sau khi sửa đổi văn bản, chúng ta có thể xóa chú thích liên kết khỏi tài liệu một cách an toàn.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Dòng này sẽ xóa siêu liên kết khỏi tệp PDF, đảm bảo rằng siêu liên kết đó không còn tồn tại trong kết quả đầu ra cuối cùng.

## Bước 9: Lưu tài liệu đã sửa đổi

Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi vào tệp PDF mới. Đây là bước cuối cùng trong quy trình của chúng ta.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Dòng này lưu tài liệu với các siêu liên kết đã được xóa, tạo một tệp PDF mới có tên`RemoveHyperlinksFromText_out.pdf`.

## Phần kết luận

Và bạn đã có nó! Bạn đã xóa thành công siêu liên kết khỏi tài liệu HTML sau khi chuyển đổi sang PDF bằng Aspose.PDF cho .NET. Quá trình này không chỉ cải thiện khả năng đọc PDF của bạn mà còn cho phép bạn kiểm soát nội dung bạn trình bày. 

## Câu hỏi thường gặp

### Tôi có thể xóa siêu liên kết khỏi bất kỳ tài liệu PDF nào không?
Có, bạn có thể xóa siêu liên kết khỏi bất kỳ tài liệu PDF nào bằng Aspose.PDF cho .NET.

### Aspose.PDF có miễn phí sử dụng không?
 Aspose.PDF cung cấp bản dùng thử miễn phí, nhưng để có đầy đủ tính năng, bạn cần mua giấy phép. Kiểm tra[mua trang](https://purchase.aspose.com/buy).

### Tôi phải làm sao nếu gặp sự cố khi sử dụng Aspose.PDF?
 Bạn có thể tìm kiếm sự giúp đỡ trên[diễn đàn hỗ trợ](https://forum.aspose.com/c/pdf/10).

### Tôi có thể chuyển đổi các định dạng tệp khác sang PDF bằng Aspose không?
Có, Aspose hỗ trợ nhiều định dạng tệp khác nhau để chuyển đổi sang PDF.

### Tôi có thể tải xuống Aspose.PDF cho .NET ở đâu?
 Bạn có thể tải nó xuống từ[liên kết tải xuống](https://releases.aspose.com/pdf/net/).