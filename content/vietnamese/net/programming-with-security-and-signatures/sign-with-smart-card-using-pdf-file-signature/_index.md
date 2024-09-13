---
title: Ký bằng thẻ thông minh sử dụng chữ ký tệp PDF
linktitle: Ký bằng thẻ thông minh sử dụng chữ ký tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách ký tệp PDF bằng thẻ thông minh với Aspose.PDF cho .NET. Thực hiện theo hướng dẫn từng bước này để có chữ ký số an toàn.
type: docs
weight: 110
url: /vi/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Giới thiệu

Trong thời đại kỹ thuật số, việc bảo mật tài liệu trở nên quan trọng hơn bao giờ hết. Cho dù đó là hợp đồng, thỏa thuận hay bất kỳ thông tin nhạy cảm nào, việc đảm bảo rằng tài liệu là xác thực và không bị giả mạo là điều tối quan trọng. Hãy nhập chữ ký số! Hôm nay, chúng ta sẽ đi sâu vào cách ký tệp PDF bằng thẻ thông minh với Aspose.PDF cho .NET. Thư viện mạnh mẽ này cho phép các nhà phát triển thao tác và tạo tài liệu PDF hiệu quả, bao gồm cả việc thêm chữ ký số an toàn. Vì vậy, hãy lấy thẻ thông minh của bạn và bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết về việc ký tệp PDF, hãy đảm bảo bạn có mọi thứ cần thiết. Sau đây là danh sách kiểm tra để giúp bạn chuẩn bị:

1.  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF. Bạn có thể tải xuống từ[địa điểm](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Môi trường phát triển nơi bạn có thể viết và chạy mã .NET.
3. Thẻ thông minh: Bạn sẽ cần một thẻ thông minh đã cài đặt chứng chỉ số hợp lệ.
4. Hiểu biết cơ bản về C#: Sự quen thuộc với lập trình C# sẽ có lợi vì chúng ta sẽ viết các đoạn mã bằng ngôn ngữ này.
5. Tài liệu PDF: Một tệp PDF mẫu (như`blank.pdf`) để kiểm tra quy trình ký của chúng tôi.

Với những điều kiện tiên quyết này, bạn đã sẵn sàng để bắt tay vào viết mã!

## Nhập gói

Trước tiên, hãy nhập các gói cần thiết. Bạn sẽ cần thêm tham chiếu đến thư viện Aspose.PDF trong dự án của mình. Sau đây là cách bạn có thể thực hiện:

1. Mở Visual Studio.
2. Tạo một dự án mới hoặc mở một dự án hiện có.
3.  Nhấp chuột phải vào dự án của bạn trong Solution Explorer và chọn`Manage NuGet Packages`.
4.  Tìm kiếm`Aspose.PDF` và cài đặt phiên bản mới nhất.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bây giờ chúng ta đã nhập các gói cần thiết, hãy cùng phân tích mã theo từng bước.

## Bước 1: Thiết lập tài liệu của bạn

Bước đầu tiên trong quy trình của chúng tôi là thiết lập tài liệu PDF mà chúng tôi muốn ký. Sau đây là cách bạn có thể thực hiện:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 Trong đoạn mã này, chúng tôi xác định đường dẫn đến thư mục tài liệu của mình và tạo một phiên bản của`Document` lớp sử dụng tệp PDF mẫu có tên`blank.pdf` . Hãy chắc chắn thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế nơi tệp PDF của bạn được lưu trữ.

## Bước 2: Khởi tạo PdfFileSignature

 Tiếp theo, chúng ta sẽ khởi tạo`PdfFileSignature` lớp có trách nhiệm xử lý quá trình ký.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Ở đây, chúng ta tạo một thể hiện của`PdfFileSignature`và liên kết nó với tài liệu PDF của chúng tôi. Thao tác này chuẩn bị tài liệu để ký.

## Bước 3: Truy cập vào Chứng chỉ thẻ thông minh

Bây giờ đến phần quan trọng—truy cập chứng chỉ số được lưu trữ trên thẻ thông minh của bạn. Đây là cách chúng ta có thể thực hiện:

### Mở kho chứng chỉ

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Chúng tôi mở kho chứng chỉ nằm trong hồ sơ người dùng hiện tại. Điều này cho phép chúng tôi truy cập các chứng chỉ được cài đặt trên máy của bạn, bao gồm cả các chứng chỉ trên thẻ thông minh của bạn.

### Chọn chứng chỉ

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Mã này nhắc người dùng chọn một chứng chỉ từ bộ sưu tập. Giao diện người dùng sẽ hiển thị tất cả các chứng chỉ có sẵn, cho phép bạn chọn chứng chỉ được liên kết với thẻ thông minh của mình.

## Bước 4: Tạo chữ ký bên ngoài

Sau khi chọn chứng chỉ, bước tiếp theo là tạo chữ ký bên ngoài bằng chứng chỉ đã chọn.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Ở đây, chúng ta tạo một thể hiện của`ExternalSignature` sử dụng chứng chỉ đã chọn. Đối tượng này sẽ được sử dụng để ký tài liệu PDF.

## Bước 5: Thiết lập giao diện chữ ký

Bây giờ, hãy thiết lập giao diện chữ ký của chúng ta. Đây là nơi bạn có thể tùy chỉnh giao diện chữ ký của mình trên tài liệu.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 Trong đoạn mã này, chúng tôi chỉ định giao diện của chữ ký bằng cách cung cấp đường dẫn đến tệp hình ảnh (như logo hoặc đồ họa chữ ký). Đảm bảo thay thế`"demo.png"` với hình ảnh thực tế mà bạn muốn sử dụng.

## Bước 6: Ký vào PDF

Khi mọi thứ đã sẵn sàng, đã đến lúc ký tài liệu PDF!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
Trong bước này, chúng ta gọi`Sign` phương pháp của chúng tôi`pdfSign` đối tượng. Sau đây là ý nghĩa của từng tham số:
- `1`: Số trang mà chữ ký sẽ xuất hiện.
- `"Reason"`: Lý do ký văn bản.
- `"Contact"`: Thông tin liên lạc của người ký.
- `"Location"`: Vị trí của người ký.
- `true`: Chỉ ra liệu có nên tạo chữ ký có thể nhìn thấy được hay không.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: Vị trí và kích thước của chữ ký trên PDF.
- `externalSignature`: Đối tượng chữ ký mà chúng ta đã tạo trước đó.

 Cuối cùng, chúng tôi lưu tài liệu đã ký dưới dạng`externalSignature2.pdf`.

## Bước 7: Xác minh chữ ký

Sau khi ký tài liệu, điều quan trọng là phải xác minh chữ ký có hợp lệ hay không. Sau đây là cách thực hiện:

### Khởi tạo quy trình xác minh

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Chúng tôi tạo một trường hợp mới của`PdfFileSignature` cho tài liệu đã ký. Sau đó, chúng tôi lấy tên của tất cả chữ ký có trong tài liệu.

### Kiểm tra tính hợp lệ của chữ ký

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Chúng tôi lặp qua từng tên chữ ký và xác minh tính hợp lệ của nó. Nếu bất kỳ chữ ký nào không xác minh được, một ngoại lệ sẽ được đưa ra, cho biết chữ ký đó không hợp lệ.

## Phần kết luận

Và bạn đã có nó! Bạn đã ký thành công một tài liệu PDF bằng thẻ thông minh với Aspose.PDF cho .NET. Quy trình này không chỉ bảo mật tài liệu của bạn mà còn thêm một lớp xác thực rất quan trọng trong thế giới kỹ thuật số ngày nay. Cho dù bạn đang xử lý hợp đồng, tài liệu pháp lý hay bất kỳ thông tin nhạy cảm nào, thì việc biết cách triển khai chữ ký số là một kỹ năng có giá trị. 

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF trong các ứng dụng .NET.

### Tôi có cần thẻ thông minh để ký tệp PDF không?
Mặc dù thẻ thông minh không phải là bắt buộc, nhưng nó được khuyến khích sử dụng cho chữ ký số an toàn vì nó cung cấp thêm một lớp bảo mật.

### Tôi có thể sử dụng bất kỳ tệp PDF nào để ký không?
Có, bạn có thể sử dụng bất kỳ tệp PDF nào, nhưng hãy đảm bảo tệp đó không được bảo vệ bằng mật khẩu. Nếu có, trước tiên bạn cần mở khóa.

### Nếu tôi không có chứng chỉ số thì sao?
Bạn có thể lấy chứng chỉ số từ một cơ quan cấp chứng chỉ (CA) đáng tin cậy hoặc sử dụng chứng chỉ tự ký cho mục đích thử nghiệm.

### Có phiên bản dùng thử của Aspose.PDF không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[Trang web Aspose](https://releases.aspose.com/).