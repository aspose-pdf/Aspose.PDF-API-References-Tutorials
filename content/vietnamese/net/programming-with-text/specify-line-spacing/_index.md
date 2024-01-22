---
title: Chỉ định khoảng cách dòng trong tệp PDF
linktitle: Chỉ định khoảng cách dòng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách chỉ định khoảng cách dòng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 510
url: /vi/net/programming-with-text/specify-line-spacing/
---
Hướng dẫn này giải thích cách chỉ định khoảng cách dòng trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện quy trình từng bước.

## Điều kiện tiên quyết

Trước khi tiếp tục với hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể lấy nó từ trang web Aspose hoặc sử dụng NuGet để cài đặt nó trong dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm các lệnh sử dụng sau vào đầu tệp C# của bạn để nhập các không gian tên được yêu cầu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` Biến đổi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tải file PDF đầu vào

 Tải tệp PDF đầu vào bằng cách sử dụng`Document` lớp học:

```csharp
Document doc = new Document();
```

## Bước 5: Tạo TextFormattingOptions

 Tạo một`TextFormattingOptions` đối tượng và đặt chế độ giãn cách dòng thành`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Bước 6: Tạo một đoạn văn bản

 Tạo một`TextFragment` đối tượng và chỉ định nội dung văn bản:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Bước 7: Load file font (tùy chọn)

 Nếu bạn muốn sử dụng một phông chữ cụ thể cho văn bản, hãy tải tệp phông chữ TrueType vào một`FileStream` sự vật:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Thay thế`"HPSimplified.TTF"` với tên tệp phông chữ thực tế.

## Bước 8: Xác định vị trí văn bản và khoảng cách dòng

 Đặt vị trí cho đoạn văn bản và gán`TextFormattingOptions` đến`TextState.FormattingOptions` tài sản:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Bước 9: Thêm văn bản vào tài liệu

 Thêm đoạn văn bản vào tài liệu bằng cách thêm nó vào một`TextBuilder` hoặc trực tiếp đến một trang`Paragraphs` bộ sưu tập:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Bước 10: Lưu tài liệu PDF thu được

Lưu tài liệu PDF đã sửa đổi:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Đảm bảo thay thế`"SpecifyLineSpacing_out.pdf"` với tên tệp đầu ra mong muốn.

### Mã nguồn mẫu cho Chỉ định khoảng cách dòng bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Tải tập tin PDF đầu vào
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
		//Đặt tên phông chữ cho chuỗi văn bản
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Chỉ định vị trí cho Text Fragment
		textFragment.Position = new Position(100, 600);
		//Đặt TextFormattingOptions của đoạn hiện tại thành được xác định trước (trỏ tới LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Thêm văn bản vào TextBuilder để có thể đặt nó lên trên tệp PDF
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

Chúc mừng! Bạn đã học thành công cách chỉ định khoảng cách dòng trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến lưu tài liệu đã sửa đổi. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để tùy chỉnh khoảng cách dòng của văn bản trong tệp PDF.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Chỉ định khoảng cách dòng trong tệp PDF" là gì?

Trả lời: Hướng dẫn "Chỉ định khoảng cách dòng trong tệp PDF" nhằm mục đích hướng dẫn người dùng cách sử dụng thư viện Aspose.PDF cho .NET để tùy chỉnh khoảng cách dòng của văn bản trong tài liệu PDF. Hướng dẫn này cung cấp hướng dẫn từng bước và mẫu mã C# để minh họa quy trình.

#### Hỏi: Hướng dẫn này giúp ích như thế nào trong việc chỉ định khoảng cách dòng trong tài liệu PDF?

Đáp: Hướng dẫn này giúp người dùng hiểu cách sử dụng các khả năng của Aspose.PDF dành cho .NET để chỉ định khoảng cách dòng cho văn bản trong tài liệu PDF. Bằng cách làm theo các bước và ví dụ về mã được cung cấp, người dùng có thể điều chỉnh khoảng cách dòng theo sở thích của mình.

#### Câu hỏi: Cần có những điều kiện tiên quyết nào để thực hiện theo hướng dẫn này?

Đáp: Trước khi bắt đầu hướng dẫn, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF for .NET. Bạn có thể lấy nó từ trang web Aspose hoặc cài đặt nó trong dự án của bạn bằng NuGet.

#### Hỏi: Làm cách nào để thiết lập dự án của tôi theo hướng dẫn này?

Đáp: Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn và thêm tham chiếu vào thư viện Aspose.PDF cho .NET. Điều này cho phép bạn tận dụng các tính năng của thư viện để làm việc với tài liệu PDF và tùy chỉnh khoảng cách dòng.

#### Hỏi: Tôi có thể sử dụng hướng dẫn này để chỉ định khoảng cách dòng cho bất kỳ loại văn bản nào không?

Đáp: Có, hướng dẫn này cung cấp hướng dẫn về cách chỉ định khoảng cách dòng cho bất kỳ nội dung văn bản nào trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng các mẫu mã được cung cấp để điều chỉnh khoảng cách dòng của văn bản theo nhu cầu của mình.

#### Hỏi: Làm cách nào để chỉ định chế độ giãn cách dòng trong hướng dẫn?

 Đáp: Phần hướng dẫn này trình bày cách tạo một`TextFormattingOptions` đối tượng và thiết lập nó`LineSpacing` tài sản để`TextFormattingOptions.LineSpacingMode.FullSize`. Chế độ này chỉ định khoảng cách dòng đầy đủ cho nội dung văn bản.

#### Hỏi: Làm cách nào tôi có thể tải một phông chữ cụ thể cho văn bản?

 Đáp: Nếu bạn muốn sử dụng một phông chữ cụ thể cho nội dung văn bản, hướng dẫn này sẽ cung cấp hướng dẫn về cách tải tệp phông chữ TrueType vào một`FileStream` đối tượng và đặt nó làm phông chữ cho`TextFragment`. Điều này cho phép bạn tùy chỉnh phông chữ của văn bản cùng với khoảng cách dòng của nó.

#### Hỏi: Làm cách nào để tùy chỉnh vị trí của văn bản trong tài liệu PDF?

 Đáp: Để tùy chỉnh vị trí của văn bản, hãy tạo một`TextFragment` đối tượng và thiết lập nó`Position`thuộc tính tới tọa độ mong muốn (X và Y). Điều này cho phép bạn kiểm soát vị trí đặt văn bản trong tài liệu PDF.

#### Câu hỏi: Tôi có thể áp dụng những sửa đổi khoảng cách dòng này cho các tài liệu PDF hiện có không?

 Đáp: Có, bạn có thể sửa đổi khoảng cách dòng cho văn bản trong tài liệu PDF hiện có. Hướng dẫn này trình bày cách tạo một`TextFragment` với khoảng cách dòng và vị trí được chỉ định, sau đó thêm nó vào phần của trang`Paragraphs` bộ sưu tập.