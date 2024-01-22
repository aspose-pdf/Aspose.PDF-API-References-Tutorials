---
title: Ký bằng thẻ thông minh bằng trường chữ ký
linktitle: Ký bằng thẻ thông minh bằng trường chữ ký
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Ký các tệp PDF của bạn một cách an toàn bằng thẻ thông minh bằng Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Ký kỹ thuật số bằng thẻ thông minh là một cách an toàn để ký các tệp PDF. Với Aspose.PDF cho .NET, bạn có thể dễ dàng ký vào tệp PDF bằng trường chữ ký và thẻ thông minh bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Dưới đây là các chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Ở bước này, bạn cần chỉ định đường dẫn đến thư mục chứa file PDF mà bạn muốn ký. Thay thế`"YOUR DOCUMENTS DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 3: Sao chép và mở tài liệu PDF

Bây giờ chúng tôi sẽ sao chép và mở tài liệu PDF sẽ được ký bằng mã sau:

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

 Cuối cùng, chúng tôi xác minh chữ ký của tệp PDF đã ký bằng cách sử dụng`PdfFileSignature` lớp học. Chúng tôi lấy tên chữ ký và kiểm tra từng cái một. Nếu chữ ký không được xác minh, một ngoại lệ sẽ được đưa ra. Đây là mã tương ứng:

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

### Mã nguồn mẫu để Ký bằng thẻ thông minh bằng Trường chữ ký bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Ký với lựa chọn chứng chỉ trong cửa hàng chứng chỉ windows
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

Xin chúc mừng! Giờ đây, bạn đã có hướng dẫn từng bước để ký tệp PDF bằng thẻ thông minh bằng trường chữ ký với Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để thêm chữ ký số an toàn vào tài liệu PDF của mình.

Hãy nhớ xem tài liệu chính thức của Aspose.PDF để biết thêm thông tin về các tính năng quản lý chứng chỉ và chữ ký số nâng cao.

### Câu hỏi thường gặp

#### Câu hỏi: Lợi ích của việc sử dụng trường chữ ký để ký điện tử bằng thẻ thông minh là gì?

Đáp: Việc sử dụng trường chữ ký để ký điện tử bằng thẻ thông minh sẽ cung cấp một khu vực được chỉ định trong tệp PDF nơi áp dụng chữ ký. Điều này giúp tăng cường độ rõ ràng của tài liệu và đảm bảo tính xác thực của chữ ký.

#### Câu hỏi: Thư viện Aspose.PDF dành cho .NET tạo điều kiện thuận lợi cho việc ký kỹ thuật số dựa trên thẻ thông minh bằng trường chữ ký như thế nào?

Trả lời: Aspose.PDF for .NET đơn giản hóa quy trình tạo trường chữ ký, chọn chứng chỉ thẻ thông minh và áp dụng chữ ký điện tử cho một khu vực cụ thể trong tài liệu PDF.

#### Câu hỏi: Tại sao việc chọn một chứng chỉ cụ thể lại quan trọng đối với việc ký dựa trên thẻ thông minh?

Đáp: Việc chọn một chứng chỉ cụ thể cho phép bạn nhận dạng duy nhất người ký và đảm bảo tính toàn vẹn của chữ ký. Điều này giúp thiết lập sự tin cậy và tuân thủ các tiêu chuẩn ký kỹ thuật số.

#### Câu hỏi: Mã nguồn được cung cấp xử lý quy trình ký dựa trên thẻ thông minh bằng trường chữ ký như thế nào?

Đáp: Mã nguồn trình bày cách tạo trường chữ ký, chọn chứng chỉ thẻ thông minh và áp dụng chữ ký điện tử với thông tin ký cụ thể. Nó cũng cho thấy cách xác minh tính hợp lệ của chữ ký.

#### Hỏi: Tôi có thể tùy chỉnh giao diện của trường chữ ký không?

Trả lời: Có, bạn có thể tùy chỉnh hình thức của trường chữ ký, chẳng hạn như kích thước, vị trí và cách trình bày trực quan để phù hợp với bố cục tài liệu của bạn.

#### Hỏi: Điều gì sẽ xảy ra nếu chữ ký không được xác minh trong bước xác minh?

Trả lời: Nếu chữ ký không được xác minh, một ngoại lệ sẽ được đưa ra, cho biết chữ ký không hợp lệ. Điều này đảm bảo rằng chỉ những chữ ký hợp lệ và đáng tin cậy mới được chấp nhận.

#### Câu hỏi: Tôi có thể áp dụng nhiều trường chữ ký và chữ ký dựa trên thẻ thông minh cho một tài liệu PDF không?

Trả lời: Hoàn toàn có thể, bạn có thể áp dụng nhiều trường chữ ký và chữ ký dựa trên thẻ thông minh cho các khu vực khác nhau của cùng một tài liệu PDF, cung cấp nhiều lớp bảo mật.

#### Câu hỏi: Việc sử dụng trường chữ ký sẽ nâng cao quy trình ký tài liệu tổng thể như thế nào?

Đáp: Việc sử dụng trường chữ ký sẽ hợp lý hóa quy trình ký tài liệu vì trường này hướng dẫn người ký đặt chữ ký của họ vào khu vực được chỉ định, giúp quy trình ký có tổ chức hơn và thân thiện với người dùng hơn.

#### Câu hỏi: Có bất kỳ hạn chế nào đối với việc sử dụng các trường chữ ký khi ký dựa trên thẻ thông minh không?

Trả lời: Không có giới hạn cố hữu nào đối với việc sử dụng các trường chữ ký với chữ ký dựa trên thẻ thông minh. Tuy nhiên, điều quan trọng là phải đảm bảo rằng vị trí trường chữ ký đã chọn không che khuất nội dung tài liệu quan trọng.

#### Câu hỏi: Tôi có thể tìm thêm trợ giúp hoặc hỗ trợ ở đâu để triển khai ký dựa trên thẻ thông minh với trường chữ ký?

Trả lời: Để được hướng dẫn và hỗ trợ thêm, bạn có thể tham khảo tài liệu chính thức của Aspose.PDF và diễn đàn cộng đồng, nơi cung cấp những hiểu biết sâu sắc và giải pháp có giá trị để triển khai chữ ký số an toàn.