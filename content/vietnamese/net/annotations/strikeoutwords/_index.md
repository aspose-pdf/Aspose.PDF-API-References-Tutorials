---
title: gạch bỏ các từ
linktitle: gạch bỏ các từ
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Bài viết này cung cấp hướng dẫn từng bước cách sử dụng Aspose.PDF cho tính năng Strike Out Words của .NET, bao gồm hướng dẫn và giải thích từng bước
type: docs
weight: 150
url: /vi/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET là thư viện xử lý và thao tác tài liệu PDF cung cấp nhiều tính năng khác nhau để tạo, sửa đổi và chuyển đổi tệp PDF. Một trong những tính năng hữu ích mà Aspose.PDF cung cấp là khả năng gạch bỏ các từ hoặc cụm từ trong tài liệu PDF bằng mã nguồn C#. Trong bài viết này, chúng tôi sẽ cung cấp hướng dẫn từng bước về cách gạch bỏ các từ bằng Aspose.PDF cho .NET.

## Bước 1: Tải tài liệu PDF
Bước đầu tiên là tải tài liệu PDF mà bạn muốn sửa đổi. Trong hướng dẫn này, chúng tôi sẽ tải một tài liệu PDF có tên "input.pdf" từ thư mục "THƯ MỤC TÀI LIỆU CỦA BẠN". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Bước 2: Tìm kiếm đoạn văn bản
Để gạch bỏ các từ hoặc cụm từ cụ thể trong tài liệu PDF, trước tiên bạn cần tìm kiếm chúng. Aspose.PDF cung cấp lớp TextFragmentAbsorber có thể được sử dụng để tìm kiếm một đoạn văn bản cụ thể trong tài liệu PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Trong đoạn mã trên, chúng tôi đang tìm kiếm đoạn văn bản "Estoque" trong tài liệu PDF. Bạn có thể sửa đổi điều này để tìm kiếm bất kỳ từ hoặc cụm từ nào khác mà bạn muốn gạch bỏ.

## Bước 3: Gạch bỏ các đoạn văn bản
Sau khi tìm thấy các đoạn văn bản, bước tiếp theo là gạch bỏ chúng. Aspose.PDF cung cấp lớp StrikeOutAnnotation có thể được sử dụng để tạo chú thích gạch ngang cho đoạn văn bản. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Trong đoạn mã trên, chúng tôi đang tạo chú thích gạch ngang cho từng đoạn văn bản mà chúng tôi tìm thấy. Chúng tôi cũng đang thiết lập độ mờ, đường viền và màu sắc của chú thích gạch ngang.

## Bước 4: Lưu tài liệu PDF đã sửa đổi
Sau khi gạch bỏ các đoạn văn bản, hãy lưu tài liệu đã sửa đổi.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Mã nguồn mẫu cho Strike Out Words sử dụng Aspose.PDF for .NET


```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document document = new Document(dataDir + "input.pdf");

// Tạo phiên bản Trình hấp thụ TextFragment để tìm kiếm đoạn văn bản cụ thể
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Lặp lại qua các trang của tài liệu PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Nhận trang đầu tiên của tài liệu PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Tạo một bộ sưu tập văn bản hấp thụ
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Lặp lại bộ sưu tập trên
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Lấy kích thước hình chữ nhật của đối tượng TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Khởi tạo phiên bản Chú thích StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Đặt độ mờ cho chú thích
	strikeOut.Opacity = .80f;
	// Đặt đường viền cho phiên bản chú thích
	strikeOut.Border = new Border(strikeOut);
	// Đặt màu của chú thích
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Thêm chú thích vào bộ sưu tập chú thích của TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.PDF cho .NET để gạch bỏ các từ cụ thể trong tài liệu PDF. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng tải tài liệu PDF, tìm kiếm các đoạn văn bản cụ thể và tạo chú thích gạch ngang để đánh dấu và gạch bỏ những từ đó một cách trực quan. Aspose.PDF for .NET cung cấp một cách đơn giản và hiệu quả để thao tác các tài liệu PDF theo chương trình, khiến nó trở thành một công cụ có giá trị cho các nhà phát triển làm việc với các tệp PDF trong ứng dụng .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Trả lời: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và thao tác các tài liệu PDF theo chương trình trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để làm việc với các tệp PDF, bao gồm trích xuất văn bản, xử lý chú thích, điền biểu mẫu, v.v.

#### Câu hỏi: Tôi có thể sử dụng Aspose.PDF cho .NET để gạch bỏ các từ cụ thể trong tài liệu PDF không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp chức năng tìm kiếm các đoạn văn bản cụ thể trong tài liệu PDF, sau đó tạo chú thích gạch ngang để đánh dấu và gạch bỏ những từ đó một cách trực quan.

#### Hỏi: Làm cách nào để chỉ định văn bản tôi muốn gạch bỏ trong tài liệu PDF?

 Đáp: Để chỉ định văn bản bạn muốn gạch bỏ, bạn có thể sử dụng`TextFragmentAbsorber` lớp được cung cấp bởi Aspose.PDF cho .NET. Nó cho phép bạn tìm kiếm một đoạn văn bản cụ thể trong tài liệu PDF dựa trên tiêu chí mong muốn của bạn.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của chú thích gạch ngang không?

Đáp: Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của chú thích gạch ngang, chẳng hạn như độ mờ, kiểu đường viền và màu sắc. Điều này cho phép bạn điều chỉnh giao diện của chú thích gạch ngang theo yêu cầu cụ thể của mình.