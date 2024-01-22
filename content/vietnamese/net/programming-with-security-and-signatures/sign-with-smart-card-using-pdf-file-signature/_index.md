---
title: Ký bằng thẻ thông minh bằng chữ ký tệp PDF
linktitle: Ký bằng thẻ thông minh bằng chữ ký tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Ký các tệp PDF của bạn một cách an toàn bằng thẻ thông minh bằng Aspose.PDF cho .NET.
type: docs
weight: 110
url: /vi/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Ký kỹ thuật số bằng thẻ thông minh là một cách an toàn để ký các tệp PDF. Với Aspose.PDF cho .NET, bạn có thể dễ dàng ký vào tệp PDF bằng thẻ thông minh bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Dưới đây là các chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa file PDF mà bạn muốn ký. Thay thế`"YOUR DOCUMENTS DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 3: Tải tài liệu PDF

Bây giờ chúng tôi sẽ tải tài liệu PDF sẽ được ký bằng mã sau:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Bước 4: Thực hiện chữ ký bằng thẻ thông minh

 Ở bước này chúng ta sẽ thực hiện chữ ký bằng thẻ thông minh bằng cách sử dụng`PdfFileSignature` lớp học từ`Facades`thư viện. Chúng tôi chọn chứng chỉ thẻ thông minh từ kho chứng chỉ Windows và chỉ định thông tin ký cần thiết. Đây là mã tương ứng:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Chọn chứng chỉ trong cửa hàng
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Bước 5: Xác minh chữ ký

 Cuối cùng, chúng tôi xác minh chữ ký của tệp PDF đã ký bằng cách sử dụng`PdfFileSignature` lớp học. Chúng tôi lấy tên chữ ký và kiểm tra từng cái một. Nếu chữ ký không được xác minh, một ngoại lệ sẽ được đưa ra. Đây là mã tương ứng:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Mã nguồn mẫu để Đăng nhập bằng thẻ thông minh bằng chữ ký tệp Pdf bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Ký với lựa chọn chứng chỉ trong cửa hàng chứng chỉ windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Chọn thủ công chứng chỉ trong cửa hàng
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để ký tệp PDF bằng thẻ thông minh bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để thêm chữ ký số an toàn vào tài liệu PDF của mình.

Hãy nhớ xem tài liệu chính thức của Aspose.PDF để biết thêm thông tin về các tính năng quản lý chứng chỉ và chữ ký số nâng cao.

### Câu hỏi thường gặp

#### Hỏi: Tại sao tôi nên cân nhắc việc ký các tệp PDF bằng thẻ thông minh?

Trả lời: Việc ký các tệp PDF bằng thẻ thông minh sẽ tăng cường bảo mật bằng cách đảm bảo tính xác thực và tính toàn vẹn của tài liệu. Chữ ký dựa trên thẻ thông minh mang lại mức độ tin cậy và tuân thủ cao hơn.

#### Câu hỏi: Việc ký kỹ thuật số dựa trên thẻ thông minh hoạt động như thế nào?

Trả lời: Việc ký kỹ thuật số dựa trên thẻ thông minh liên quan đến việc sử dụng khóa mật mã được lưu trữ trên thẻ thông minh để tạo chữ ký số duy nhất. Chữ ký này được đính kèm vào tệp PDF, cho phép người nhận xác minh nguồn gốc và tính toàn vẹn của tài liệu.

#### Câu hỏi: Vai trò của Aspose.PDF đối với .NET trong ký kết dựa trên thẻ thông minh là gì?

Trả lời: Aspose.PDF for .NET cung cấp một bộ công cụ và thư viện toàn diện để hỗ trợ việc ký kỹ thuật số các tệp PDF dựa trên thẻ thông minh. Nó đơn giản hóa quy trình và đảm bảo việc ký tài liệu an toàn.

#### Hỏi: Tôi có thể chọn chứng chỉ thẻ thông minh cụ thể để ký không?

Trả lời: Có, bạn có thể chọn chứng chỉ thẻ thông minh cụ thể từ kho chứng chỉ Windows để ký. Aspose.PDF for .NET cho phép bạn tích hợp liền mạch việc lựa chọn chứng chỉ vào ứng dụng của mình.

#### Câu hỏi: Mã nguồn được cung cấp xử lý việc ký dựa trên thẻ thông minh như thế nào?

Đáp: Mã nguồn trình bày cách liên kết tài liệu PDF, chọn chứng chỉ thẻ thông minh, chỉ định thông tin ký và tạo chữ ký điện tử. Nó cũng cho thấy cách xác minh tính hợp lệ của chữ ký.

#### Câu hỏi: Tôi có thể áp dụng nhiều chữ ký bằng thẻ thông minh trong một tệp PDF không?

Đáp: Hoàn toàn có thể, bạn có thể áp dụng nhiều chữ ký dựa trên thẻ thông minh cho một tệp PDF. Mỗi chữ ký là duy nhất và góp phần tăng cường tính bảo mật tổng thể của tài liệu.

#### Hỏi: Điều gì sẽ xảy ra nếu chữ ký không được xác minh trong bước xác minh?

Trả lời: Nếu chữ ký không được xác minh, một ngoại lệ sẽ được đưa ra, cho biết chữ ký không hợp lệ. Điều này đảm bảo rằng chỉ những chữ ký hợp lệ và đáng tin cậy mới được chấp nhận.

#### Câu hỏi: Việc ký dựa trên thẻ thông minh có tương thích với tất cả các loại tài liệu PDF không?

Trả lời: Có, ký dựa trên thẻ thông minh tương thích với tất cả các loại tài liệu PDF. Bạn có thể áp dụng chữ ký điện tử cho nhiều loại tệp PDF khác nhau, bao gồm biểu mẫu, báo cáo, v.v.

#### Câu hỏi: Làm cách nào tôi có thể tìm hiểu thêm về quản lý chứng chỉ và chữ ký số nâng cao?

Trả lời: Khám phá tài liệu Aspose.PDF chính thức để biết thông tin chi tiết về các tính năng chữ ký số nâng cao, quản lý chứng chỉ và các phương pháp hay nhất để đảm bảo bảo mật tài liệu.

#### Câu hỏi: Tôi có thể tìm thêm trợ giúp hoặc hỗ trợ ở đâu để triển khai ký kết dựa trên thẻ thông minh?

Đáp: Để được hướng dẫn và hỗ trợ thêm, hãy liên hệ với diễn đàn cộng đồng Aspose.PDF hoặc tham khảo tài liệu để biết thông tin toàn diện về việc ký dựa trên thẻ thông minh.