---
title: Tùy chỉnh số trang trong khi thêm TOC
linktitle: Tùy chỉnh số trang trong khi thêm TOC
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tùy chỉnh số trang trong khi thêm mục lục (TOC) bằng Aspose.PDF cho .NET với ví dụ về mã và hướng dẫn từng bước này.
type: docs
weight: 100
url: /vi/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
Trong hướng dẫn này, chúng ta sẽ khám phá cách tùy chỉnh số trang trong khi thêm mục lục (TOC) bằng Aspose.PDF cho .NET. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với ví dụ về mã để giúp bạn đạt được điều này.

## Bước 1: Tải tệp PDF hiện có

Đầu tiên, chúng ta cần tải một tệp PDF hiện có. Đối với hướng dẫn này, chúng tôi sẽ sử dụng tệp "42824.pdf" nằm trong thư mục "THƯ MỤC TÀI LIỆU CỦA BẠN". Thay thế đường dẫn thư mục này bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Bước 2: Thêm trang TOC

 Tiếp theo, chúng ta cần thêm một trang mới vào đầu tài liệu để đóng vai trò là trang TOC. Chúng ta có thể đạt được điều này bằng cách sử dụng`Insert()` phương pháp của`Pages` bộ sưu tập của`Document` sự vật.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Bước 3: Tạo đối tượng TOC

 Để tạo một đối tượng TOC, trước tiên chúng ta cần tạo một đối tượng`TocInfo` đối tượng và thiết lập các thuộc tính của nó. Trong hướng dẫn này, chúng tôi sẽ đặt tiêu đề của TOC thành "Mục lục" và tiền tố số trang thành "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Bước 4: Tạo mục TOC

Để tạo các mục TOC, chúng ta cần lặp qua tất cả các trang của tài liệu, ngoại trừ trang TOC và tạo đối tượng tiêu đề cho mỗi trang. Sau đó chúng ta có thể thêm đối tượng tiêu đề vào trang TOC và chỉ định trang đích của nó.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Tạo đối tượng Tiêu đề
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Chỉ định trang đích cho đối tượng tiêu đề
    heading2.DestinationPage = doc.Pages[i + 1];
    // Trang đích
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Tọa độ đích
    segment2.Text = "Page " + i.ToString();
    // Thêm tiêu đề vào trang chứa TOC
    tocPage.Paragraphs.Add(heading2);
}
```

## Bước 5: Lưu tài liệu đã cập nhật

Cuối cùng, chúng ta cần lưu tài liệu đã cập nhật vào một tệp mới. Chúng ta có thể đạt được điều này bằng cách sử dụng`Save()` phương pháp của`Document` sự vật.

```csharp
doc.Save(outFile);
```

### Mã nguồn ví dụ để tùy chỉnh số trang trong khi thêm TOC bằng Aspose.PDF cho .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Tải tệp PDF hiện có
Document doc = new Document(inFile);
// Nhận quyền truy cập vào trang đầu tiên của tệp PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Tạo đối tượng thể hiện thông tin TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Đặt tiêu đề cho TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Tạo đối tượng Tiêu đề
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Chỉ định trang đích cho đối tượng tiêu đề
	heading2.DestinationPage = doc.Pages[i + 1];
	// Trang đích
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Tọa độ đích
	segment2.Text = "Page " + i.ToString();
	// Thêm tiêu đề vào trang chứa TOC
	tocPage.Paragraphs.Add(heading2);
}

// Lưu tài liệu đã cập nhật
doc.Save(outFile);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã cung cấp hướng dẫn từng bước về cách tùy chỉnh số trang trong khi thêm TOC bằng Aspose.PDF cho .NET. Chúng tôi cũng đã cung cấp một ví dụ về mã mà bạn có thể sử dụng làm tài liệu tham khảo khi triển khai tính năng này trong

### Câu hỏi thường gặp

#### Câu hỏi: Mục lục (TOC) trong tài liệu PDF là gì?

Đáp: Mục lục (TOC) trong tài liệu PDF là công cụ hỗ trợ điều hướng cung cấp danh sách có tổ chức các phần hoặc chương tài liệu cùng với số trang tương ứng của chúng. Nó cho phép người đọc nhanh chóng điều hướng đến các phần cụ thể trong tài liệu.

#### Hỏi: Tại sao tôi muốn tùy chỉnh số trang trong TOC?

Đáp: Việc tùy chỉnh số trang trong TOC có thể hữu ích khi bạn muốn sử dụng định dạng đánh số trang cụ thể hoặc bao gồm thông tin bổ sung cùng với số trang. Nó cho phép bạn tạo một mục lục mang tính cá nhân hóa và nhiều thông tin hơn.

#### Hỏi: Tôi có thể đưa các siêu liên kết vào TOC để liên kết đến các phần hoặc trang cụ thể trong tài liệu PDF không?

Trả lời: Có, Aspose.PDF for .NET cho phép bạn tạo các siêu liên kết trong TOC liên kết đến các phần hoặc trang cụ thể trong tài liệu PDF. Điều này giúp tăng cường tính tương tác và điều hướng của tài liệu PDF.

#### Câu hỏi: Aspose.PDF cho .NET có tương thích với các tiêu chuẩn PDF/A không?

Đáp: Có, Aspose.PDF for .NET hỗ trợ các tiêu chuẩn PDF/A, bao gồm PDF/A-1, PDF/A-2 và PDF/A-3. Nó cho phép bạn tạo các tài liệu PDF tuân thủ các yêu cầu lưu trữ và bảo quản lâu dài.

#### Câu hỏi: Tôi có thể thêm nhiều định dạng hơn cho các mục TOC, chẳng hạn như kiểu phông chữ hoặc màu sắc không?

Trả lời: Có, bạn có thể thêm định dạng bổ sung cho các mục TOC, chẳng hạn như kiểu phông chữ, màu sắc và kích thước phông chữ bằng cách sử dụng Aspose.PDF cho .NET. Điều này cho phép bạn tùy chỉnh giao diện của TOC theo yêu cầu của bạn.
