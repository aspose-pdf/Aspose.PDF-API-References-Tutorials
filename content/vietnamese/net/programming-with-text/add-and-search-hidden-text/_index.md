---
title: Thêm và tìm kiếm văn bản ẩn trong tệp PDF
linktitle: Thêm và tìm kiếm văn bản ẩn trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để thêm và tìm kiếm văn bản ẩn trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 20
url: /vi/net/programming-with-text/add-and-search-hidden-text/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thêm và tìm kiếm văn bản ẩn trong tệp PDF bằng Aspose.PDF cho .NET. Thực hiện theo các bước sau để thực hiện thao tác này một cách dễ dàng.

## 1. Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Cài đặt và cấu hình Visual Studio hoặc bất kỳ môi trường phát triển nào khác.
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET đã được cài đặt. Bạn có thể tải xuống từ trang web chính thức của Aspose.

## 2. Tạo tài liệu PDF có văn bản ẩn

Để bắt đầu, hãy sử dụng mã sau để tạo một tài liệu PDF mới có chứa văn bản ẩn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Tạo một tài liệu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Đặt thuộc tính văn bản - vô hình
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Hãy đảm bảo cung cấp đường dẫn và tên tệp mong muốn cho tài liệu PDF.

## 3. Tìm kiếm văn bản trong tài liệu

Tiếp theo, chúng ta sẽ tìm kiếm văn bản ẩn trong tài liệu PDF. Sử dụng mã sau:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Làm gì đó với các mảnh vỡ
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Tính năng này sẽ tìm kiếm văn bản ẩn trong trang thứ hai của tài liệu PDF và hiển thị thông tin có liên quan.

### Mã nguồn mẫu cho Thêm và Tìm kiếm Văn bản Ẩn bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Tạo tài liệu có văn bản ẩn
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Đặt thuộc tính văn bản - vô hình
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Tìm kiếm văn bản trong tài liệu
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Làm gì đó với các mảnh vỡ
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Phần kết luận

Xin chúc mừng! Bạn đã thêm và tìm thấy văn bản ẩn trong tài liệu PDF thành công bằng Aspose.PDF cho .NET. Bây giờ bạn có thể áp dụng phương pháp này vào các dự án của riêng mình để thao tác và tìm kiếm văn bản ẩn trong tệp PDF.

### Câu hỏi thường gặp

#### H: Aspose.PDF dành cho .NET là gì?

A: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi các tài liệu PDF trong các ứng dụng .NET.

#### H: Có thể sử dụng văn bản ẩn để thêm hình mờ không?

A: Hoàn toàn đúng! Văn bản ẩn có thể là phương tiện hiệu quả để đóng dấu bản quyền tài liệu PDF, tăng thêm một lớp bảo mật.

#### H: Có thể hiển thị văn bản ẩn trong tài liệu PDF không?

A: Có, quá trình tìm kiếm và hiển thị văn bản ẩn trong tài liệu PDF có thể thực hiện được bằng các kỹ thuật được nêu trong hướng dẫn này.

#### H: Aspose.PDF for .NET còn cung cấp những chức năng nào khác?

A: Ngoài chức năng chỉnh sửa văn bản ẩn, Aspose.PDF cho .NET còn cung cấp nhiều tính năng khác, bao gồm tạo PDF, chuyển đổi, mã hóa, v.v.