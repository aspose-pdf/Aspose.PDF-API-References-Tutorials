---
title: Ẩn số trang trong TOC
linktitle: Ẩn số trang trong TOC
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách ẩn số trang trong mục lục bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 220
url: /vi/net/programming-with-document/hidepagenumbersintoc/
---
Trong bài viết này, chúng ta sẽ thảo luận về việc triển khai tính năng Ẩn số trang trong TOC của Aspose.PDF cho .NET bằng C#. Chúng tôi sẽ bắt đầu bằng phần giới thiệu ngắn gọn về Aspose.PDF cho .NET và sau đó đi sâu vào hướng dẫn từng bước để triển khai tính năng này. 

## Giới thiệu về Aspose.PDF cho .NET

Aspose.PDF for .NET là một thành phần thao tác PDF mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và thao tác với các tệp PDF theo chương trình. Nó cung cấp nhiều tính năng và chức năng giúp bạn dễ dàng làm việc với các tài liệu PDF. Aspose.PDF for .NET hỗ trợ cả hệ điều hành 32 bit và 64 bit và có thể được sử dụng với các nền tảng .NET Framework, .NET Core và Xamarin. 

## Tính năng Ẩn số trang trong TOC là gì?

Mục lục (TOC) là một phần thiết yếu của tài liệu PDF cung cấp cho người dùng cái nhìn tổng quan nhanh chóng về nội dung. Đôi khi, người dùng có thể muốn ẩn số trang trong TOC để thân thiện hơn với người dùng. Aspose.PDF for .NET cung cấp tính năng tích hợp sẵn để ẩn số trang trong TOC. Tính năng này có thể được sử dụng để tạo các tài liệu PDF thân thiện hơn với người dùng. 

## Điều kiện tiên quyết

Để làm theo hướng dẫn này, bạn sẽ cần những điều sau:

- Visual Studio 2010 trở lên
- Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn
- Kiến thức cơ bản về ngôn ngữ lập trình C#

## Hướng dẫn từng bước triển khai tính năng Ẩn số trang trong TOC

Thực hiện theo các bước bên dưới để triển khai tính năng Ẩn số trang trong TOC bằng Aspose.PDF cho .NET:

## Bước 1: Tạo ứng dụng bảng điều khiển C# mới trong Visual Studio

Mở Visual Studio và tạo ứng dụng bảng điều khiển C# mới.

## Bước 2: Thêm tham chiếu vào Aspose.PDF cho .NET

Nhấp chuột phải vào thư mục Tài liệu tham khảo trong dự án của bạn và chọn Thêm tài liệu tham khảo. Duyệt đến vị trí cài đặt Aspose.PDF for .NET trên hệ thống của bạn và thêm tham chiếu đến nó.

## Bước 1: Tạo một tài liệu PDF mới

Tạo một tài liệu PDF mới bằng mã sau:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Bước 2: Tạo trang TOC

Tạo một trang mới cho TOC và thêm nó vào tài liệu PDF bằng mã sau:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Bước 3: Thêm phần danh sách vào bộ sưu tập phần của tài liệu PDF

Thêm phần danh sách vào bộ sưu tập phần của tài liệu PDF bằng mã sau:

```csharp
tocPage.TocInfo = tocInfo;
```

## Bước 4: Xác định định dạng của danh sách bốn cấp độ

Xác định định dạng của danh sách bốn cấp độ bằng cách đặt lề trái và cài đặt định dạng văn bản của từng cấp độ bằng mã sau:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Bước 5: Thêm bốn tiêu đề trong phần

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Mã nguồn ví dụ để ẩn số trang trong TOC bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Thêm phần danh sách vào bộ sưu tập phần của tài liệu Pdf
tocPage.TocInfo = tocInfo;
//Xác định định dạng của danh sách bốn cấp độ bằng cách đặt lề trái và
//cài đặt định dạng văn bản của từng cấp độ

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Thêm bốn tiêu đề trong phần
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách làm việc với siêu dữ liệu XMP trong tài liệu PDF bằng Aspose.PDF cho .NET. Siêu dữ liệu XMP cung cấp thông tin có giá trị về tài liệu PDF, bao gồm tiêu đề, tác giả, ngày tạo, v.v. Aspose.PDF for .NET cho phép các nhà phát triển truy cập và thao tác siêu dữ liệu này, cung cấp API linh hoạt và mạnh mẽ để làm việc với các tài liệu PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Siêu dữ liệu XMP trong tài liệu PDF là gì?

Đáp: Siêu dữ liệu XMP (Nền tảng siêu dữ liệu mở rộng) trong tài liệu PDF là định dạng chuẩn để lưu trữ thông tin siêu dữ liệu về tài liệu. Nó bao gồm các chi tiết như tiêu đề tài liệu, tác giả, ngày tạo, từ khóa, v.v. Siêu dữ liệu XMP cung cấp một cách có cấu trúc và tiêu chuẩn hóa để lưu trữ và chia sẻ thông tin về tài liệu PDF.

#### Câu hỏi: Tôi có thể sửa đổi siêu dữ liệu XMP của tài liệu PDF bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể sửa đổi siêu dữ liệu XMP của tài liệu PDF theo chương trình bằng cách sử dụng Aspose.PDF cho .NET. Bạn có thể truy cập`Info` tài sản của`Document` đối tượng, cho phép bạn truy cập vào các thuộc tính siêu dữ liệu XMP. Sau đó, bạn có thể cập nhật giá trị của các thuộc tính này để sửa đổi siêu dữ liệu XMP của tài liệu PDF.

#### Câu hỏi: Tôi có thể trích xuất các thuộc tính siêu dữ liệu XMP tùy chỉnh từ tài liệu PDF bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể trích xuất các thuộc tính siêu dữ liệu XMP tùy chỉnh từ tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể dùng`Metadata` tài sản của`Document`đối tượng, cung cấp quyền truy cập vào tất cả các thuộc tính siêu dữ liệu XMP của tài liệu PDF. Sau đó, bạn có thể trích xuất các thuộc tính tùy chỉnh và sử dụng giá trị của chúng nếu cần.