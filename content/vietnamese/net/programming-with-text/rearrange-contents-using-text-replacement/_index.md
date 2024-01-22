---
title: Sắp xếp lại nội dung bằng cách sử dụng thay thế văn bản
linktitle: Sắp xếp lại nội dung bằng cách sử dụng thay thế văn bản
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sắp xếp lại nội dung trong tài liệu PDF bằng cách thay thế văn bản bằng Aspose.PDF cho .NET.
type: docs
weight: 270
url: /vi/net/programming-with-text/rearrange-contents-using-text-replacement/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách sắp xếp lại nội dung trong tài liệu PDF bằng cách sử dụng tính năng thay thế văn bản bằng thư viện Aspose.PDF cho .NET. Chúng ta sẽ thực hiện quy trình từng bước tải tệp PDF, tìm kiếm các đoạn văn bản cụ thể, thay thế văn bản và lưu tệp PDF đã sửa đổi bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Trước tiên, bạn cần đặt đường dẫn đến thư mục chứa tệp PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến bằng đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải nguồn PDF

 Tiếp theo, chúng tôi tải tài liệu PDF nguồn bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Bước 3: Tìm kiếm và thay thế các đoạn văn bản

 Chúng tôi tạo ra một`TextFragmentAbsorber` đối tượng có biểu thức chính quy để tìm kiếm các đoạn văn bản cụ thể. Sau đó, chúng tôi lặp qua các đoạn văn bản, tùy chỉnh phông chữ, kích thước, màu sắc và thay thế văn bản.

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

## Bước 4: Lưu tệp PDF đã sửa đổi

Cuối cùng, chúng tôi lưu tài liệu PDF đã sửa đổi vào tệp đầu ra được chỉ định.

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
	// Tải tập tin PDF nguồn
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Tạo đối tượng TextFragment Hấp thụ với biểu thức chính quy
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Thay thế từng đoạn văn bản
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Đặt phông chữ của đoạn văn bản đang được thay thế
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Đặt kích thước phông chữ
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Thay thế văn bản bằng chuỗi lớn hơn phần giữ chỗ
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Lưu kết quả PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách sắp xếp lại nội dung trong tài liệu PDF bằng cách sử dụng tính năng thay thế văn bản bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tìm kiếm các đoạn văn bản cụ thể, tùy chỉnh giao diện của chúng và thay thế văn bản trong tài liệu PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Sắp xếp lại nội dung bằng cách sử dụng thay thế văn bản" là gì?

Đáp: Hướng dẫn "Sắp xếp lại nội dung bằng cách thay thế văn bản" trình bày cách sử dụng thư viện Aspose.PDF cho .NET để sắp xếp lại nội dung trong tài liệu PDF bằng cách thực hiện thay thế văn bản. Hướng dẫn này cung cấp hướng dẫn từng bước và mã nguồn C# để giúp bạn tải tệp PDF, tìm kiếm các đoạn văn bản cụ thể, thay thế văn bản và lưu tệp PDF đã sửa đổi.

#### Hỏi: Tại sao tôi muốn sắp xếp lại nội dung trong tài liệu PDF?

Đáp: Việc sắp xếp lại nội dung trong tài liệu PDF có thể hữu ích cho nhiều mục đích khác nhau, chẳng hạn như cập nhật văn bản, định dạng lại bố cục hoặc thực hiện các chỉnh sửa. Kỹ thuật này cho phép bạn tự động sửa đổi nội dung của tệp PDF trong khi vẫn giữ nguyên cấu trúc và hình thức của nó.

#### Hỏi: Làm cách nào để thiết lập thư mục tài liệu?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến bằng đường dẫn đến thư mục chứa tệp PDF của bạn.

#### Hỏi: Làm cách nào để thực hiện thay thế văn bản trong tài liệu PDF?

 Đáp: Hướng dẫn này sẽ hướng dẫn bạn qua quá trình tìm kiếm các đoạn văn bản cụ thể trong một tệp PDF bằng cách sử dụng`TextFragmentAbsorber`lớp học. Nó trình bày cách tùy chỉnh giao diện của các đoạn văn bản và thay thế nội dung của chúng.

#### Hỏi: Tôi có thể tùy chỉnh phông chữ, kích thước và màu sắc của văn bản được thay thế không?

 Đáp: Có, bạn có thể tùy chỉnh phông chữ, kích thước và màu sắc của văn bản được thay thế bằng cách sửa đổi`TextState` thuộc tính của`TextFragment` sự vật. Hướng dẫn này cung cấp ví dụ về cách đặt phông chữ, cỡ chữ và màu nền trước của văn bản.

#### Hỏi: Làm cách nào để lưu tài liệu PDF đã sửa đổi?

 Đáp: Sau khi thực hiện thay thế văn bản và tùy chỉnh các đoạn văn bản, bạn có thể lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp học. Cung cấp đường dẫn tệp đầu ra mong muốn làm đối số cho`Save` phương pháp.

#### Hỏi: Kết quả mong đợi của hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn và thực thi mã C# được cung cấp, bạn sẽ tạo một tài liệu PDF đã sửa đổi trong đó các đoạn văn bản cụ thể đã được thay thế và tùy chỉnh theo thông số kỹ thuật của bạn.

#### Câu hỏi: Tôi có thể sử dụng các biểu thức chính quy khác nhau để tìm kiếm văn bản không?

 Đáp: Có, bạn có thể sử dụng các biểu thức chính quy khác nhau để tìm kiếm các đoạn văn bản cụ thể trong tài liệu PDF. Ví dụ được cung cấp trong hướng dẫn này minh họa cách tạo một`TextFragmentAbsorber`đối tượng có biểu thức chính quy cụ thể để tìm kiếm và thay thế văn bản.

#### Câu hỏi: Có cần phải có Giấy phép Aspose hợp lệ cho hướng dẫn này không?

Trả lời: Có, cần có Giấy phép Aspose hợp lệ để hướng dẫn này hoạt động chính xác. Bạn có thể mua giấy phép đầy đủ hoặc lấy giấy phép tạm thời 30 ngày từ trang web Aspose.