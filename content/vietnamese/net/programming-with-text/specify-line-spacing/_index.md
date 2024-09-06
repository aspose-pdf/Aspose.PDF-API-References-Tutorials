---
title: Chỉ định khoảng cách dòng trong tệp PDF
linktitle: Chỉ định khoảng cách dòng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách chỉ định khoảng cách dòng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 510
url: /vi/net/programming-with-text/specify-line-spacing/
---
Hướng dẫn này giải thích cách chỉ định khoảng cách dòng trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày từng bước thực hiện.

## Điều kiện tiên quyết

Trước khi thực hiện hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để cài đặt vào dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) mà bạn thích và thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm lệnh using sau vào đầu tệp C# của bạn để nhập các không gian tên cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` biến:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tải tệp PDF đầu vào

 Tải tệp PDF đầu vào bằng cách sử dụng`Document` lớp học:

```csharp
Document doc = new Document();
```

## Bước 5: Tạo TextFormattingOptions

 Tạo một`TextFormattingOptions` đối tượng và thiết lập chế độ giãn cách dòng thành`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Bước 6: Tạo một TextFragment

 Tạo một`TextFragment` đối tượng và chỉ định nội dung văn bản:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Bước 7: Tải tệp phông chữ (tùy chọn)

 Nếu bạn muốn sử dụng một phông chữ cụ thể cho văn bản, hãy tải tệp phông chữ TrueType vào`FileStream` sự vật:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Thay thế`"HPSimplified.TTF"` với tên tệp phông chữ thực tế.

## Bước 8: Xác định vị trí văn bản và khoảng cách dòng

 Đặt vị trí cho đoạn văn bản và chỉ định`TextFormattingOptions` đến`TextState.FormattingOptions` tài sản:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Bước 9: Thêm văn bản vào tài liệu

 Thêm đoạn văn bản vào tài liệu, bằng cách thêm nó vào`TextBuilder` hoặc trực tiếp đến một trang`Paragraphs` bộ sưu tập:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Bước 10: Lưu tài liệu PDF kết quả

Lưu tài liệu PDF đã sửa đổi:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Hãy chắc chắn thay thế`"SpecifyLineSpacing_out.pdf"` với tên tập tin đầu ra mong muốn.

### Mã nguồn mẫu để Chỉ định khoảng cách dòng bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Tải tệp PDF đầu vào
Document doc = new Document();
//Tạo TextFormattingOptions với LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Tạo đối tượng xây dựng văn bản cho trang đầu tiên của tài liệu
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Tạo đoạn văn bản với chuỗi mẫu
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Tải phông chữ TrueType vào đối tượng luồng
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Đặt tên phông chữ cho chuỗi văn bản
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Chỉ định vị trí cho Đoạn văn bản
		textFragment.Position = new Position(100, 600);
		//Đặt TextFormattingOptions của đoạn hiện tại thành predefined (trỏ đến LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Thêm văn bản vào TextBuilder để có thể đặt lên tệp PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Lưu tài liệu PDF kết quả
	doc.Save(dataDir);
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách chỉ định khoảng cách dòng trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến lưu tài liệu đã sửa đổi. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để tùy chỉnh khoảng cách dòng của văn bản trong tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Chỉ định khoảng cách dòng trong tệp PDF" là gì?

A: Hướng dẫn "Chỉ định khoảng cách dòng trong tệp PDF" nhằm hướng dẫn người dùng cách sử dụng thư viện Aspose.PDF cho .NET để tùy chỉnh khoảng cách dòng của văn bản trong tài liệu PDF. Hướng dẫn cung cấp hướng dẫn từng bước và các mẫu mã C# để chứng minh quy trình.

#### H: Hướng dẫn này giúp ích gì trong việc xác định khoảng cách dòng trong tài liệu PDF?

A: Hướng dẫn này giúp người dùng hiểu cách sử dụng các khả năng của Aspose.PDF cho .NET để chỉ định khoảng cách dòng cho văn bản trong tài liệu PDF. Bằng cách làm theo các bước và ví dụ mã được cung cấp, người dùng có thể điều chỉnh khoảng cách dòng theo sở thích của mình.

#### H: Cần có những điều kiện tiên quyết nào để làm theo hướng dẫn này?

A: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt vào dự án của mình bằng NuGet.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Điều này cho phép bạn tận dụng các tính năng của thư viện để làm việc với tài liệu PDF và tùy chỉnh khoảng cách dòng.

#### H: Tôi có thể sử dụng hướng dẫn này để chỉ định khoảng cách dòng cho bất kỳ loại văn bản nào không?

A: Có, hướng dẫn này cung cấp hướng dẫn về cách chỉ định khoảng cách dòng cho bất kỳ nội dung văn bản nào trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng các mẫu mã được cung cấp để điều chỉnh khoảng cách dòng của văn bản theo nhu cầu của mình.

#### H: Làm thế nào để chỉ định chế độ giãn dòng trong hướng dẫn?

 A: Hướng dẫn này trình bày cách tạo một`TextFormattingOptions` đối tượng và thiết lập của nó`LineSpacing` tài sản để`TextFormattingOptions.LineSpacingMode.FullSize`. Chế độ này chỉ định khoảng cách dòng đầy đủ cho nội dung văn bản.

#### H: Làm thế nào tôi có thể tải phông chữ cụ thể cho văn bản?

 A: Nếu bạn muốn sử dụng một phông chữ cụ thể cho nội dung văn bản, hướng dẫn sẽ cung cấp hướng dẫn về cách tải tệp phông chữ TrueType vào`FileStream` đối tượng và đặt nó làm phông chữ cho`TextFragment`. Tính năng này cho phép bạn tùy chỉnh phông chữ của văn bản cùng với khoảng cách dòng.

#### H: Làm thế nào để tùy chỉnh vị trí của văn bản trong tài liệu PDF?

 A: Để tùy chỉnh vị trí của văn bản, hãy tạo một`TextFragment` đối tượng và thiết lập của nó`Position`thuộc tính theo tọa độ mong muốn (X và Y). Điều này cho phép bạn kiểm soát vị trí đặt văn bản trong tài liệu PDF.

#### H: Tôi có thể áp dụng những thay đổi khoảng cách dòng này cho các tài liệu PDF hiện có không?

 A: Có, bạn có thể sửa đổi khoảng cách dòng cho văn bản trong các tài liệu PDF hiện có. Hướng dẫn này trình bày cách tạo`TextFragment` với khoảng cách dòng và vị trí được chỉ định, sau đó thêm nó vào trang`Paragraphs` bộ sưu tập.