---
title: Tùy chỉnh Tab dừng trong tệp PDF
linktitle: Tùy chỉnh Tab dừng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo điểm dừng tab tùy chỉnh trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 120
url: /vi/net/programming-with-text/custom-tab-stops/
---

Hướng dẫn này sẽ hướng dẫn bạn quy trình tạo các điểm dừng tab tùy chỉnh trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn tạo điểm dừng tab tùy chỉnh, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Tạo một phiên bản Tài liệu mới
 Khởi tạo một cái mới`Document` đối tượng bằng cách thêm dòng mã sau:

```csharp
Document _pdfdocument = new Document();
```

## Bước 5: Thêm một trang vào tài liệu
 Thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập. Trong mã được cung cấp, trang mới được gán cho biến`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Bước 6: Tạo các điểm dừng tab tùy chỉnh
 Tạo một`TabStops` đối tượng và thêm các điểm dừng tab tùy chỉnh vào đó. Đặt loại căn chỉnh và loại đường dẫn cho mỗi điểm dừng tab.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Bước 7: Tạo các đoạn văn bản có điểm dừng tab
 Tạo nên`TextFragment` đối tượng và chuyển các điểm dừng tab tùy chỉnh cho chúng. Sử dụng các ký tự đặc biệt`#$TAB` để chỉ ra các điểm dừng tab trong văn bản.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Bước 8: Lưu tài liệu PDF
 Lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu cho Tab Stop tùy chỉnh sử dụng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Bạn đã tạo thành công một tài liệu PDF với các điểm dừng tab tùy chỉnh bằng Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Trọng tâm của hướng dẫn này là gì?

A: Hướng dẫn này tập trung vào việc hướng dẫn bạn thực hiện quy trình tạo các điểm dừng tab tùy chỉnh trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết để thực hiện việc này.

#### H: Tôi nên nhập những không gian tên nào cho hướng dẫn này?

A: Trong tệp mã mà bạn muốn tạo điểm dừng tab tùy chỉnh, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để tạo một phiên bản Tài liệu mới?

 A: Ở Bước 4, bạn sẽ tạo một phiên bản mới`Document` đối tượng sử dụng mã được cung cấp.

#### H: Làm thế nào để thêm trang vào tài liệu?

 A: Ở Bước 5, bạn sẽ thêm một trang mới vào tài liệu bằng cách sử dụng`Add` phương pháp của`Pages` bộ sưu tập.

#### H: Làm thế nào để tạo điểm dừng tab tùy chỉnh?

 A: Ở Bước 6, bạn sẽ tạo một`TabStops` đối tượng và thêm các điểm dừng tab tùy chỉnh vào đó. Bạn cũng sẽ thiết lập kiểu căn chỉnh và đường dẫn cho mỗi điểm dừng tab.

#### H: Làm thế nào để tạo các đoạn văn bản có điểm dừng tab?

 A: Ở Bước 7, bạn sẽ tạo`TextFragment` đối tượng và chuyển các điểm dừng tab tùy chỉnh cho chúng. Bạn sẽ sử dụng các ký tự đặc biệt`#$TAB` để chỉ ra các điểm dừng tab trong văn bản.

#### H: Làm thế nào để lưu tài liệu PDF?

 A: Ở Bước 8, bạn sẽ lưu tài liệu PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### H: Nội dung chính rút ra từ hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo tài liệu PDF với các điểm dừng tab tùy chỉnh bằng Aspose.PDF cho .NET. Điều này có thể hữu ích để sắp xếp và căn chỉnh văn bản theo cách có cấu trúc.