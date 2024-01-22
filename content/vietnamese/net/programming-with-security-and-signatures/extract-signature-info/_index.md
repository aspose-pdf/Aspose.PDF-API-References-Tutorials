---
title: Trích xuất thông tin chữ ký
linktitle: Trích xuất thông tin chữ ký
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Trích xuất thông tin chữ ký bằng Aspose.PDF cho .NET.
type: docs
weight: 80
url: /vi/net/programming-with-security-and-signatures/extract-signature-info/
---
Quá trình trích xuất thông tin chữ ký từ tài liệu PDF có thể khá hữu ích trong nhiều trường hợp khác nhau. Cho dù bạn cần xác thực tính xác thực của tài liệu đã ký hay phân tích chứng chỉ được sử dụng cho chữ ký, thư viện Aspose.PDF cho .NET đều cung cấp giải pháp thuận tiện. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước trích xuất thông tin chữ ký bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Kiến thức cơ bản về ngôn ngữ lập trình C#.
2. Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
3. Tài liệu PDF hợp lệ có một hoặc nhiều trường chữ ký.

Bây giờ, hãy đi sâu vào chi tiết triển khai.

## Bước 1: Nhập thư viện cần thiết

 Để bắt đầu, bạn cần nhập các thư viện cần thiết vào dự án C# của mình. Trong trường hợp này, chúng ta cần nhập`Aspose.Pdf` Và`System.IO` không gian tên. Điều này có thể được thực hiện bằng cách thêm đoạn mã sau vào đầu tệp C# của bạn:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Bước 2: Đặt đường dẫn tài liệu

Tiếp theo, bạn cần đặt đường dẫn đến tài liệu PDF mà bạn muốn trích xuất thông tin chữ ký. Thay thế`"YOUR DOCUMENTS DIRECTORY"` trong đoạn mã sau với đường dẫn thực tế tới tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Bước 3: Trích xuất thông tin chữ ký

Bây giờ, hãy chuyển sang phần chính của mã nơi chúng tôi trích xuất thông tin chữ ký từ tài liệu PDF. Chúng tôi lặp qua từng trường trong biểu mẫu của tài liệu và kiểm tra xem đó có phải là trường chữ ký hay không. Nếu tìm thấy trường chữ ký, chúng tôi tiến hành trích xuất chứng chỉ. Thêm đoạn mã sau:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Trích xuất chứng chỉ
             Stream cerStream = sf.ExtractCertificate();
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
         }
     }
}
```

## Bước 4: Trích xuất chứng chỉ

Trong bước này, chúng tôi trích xuất chứng chỉ từ trường chữ ký và lưu nó dưới dạng tệp. Chứng chỉ được trích xuất có thể được phân tích sâu hơn hoặc được sử dụng cho mục đích xác nhận. Đoạn mã dưới đây minh họa quá trình trích xuất và lưu:

```csharp
Stream cerStream = sf.ExtractCertificate();
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

## Bước 5

: Lưu chứng chỉ

Cuối cùng, chúng tôi lưu chứng chỉ đã trích xuất dưới dạng tệp. Trong ví dụ này, chứng chỉ được lưu với tên "input.cer" trong thư mục được chỉ định. Bạn có thể sửa đổi mã cho phù hợp với yêu cầu của bạn. Đây là đoạn mã để lưu chứng chỉ:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Đó là nó! Bạn đã trích xuất thành công thông tin chữ ký bằng Aspose.PDF for .NET. Vui lòng tích hợp mã này vào các ứng dụng của riêng bạn hoặc sửa đổi nó theo nhu cầu của bạn.

### Mã nguồn mẫu để trích xuất thông tin chữ ký bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
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

Trong hướng dẫn này, chúng tôi đã hướng dẫn từng bước về cách trích xuất thông tin chữ ký từ tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi đã đề cập đến quá trình nhập các thư viện cần thiết, thiết lập đường dẫn tài liệu, trích xuất thông tin chữ ký, trích xuất chứng chỉ và lưu nó vào một tệp. Bằng cách làm theo các bước này, bạn có thể dễ dàng truy xuất chi tiết chữ ký và làm việc với chúng khi cần.

### Câu hỏi thường gặp

#### Hỏi: Tại sao tôi cần trích xuất thông tin chữ ký từ tài liệu PDF?

Đáp: Việc trích xuất thông tin chữ ký từ tài liệu PDF rất hữu ích cho việc xác thực tính xác thực của tài liệu đã ký và phân tích chứng chỉ được sử dụng cho chữ ký. Quá trình này giúp đảm bảo tính toàn vẹn của nội dung đã ký và có thể cần thiết cho các mục đích pháp lý và bảo mật.

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Trả lời: Aspose.PDF for .NET là thư viện cho phép các nhà phát triển làm việc với tài liệu PDF trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để tạo, sửa đổi và tương tác với các tệp PDF theo chương trình.

#### Câu hỏi: Điều kiện tiên quyết để trích xuất thông tin chữ ký bằng Aspose.PDF cho .NET là gì?

Đáp: Để trích xuất thông tin chữ ký, bạn cần có kiến thức cơ bản về ngôn ngữ lập trình C#, thư viện Aspose.PDF for .NET được cài đặt trên hệ thống của bạn và tài liệu PDF hợp lệ chứa một hoặc nhiều trường chữ ký.

#### Câu hỏi: Làm cách nào để nhập các thư viện cần thiết cho quá trình giải nén?

Trả lời: Bạn có thể nhập các thư viện cần thiết bằng cách thêm`using` chỉ thị cho`Aspose.Pdf` Và`System.IO` ở đầu tệp C# của bạn. Những chỉ thị này cho phép bạn sử dụng các lớp và phương thức cần thiết để trích xuất thông tin chữ ký.

#### Hỏi: Làm cách nào để chỉ định tài liệu PDF để trích xuất thông tin chữ ký?

 Trả lời: Bạn có thể đặt đường dẫn đến tài liệu PDF bằng cách thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế tới tài liệu của bạn trong đoạn mã được cung cấp. Đường dẫn này được sử dụng để tải tài liệu PDF mà bạn muốn trích xuất thông tin chữ ký từ đó.

#### Hỏi: Quá trình trích xuất thông tin chữ ký từ tài liệu PDF là gì?

Trả lời: Quá trình trích xuất bao gồm việc lặp qua các trường biểu mẫu của tài liệu PDF, kiểm tra xem mỗi trường có phải là trường chữ ký hay không và nếu có thì trích xuất chứng chỉ liên quan. Chứng chỉ được trích xuất có thể được lưu dưới dạng tệp để phân tích hoặc xác nhận thêm.

#### Câu hỏi: Chứng chỉ được trích xuất từ trường chữ ký như thế nào?

Trả lời: Chứng chỉ được trích xuất từ trường chữ ký bằng cách sử dụng`ExtractCertificate()` phương pháp được cung cấp bởi`SignatureField` lớp trong Aspose.PDF cho .NET. Phương thức này trả về một luồng chứa dữ liệu chứng chỉ.

#### Câu hỏi: Làm cách nào để lưu chứng chỉ đã trích xuất dưới dạng tệp?

 Trả lời: Bạn có thể lưu chứng chỉ được trích xuất dưới dạng tệp bằng cách đọc luồng chứng chỉ và ghi nội dung của nó vào một tệp bằng cách sử dụng`FileStream` lớp học. Mã được cung cấp trong hướng dẫn thể hiện quá trình này.

#### Câu hỏi: Tôi có thể sử dụng chứng chỉ được trích xuất này để xác thực chữ ký không?

Trả lời: Có, chứng chỉ được trích xuất có thể được sử dụng để xác thực chữ ký. Bạn có thể phân tích chi tiết của chứng chỉ và xác minh tính xác thực của nó để đảm bảo tính toàn vẹn của tài liệu đã ký.

#### Câu hỏi: Làm cách nào tôi có thể tích hợp mã này vào các ứng dụng của riêng mình?

Đáp: Bạn có thể tích hợp mã được cung cấp vào các ứng dụng C# của riêng mình bằng cách làm theo hướng dẫn từng bước. Sửa đổi đường dẫn và tên tệp nếu cần, đồng thời kết hợp mã vào các dự án hiện có của bạn.

#### Câu hỏi: Có các tính năng khác trong Aspose.PDF dành cho .NET liên quan đến quản lý chữ ký không?

Trả lời: Có, Aspose.PDF for .NET cung cấp nhiều tính năng để làm việc với chữ ký số, bao gồm ký tài liệu, xác minh chữ ký và thêm thông tin dấu thời gian. Bạn có thể khám phá tài liệu chính thức để biết thêm chi tiết về các tính năng này.

#### Câu hỏi: Tôi có thể tìm thêm tài nguyên để sử dụng Aspose.PDF cho .NET ở đâu?

 Đáp: Để biết thêm thông tin, hướng dẫn và tài nguyên về cách sử dụng Aspose.PDF cho .NET,[Aspose.PDF cho .NET](https://reference.aspose.com/pdf/net/).

#### Hỏi: Có thể trích xuất chữ ký từ tài liệu PDF được mã hóa không?

Trả lời: Khả năng trích xuất chữ ký từ tài liệu PDF được mã hóa có thể phụ thuộc vào cài đặt mã hóa và quyền của tài liệu. Bạn có thể cần đảm bảo rằng bạn có các quyền cần thiết để truy cập và trích xuất thông tin chữ ký.

#### Hỏi: Tôi có thể trích xuất nhiều chữ ký từ một tài liệu PDF không?

Đáp: Có, bạn có thể sửa đổi mã được cung cấp để lặp qua tất cả các trường chữ ký trong tài liệu PDF và trích xuất thông tin chữ ký từ mỗi trường. Điều này cho phép bạn trích xuất thông tin về nhiều chữ ký có trong tài liệu.

#### Câu hỏi: Một số trường hợp sử dụng thực tế để trích xuất thông tin chữ ký là gì?

Đáp: Một số trường hợp sử dụng thực tế để trích xuất thông tin chữ ký bao gồm xác thực tính xác thực của tài liệu được ký điện tử, phân tích chi tiết chứng chỉ cho mục đích tuân thủ và duy trì hồ sơ về chữ ký và người ký cho mục đích kiểm tra.

#### Hỏi: Có bất kỳ cân nhắc pháp lý nào khi trích xuất thông tin chữ ký không?

Trả lời: Việc trích xuất thông tin chữ ký có thể có ý nghĩa pháp lý, đặc biệt khi xử lý các tài liệu có tính ràng buộc về mặt pháp lý. Đảm bảo rằng bạn tuân thủ các quy định và luật liên quan liên quan đến chữ ký điện tử và tính xác thực của tài liệu tại khu vực pháp lý của bạn.