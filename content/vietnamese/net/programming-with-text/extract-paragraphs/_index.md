---
title: Trích xuất đoạn văn trong tệp PDF
linktitle: Trích xuất đoạn văn trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất đoạn văn trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 160
url: /vi/net/programming-with-text/extract-paragraphs/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất đoạn văn trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn trích xuất đoạn văn, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Mở tài liệu PDF
 Mở một tài liệu PDF hiện có bằng cách sử dụng`Document`hàm tạo và truyền đường dẫn đến tệp PDF đầu vào.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 5: Trích xuất đoạn văn
 Khởi tạo`ParagraphAbsorber` lớp và sử dụng nó`Visit` phương pháp trích xuất đoạn văn từ tài liệu.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Bước 6: Lặp lại qua các đoạn văn
Lặp qua các đoạn văn đã trích xuất để truy cập nội dung văn bản. Sử dụng các vòng lặp lồng nhau để duyệt qua các phần và dòng trong mỗi đoạn văn.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Mã nguồn mẫu để trích xuất đoạn văn bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở một tệp PDF hiện có
Document doc = new Document(dataDir + "input.pdf");
// Khởi tạo ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Phần kết luận
Bạn đã trích xuất thành công các đoạn văn từ tài liệu PDF bằng Aspose.PDF cho .NET. Các đoạn văn đã trích xuất đã được hiển thị trong cửa sổ bảng điều khiển.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn này là gì?

A: Hướng dẫn này nhằm mục đích hướng dẫn bạn thực hiện quy trình trích xuất đoạn văn từ tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# đi kèm cung cấp các bước thực tế để thực hiện nhiệm vụ này.

#### H: Tôi nên nhập những không gian tên nào?

A: Trong tệp mã mà bạn định trích xuất đoạn văn, hãy bao gồm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Xác định vị trí đường thẳng`string dataDir = "YOUR DOCUMENT DIRECTORY";` trong mã và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để mở một tài liệu PDF hiện có?

 A: Ở Bước 4, bạn sẽ mở một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và cung cấp đường dẫn đến tệp PDF đầu vào.

#### H: Làm thế nào để trích xuất đoạn văn từ tài liệu?

 A: Bước 5 bao gồm việc tạo một phiên bản của`ParagraphAbsorber` lớp và sử dụng nó`Visit` phương pháp trích xuất đoạn văn từ tài liệu PDF.

#### H: Làm thế nào để lặp lại các đoạn văn đã trích xuất?

A: Bước 6 hướng dẫn bạn cách lặp qua các đoạn văn đã trích xuất. Các vòng lặp lồng nhau được sử dụng để duyệt qua các phần và dòng trong mỗi đoạn văn, cuối cùng là truy cập và hiển thị nội dung văn bản.

#### H: Điểm chính cần lưu ý trong hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học cách trích xuất các đoạn văn từ tài liệu PDF bằng Aspose.PDF cho .NET. Các đoạn văn được trích xuất đã được hiển thị trong cửa sổ bảng điều khiển, cung cấp cho bạn thông tin chi tiết có giá trị về cấu trúc nội dung của tài liệu.