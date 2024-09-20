---
title: Thêm và tìm kiếm văn bản ẩn trong tệp PDF
linktitle: Thêm và tìm kiếm văn bản ẩn trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Học cách thêm và tìm kiếm văn bản ẩn trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước có kèm ví dụ về mã.
type: docs
weight: 20
url: /vi/net/programming-with-text/add-and-search-hidden-text/
---
## Giới thiệu

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách thêm và tìm kiếm văn bản ẩn trong tệp PDF bằng Aspose.PDF cho .NET. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới bắt đầu muốn nâng cao kỹ năng lập trình của mình, bài viết này sẽ cung cấp cho bạn những hiểu biết cần thiết để kết hợp chức năng văn bản ẩn vào ứng dụng của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu phần mã hóa, bạn cần lưu ý một số điều kiện tiên quyết sau:

### Danh sách kiểm tra yêu cầu
- Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio. Hướng dẫn này giả định rằng bạn đang sử dụng .NET Framework.
-  Aspose.PDF cho .NET: Bạn cần có thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống[đây](https://releases.aspose.com/pdf/net/).
- Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu các đoạn mã tốt hơn.

## Nhập gói

Trước khi bạn có thể bắt đầu với mã của mình, bạn cần đảm bảo rằng bạn đã nhập các không gian tên Aspose.PDF cần thiết. Sau đây là cách thực hiện:

### Thiết lập dự án của bạn
1. Mở Visual Studio và tạo một dự án C# mới hoặc sử dụng dự án hiện có.
2.  Cài đặt Aspose.PDF bằng cách thêm gói NuGet. Bạn có thể thực hiện việc này bằng cách điều hướng đến NuGet Package Manager và tìm kiếm`Aspose.PDF`. 
3.  Ngoài ra, bạn có thể tải trực tiếp thư viện từ[đây](https://releases.aspose.com/pdf/net/) và thêm nó làm tài liệu tham khảo trong dự án của bạn.

### Nhập không gian tên bắt buộc
Ở đầu tệp C# của bạn, hãy nhập các không gian tên sau:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bước này rất quan trọng vì các không gian tên này chứa các lớp và phương thức cần thiết để thao tác với tài liệu PDF.

## Tạo một tài liệu PDF có văn bản ẩn

Bây giờ bạn đã thiết lập xong, chúng ta hãy cùng thực hiện các bước để tạo tài liệu PDF chứa cả văn bản hiển thị và văn bản ẩn.

### Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn sẽ muốn thiết lập đường dẫn nơi tệp PDF sẽ được lưu. Đây chính là nơi phép thuật bắt đầu!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Thay đổi điều này vào thư mục của bạn
```

 Dòng này xác định nơi PDF được tạo của bạn sẽ được lưu trữ. Đừng quên thay thế`YOUR DOCUMENT DIRECTORY` với đường dẫn thực tế của bạn.

### Bước 2: Tạo một tài liệu PDF
Tiếp theo, hãy tạo một tài liệu PDF mới và thêm trang vào đó.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Ở đây, chúng ta đang khởi tạo một tài liệu mới và thêm một trang để đặt các đoạn văn bản của mình.

### Bước 3: Thêm văn bản hiển thị và ẩn
Bây giờ chúng ta sẽ thêm cả văn bản hiển thị và văn bản ẩn vào tệp PDF.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 Trong đoạn trích này,`frag1` sẽ được nhìn thấy, trong khi`frag2` sẽ được đặt thành vô hình tiếp theo.

### Bước 4: Đặt Văn bản thành Vô hình
 Để làm cho văn bản của`frag2` vô hình, bạn chỉ cần sửa đổi nó`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Bằng cách thiết lập thuộc tính này, bất kỳ văn bản nào được liên kết với`frag2` sẽ không được hiển thị khi xem PDF.

### Bước 5: Thêm đoạn văn bản vào trang
Cuối cùng, chúng ta thêm các đoạn văn bản này vào trang và lưu PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Phần mã này thêm các đoạn văn bản của chúng ta vào trang. Sau đó, chúng ta lưu và xử lý tài liệu đúng cách.

## Tìm kiếm văn bản ẩn trong PDF

Bây giờ chúng ta đã tạo PDF với cả văn bản hiển thị và ẩn, làm thế nào để tìm kiếm văn bản ẩn đó? Hãy cùng phân tích nhé.

### Bước 1: Tải Tài liệu PDF
Để tìm kiếm văn bản trong tệp PDF, trước tiên chúng ta cần tải tài liệu vừa tạo.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Bước 2: Tạo một công cụ hấp thụ đoạn văn bản
 Chúng tôi sẽ sử dụng`TextFragmentAbsorber` để chụp lại toàn bộ các đoạn văn bản trong PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Ở đây, chúng tôi chỉ rõ rằng chúng tôi muốn hấp thụ tất cả các đoạn văn bản từ trang đầu tiên.

### Bước 3: Lặp lại qua các đoạn
Bây giờ, chúng ta có thể lặp lại các đoạn văn bản đã thu thập để tìm ra đoạn nào hiển thị và đoạn nào bị ẩn.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Vòng lặp này kiểm tra từng đoạn văn bản và in ra nội dung của nó cùng với vị trí và trạng thái hiển thị của nó. Nếu`fragment.TextState.Invisible` được đặt thành đúng, nghĩa là văn bản bị ẩn!

### Bước 4: Vứt bỏ tài liệu
Cuối cùng, hãy nhớ vứt bỏ tài liệu sau khi hoàn tất.

```csharp
doc.Dispose();
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã hướng dẫn bạn quy trình thú vị để thêm và tìm kiếm văn bản ẩn trong các tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi đã học cách tạo tài liệu PDF có cả văn bản hiển thị và văn bản ẩn, cũng như cách tìm kiếm văn bản ẩn đó theo chương trình. Khả năng này có thể cực kỳ hữu ích trong nhiều ứng dụng khác nhau, cho dù bạn cần lưu trữ thông tin bí mật hay cung cấp trải nghiệm người dùng độc đáo trong tài liệu của mình.

Khi bạn trở nên quen thuộc hơn với ASPose.PDF, khả năng trở nên vô tận. Hãy tiếp tục thử nghiệm và mở rộng ranh giới của những gì bạn có thể đạt được với các tài liệu PDF của mình!

## Câu hỏi thường gặp

### Aspose.PDF có thể xử lý các tệp PDF được mã hóa không?  
Có, Aspose.PDF hỗ trợ mã hóa và giải mã tài liệu PDF. Bạn có thể dễ dàng bảo mật PDF của mình bằng mật khẩu.

### Có phiên bản dùng thử nào cho Aspose.PDF không?  
 Chắc chắn rồi! Bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Aspose.PDF hỗ trợ những ngôn ngữ lập trình nào?  
Aspose.PDF hỗ trợ nhiều ngôn ngữ, bao gồm C#, Java và Python.

### Tôi có thể tìm tài liệu về Aspose.PDF ở đâu?  
 Bạn có thể truy cập tài liệu[đây](https://reference.aspose.com/pdf/net/).

### Tôi có thể nhận được hỗ trợ như thế nào nếu gặp vấn đề?  
 Để được hỗ trợ, bạn có thể truy cập diễn đàn Aspose[đây](https://forum.aspose.com/c/pdf/10).