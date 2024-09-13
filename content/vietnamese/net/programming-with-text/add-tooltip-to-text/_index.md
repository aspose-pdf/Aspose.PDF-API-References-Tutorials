---
title: Thêm chú giải công cụ vào văn bản trong tệp PDF
linktitle: Thêm chú giải công cụ vào văn bản trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm chú giải công cụ vào văn bản trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 90
url: /vi/net/programming-with-text/add-tooltip-to-text/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm chú giải công cụ vào văn bản trong tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn thêm chú giải công cụ vào văn bản, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Tạo một tài liệu mẫu có văn bản
 Tạo một cái mới`Document`đối tượng và thêm các trang có đoạn văn bản. Trong mã được cung cấp, hai đoạn văn bản được thêm vào tài liệu với văn bản chú giải công cụ tương ứng.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Bước 5: Mở tài liệu và tìm các đoạn văn bản
 Tải tài liệu đã tạo bằng cách sử dụng`Document` constructor và tìm các đoạn văn bản cần chú giải công cụ bằng cách sử dụng`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Bước 6: Thêm chú giải công cụ vào các đoạn văn bản
 Lặp qua các đoạn văn bản đã trích xuất và tạo các nút vô hình tại vị trí của chúng. Gán văn bản chú giải công cụ mong muốn cho`AlternateName` tài sản của`ButtonField`. Thêm các trường nút vào biểu mẫu của tài liệu.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Bước 7: Lặp lại cho các đoạn văn bản bổ sung có chú giải công cụ dài
Lặp lại bước 5 và 6 cho các đoạn văn bản có chú giải công cụ dài. Sửa đổi tiêu chí tìm kiếm và văn bản chú giải công cụ cho phù hợp.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Bước 8: Lưu tài liệu đã sửa đổi
 Lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
document. Save(outputFile);
```

### Mã nguồn mẫu để Thêm chú giải công cụ vào văn bản bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Tạo tài liệu mẫu có văn bản
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Mở tài liệu có văn bản
Document document = new Document(outputFile);
//Tạo đối tượng TextAbsorber để tìm tất cả các cụm từ khớp với biểu thức chính quy
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Chấp nhận bộ hấp thụ cho các trang tài liệu
document.Pages.Accept(absorber);
// Lấy các đoạn văn bản đã trích xuất
TextFragmentCollection textFragments = absorber.TextFragments;
// Lặp lại các đoạn
foreach (TextFragment fragment in textFragments)
{
	// Tạo nút vô hình trên vị trí đoạn văn bản
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Giá trị AlternateName sẽ được hiển thị dưới dạng chú giải công cụ bởi ứng dụng trình xem
	field.AlternateName = "Tooltip for text.";
	// Thêm trường nút vào tài liệu
	document.Form.Add(field);
}
// Tiếp theo sẽ là mẫu của tooltip rất dài
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Đặt văn bản rất dài
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Lưu tài liệu
document.Save(outputFile);
```

## Phần kết luận
Bạn đã thêm thành công chú giải công cụ vào văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

## Câu hỏi thường gặp

#### H: Trọng tâm của hướng dẫn này là gì?

A: Hướng dẫn này tập trung vào việc thêm chú giải công cụ vào văn bản trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết để thực hiện việc này.

#### H: Những không gian tên nào cần được nhập cho hướng dẫn này?

A: Trong tệp mã mà bạn muốn thêm chú giải công cụ vào văn bản, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Trong mã, tìm dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào tôi có thể tạo một tài liệu mẫu có văn bản?

 A: Ở Bước 4, bạn sẽ tạo một`Document` đối tượng và thêm các trang có đoạn văn bản. Mã được cung cấp sẽ thêm hai đoạn văn bản có văn bản chú giải công cụ tương ứng.

#### H: Làm thế nào để mở tài liệu và tìm các đoạn văn bản?

 A: Ở Bước 5, bạn sẽ tải tài liệu đã tạo bằng cách sử dụng`Document` constructor và tìm các đoạn văn bản yêu cầu chú giải công cụ bằng cách sử dụng`TextFragmentAbsorber`.

#### H: Làm thế nào để thêm chú giải công cụ vào đoạn văn bản?

 A: Ở Bước 6, bạn sẽ lặp qua các đoạn văn bản đã trích xuất và tạo các nút vô hình tại vị trí của chúng. Văn bản chú giải công cụ được gán cho`AlternateName` tài sản của`ButtonField`, được thêm vào mẫu của tài liệu.

#### H: Làm thế nào để lặp lại quy trình này cho các đoạn văn bản bổ sung có chú giải công cụ dài?

A: Đối với các đoạn văn bản có chú giải công cụ dài, hãy lặp lại Bước 5 và 6. Sửa đổi tiêu chí tìm kiếm và văn bản chú giải công cụ cho phù hợp.

#### H: Làm thế nào để lưu tài liệu đã chỉnh sửa?

 A: Ở Bước 8, bạn sẽ lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### H: Nội dung chính rút ra từ hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học cách cải thiện tài liệu PDF của mình bằng cách thêm chú giải công cụ vào văn bản bằng Aspose.PDF cho .NET. Điều này có thể cung cấp thông tin bổ sung có giá trị cho người đọc khi họ tương tác với nội dung PDF.