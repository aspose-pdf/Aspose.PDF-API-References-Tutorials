---
title: Trích xuất thông tin chữ ký
linktitle: Trích xuất thông tin chữ ký
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Trích xuất thông tin chữ ký bằng Aspose.PDF cho .NET.
type: docs
weight: 80
url: /vi/net/programming-with-security-and-signatures/extract-signature-info/
---
Quá trình trích xuất thông tin chữ ký từ tài liệu PDF có thể khá hữu ích trong nhiều tình huống khác nhau. Cho dù bạn cần xác thực tính xác thực của tài liệu đã ký hay phân tích chứng chỉ được sử dụng cho chữ ký, thư viện Aspose.PDF cho .NET đều cung cấp giải pháp tiện lợi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước trích xuất thông tin chữ ký bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Kiến thức cơ bản về ngôn ngữ lập trình C#.
2. Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
3. Một tài liệu PDF hợp lệ có một hoặc nhiều trường chữ ký.

Bây giờ, chúng ta hãy đi sâu vào chi tiết triển khai.

## Bước 1: Nhập các thư viện cần thiết

 Để bắt đầu, bạn cần nhập các thư viện cần thiết vào dự án C# của mình. Trong trường hợp này, chúng ta cần nhập`Aspose.Pdf` Và`System.IO` không gian tên. Bạn có thể thực hiện điều này bằng cách thêm đoạn mã sau vào đầu tệp C# của mình:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Bước 2: Thiết lập đường dẫn tài liệu

Tiếp theo, bạn cần thiết lập đường dẫn đến tài liệu PDF mà bạn muốn trích xuất thông tin chữ ký. Thay thế`"YOUR DOCUMENTS DIRECTORY"` trong đoạn mã sau với đường dẫn thực tế đến tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Bước 3: Trích xuất thông tin chữ ký

Bây giờ, chúng ta hãy chuyển sang phần chính của mã, nơi chúng ta trích xuất thông tin chữ ký từ tài liệu PDF. Chúng ta lặp lại từng trường trong biểu mẫu của tài liệu và kiểm tra xem đó có phải là trường chữ ký hay không. Nếu tìm thấy trường chữ ký, chúng ta sẽ tiến hành trích xuất chứng chỉ. Thêm đoạn mã sau:

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

Trong bước này, chúng tôi trích xuất chứng chỉ từ trường chữ ký và lưu dưới dạng tệp. Chứng chỉ được trích xuất có thể được phân tích thêm hoặc sử dụng cho mục đích xác thực. Đoạn mã dưới đây minh họa quá trình trích xuất và lưu:

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

Cuối cùng, chúng ta lưu chứng chỉ đã trích xuất dưới dạng tệp. Trong ví dụ này, chứng chỉ được lưu với tên "input.cer" trong thư mục đã chỉ định. Bạn có thể sửa đổi mã cho phù hợp với yêu cầu của mình. Sau đây là đoạn mã để lưu chứng chỉ:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Vậy là xong! Bạn đã trích xuất thành công thông tin chữ ký bằng Aspose.PDF cho .NET. Hãy thoải mái tích hợp mã này vào các ứng dụng của riêng bạn hoặc sửa đổi nó theo nhu cầu của bạn.

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

Trong hướng dẫn này, chúng tôi đã hướng dẫn từng bước về cách trích xuất thông tin chữ ký từ tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi đã đề cập đến quy trình nhập các thư viện cần thiết, thiết lập đường dẫn tài liệu, trích xuất thông tin chữ ký, trích xuất chứng chỉ và lưu vào tệp. Bằng cách làm theo các bước này, bạn có thể dễ dàng lấy thông tin chi tiết về chữ ký và làm việc với chúng khi cần.

### Câu hỏi thường gặp

#### H: Tại sao tôi cần phải trích xuất thông tin chữ ký từ tài liệu PDF?

A: Trích xuất thông tin chữ ký từ tài liệu PDF rất hữu ích để xác thực tính xác thực của tài liệu đã ký và phân tích chứng chỉ được sử dụng cho chữ ký. Quá trình này giúp đảm bảo tính toàn vẹn của nội dung đã ký và có thể cần thiết cho mục đích pháp lý và bảo mật.

#### H: Aspose.PDF dành cho .NET là gì?

A: Aspose.PDF for .NET là một thư viện cho phép các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để tạo, sửa đổi và tương tác với các tệp PDF theo chương trình.

#### H: Điều kiện tiên quyết để trích xuất thông tin chữ ký bằng Aspose.PDF cho .NET là gì?

A: Để trích xuất thông tin chữ ký, bạn cần có kiến thức cơ bản về ngôn ngữ lập trình C#, thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn và một tài liệu PDF hợp lệ chứa một hoặc nhiều trường chữ ký.

#### H: Làm thế nào để nhập các thư viện cần thiết cho quá trình trích xuất?

A: Bạn có thể nhập các thư viện cần thiết bằng cách thêm`using` chỉ thị cho`Aspose.Pdf` Và`System.IO` ở đầu tệp C# của bạn. Các chỉ thị này cho phép bạn sử dụng các lớp và phương thức cần thiết để trích xuất thông tin chữ ký.

#### H: Làm thế nào để chỉ định tài liệu PDF để trích xuất thông tin chữ ký?

 A: Bạn có thể thiết lập đường dẫn đến tài liệu PDF bằng cách thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn trong đoạn mã được cung cấp. Đường dẫn này được sử dụng để tải tài liệu PDF mà bạn muốn trích xuất thông tin chữ ký.

#### H: Quy trình trích xuất thông tin chữ ký từ tài liệu PDF là gì?

A: Quá trình trích xuất bao gồm việc lặp lại qua các trường biểu mẫu của tài liệu PDF, kiểm tra xem mỗi trường có phải là trường chữ ký hay không và nếu có, trích xuất chứng chỉ liên quan. Chứng chỉ đã trích xuất có thể được lưu dưới dạng tệp để phân tích hoặc xác thực thêm.

#### H: Chứng chỉ được trích xuất từ trường chữ ký như thế nào?

A: Chứng chỉ được trích xuất từ trường chữ ký bằng cách sử dụng`ExtractCertificate()` phương pháp được cung cấp bởi`SignatureField` lớp trong Aspose.PDF cho .NET. Phương pháp này trả về một luồng chứa dữ liệu chứng chỉ.

#### H: Làm thế nào để lưu chứng chỉ đã trích xuất thành một tệp?

 A: Bạn có thể lưu chứng chỉ đã trích xuất dưới dạng tệp bằng cách đọc luồng chứng chỉ và ghi nội dung của nó vào tệp bằng cách sử dụng`FileStream` lớp. Mã được cung cấp trong hướng dẫn minh họa quá trình này.

#### H: Tôi có thể sử dụng chứng chỉ đã trích xuất này để xác thực chữ ký không?

A: Có, chứng chỉ đã trích xuất có thể được sử dụng để xác thực chữ ký. Bạn có thể phân tích chi tiết chứng chỉ và xác minh tính xác thực của nó để đảm bảo tính toàn vẹn của tài liệu đã ký.

#### H: Làm sao tôi có thể tích hợp mã này vào ứng dụng của mình?

A: Bạn có thể tích hợp mã được cung cấp vào các ứng dụng C# của riêng bạn bằng cách làm theo hướng dẫn từng bước. Sửa đổi đường dẫn và tên tệp khi cần thiết và kết hợp mã vào các dự án hiện có của bạn.

#### H: Có những tính năng nào khác trong Aspose.PDF dành cho .NET liên quan đến quản lý chữ ký không?

A: Có, Aspose.PDF for .NET cung cấp nhiều tính năng để làm việc với chữ ký số, bao gồm ký tài liệu, xác minh chữ ký và thêm thông tin dấu thời gian. Bạn có thể khám phá tài liệu chính thức để biết thêm chi tiết về các tính năng này.

#### H: Tôi có thể tìm thêm tài nguyên về cách sử dụng Aspose.PDF cho .NET ở đâu?

 A: Để biết thêm thông tin, hướng dẫn và tài nguyên về cách sử dụng Aspose.PDF cho .NET,[Aspose.PDF cho .NET](https://reference.aspose.com/pdf/net/).

#### H: Có thể trích xuất chữ ký từ các tài liệu PDF được mã hóa không?

A: Khả năng trích xuất chữ ký từ các tài liệu PDF được mã hóa có thể phụ thuộc vào cài đặt mã hóa và quyền của tài liệu. Bạn có thể cần đảm bảo rằng mình có các quyền cần thiết để truy cập và trích xuất thông tin chữ ký.

#### H: Tôi có thể trích xuất nhiều chữ ký từ một tài liệu PDF không?

A: Có, bạn có thể sửa đổi mã được cung cấp để lặp qua tất cả các trường chữ ký trong tài liệu PDF và trích xuất thông tin chữ ký từ mỗi trường. Điều này cho phép bạn trích xuất thông tin về nhiều chữ ký có trong tài liệu.

#### H: Một số trường hợp sử dụng thực tế để trích xuất thông tin chữ ký là gì?

A: Một số trường hợp sử dụng thực tế để trích xuất thông tin chữ ký bao gồm xác thực tính xác thực của các tài liệu được ký kỹ thuật số, phân tích chi tiết chứng chỉ cho mục đích tuân thủ và lưu giữ hồ sơ chữ ký và người ký cho mục đích kiểm toán.

#### H: Có cân nhắc nào về mặt pháp lý khi trích xuất thông tin chữ ký không?

A: Việc trích xuất thông tin chữ ký có thể có những tác động pháp lý, đặc biệt là khi xử lý các tài liệu ràng buộc về mặt pháp lý. Đảm bảo rằng bạn tuân thủ các quy định và luật pháp có liên quan đến chữ ký điện tử và tính xác thực của tài liệu trong phạm vi quyền hạn của bạn.