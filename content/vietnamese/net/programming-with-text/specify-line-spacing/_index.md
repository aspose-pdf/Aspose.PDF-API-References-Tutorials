---
title: Chỉ định khoảng cách dòng trong tệp PDF
linktitle: Chỉ định khoảng cách dòng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách chỉ định khoảng cách dòng trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này. Hoàn hảo cho các nhà phát triển đang tìm kiếm định dạng văn bản chính xác.
type: docs
weight: 510
url: /vi/net/programming-with-text/specify-line-spacing/
---
## Giới thiệu

Bạn đã bao giờ gặp khó khăn trong việc kiểm soát khoảng cách dòng trong tệp PDF chưa? Có thể bạn đã từng thấy văn bản trông quá chật chội hoặc trông không được trau chuốt như bạn muốn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách dễ dàng chỉ định khoảng cách dòng trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ sử dụng hướng dẫn từng bước đơn giản để đưa bạn từ tệp PDF trống sang tệp PDF có khoảng cách dòng tùy chỉnh. Điều này hoàn hảo nếu bạn cần độ chính xác trong bố cục văn bản cho các tài liệu như báo cáo, hóa đơn hoặc chứng chỉ.

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn đã có mọi thứ cần thiết:

1.  Đã cài đặt Aspose.PDF cho .NET. Nếu bạn chưa có, hãy tải xuống từ[Trang tải xuống Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. Môi trường phát triển .NET (như Visual Studio).
3. Một tập tin phông chữ TrueType (`.ttf` ) mà chúng ta sẽ sử dụng trong ví dụ. Bạn có thể sử dụng bất kỳ phông chữ nào, nhưng đối với hướng dẫn này, chúng ta sẽ sử dụng`HPSimplified.TTF` phông chữ.
4. Kiến thức cơ bản về C# và thao tác PDF.

Nếu bạn đã sẵn sàng, chúng ta hãy chuyển sang nhập các gói cần thiết.

## Nhập gói

Trong dự án C# của bạn, bạn sẽ cần nhập không gian tên Aspose.PDF để làm việc với các chức năng PDF. Sau đây là cách bạn thực hiện:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Các không gian tên này cho phép bạn tạo và thao tác với các tài liệu PDF, cũng như làm việc với định dạng văn bản và tùy chọn phông chữ.

Chúng tôi sẽ chia nhỏ thành các bước nhỏ để bạn có thể dễ dàng theo dõi. Mỗi bước sẽ tập trung vào một phần chính của quy trình, từ thiết lập PDF đến chỉ định khoảng cách dòng.

## Bước 1: Thiết lập dự án của bạn và xác định thư mục tài liệu

Điều đầu tiên chúng ta cần làm là xác định vị trí các tệp của mình. Điều này giúp chương trình biết tìm phông chữ ở đâu và lưu tệp PDF kết quả ở đâu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 Trong bước này, bạn sẽ thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến nơi bạn lưu trữ các tập tin của mình. Đây sẽ là nơi bạn đặt tập tin phông chữ của mình (`HPSimplified.TTF`) và nơi tệp PDF sẽ được lưu.

## Bước 2: Tải tài liệu PDF

Bây giờ, chúng ta cần tạo một tài liệu PDF mới. Đối với hướng dẫn này, chúng ta sẽ bắt đầu với một tài liệu trống, nhưng bạn cũng có thể tải một tệp PDF hiện có nếu cần.

```csharp
Document doc = new Document();
```

Thao tác này sẽ tạo ra một tài liệu PDF mới, trống. Dễ phải không?

## Bước 3: Thiết lập tùy chọn định dạng văn bản

 Đây là nơi phép thuật xảy ra. Chúng ta sẽ chỉ định chế độ giãn dòng cho văn bản mà chúng ta muốn thêm vào PDF. Aspose.PDF cung cấp cho chúng ta một số tùy chọn, nhưng trong hướng dẫn này, chúng ta sẽ sử dụng`LineSpacingMode.FullSize`, đảm bảo khoảng cách giữa các dòng được tuân thủ đầy đủ.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Mã này thiết lập chế độ giãn cách dòng thành`FullSize` , đảm bảo rằng văn bản sẽ được hiển thị với khoảng cách thích hợp. Có những tùy chọn khác như`Proportional` nếu bạn muốn các hành vi khoảng cách khác nhau, nhưng bây giờ, chúng ta hãy gắn bó với`FullSize`.

## Bước 4: Tạo một đoạn văn bản

Bây giờ, chúng ta sẽ tạo văn bản thực tế sẽ được đặt trong PDF. Văn bản này sẽ tuân thủ khoảng cách dòng mà chúng ta đã xác định.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Chúng tôi đã tạo một đoạn văn bản có chuỗi`"Hello world"`. Tất nhiên, bạn có thể tùy chỉnh văn bản này theo ý thích của mình.

## Bước 5: Tải và áp dụng phông chữ tùy chỉnh

Để làm nổi bật văn bản, chúng ta sẽ tải phông chữ TrueType tùy chỉnh từ tệp. Bước này là tùy chọn, nhưng nó có thể thêm nét chuyên nghiệp cho tệp PDF của bạn.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Ở đây, chúng tôi tải tệp phông chữ và áp dụng nó vào đoạn văn bản. Nếu đường dẫn tệp hợp lệ, phông chữ sẽ được sử dụng. Nếu không, phông chữ mặc định sẽ được áp dụng.

## Bước 6: Thiết lập vị trí và định dạng văn bản

Tiếp theo, chúng ta cần định vị văn bản trên PDF. Chúng ta cũng sẽ áp dụng các tùy chọn định dạng đã tạo trước đó.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 Các`Position` phương pháp này đặt tọa độ nơi văn bản sẽ xuất hiện trên trang (trong trường hợp này là 100 đơn vị từ bên trái và 600 đơn vị từ bên dưới). Các tùy chọn định dạng, bao gồm chế độ giãn dòng, được áp dụng tại đây.

## Bước 7: Thêm văn bản vào trang PDF

Bây giờ văn bản của chúng ta đã được định dạng và định vị xong, đã đến lúc thêm nó vào tài liệu PDF.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Mã này tạo một trang mới trong tài liệu PDF và thêm đoạn văn bản vào đó.

## Bước 8: Lưu PDF

Chúng ta đã đến bước cuối cùng! Bây giờ mọi thứ đã được thiết lập, hãy lưu PDF.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Thao tác này sẽ lưu tệp PDF với khoảng cách dòng được chỉ định và tệp của bạn đã sẵn sàng!

## Phần kết luận

Và thế là xong! Bạn vừa tạo một tài liệu PDF với khoảng cách dòng tùy chỉnh bằng Aspose.PDF cho .NET. Đây là một công cụ mạnh mẽ cho phép bạn kiểm soát mọi khía cạnh của tệp PDF và đây chỉ là một ví dụ về những gì bạn có thể đạt được. Từ vị trí văn bản đến định dạng, khả năng là vô tận.

Nếu bạn muốn tìm hiểu sâu hơn về thao tác PDF, Aspose.PDF cung cấp rất nhiều tính năng để khám phá. Đừng ngần ngại thử nghiệm và vượt qua giới hạn những gì bạn có thể làm với tài liệu của mình!

## Câu hỏi thường gặp

### Tôi có thể điều chỉnh khoảng cách dòng sang chế độ khác không?  
 Có, bạn có thể sử dụng các chế độ khác như`Proportional` hoặc`Fixed` tùy thuộc vào nhu cầu của bạn.

### Có thể tải phông chữ từ hệ thống thay vì từ tệp không?  
 Có, bạn có thể tải phông chữ được cài đặt trong hệ thống bằng cách sử dụng`FontRepository`.

### Tôi có thể sử dụng Aspose.PDF cho .NET với các định dạng tệp khác không?  
Chắc chắn rồi! Aspose.PDF cho .NET hỗ trợ nhiều định dạng như XML, HTML, v.v.

### Tôi có cần giấy phép để sử dụng Aspose.PDF cho .NET không?  
Có, để có đầy đủ chức năng, bạn sẽ cần giấy phép, bạn có thể xin giấy phép[đây](https://purchase.aspose.com/buy).

### Làm thế nào để thiết lập khoảng cách dòng cho nhiều đoạn văn?  
 Bạn có thể áp dụng`TextFormattingOptions` cho mỗi người`TextFragment` hoặc`TextParagraph` để kiểm soát khoảng cách giữa nhiều dòng hoặc nhiều đoạn văn.