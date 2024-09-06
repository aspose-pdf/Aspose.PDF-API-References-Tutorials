---
title: Đăng nhập kỹ thuật số vào tệp PDF
linktitle: Đăng nhập kỹ thuật số vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách ký kỹ thuật số vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/programming-with-security-and-signatures/digitally-sign/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình ký số vào tệp PDF bằng Aspose.PDF cho .NET. Chữ ký số đảm bảo tính xác thực và toàn vẹn của tài liệu bằng cách thêm dấu vân tay điện tử duy nhất.

## Bước 1: Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Cài đặt Visual Studio trên máy của bạn
- Thư viện Aspose.PDF cho .NET đã được cài đặt

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

Bước đầu tiên là ký số vào tệp PDF. Mã được cung cấp cho biết cách tạo chữ ký số bằng Aspose.PDF cho .NET.

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

Mã này tải tệp PDF, tạo chữ ký số có giao diện được chỉ định, sau đó lưu tệp PDF có chữ ký đã thêm vào.

## Bước 4: Xác minh chữ ký

Sau khi thêm chữ ký số, bạn có thể kiểm tra xem tệp PDF có chứa chữ ký hợp lệ hay không.

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
                         // Làm gì đó
                     }
                 }
             }
         }
     }
}
```

Mã này xác minh chữ ký đầu tiên của tệp PDF và thực hiện các hành động bổ sung nếu chữ ký đã được chứng thực và có các quyền cụ thể.

### Mã nguồn mẫu cho Digitally Sign sử dụng Aspose.PDF cho .NET 
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
			// Thiết lập giao diện chữ ký
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Tạo bất kỳ loại chữ ký nào trong ba loại
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
				if (signature.VerifySigned(sigNames[0] as string)) // Xác minh đầu tiên
				{
					if (signature.IsCertified) // Đã được chứng nhận?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Nhận quyền truy cập
						{
							// Làm gì đó
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

Xin chúc mừng! Bạn đã thực hiện thành công chữ ký số trên tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này bao gồm quy trình từng bước, từ việc thêm chữ ký số đến xác minh tính hợp lệ của nó. Bây giờ bạn có thể sử dụng tính năng này để bảo mật tệp PDF của mình bằng chữ ký số.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này hướng dẫn bạn quy trình ký số tệp PDF bằng Aspose.PDF cho .NET. Chữ ký số thêm dấu vân tay điện tử để đảm bảo tính xác thực và toàn vẹn của tài liệu.

#### H: Cần có những điều kiện tiên quyết nào trước khi bắt đầu?

A: Trước khi bắt đầu, hãy đảm bảo bạn có hiểu biết cơ bản về ngôn ngữ lập trình C#, đã cài đặt Visual Studio và thư viện Aspose.PDF cho .NET.

#### H: Tôi thiết lập môi trường phát triển như thế nào?

A: Thực hiện theo các bước được cung cấp để thiết lập môi trường phát triển của bạn, bao gồm tạo một dự án C# mới trong Visual Studio và nhập các không gian tên cần thiết.

#### H: Làm thế nào để thêm chữ ký số vào tệp PDF?

 A: Mã mẫu được cung cấp minh họa cách tải tệp PDF, tạo chữ ký số, chỉ định giao diện và lưu tệp PDF đã ký. Chữ ký số được thêm bằng cách sử dụng`Certify` phương pháp của`PdfFileSignature` sự vật.

#### H: Làm thế nào để xác minh tính hợp lệ của chữ ký số?

A: Sau khi thêm chữ ký số, bạn có thể sử dụng mã mẫu để xác minh tính hợp lệ của chữ ký. Mã này kiểm tra xem chữ ký có được chứng thực và có quyền truy cập cụ thể hay không.

####  Q: Cái gì làm`PKCS7` object represent?

 A: Cái`PKCS7` Đối tượng được sử dụng để cung cấp chức năng mã hóa cho chữ ký số. Nó được sử dụng để tạo chữ ký số trong mã mẫu được cung cấp.

#### H: Tôi có thể tùy chỉnh giao diện của chữ ký số không?

 A: Có, bạn có thể tùy chỉnh giao diện của chữ ký số bằng cách chỉ định đường dẫn đến hình ảnh trong`SignatureAppearance` tài sản của`PdfFileSignature` sự vật.

#### H: Điều gì xảy ra nếu chữ ký không hợp lệ?

A: Nếu chữ ký không hợp lệ, quá trình xác minh sẽ không thành công và các hành động tương ứng trong khối mã xác minh sẽ không được thực hiện.

#### H: Làm thế nào tôi có thể đảm bảo tính bảo mật cho chữ ký số của mình?

A: Chữ ký số được thiết kế an toàn và sử dụng các kỹ thuật mã hóa để đảm bảo tính xác thực và toàn vẹn. Hãy đảm bảo rằng bạn giữ khóa riêng của mình an toàn và tuân thủ các biện pháp tốt nhất để xử lý chữ ký số.

#### H: Tôi có thể thêm nhiều chữ ký số vào một tệp PDF không?

 A: Có, bạn có thể thêm nhiều chữ ký số vào một tệp PDF bằng cách sử dụng`PdfFileSignature` đối tượng của`Sign` hoặc`Certify` phương pháp. Mỗi chữ ký sẽ có giao diện và cấu hình riêng.