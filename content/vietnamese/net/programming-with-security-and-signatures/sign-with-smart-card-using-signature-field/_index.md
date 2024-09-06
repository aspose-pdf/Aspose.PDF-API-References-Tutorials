---
title: Ký bằng thẻ thông minh sử dụng trường chữ ký
linktitle: Ký bằng thẻ thông minh sử dụng trường chữ ký
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Ký tệp PDF của bạn một cách an toàn bằng thẻ thông minh bằng Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Ký số bằng thẻ thông minh là cách an toàn để ký tệp PDF. Với Aspose.PDF cho .NET, bạn có thể dễ dàng ký tệp PDF bằng trường chữ ký và thẻ thông minh bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Sau đây là các chỉ thị nhập cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF mà bạn muốn ký. Thay thế`"YOUR DOCUMENTS DIRECTORY"` trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 3: Sao chép và mở tài liệu PDF

Bây giờ chúng ta sẽ sao chép và mở tài liệu PDF cần ký bằng mã sau:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Tạo trường chữ ký
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Chọn chứng chỉ trong cửa hàng
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Tạo chữ ký bên ngoài với thông tin cần thiết
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Bước 4: Xác minh chữ ký

 Cuối cùng, chúng tôi xác minh chữ ký của tệp PDF đã ký bằng cách sử dụng`PdfFileSignature` lớp. Chúng tôi lấy tên chữ ký và kiểm tra từng cái một. Nếu chữ ký không xác minh được, một ngoại lệ sẽ được đưa ra. Sau đây là mã tương ứng:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Mã nguồn mẫu cho Ký bằng thẻ thông minh sử dụng trường chữ ký bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Ký bằng lựa chọn chứng chỉ trong kho chứng chỉ Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Chọn thủ công chứng chỉ trong cửa hàng
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
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

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để ký tệp PDF bằng thẻ thông minh bằng cách sử dụng trường chữ ký với Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để thêm chữ ký số an toàn vào tài liệu PDF của mình.

Hãy nhớ xem tài liệu chính thức của Aspose.PDF để biết thêm thông tin về các tính năng quản lý chứng chỉ và chữ ký số nâng cao.

### Câu hỏi thường gặp

#### H: Lợi ích của việc sử dụng trường chữ ký để ký số bằng thẻ thông minh là gì?

A: Sử dụng trường chữ ký để ký kỹ thuật số bằng thẻ thông minh sẽ cung cấp một vùng được chỉ định trong PDF nơi chữ ký được áp dụng. Điều này làm tăng tính rõ ràng của tài liệu và đảm bảo tính xác thực của chữ ký.

#### H: Thư viện Aspose.PDF cho .NET hỗ trợ ký số dựa trên thẻ thông minh với trường chữ ký như thế nào?

A: Aspose.PDF cho .NET đơn giản hóa quy trình tạo trường chữ ký, chọn chứng chỉ thẻ thông minh và áp dụng chữ ký số vào một vùng cụ thể trong tài liệu PDF.

#### H: Tại sao việc lựa chọn chứng chỉ cụ thể lại quan trọng khi ký bằng thẻ thông minh?

A: Việc lựa chọn một chứng chỉ cụ thể cho phép bạn xác định duy nhất người ký và đảm bảo tính toàn vẹn của chữ ký. Điều này giúp thiết lập sự tin cậy và tuân thủ các tiêu chuẩn ký kỹ thuật số.

#### H: Mã nguồn được cung cấp xử lý quy trình ký dựa trên thẻ thông minh với trường chữ ký như thế nào?

A: Mã nguồn trình bày cách tạo trường chữ ký, chọn chứng chỉ thẻ thông minh và áp dụng chữ ký số với thông tin ký cụ thể. Mã nguồn cũng trình bày cách xác minh tính hợp lệ của chữ ký.

#### H: Tôi có thể tùy chỉnh giao diện của trường chữ ký không?

A: Có, bạn có thể tùy chỉnh giao diện của trường chữ ký, chẳng hạn như kích thước, vị trí và cách hiển thị trực quan, để phù hợp với bố cục tài liệu của bạn.

#### H: Điều gì xảy ra nếu chữ ký không vượt qua được bước xác minh?

A: Nếu chữ ký không xác minh được, một ngoại lệ sẽ được đưa ra, cho biết chữ ký không hợp lệ. Điều này đảm bảo rằng chỉ những chữ ký hợp lệ và đáng tin cậy mới được chấp nhận.

#### H: Tôi có thể áp dụng nhiều trường chữ ký và chữ ký dựa trên thẻ thông minh cho một tài liệu PDF không?

A: Hoàn toàn có thể, bạn có thể áp dụng nhiều trường chữ ký và chữ ký dựa trên thẻ thông minh vào các khu vực khác nhau của cùng một tài liệu PDF, cung cấp nhiều lớp bảo mật.

#### H: Việc sử dụng trường chữ ký có tác dụng gì trong việc nâng cao toàn bộ quá trình ký tài liệu?

A: Việc sử dụng trường chữ ký sẽ hợp lý hóa quy trình ký tài liệu vì nó hướng dẫn người ký đặt chữ ký của họ vào một khu vực được chỉ định, giúp quy trình ký trở nên có tổ chức hơn và thân thiện hơn với người dùng.

#### H: Có bất kỳ hạn chế nào khi sử dụng trường chữ ký với chức năng ký bằng thẻ thông minh không?

A: Không có giới hạn cố hữu nào khi sử dụng trường chữ ký với chữ ký dựa trên thẻ thông minh. Tuy nhiên, điều quan trọng là phải đảm bảo rằng vị trí trường chữ ký đã chọn không che khuất nội dung tài liệu quan trọng.

#### H: Tôi có thể tìm thêm sự hỗ trợ hoặc trợ giúp để triển khai chữ ký dựa trên thẻ thông minh với trường chữ ký ở đâu?

A: Để được hướng dẫn và hỗ trợ thêm, bạn có thể tham khảo tài liệu chính thức của Aspose.PDF và diễn đàn cộng đồng, nơi cung cấp những thông tin chi tiết và giải pháp có giá trị để triển khai chữ ký số an toàn.