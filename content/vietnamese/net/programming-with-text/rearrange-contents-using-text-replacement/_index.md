---
title: Sắp xếp lại nội dung bằng cách sử dụng thay thế văn bản
linktitle: Sắp xếp lại nội dung bằng cách sử dụng thay thế văn bản
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sắp xếp lại nội dung trong tài liệu PDF bằng cách thay thế văn bản với Aspose.PDF cho .NET.
type: docs
weight: 270
url: /vi/net/programming-with-text/rearrange-contents-using-text-replacement/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách sắp xếp lại nội dung trong tài liệu PDF bằng cách sử dụng thay thế văn bản với thư viện Aspose.PDF cho .NET. Chúng tôi sẽ thực hiện từng bước quy trình tải PDF, tìm kiếm các đoạn văn bản cụ thể, thay thế văn bản và lưu PDF đã sửa đổi bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục chứa các tệp PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải PDF nguồn

 Tiếp theo, chúng tôi tải tài liệu PDF nguồn bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Bước 3: Tìm kiếm và thay thế các đoạn văn bản

 Chúng tôi tạo ra một`TextFragmentAbsorber` đối tượng có biểu thức chính quy để tìm kiếm các đoạn văn bản cụ thể. Sau đó, chúng tôi lặp lại các đoạn văn bản, tùy chỉnh phông chữ, kích thước, màu sắc và thay thế văn bản.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Bước 4: Lưu PDF đã sửa đổi

Cuối cùng, chúng ta lưu tài liệu PDF đã chỉnh sửa vào tệp đầu ra đã chỉ định.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu cho Sắp xếp lại nội dung bằng cách sử dụng Thay thế văn bản bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tệp PDF nguồn
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Tạo đối tượng TextFragment Absorber với biểu thức chính quy
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Thay thế từng TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Đặt phông chữ của đoạn văn bản đang được thay thế
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Đặt kích thước phông chữ
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Thay thế văn bản bằng chuỗi lớn hơn chỗ giữ chỗ
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Lưu PDF kết quả
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách sắp xếp lại nội dung trong tài liệu PDF bằng cách sử dụng thay thế văn bản với thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tìm kiếm các đoạn văn bản cụ thể, tùy chỉnh giao diện của chúng và thay thế văn bản trong tài liệu PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Sắp xếp lại nội dung bằng cách thay thế văn bản" là gì?

A: Hướng dẫn "Sắp xếp lại nội dung bằng cách thay thế văn bản" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để sắp xếp lại nội dung trong tài liệu PDF bằng cách thực hiện thay thế văn bản. Hướng dẫn cung cấp hướng dẫn từng bước và mã nguồn C# để giúp bạn tải PDF, tìm kiếm các đoạn văn bản cụ thể, thay thế văn bản và lưu PDF đã sửa đổi.

#### H: Tại sao tôi muốn sắp xếp lại nội dung trong tài liệu PDF?

A: Việc sắp xếp lại nội dung trong tài liệu PDF có thể hữu ích cho nhiều mục đích khác nhau, chẳng hạn như cập nhật văn bản, định dạng lại bố cục hoặc chỉnh sửa. Kỹ thuật này cho phép bạn sửa đổi nội dung PDF một cách động trong khi vẫn giữ nguyên cấu trúc và giao diện của nó.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục chứa các tệp PDF của bạn.

#### H: Làm thế nào để thực hiện thay thế văn bản trong tài liệu PDF?

 A: Hướng dẫn này hướng dẫn bạn quy trình tìm kiếm các đoạn văn bản cụ thể trong PDF bằng cách sử dụng`TextFragmentAbsorber`lớp. Nó trình bày cách tùy chỉnh giao diện của các đoạn văn bản và thay thế nội dung của chúng.

#### H: Tôi có thể tùy chỉnh phông chữ, kích thước và màu sắc của văn bản thay thế không?

 A: Có, bạn có thể tùy chỉnh phông chữ, kích thước và màu sắc của văn bản được thay thế bằng cách sửa đổi`TextState` tính chất của`TextFragment` đối tượng. Hướng dẫn cung cấp ví dụ về cách thiết lập phông chữ, cỡ chữ và màu nền của văn bản.

#### H: Làm thế nào để lưu tài liệu PDF đã chỉnh sửa?

 A: Sau khi thực hiện thay thế văn bản và tùy chỉnh các đoạn văn bản, bạn có thể lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp. Cung cấp đường dẫn tệp đầu ra mong muốn làm đối số cho`Save` phương pháp.

#### H: Kết quả mong đợi của hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn và thực thi mã C# được cung cấp, bạn sẽ tạo ra một tài liệu PDF đã sửa đổi, trong đó các đoạn văn bản cụ thể đã được thay thế và tùy chỉnh theo thông số kỹ thuật của bạn.

#### H: Tôi có thể sử dụng các biểu thức chính quy khác nhau để tìm kiếm văn bản không?

 A: Có, bạn có thể sử dụng các biểu thức chính quy khác nhau để tìm kiếm các đoạn văn bản cụ thể trong tài liệu PDF. Ví dụ được cung cấp trong hướng dẫn này minh họa cách tạo`TextFragmentAbsorber`đối tượng có biểu thức chính quy cụ thể để tìm kiếm và thay thế văn bản.

#### H: Có cần Giấy phép Aspose hợp lệ cho hướng dẫn này không?

A: Có, cần phải có Giấy phép Aspose hợp lệ để hướng dẫn này hoạt động chính xác. Bạn có thể mua giấy phép đầy đủ hoặc xin giấy phép tạm thời 30 ngày từ trang web Aspose.