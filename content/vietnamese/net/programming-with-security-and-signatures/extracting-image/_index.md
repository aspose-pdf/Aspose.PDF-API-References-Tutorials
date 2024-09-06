---
title: Trích xuất hình ảnh
linktitle: Trích xuất hình ảnh
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng trích xuất hình ảnh từ tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 70
url: /vi/net/programming-with-security-and-signatures/extracting-image/
---
Trích xuất hình ảnh từ tài liệu PDF có thể hữu ích trong nhiều trường hợp. Với Aspose.PDF for .NET, bạn có thể trích xuất hình ảnh dễ dàng bằng cách sử dụng mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Sau đây là các chỉ thị nhập cần thiết:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Trong bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF mà bạn muốn trích xuất hình ảnh. Thay thế`"YOUR DOCUMENTS DIRECTORY"` trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Bước 3: Trích xuất hình ảnh từ tài liệu PDF

Bây giờ chúng ta sẽ trích xuất hình ảnh từ tài liệu PDF bằng đoạn mã sau:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

Trong ví dụ này, chúng tôi lặp qua từng trường của biểu mẫu trong tài liệu PDF. Nếu tìm thấy trường chữ ký, chúng tôi sẽ trích xuất hình ảnh liên quan và lưu vào tệp JPEG.

### Mã nguồn mẫu để trích xuất hình ảnh bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước để trích xuất hình ảnh từ tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể tích hợp mã này vào các dự án của riêng mình để trích xuất hình ảnh và sử dụng chúng khi cần.

Hãy nhớ xem tài liệu chính thức của Aspose.PDF để biết thêm thông tin về các tính năng trích xuất hình ảnh nâng cao và thao tác với tài liệu PDF.


### Câu hỏi thường gặp

#### H: Aspose.PDF cho .NET có phù hợp với người mới bắt đầu không?

A: Mặc dù việc quen thuộc với lập trình C# sẽ hữu ích, nhưng hướng dẫn của chúng tôi được thiết kế thân thiện với người mới bắt đầu, hướng dẫn bạn từng bước.

#### H: Tôi có thể trích xuất nhiều hình ảnh cùng một lúc không?

A: Hoàn toàn được! Bằng cách triển khai vòng lặp và điều chỉnh mã được cung cấp, bạn có thể trích xuất nhiều hình ảnh từ một tài liệu PDF.

#### H: Aspose.PDF cho .NET có phải là giải pháp duy nhất để trích xuất hình ảnh không?

A: Mặc dù có nhiều công cụ khác, Aspose.PDF cho .NET nổi tiếng về hiệu quả và các tính năng toàn diện.

#### H: Tôi có thể sử dụng hình ảnh trích xuất cho mục đích thương mại không?

A: Có, sau khi trích xuất, bạn có thể sử dụng hình ảnh theo nhu cầu, bao gồm cả cho các dự án thương mại.

#### H: Tôi có thể tìm thêm tài nguyên về cách xử lý PDF bằng Aspose.PDF ở đâu?

A: Truy cập tài liệu chính thức của chúng tôi để biết thêm nhiều tài nguyên và thông tin chi tiết về cách thao tác PDF nâng cao với Aspose.PDF cho .NET.