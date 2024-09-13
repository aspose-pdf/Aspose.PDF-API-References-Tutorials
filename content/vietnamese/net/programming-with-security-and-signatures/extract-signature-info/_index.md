---
title: Trích xuất thông tin chữ ký
linktitle: Trích xuất thông tin chữ ký
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất chữ ký số và thông tin chứng chỉ từ tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước đầy đủ dành cho nhà phát triển C#.
type: docs
weight: 80
url: /vi/net/programming-with-security-and-signatures/extract-signature-info/
---
## Giới thiệu

Trong thế giới kỹ thuật số ngày nay, việc đảm bảo tính bảo mật và toàn vẹn của tài liệu là rất quan trọng. Một trong những phương pháp phổ biến được sử dụng để bảo mật PDF là thêm chữ ký số. Tuy nhiên, việc truy xuất và xác minh thông tin chi tiết của chữ ký đôi khi có thể là một thách thức, đặc biệt là khi bạn đang xử lý nhiều chứng chỉ khác nhau. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình trích xuất thông tin chữ ký từ các tài liệu PDF bằng Aspose.PDF cho .NET, giúp công việc này trở nên dễ dàng. Bạn sẽ học cách truy cập các trường chữ ký, trích xuất thông tin chứng chỉ và lưu vào tệp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã sẵn sàng mọi thứ để bắt đầu.

-  Aspose.PDF cho Thư viện .NET: Nếu bạn chưa có, bạn có thể tải xuống từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/). 
- Môi trường phát triển .NET: Bạn sẽ cần một IDE như Visual Studio.
- Kiến thức cơ bản về C#: Sự quen thuộc với C# sẽ hữu ích cho việc hiểu các đoạn mã trong hướng dẫn này.
- Tài liệu PDF có chữ ký số: Để thử nghiệm, hãy đảm bảo bạn có tệp PDF có chứa ít nhất một chữ ký số.

## Nhập không gian tên bắt buộc

Trước khi bắt đầu code, điều quan trọng là phải import các namespace cần thiết. Các namespace này sẽ cho phép bạn truy cập chức năng Aspose.PDF và làm việc với các tài liệu PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Bây giờ bạn đã thiết lập xong những điều cần thiết, hãy chuyển sang quá trình trích xuất thông tin chữ ký từ tệp PDF.

## Bước 1: Thiết lập thư mục tài liệu

 Trước khi làm việc trên một tài liệu PDF, bạn cần phải chỉ định vị trí của tập tin bạn sẽ sử dụng. Bạn có thể thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục nơi lưu trữ các tệp PDF của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Ở đây, chúng tôi chỉ định thư mục chứa tệp PDF và tên tệp. Hãy đảm bảo tệp tồn tại trong thư mục đó!

## Bước 2: Tải tài liệu PDF

 Bây giờ bạn đã thiết lập thư mục của mình, bước tiếp theo là tải tài liệu PDF bằng cách sử dụng`Document` lớp từ Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Xử lý PDF tại đây.
}
```

 Dòng mã này khởi tạo một`Document`đối tượng đại diện cho tệp PDF.`using` câu lệnh đảm bảo rằng các tài nguyên được dọn sạch sau khi tài liệu được xử lý.

## Bước 3: Truy cập vào các trường biểu mẫu

Trong bước này, chúng ta sẽ lặp qua tất cả các trường biểu mẫu trong tài liệu PDF. Vì chữ ký thường được lưu trữ dưới dạng trường biểu mẫu, bước này sẽ giúp chúng ta xác định các trường chữ ký.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Xác định các trường chữ ký ở đây.
}
```

 Bằng cách lặp lại thông qua`Form` tài sản của`Document` đối tượng, chúng ta có thể kiểm tra từng trường biểu mẫu để xem đó có phải là trường chữ ký hay không.

## Bước 4: Xác định các trường chữ ký

 Sau khi bạn đã truy cập vào các trường biểu mẫu, bước tiếp theo là xác định trường nào là trường chữ ký. Chúng ta có thể thực hiện điều này bằng cách chuyển đổi từng trường thành một`SignatureField` sự vật.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Trích xuất thông tin chữ ký.
}
```

 Ở đây, chúng tôi sử dụng`as` từ khóa để cố gắng chuyển đổi từng trường biểu mẫu thành một`SignatureField`. Nếu việc đúc thành công, chúng ta biết rằng trường đó là một chữ ký.

## Bước 5: Trích xuất chứng chỉ

Bây giờ bạn đã xác định được trường chữ ký, nhiệm vụ tiếp theo là trích xuất chứng chỉ từ chữ ký. Chứng chỉ chứa thông tin quan trọng về người ký và tính hợp lệ của chữ ký.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 Các`ExtractCertificate` phương pháp trả về một`Stream` đối tượng chứa dữ liệu chứng chỉ. Luồng này có thể được sử dụng để lưu chứng chỉ để phân tích hoặc lưu trữ thêm.

## Bước 6: Lưu chứng chỉ vào tệp

 Sau khi bạn đã trích xuất chứng chỉ, bước cuối cùng là lưu nó vào một tệp. Trong trường hợp này, chúng tôi sẽ lưu chứng chỉ dưới dạng`.cer` tài liệu.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

Trong khối mã này, chúng tôi:

1. Kiểm tra xem luồng chứng chỉ có phải là null không.
2. Đọc dữ liệu chứng chỉ vào một mảng byte.
3.  Viết mảng byte vào một`.cer` tập tin trong thư mục tài liệu.

## Phần kết luận

Trích xuất chữ ký số và thông tin chứng chỉ liên quan từ các tài liệu PDF bằng Aspose.PDF cho .NET khá đơn giản khi được chia thành các bước đơn giản. Cho dù bạn đang kiểm tra tài liệu, xác minh chữ ký hay chỉ lưu trữ chứng chỉ để bảo quản, hướng dẫn này sẽ cung cấp cho bạn kiến thức để thực hiện hiệu quả. Hãy nhớ rằng, bảo mật và xác minh tài liệu là rất quan trọng trong thế giới kỹ thuật số ngày nay và việc sử dụng các công cụ như Aspose.PDF cho .NET giúp bạn xử lý dễ dàng hơn nhiều.

## Câu hỏi thường gặp

### Tôi có thể trích xuất nhiều chữ ký từ một tệp PDF bằng Aspose.PDF cho .NET không?
Có, đoạn mã này lặp qua tất cả các trường biểu mẫu trong tài liệu, cho phép bạn trích xuất nhiều chữ ký nếu chúng tồn tại.

### Điều gì xảy ra nếu không tìm thấy chữ ký trong tệp PDF?
Nếu không có trường chữ ký nào, mã sẽ bỏ qua chúng mà không báo lỗi.

### Tôi có thể sử dụng cách này để xác minh tính hợp lệ của chữ ký không?
Mặc dù bạn có thể trích xuất chứng chỉ, việc xác minh tính hợp lệ của chữ ký đòi hỏi các bước bổ sung, chẳng hạn như kiểm tra chuỗi tin cậy của chứng chỉ.

### Có thể trích xuất dữ liệu trường biểu mẫu khác bằng Aspose.PDF cho .NET không?
Có, Aspose.PDF cho phép bạn truy cập và thao tác nhiều loại trường biểu mẫu khác nhau trong PDF, không chỉ các trường chữ ký.

### Tôi có thể xem thông tin chi tiết của chứng chỉ đã trích xuất như thế nào?
 Sau khi chứng chỉ được lưu dưới dạng`.cer` tệp, bạn có thể mở tệp đó bằng bất kỳ trình xem chứng chỉ nào hoặc nhập tệp đó vào kho chứng chỉ hệ thống để kiểm tra thêm.