---
title: Thêm TOC vào tệp PDF
linktitle: Thêm TOC vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm mục lục vào tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với mã nguồn ví dụ. Tăng cường điều hướng tài liệu!
type: docs
weight: 40
url: /vi/net/programming-with-document/addtoc/
---
Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng tính năng Thêm TOC (Mục lục) vào tệp PDF của Aspose.PDF cho .NET để thêm mục lục vào tài liệu PDF. Chúng tôi sẽ cung cấp hướng dẫn từng bước và giải thích mã nguồn C# cần thiết để đạt được điều này. Đến cuối hướng dẫn này, bạn sẽ có thể tạo tài liệu PDF có mục lục bằng Aspose.PDF cho .NET.


## Bước 1: Tải tệp PDF hiện có

 Để bắt đầu, chúng ta cần tải một tệp PDF hiện có. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong đoạn mã sau với đường dẫn thực tế tới tệp PDF của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Bước 2: Tạo trang mới cho mục lục

Chúng ta sẽ tạo một trang mới để chứa mục lục. Đoạn mã sau chèn một trang mới vào chỉ mục 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Bước 3: Xác định thông tin mục lục

Tiếp theo, chúng ta cần xác định thông tin mục lục. Chúng ta sẽ đặt tiêu đề và các thuộc tính khác của mục lục. Thêm mã sau đây:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Bước 4: Tạo phần tử TOC

Bây giờ, chúng ta sẽ tạo các thành phần của mục lục. Trong hướng dẫn này, chúng tôi sẽ tạo bốn phần tử TOC tương ứng với các trang khác nhau. Sửa đổi mã sau theo yêu cầu của bạn:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Bước 5: Lưu tài liệu đã cập nhật

 Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi cùng với mục lục. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong đoạn mã bên dưới với đường dẫn tệp đầu ra mong muốn:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để thêm TOC vào tài liệu PDF bằng Aspose.PDF for .NET

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tệp PDF hiện có
Document doc = new Document(dataDir + "AddTOC.pdf");

// Nhận quyền truy cập vào trang đầu tiên của tệp PDF
Page tocPage = doc.Pages.Insert(1);

// Tạo đối tượng thể hiện thông tin TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Đặt tiêu đề cho TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Tạo các đối tượng chuỗi sẽ được sử dụng làm phần tử TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Tạo đối tượng Tiêu đề
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Chỉ định trang đích cho đối tượng tiêu đề
	heading2.DestinationPage = doc.Pages[i + 2];

	// Trang đích
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Tọa độ đích
	segment2.Text = titles[i];

	// Thêm tiêu đề vào trang chứa TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Lưu tài liệu đã cập nhật
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách thêm mục lục (TOC) vào tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng tạo tài liệu PDF có mục lục. TOC nâng cao khả năng sử dụng của tài liệu, cho phép người dùng điều hướng đến các phần hoặc trang cụ thể hiệu quả hơn. Aspose.PDF for .NET cung cấp giải pháp mạnh mẽ và thân thiện với người dùng để làm việc với các tệp PDF trong các ứng dụng .NET, cho phép bạn tạo các tài liệu PDF động và tương tác một cách dễ dàng.

### Câu hỏi thường gặp về thêm TOC vào tệp PDF

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Trả lời: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PDF trong ứng dụng .NET một cách hiệu quả. Nó cung cấp nhiều tính năng để tạo, thao tác và quản lý tài liệu PDF theo chương trình.

#### Hỏi: Mục đích của việc thêm mục lục (TOC) vào tài liệu PDF là gì?

Đáp: Mục lục (TOC) cung cấp công cụ hỗ trợ điều hướng cho người dùng, cho phép họ nhanh chóng chuyển đến các phần hoặc trang cụ thể trong tài liệu PDF. Nó cải thiện khả năng sử dụng của tài liệu và trải nghiệm người dùng.

#### Câu hỏi: Làm cách nào để thêm mục lục vào tài liệu PDF bằng Aspose.PDF cho .NET?

Trả lời: Để thêm mục lục vào tài liệu PDF bằng Aspose.PDF cho .NET, bạn cần tạo một trang mới để giữ TOC, xác định thông tin mục lục và sau đó tạo các phần tử TOC tương ứng với các trang cụ thể hoặc các phần trong tài liệu.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của mục lục không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của mục lục bằng cách đặt các thuộc tính khác nhau của các thành phần TOC, chẳng hạn như kích thước phông chữ, kiểu phông chữ và căn chỉnh. Aspose.PDF for .NET mang đến sự linh hoạt trong việc thiết kế TOC để phù hợp với giao diện mong muốn của bạn.

#### Câu hỏi: Aspose.PDF cho .NET có phù hợp để thêm các tính năng nâng cao vào tài liệu PDF không?

Đáp: Hoàn toàn có thể, Aspose.PDF for .NET là một thư viện giàu tính năng cho phép bạn thêm các chức năng nâng cao vào tài liệu PDF, bao gồm các phần tử tương tác, trường biểu mẫu, chữ ký số, v.v.