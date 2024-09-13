---
title: Ký bằng thẻ thông minh sử dụng trường chữ ký
linktitle: Ký bằng thẻ thông minh sử dụng trường chữ ký
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách ký PDF an toàn bằng thẻ thông minh với Aspose.PDF cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để triển khai dễ dàng.
type: docs
weight: 120
url: /vi/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Giới thiệu

Trong thế giới kỹ thuật số ngày nay, việc bảo mật tài liệu quan trọng hơn bao giờ hết. Cho dù bạn là nhà phát triển, chủ doanh nghiệp hay chỉ là người xử lý thông tin nhạy cảm, việc biết cách ký PDF điện tử có thể giúp bạn tiết kiệm thời gian và đảm bảo tài liệu của bạn được xác thực. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình ký PDF bằng thẻ thông minh và trường chữ ký với Aspose.PDF cho .NET. 

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết của quá trình ký kết, hãy đảm bảo rằng bạn có mọi thứ cần thiết để bắt đầu. Sau đây là danh sách kiểm tra các điều kiện tiên quyết:

1. Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF trong môi trường .NET của mình. Bạn có thể tải xuống từ[địa điểm](https://releases.aspose.com/pdf/net/).

2. Visual Studio: Bạn sẽ cần một IDE để viết và chạy mã .NET. Visual Studio Community Edition là một lựa chọn miễn phí tuyệt vời.

3. Thẻ thông minh: Đây là điều cần thiết để ký PDF của bạn. Đảm bảo bạn có đầu đọc thẻ thông minh và các chứng chỉ cần thiết được cài đặt trên máy của bạn.

4. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu các đoạn mã chúng ta sẽ sử dụng.

5. Tài liệu PDF mẫu: Chuẩn bị sẵn một tài liệu PDF mẫu để thử nghiệm. Bạn có thể tạo một tệp PDF trống hoặc sử dụng tệp PDF hiện có.

## Nhập gói

Trước khi bắt đầu mã hóa, hãy nhập các gói cần thiết. Bạn sẽ cần bao gồm các không gian tên sau trong tệp C# của mình:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Các không gian tên này sẽ cung cấp cho bạn quyền truy cập vào các lớp và phương thức cần thiết để làm việc với tệp PDF và xử lý chữ ký số.

## Hướng dẫn từng bước để ký PDF bằng Thẻ thông minh

Bây giờ chúng ta đã sắp xếp xong các điều kiện tiên quyết, hãy chia nhỏ quy trình ký thành các bước dễ quản lý. Chúng ta sẽ xem xét từng bước một cách chi tiết, đảm bảo bạn hiểu được những gì đang diễn ra bên trong.

### Bước 1: Thiết lập thư mục tài liệu của bạn

Cần làm gì: Xác định đường dẫn đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Giải thích: Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế nơi các tệp PDF của bạn được lưu trữ. Đây là nơi chúng tôi sẽ đọc tệp PDF trống và lưu tài liệu đã ký.

### Bước 2: Sao chép tệp PDF trống

Cần làm gì: Tạo một bản sao PDF trống để làm việc.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Giải thích: Dòng này sao chép`blank.pdf`tập tin vào một tập tin mới có tên`externalSignature1.pdf` . Các`true` tham số cho phép ghi đè nếu tệp đã tồn tại.

### Bước 3: Mở Tài liệu PDF

Cần làm gì: Mở tệp PDF đã sao chép để đọc và ghi.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Các bước tiếp theo sẽ diễn ra ở đây
    }
}
```

 Giải thích: Chúng tôi sử dụng một`FileStream` để mở tệp PDF của chúng tôi.`Document` lớp từ Aspose.PDF cho phép chúng ta thao tác nội dung PDF.

### Bước 4: Tạo trường chữ ký

Cần làm gì: Xác định trường chữ ký trong tệp PDF nơi chữ ký sẽ được đặt.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Giải thích: Ở đây, chúng ta tạo ra một`SignatureField` trên trang thứ hai (chỉ mục trang bắt đầu từ 1) của PDF.`Rectangle` xác định vị trí và kích thước của trường chữ ký.

### Bước 5: Truy cập vào Kho lưu trữ chứng chỉ thẻ thông minh

Cần làm gì: Mở kho chứng chỉ để chọn chứng chỉ thẻ thông minh của bạn.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Giải thích: Chúng tôi truy cập kho chứng chỉ cho người dùng hiện tại. Đây là nơi lưu trữ chứng chỉ thẻ thông minh của bạn.

### Bước 6: Chọn Chứng chỉ

Cần làm gì: Yêu cầu người dùng chọn chứng chỉ từ cửa hàng.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Giải thích: Dòng này mở hộp thoại để bạn chọn chứng chỉ. Bạn có thể chọn chứng chỉ được liên kết với thẻ thông minh của mình.

### Bước 7: Tạo chữ ký bên ngoài

 Cần làm gì: Tạo một phiên bản của`ExternalSignature` sử dụng chứng chỉ đã chọn.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Giải thích: Chúng tôi khởi tạo`ExternalSignature` với chứng chỉ đã chọn. Bạn cũng có thể thiết lập thẩm quyền, lý do ký và thông tin liên hệ.

### Bước 8: Thêm Trường Chữ ký vào Tài liệu

Cần làm gì: Thêm trường chữ ký vào tài liệu.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Giải thích: Chúng tôi đặt tên cho trường chữ ký và thêm vào trang đầu tiên của tài liệu. Thao tác này chuẩn bị PDF để ký.

### Bước 9: Ký vào tài liệu

Cần làm gì: Sử dụng chữ ký bên ngoài để ký PDF.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Giải thích: Dòng này ký tài liệu bằng chữ ký bên ngoài và lưu các thay đổi vào PDF. Tài liệu của bạn hiện đã được ký!

### Bước 10: Xác minh chữ ký

Cần làm gì: Kiểm tra xem chữ ký có hợp lệ không.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Giải thích: Chúng ta tạo một thể hiện của`PdfFileSignature` để xác minh chữ ký trong tài liệu. Nếu chữ ký không hợp lệ, một ngoại lệ sẽ được đưa ra.

## Phần kết luận

Xin chúc mừng! Bạn vừa học cách ký tài liệu PDF bằng thẻ thông minh và trường chữ ký với Aspose.PDF cho .NET. Quy trình này không chỉ bảo mật tài liệu của bạn mà còn đảm bảo tính xác thực, khiến nó trở thành một kỹ năng thiết yếu trong bối cảnh kỹ thuật số ngày nay. Cho dù bạn đang ký hợp đồng, hóa đơn hay bất kỳ tài liệu quan trọng nào khác, việc biết cách triển khai chữ ký số có thể giúp bạn tiết kiệm thời gian và mang lại sự an tâm.

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF trong các ứng dụng .NET.

### Tôi có cần thẻ thông minh để ký tệp PDF không?
Có, cần có thẻ thông minh để ký PDF một cách an toàn bằng chứng chỉ số.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
 Aspose.PDF cung cấp bản dùng thử miễn phí, bạn có thể tải xuống[đây](https://releases.aspose.com/).

### Tôi có thể xác minh tệp PDF đã ký như thế nào?
 Bạn có thể sử dụng`PdfFileSignature` lớp trong Aspose.PDF để xác minh chữ ký trong tài liệu PDF của bạn.

### Tôi có thể tìm thêm tài liệu về Aspose.PDF ở đâu?
 Bạn có thể kiểm tra[Tài liệu Aspose.PDF](https://reference.aspose.com/pdf/net/) để biết thêm chi tiết và ví dụ.