---
title: Văn bản và hình ảnh như đoạn văn trong tệp PDF
linktitle: Văn bản và hình ảnh như đoạn văn trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tạo PDF có văn bản và hình ảnh bằng Aspose.PDF cho .NET. Tìm hiểu cách thêm văn bản và hình ảnh nội tuyến từng bước.
type: docs
weight: 530
url: /vi/net/programming-with-text/text-and-image-as-paragraph/
---
## Giới thiệu

Trong thế giới kỹ thuật số ngày nay, PDF là định dạng tài liệu phổ biến mà hầu hết chúng ta đều gặp hàng ngày. Cho dù đó là báo cáo, sách điện tử hay hóa đơn kinh doanh, PDF giúp bạn dễ dàng chia sẻ thông tin trên nhiều nền tảng khác nhau. Nhưng nếu bạn muốn tùy chỉnh PDF theo chương trình thì sao? Đó chính là lúc Aspose.PDF cho .NET xuất hiện. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách chèn văn bản và hình ảnh dưới dạng đoạn văn nội tuyến vào tệp PDF bằng Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn có mọi thứ cần thiết để theo dõi một cách suôn sẻ:

-  Aspose.PDF cho Thư viện .NET: Bạn sẽ cần cài đặt Aspose.PDF cho .NET. Bạn có thể tải xuống[đây](https://releases.aspose.com/pdf/net/).
- Visual Studio: Bất kỳ phiên bản nào hỗ trợ .NET đều hoạt động tốt.
- Hiểu biết cơ bản về C#: Một chút quen thuộc với C# sẽ hữu ích nhưng đừng lo lắng—tôi sẽ hướng dẫn bạn từng bước!
- Tài liệu PDF đã sẵn sàng: Nếu bạn muốn thêm hình ảnh tùy chỉnh, hãy chuẩn bị sẵn hình ảnh.

 Bạn cũng có thể dùng thử thư viện miễn phí[đây](https://releases.aspose.com/) hoặc nếu bạn đang làm việc trên một dự án quy mô lớn, hãy cân nhắc mua nó[đây](https://purchase.aspose.com/buy) . Cần thêm thông tin chi tiết? Kiểm tra tài liệu[đây](https://reference.aspose.com/pdf/net/).

## Nhập gói

Để bắt đầu với Aspose.PDF cho .NET, bạn cần nhập các không gian tên bắt buộc. Các không gian tên này cho phép mã C# của bạn tương tác với các chức năng của Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Đơn giản phải không? Bây giờ chúng ta hãy bắt đầu phần thú vị—tạo tệp PDF của riêng bạn.

## Hướng dẫn từng bước: Tạo PDF có văn bản và hình ảnh nội tuyến

Hãy chia nhỏ điều này thành các bước dễ hiểu và dễ làm theo. Hãy tưởng tượng bạn đang lắp ráp một câu đố; mỗi bước giống như việc tìm và đặt đúng mảnh ghép.

## Bước 1: Khởi tạo Tài liệu PDF

Bước đầu tiên là khởi tạo một tài liệu PDF mới bằng Aspose.PDF. Tài liệu này sẽ đóng vai trò là nền tảng để thêm văn bản và hình ảnh.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo phiên bản Tài liệu
Document doc = new Document();
```

 Chuyện gì đang xảy ra ở đây? Chúng tôi chỉ đơn giản là tạo một tài liệu mới bằng cách sử dụng`Document`lớp và xác định thư mục bạn muốn lưu PDF. Giống như mở một bức tranh mới cho kiệt tác của bạn vậy!

## Bước 2: Thêm một trang vào PDF của bạn

Một tài liệu sẽ chẳng có tác dụng gì nếu không có trang, đúng không? Hãy thêm một trang trống vào tài liệu của bạn.

```csharp
// Thêm trang vào bộ sưu tập trang của phiên bản Tài liệu
Page page = doc.Pages.Add();
```

Đoạn mã này thêm một trang mới vào bộ sưu tập trang của tài liệu. Hãy nghĩ đến việc lật mở một trang trắng trong sổ tay.

## Bước 3: Thêm văn bản dưới dạng đoạn văn

Tiếp theo, chúng ta sẽ thêm một đoạn văn bản. Đây là nơi bạn có thể chèn tin nhắn hoặc tiêu đề của mình.

```csharp
// Tạo TextFragment
TextFragment text = new TextFragment("Hello World.. ");
// Thêm đoạn văn bản vào bộ sưu tập đoạn văn của đối tượng Trang
page.Paragraphs.Add(text);
```

 Ở đây, chúng tôi tạo ra một`TextFragment` đối tượng để giữ văn bản "Hello World..", sau đó được thêm vào trang dưới dạng một đoạn văn. Giống như viết câu đầu tiên trong tài liệu PDF của bạn.

## Bước 4: Thêm hình ảnh dưới dạng đoạn văn nội tuyến

Bây giờ chúng ta đã có văn bản, hãy làm cho mọi thứ trở nên thú vị hơn bằng cách thêm hình ảnh dưới dạng đoạn văn nội tuyến. Đoạn văn nội tuyến chỉ đơn giản có nghĩa là hình ảnh sẽ xuất hiện ngay sau văn bản, giống như cách hình ảnh được hiển thị trong tài liệu Word.

```csharp
// Tạo một phiên bản hình ảnh
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Đặt hình ảnh thành đoạn văn nội tuyến để nó xuất hiện ngay sau
// Đối tượng đoạn văn trước (TextFragment)
image.IsInLineParagraph = true;
// Chỉ định đường dẫn tệp hình ảnh
image.File = dataDir + "aspose-logo.jpg";
```

 Trong đoạn trích này, chúng tôi tạo ra một`Image` đối tượng, yêu cầu nó căn chỉnh theo dòng với văn bản và chỉ định đường dẫn đến tệp hình ảnh. Điều này tương đương với việc dán hình ảnh ngay sau một câu trong tài liệu. Bạn có thể hoán đổi "aspose-logo.jpg" bằng hình ảnh mong muốn của mình.

## Bước 5: Đặt kích thước hình ảnh (Tùy chọn)

Bạn muốn thay đổi kích thước hình ảnh? Không vấn đề gì. Aspose.PDF cung cấp cho bạn tùy chọn điều chỉnh chiều cao và chiều rộng của hình ảnh trước khi thêm vào tài liệu.

```csharp
// Đặt Chiều cao hình ảnh (tùy chọn)
image.FixHeight = 30;
// Đặt chiều rộng hình ảnh (tùy chọn)
image.FixWidth = 100;
```

Phần này là tùy chọn, nhưng nó giúp bạn kiểm soát kích thước hình ảnh hiển thị trong tệp PDF của bạn. Giống như việc thay đổi kích thước ảnh trước khi in.

## Bước 6: Thêm hình ảnh vào bộ sưu tập đoạn văn

Chúng ta đã chuẩn bị hình ảnh. Bây giờ hãy chèn nó vào tài liệu dưới dạng một đoạn văn nội tuyến.

```csharp
// Thêm hình ảnh vào bộ sưu tập đoạn văn của đối tượng trang
page.Paragraphs.Add(image);
```

Dòng này thêm hình ảnh ngay sau văn bản trong bộ sưu tập đoạn văn. Giống như việc nhấn nút "Chèn hình ảnh" trong trình soạn thảo văn bản.

## Bước 7: Thêm một đoạn văn bản nội tuyến khác

Nếu bạn muốn thêm văn bản ngay sau hình ảnh thì sao? Hãy thực hiện bằng cách chèn thêm một đoạn văn bản nội tuyến khác.

```csharp
// Khởi tạo lại đối tượng TextFragment với nội dung khác
text = new TextFragment(" Hello Again..");
// Đặt TextFragment thành đoạn văn nội tuyến
text.IsInLineParagraph = true;
// Thêm TextFragment mới tạo vào bộ sưu tập đoạn văn của trang
page.Paragraphs.Add(text);
```

 Chúng tôi đang tái sử dụng`TextFragment`đối tượng ở đây với văn bản mới ("Xin chào lần nữa..") và chèn nó vào dòng, ngay sau hình ảnh. Điều này mang lại cho PDF của bạn một giao diện liền mạch, gắn kết.

## Bước 8: Lưu tài liệu PDF

Chúng ta gần hoàn tất rồi! Bây giờ, hãy lưu tài liệu vào thư mục bạn chỉ định.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Bước cuối cùng này sẽ lưu tệp trong thư mục của bạn với tên "TextAndImageAsParagraph_out.pdf". Xin chúc mừng—bạn đã tạo được tệp PDF có cả văn bản và hình ảnh nội tuyến!

## Phần kết luận

Và bạn đã có nó rồi—tạo PDF với văn bản và hình ảnh dưới dạng đoạn văn nội tuyến bằng Aspose.PDF cho .NET cũng đơn giản như làm theo các bước sau. Chỉ với một vài dòng mã, bạn có thể thêm nội dung động vào tệp PDF của mình, khiến chúng hấp dẫn hơn về mặt thị giác và chuyên nghiệp hơn. Cho dù đó là báo cáo kinh doanh hay sách điện tử, việc kiểm soát bố cục của tệp PDF có thể tạo ra sự khác biệt lớn.

## Câu hỏi thường gặp

### Tôi có thể thêm nhiều hình ảnh dưới dạng đoạn văn nội tuyến không?  
 Có, bạn có thể thêm nhiều hình ảnh bằng cách tạo các hình ảnh riêng biệt`Image` đối tượng và thêm chúng vào bộ sưu tập đoạn văn.

### Tôi có thể kiểm soát vị trí của văn bản và hình ảnh trong PDF không?  
Có, bằng cách sử dụng các thuộc tính như lề, bạn có thể kiểm soát vị trí chính xác của văn bản và hình ảnh.

### Aspose.PDF cho .NET có miễn phí không?  
 Không, đó là sản phẩm được cấp phép, nhưng bạn có thể nhận được[dùng thử miễn phí](https://releases.aspose.com/) hoặc mua giấy phép[đây](https://purchase.aspose.com/buy).

### Tôi có thể thêm siêu liên kết vào văn bản không?  
 Có, Aspose.PDF cho phép bạn thêm siêu liên kết trong các đoạn văn bản. Kiểm tra[tài liệu](https://reference.aspose.com/pdf/net/) để biết thêm chi tiết.

### Tôi có thể tùy chỉnh phông chữ và kiểu chữ của văn bản không?  
Chắc chắn rồi! Bạn có thể dễ dàng tùy chỉnh phông chữ, màu sắc và các thuộc tính kiểu dáng khác của đoạn văn bản.