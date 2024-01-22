---
title: Đăng nhập kỹ thuật số vào tệp PDF
linktitle: Đăng nhập kỹ thuật số vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đăng nhập kỹ thuật số vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-security-and-signatures/digitally-sign/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình đăng nhập kỹ thuật số vào tệp PDF bằng Aspose.PDF cho .NET. Chữ ký số đảm bảo tính xác thực và tính toàn vẹn của tài liệu bằng cách thêm dấu vân tay điện tử duy nhất.

## Bước 1: Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Cài đặt Visual Studio trên máy của bạn
- Thư viện Aspose.PDF để cài đặt .NET

## Bước 2: Thiết lập môi trường

Để bắt đầu, hãy làm theo các bước sau để thiết lập môi trường phát triển của bạn:

1. Mở Visual Studio và tạo một dự án C# mới.
2. Nhập các không gian tên cần thiết vào tệp mã của bạn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Bước 3: Chữ ký số

Bước đầu tiên là ký điện tử vào tệp PDF. Mã được cung cấp cho biết cách tạo chữ ký điện tử bằng Aspose.PDF cho .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Mã này tải tệp PDF, tạo chữ ký điện tử với hình thức được chỉ định, sau đó lưu tệp PDF có chữ ký được thêm vào.

## Bước 4: Xác minh chữ ký

Sau khi thêm chữ ký số, bạn có thể kiểm tra xem tệp PDF có chữ ký hợp lệ hay không.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Làm việc gì đó
                     }
                 }
             }
         }
     }
}
```

Mã này xác minh chữ ký đầu tiên của tệp PDF và thực hiện các hành động bổ sung nếu chữ ký được chứng nhận và có các quyền cụ thể.

### Mã nguồn mẫu cho Ký điện tử bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Sử dụng các đối tượng PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Đặt giao diện chữ ký
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Tạo bất kỳ loại nào trong ba loại chữ ký
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Lưu tệp PDF đầu ra
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Có chữ ký nào không?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Xác minh cái đầu tiên
				{
					if (signature.IsCertified) // Chứng nhận?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Nhận quyền truy cập
						{
							// Làm việc gì đó
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã thực hiện thành công chữ ký điện tử trên tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này trình bày quy trình từng bước, từ việc thêm chữ ký điện tử đến xác minh tính hợp lệ của nó. Bây giờ bạn có thể sử dụng tính năng này để bảo mật các tệp PDF của mình bằng chữ ký điện tử.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này hướng dẫn bạn qua quy trình ký điện tử tệp PDF bằng Aspose.PDF cho .NET. Chữ ký số thêm dấu vân tay điện tử để đảm bảo tính xác thực và toàn vẹn của tài liệu.

#### Hỏi: Những điều kiện tiên quyết nào được yêu cầu trước khi bắt đầu?

Đáp: Trước khi bắt đầu, hãy đảm bảo bạn có hiểu biết cơ bản về ngôn ngữ lập trình C#, đã cài đặt Visual Studio và cài đặt thư viện Aspose.PDF cho .NET.

#### Câu hỏi: Làm cách nào để thiết lập môi trường phát triển?

Đáp: Hãy làm theo các bước được cung cấp để thiết lập môi trường phát triển của bạn, bao gồm tạo dự án C# mới trong Visual Studio và nhập các vùng tên được yêu cầu.

#### Hỏi: Làm cách nào để thêm chữ ký điện tử vào tệp PDF?

 Đáp: Mã mẫu được cung cấp minh họa cách tải tệp PDF, tạo chữ ký điện tử, chỉ định hình thức và lưu tệp PDF đã ký. Chữ ký số được thêm vào bằng cách sử dụng`Certify` phương pháp của`PdfFileSignature` sự vật.

#### Hỏi: Làm cách nào để xác minh tính hợp lệ của chữ ký số?

Trả lời: Sau khi thêm chữ ký số, bạn có thể sử dụng mã mẫu để xác minh tính hợp lệ của chữ ký. Nó kiểm tra xem chữ ký có được chứng nhận hay không và có quyền truy cập cụ thể hay không.

####  Hỏi: Cái gì làm`PKCS7` object represent?

 Đáp: Cái`PKCS7` đối tượng được sử dụng để cung cấp chức năng mã hóa cho chữ ký số. Nó được sử dụng để tạo chữ ký số trong mã mẫu được cung cấp.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của chữ ký điện tử không?

 Trả lời: Có, bạn có thể tùy chỉnh hình thức của chữ ký số bằng cách chỉ định đường dẫn đến hình ảnh trong`SignatureAppearance` tài sản của`PdfFileSignature` sự vật.

#### Hỏi: Điều gì xảy ra nếu chữ ký không hợp lệ?

Trả lời: Nếu chữ ký không hợp lệ, quá trình xác minh sẽ thất bại và các hành động tương ứng trong khối mã xác minh sẽ không được thực thi.

#### Câu hỏi: Làm cách nào tôi có thể đảm bảo tính bảo mật cho chữ ký số của mình?

Đáp: Chữ ký số được bảo mật theo thiết kế và sử dụng các kỹ thuật mã hóa để đảm bảo tính xác thực và toàn vẹn. Đảm bảo rằng bạn giữ khóa riêng của mình an toàn và tuân theo các phương pháp hay nhất để xử lý chữ ký số.

#### Câu hỏi: Tôi có thể thêm nhiều chữ ký điện tử vào một tệp PDF không?

 Đáp: Có, bạn có thể thêm nhiều chữ ký điện tử vào một tệp PDF bằng cách sử dụng`PdfFileSignature` các đối tượng`Sign` hoặc`Certify` phương pháp. Mỗi chữ ký sẽ có hình dáng và cấu hình riêng.