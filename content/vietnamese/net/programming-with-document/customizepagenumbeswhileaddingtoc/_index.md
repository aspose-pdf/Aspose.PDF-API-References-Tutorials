---
title: Tùy chỉnh số trang khi thêm mục lục
linktitle: Tùy chỉnh số trang khi thêm mục lục
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tùy chỉnh số trang khi thêm Mục lục vào tài liệu PDF của bạn bằng Aspose.PDF cho .NET trong hướng dẫn toàn diện này.
type: docs
weight: 100
url: /vi/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Giới thiệu

Trong thế giới quản lý tài liệu, PDF thống trị tối cao. Chúng là định dạng được sử dụng để chia sẻ và lưu trữ tài liệu trên nhiều nền tảng khác nhau. Nhưng điều gì sẽ xảy ra khi bạn muốn nâng cao tài liệu PDF của mình bằng các tính năng như Mục lục (TOC)? Đó chính là lúc Aspose.PDF cho .NET phát huy tác dụng! Thư viện mạnh mẽ này cho phép các nhà phát triển dễ dàng thao tác với các tệp PDF, cho phép họ thêm, sửa đổi và tùy chỉnh nội dung một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tùy chỉnh số trang trong khi thêm Mục lục vào tài liệu PDF của bạn bằng Aspose.PDF cho .NET. Vì vậy, hãy đội mũ lập trình của bạn và bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, bạn cần chuẩn bị một số thứ sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Đây sẽ là môi trường phát triển của chúng tôi.
2. Aspose.PDF cho .NET: Bạn cần tải xuống và cài đặt thư viện Aspose.PDF. Bạn có thể tìm thấy nó[đây](https://releases.aspose.com/pdf/net/).
3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu các đoạn mã tốt hơn.
4. Tệp PDF mẫu: Chuẩn bị tệp PDF mẫu mà chúng tôi có thể sử dụng. Bạn có thể tạo tệp PDF đơn giản hoặc tải xuống tệp PDF hiện có.

## Nhập gói

Để bắt đầu, chúng ta cần nhập các gói cần thiết. Mở dự án Visual Studio của bạn và thêm tham chiếu đến thư viện Aspose.PDF. Bạn có thể thực hiện việc này bằng cách sử dụng NuGet Package Manager:

1. Nhấp chuột phải vào dự án của bạn trong Solution Explorer.
2. Chọn "Quản lý gói NuGet".
3. Tìm kiếm "Aspose.PDF" và cài đặt.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sau khi đã cài đặt thư viện, bạn có thể bắt đầu viết mã!

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, chúng ta cần thiết lập thư mục tài liệu. Đây là nơi chúng ta sẽ lưu trữ các tệp PDF đầu vào và đầu ra. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Trong đoạn trích này, hãy thay thế`YOUR DOCUMENT DIRECTORY` với đường dẫn thực tế nơi các tệp PDF của bạn được lưu trữ. Điều này sẽ giúp chúng tôi tải tệp PDF hiện có và lưu phiên bản đã sửa đổi.

## Bước 2: Tải tệp PDF hiện có

Bây giờ chúng ta đã thiết lập xong thư mục tài liệu, hãy tải tệp PDF hiện có. 

```csharp
Document doc = new Document(inFile);
```

 Ở đây, chúng ta tạo ra một cái mới`Document` đối tượng bằng cách truyền đường dẫn tệp đầu vào. Điều này cho phép chúng ta thao tác nội dung PDF theo chương trình.

## Bước 3: Chèn một trang mới cho mục lục

Tiếp theo, chúng ta cần tạo một trang mới trong tệp PDF để chứa Mục lục.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Dòng này chèn một trang mới vào đầu tài liệu. Mục lục sẽ được hiển thị trên trang này.

## Bước 4: Tạo thông tin mục lục

Bây giờ, chúng ta hãy tạo một đối tượng để biểu diễn thông tin mục lục.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 Trong bước này, chúng ta tạo ra một`TocInfo` đối tượng và đặt tiêu đề của nó thành "Mục lục". Chúng tôi cũng tùy chỉnh kích thước và kiểu phông chữ.`PageNumbersPrefix` được đặt thành "P", sẽ thêm tiền tố vào số trang trong mục lục.

## Bước 5: Thêm Tiêu đề vào Mục lục

Bây giờ đến phần thú vị! Chúng ta sẽ duyệt qua các trang của tài liệu và thêm tiêu đề vào Mục lục.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 Trong vòng lặp này, chúng ta tạo ra một vòng lặp mới`Heading` đối tượng cho mỗi trang. Chúng tôi thiết lập trang đích cho mỗi tiêu đề và chỉ định văn bản hiển thị, đó là "Trang X" trong đó X là số trang. Cuối cùng, chúng tôi thêm tiêu đề vào trang TOC.

## Bước 6: Lưu tài liệu đã cập nhật

Sau khi thêm tất cả các tiêu đề cần thiết, đã đến lúc lưu tài liệu đã cập nhật của chúng ta.

```csharp
doc.Save(outFile);
```

Dòng này lưu PDF đã sửa đổi với TOC được bao gồm. Bây giờ bạn có thể mở tệp đầu ra và xem Mục lục tùy chỉnh của mình!

## Phần kết luận

Và thế là xong! Bạn đã tùy chỉnh thành công số trang trong khi thêm Mục lục vào tài liệu PDF của mình bằng Aspose.PDF cho .NET. Thư viện mạnh mẽ này giúp bạn dễ dàng thao tác với các tệp PDF và chỉ với một vài dòng mã, bạn có thể cải thiện đáng kể tài liệu của mình. Cho dù bạn đang tạo báo cáo, sách điện tử hay bất kỳ loại PDF nào khác, việc có Mục lục có thể cải thiện đáng kể khả năng điều hướng cho người đọc của bạn. Vậy, bạn còn chờ gì nữa? Hãy khám phá Aspose.PDF và bắt đầu tạo các tệp PDF tuyệt vời ngay hôm nay!

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF theo cách lập trình.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
 Có, Aspose cung cấp phiên bản dùng thử miễn phí mà bạn có thể sử dụng để khám phá các tính năng của thư viện. Bạn có thể tải xuống[đây](https://releases.aspose.com/).

### Làm thế nào để tôi nhận được hỗ trợ cho Aspose.PDF?
 Bạn có thể nhận được hỗ trợ bằng cách truy cập diễn đàn Aspose[đây](https://forum.aspose.com/c/pdf/10).

### Có giấy phép tạm thời không?
 Có, bạn có thể yêu cầu cấp giấy phép tạm thời cho Aspose.PDF[đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể mua Aspose.PDF cho .NET ở đâu?
 Bạn có thể mua Aspose.PDF cho .NET[đây](https://purchase.aspose.com/buy).