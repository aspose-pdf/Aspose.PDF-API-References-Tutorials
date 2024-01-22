---
title: Trích xuất đoạn văn trong tệp PDF
linktitle: Trích xuất đoạn văn trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất các đoạn trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 160
url: /vi/net/programming-with-text/extract-paragraphs/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình trích xuất các đoạn văn trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp thể hiện các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt nó.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn.
2. Thêm tham chiếu đến thư viện Aspose.PDF for .NET.

## Bước 2: Nhập các không gian tên bắt buộc
Trong tệp mã nơi bạn muốn trích xuất các đoạn văn, hãy thêm các lệnh sử dụng sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, xác định dòng có nội dung`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục nơi tài liệu của bạn được lưu trữ.

## Bước 4: Mở tài liệu PDF
 Mở tài liệu PDF hiện có bằng cách sử dụng`Document`constructor và chuyển đường dẫn đến tệp PDF đầu vào.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 5: Trích xuất đoạn văn
 Khởi tạo`ParagraphAbsorber` lớp và sử dụng nó`Visit` phương pháp trích xuất các đoạn văn từ tài liệu.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Bước 6: Lặp lại các đoạn văn
Lặp lại các đoạn văn được trích xuất để truy cập nội dung văn bản. Sử dụng các vòng lặp lồng nhau để duyệt qua các phần và dòng trong mỗi đoạn.

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

### Mã nguồn mẫu cho Trích xuất đoạn văn bằng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Mở tệp PDF hiện có
Document doc = new Document(dataDir + "input.pdf");
// Khởi tạo trình hấp thụ đoạn văn
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
Bạn đã trích xuất thành công các đoạn văn từ tài liệu PDF bằng Aspose.PDF for .NET. Các đoạn trích xuất đã được hiển thị trong cửa sổ bảng điều khiển.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này nhằm mục đích hướng dẫn bạn quy trình trích xuất các đoạn văn từ tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# đi kèm cung cấp các bước thực tế để đạt được nhiệm vụ này.

#### Câu hỏi: Tôi nên nhập những không gian tên nào?

Đáp: Trong tệp mã nơi bạn định trích xuất các đoạn văn, hãy bao gồm các lệnh sử dụng sau ở đầu tệp:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Câu hỏi: Làm cách nào để chỉ định thư mục tài liệu?

 A: Xác định vị trí dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` trong mã và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### Hỏi: Làm cách nào để mở tài liệu PDF hiện có?

 Đáp: Ở Bước 4, bạn sẽ mở tài liệu PDF hiện có bằng cách sử dụng`Document` constructor và cung cấp đường dẫn đến tệp PDF đầu vào.

#### Hỏi: Làm cách nào để trích xuất các đoạn văn từ tài liệu?

 Đáp: Bước 5 liên quan đến việc tạo một phiên bản của`ParagraphAbsorber` lớp và sử dụng nó`Visit` phương pháp trích xuất các đoạn văn từ tài liệu PDF.

#### Hỏi: Làm cách nào để lặp lại các đoạn văn được trích xuất?

Đáp: Bước 6 hướng dẫn bạn lặp lại các đoạn văn được trích xuất. Các vòng lặp lồng nhau được sử dụng để duyệt qua các phần và dòng trong mỗi đoạn văn, cuối cùng là truy cập và hiển thị nội dung văn bản.

#### Hỏi: Điểm mấu chốt rút ra từ hướng dẫn này là gì?

Đáp: Bằng cách làm theo hướng dẫn này, bạn đã học cách trích xuất các đoạn văn từ tài liệu PDF bằng Aspose.PDF cho .NET. Các đoạn được trích xuất đã được hiển thị trong cửa sổ bảng điều khiển, cung cấp cho bạn cái nhìn sâu sắc có giá trị về cấu trúc nội dung của tài liệu.