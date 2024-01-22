---
title: Đánh dấu ký tự trong tệp PDF
linktitle: Đánh dấu ký tự trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đánh dấu các ký tự trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 240
url: /vi/net/programming-with-text/highlight-character-in-pdf/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách đánh dấu các ký tự trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng ta sẽ thực hiện quy trình từng bước đánh dấu các ký tự trong tệp PDF bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Trước tiên, bạn cần đặt đường dẫn đến thư mục chứa tệp PDF đầu vào của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến bằng đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu PDF

 Tiếp theo, chúng tôi tải tài liệu PDF đầu vào bằng cách sử dụng`Aspose.Pdf.Document` lớp học.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Bước 3: Chuyển đổi PDF thành hình ảnh

 Để làm nổi bật các ký tự, chúng tôi chuyển đổi tài liệu PDF thành hình ảnh bằng cách sử dụng`PdfConverter` lớp học. Chúng tôi đặt độ phân giải cho chuyển đổi và truy xuất hình ảnh dưới dạng`Bitmap` sự vật.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Bước 4: Đánh dấu nhân vật

 Chúng tôi lặp qua từng trang của tài liệu PDF và sử dụng một`TextFragmentAbsorber` đối tượng để tìm tất cả các từ trong trang. Sau đó, chúng tôi lặp lại các đoạn văn bản, phân đoạn và ký tự để đánh dấu chúng bằng hình chữ nhật.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Đặt tỷ lệ và chuyển đổi
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Lặp qua các trang
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Tìm tất cả các từ trong trang
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Lặp qua các đoạn văn bản
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Làm nổi bật các ký tự
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Lặp qua các phân đoạn
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Đánh dấu đoạn
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Lặp qua các ký tự
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // nhân vật nổi bật
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Bước 5: Lưu hình ảnh đầu ra

Cuối cùng, chúng tôi lưu hình ảnh đã sửa đổi có các ký tự được đánh dấu vào tệp đầu ra được chỉ định.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Mã nguồn mẫu cho Ký tự nổi bật trong PDF bằng Aspose.PDF for .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Tạo đối tượng TextAbsorber để tìm tất cả các từ
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Lấy các đoạn văn bản được trích xuất
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Lặp lại các mảnh vỡ
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đánh dấu các ký tự trong tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể đánh dấu các ký tự trong tệp PDF và lưu kết quả đầu ra dưới dạng hình ảnh.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Đánh dấu ký tự trong tệp PDF" là gì?

Đáp: Hướng dẫn "Đánh dấu ký tự trong tệp PDF" giải thích cách sử dụng thư viện Aspose.PDF cho .NET để đánh dấu các ký tự trong tài liệu PDF. Hướng dẫn này cung cấp hướng dẫn từng bước và mã nguồn C# để đạt được điều này.

#### Hỏi: Tại sao tôi muốn đánh dấu các ký tự trong tài liệu PDF?

Đáp: Việc đánh dấu các ký tự trong tài liệu PDF có thể hữu ích cho nhiều mục đích khác nhau, chẳng hạn như nhấn mạnh nội dung cụ thể hoặc làm cho văn bản nhất định hiển thị và dễ phân biệt hơn.

#### Hỏi: Làm cách nào để thiết lập thư mục tài liệu?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến có đường dẫn đến thư mục chứa tệp PDF đầu vào của bạn.

#### Hỏi: Làm cách nào để tải tài liệu PDF và chuyển đổi nó thành hình ảnh?

 A: Trong phần hướng dẫn,`Aspose.Pdf.Document` lớp được sử dụng để tải tài liệu PDF đầu vào. Sau đó,`PdfConverter` lớp được sử dụng để chuyển đổi tài liệu PDF thành hình ảnh. Độ phân giải của hình ảnh được đặt và hình ảnh được truy xuất dưới dạng`Bitmap` sự vật.

#### Hỏi: Làm cách nào để đánh dấu các ký tự trong hình ảnh tài liệu PDF?

Đáp: Hướng dẫn này hướng dẫn bạn qua quy trình lặp qua từng trang của tài liệu PDF, tìm từ bằng cách sử dụng một`TextFragmentAbsorber`và lặp qua các đoạn văn bản, phân đoạn và ký tự để đánh dấu chúng bằng hình chữ nhật.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của các ký tự và phân đoạn được đánh dấu không?

Đáp: Có, bạn có thể tùy chỉnh hình thức của các ký tự và đoạn được đánh dấu bằng cách sửa đổi màu sắc và kiểu dáng được sử dụng trong các thao tác vẽ.

#### Hỏi: Làm cách nào để lưu hình ảnh đã sửa đổi với các ký tự được đánh dấu?

 Đáp: Hướng dẫn trình bày cách lưu hình ảnh đã sửa đổi với các ký tự được tô sáng vào tệp đầu ra được chỉ định bằng cách sử dụng`Save` phương pháp của`Bitmap` lớp học.

#### Câu hỏi: Có cần phải có Giấy phép Aspose hợp lệ cho hướng dẫn này không?

Trả lời: Có, cần có Giấy phép Aspose hợp lệ để hướng dẫn này hoạt động chính xác. Bạn có thể mua giấy phép đầy đủ hoặc lấy giấy phép tạm thời 30 ngày từ trang web Aspose.