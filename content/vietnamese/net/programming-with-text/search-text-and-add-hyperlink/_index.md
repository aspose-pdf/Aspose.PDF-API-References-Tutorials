---
title: Tìm kiếm văn bản và thêm siêu liên kết
linktitle: Tìm kiếm văn bản và thêm siêu liên kết
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tìm kiếm văn bản trong PDF, thêm siêu liên kết vào văn bản tìm thấy và lưu tài liệu đã sửa đổi bằng Aspose.PDF cho .NET.
type: docs
weight: 450
url: /vi/net/programming-with-text/search-text-and-add-hyperlink/
---
Hướng dẫn này giải thích cách sử dụng Aspose.PDF cho .NET để tìm kiếm văn bản cụ thể trong tài liệu PDF, thêm siêu liên kết đến văn bản tìm thấy và lưu tài liệu đã sửa đổi. Mã nguồn C# được cung cấp trình bày quy trình từng bước.

## Điều kiện tiên quyết

Trước khi thực hiện hướng dẫn, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc sử dụng NuGet để cài đặt vào dự án của bạn.

## Bước 1: Thiết lập dự án

Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) mà bạn thích và thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết

Thêm lệnh using sau vào đầu tệp C# của bạn để nhập các không gian tên cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Bước 3: Đặt đường dẫn đến thư mục tài liệu

 Đặt đường dẫn đến thư mục tài liệu của bạn bằng cách sử dụng`dataDir` biến:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 4: Tạo TextFragmentAbsorber

 Tạo một`TextFragmentAbsorber` đối tượng để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Thay thế`"\\d{4}-\\d{4}"` với mẫu biểu thức chính quy bạn mong muốn.

## Bước 5: Bật tìm kiếm biểu thức chính quy

 Cho phép tìm kiếm biểu thức chính quy bằng cách thiết lập`TextSearchOptions` Tính chất của chất hấp thụ:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Bước 6: Mở và đóng tài liệu PDF

 Tạo một`PdfContentEditor` đối tượng và liên kết nó với tệp PDF nguồn:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Thay thế`"SearchRegularExpressionPage.pdf"` bằng tên thực của tệp PDF của bạn.

## Bước 7: Chấp nhận bộ hấp thụ cho trang

Chấp nhận bộ hấp thụ cho trang mong muốn của tài liệu:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Thay thế`1` với số trang mong muốn.

## Bước 8: Thêm siêu liên kết vào văn bản tìm thấy

Lặp qua các đoạn văn bản đã lấy được và thêm siêu liên kết vào chúng:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Tạo một hình chữ nhật dựa trên vị trí của đoạn văn bản
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Thêm liên kết web vào hình chữ nhật
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.draw.Color.Blue);
}
```

 Thay thế`"http://www.aspose.com"` với URL siêu liên kết mong muốn.

## Bước 9: Lưu và đóng tài liệu đã sửa đổi

Lưu tài liệu đã sửa đổi và đóng trình soạn thảo:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Hãy chắc chắn thay thế`"SearchTextAndAddHyperlink_out.pdf"` với tên tập tin đầu ra mong muốn.

### Mã nguồn mẫu cho Tìm kiếm văn bản và thêm siêu liên kết bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tạo đối tượng hấp thụ để tìm tất cả các trường hợp của cụm từ tìm kiếm đầu vào
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Bật tìm kiếm biểu thức chính quy
absorber.TextSearchOptions = new TextSearchOptions(true);
// Mở tài liệu
PdfContentEditor editor = new PdfContentEditor();
// Liên kết tệp PDF nguồn
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Chấp nhận bộ hấp thụ cho trang
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Lặp lại các đoạn
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, màu xanh, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách tìm kiếm văn bản cụ thể trong tài liệu PDF, thêm siêu liên kết vào văn bản đã tìm thấy và lưu tài liệu đã sửa đổi bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước, từ thiết lập dự án đến thực hiện các hành động cần thiết. Bây giờ bạn có thể kết hợp mã này vào các dự án C# của riêng mình để thao tác văn bản và thêm siêu liên kết vào tệp PDF.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Tìm kiếm văn bản và thêm siêu liên kết" là gì?

A: Hướng dẫn "Tìm kiếm văn bản và thêm siêu liên kết" nhằm mục đích chứng minh cách sử dụng thư viện Aspose.PDF cho .NET để tìm kiếm văn bản cụ thể trong tài liệu PDF, thêm siêu liên kết vào văn bản tìm thấy và sau đó lưu tài liệu đã sửa đổi. Hướng dẫn cung cấp hướng dẫn toàn diện và các mẫu mã C# để minh họa quy trình từng bước.

#### H: Hướng dẫn này giúp ích gì khi thêm siêu liên kết vào văn bản cụ thể trong tài liệu PDF?

A: Hướng dẫn này hướng dẫn bạn quy trình sử dụng thư viện Aspose.PDF để định vị văn bản cụ thể trong tài liệu PDF, áp dụng siêu liên kết đến văn bản đã xác định và lưu PDF đã sửa đổi. Hướng dẫn này bao gồm các bước thiết yếu như thiết lập dự án, tải tài liệu, bật tìm kiếm biểu thức chính quy và thêm siêu liên kết vào văn bản đã tìm thấy.

#### H: Cần có những điều kiện tiên quyết nào để làm theo hướng dẫn này?

A: Trước khi bắt đầu, bạn nên có hiểu biết cơ bản về ngôn ngữ lập trình C#. Ngoài ra, bạn cần cài đặt thư viện Aspose.PDF cho .NET, có thể tải xuống từ trang web Aspose hoặc cài đặt bằng NuGet trong dự án của bạn.

#### H: Tôi phải thiết lập dự án của mình như thế nào để thực hiện theo hướng dẫn này?

A: Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển tích hợp (IDE) ưa thích của bạn. Sau đó, thêm tham chiếu đến thư viện Aspose.PDF cho .NET, cho phép bạn sử dụng các khả năng của thư viện trong dự án của mình.

#### H: Tôi có thể thêm siêu liên kết vào văn bản cụ thể bằng hướng dẫn này không?

A: Có, hướng dẫn này tập trung cụ thể vào việc thêm siêu liên kết vào văn bản cụ thể trong tài liệu PDF. Nó trình bày cách tìm và trích xuất văn bản mong muốn bằng cách sử dụng biểu thức chính quy, tạo siêu liên kết liên kết với các đoạn văn bản và lưu PDF đã sửa đổi.

#### H: Làm thế nào để xác định văn bản tôi muốn tìm kiếm và thêm siêu liên kết vào?

 A: Để chỉ định văn bản bạn muốn tìm kiếm và thêm siêu liên kết vào, hãy tạo`TextFragmentAbsorber` đối tượng và thiết lập mẫu của nó bằng cách sử dụng`Text` tham số. Thay thế mẫu mặc định`"\\d{4}-\\d{4}"` trong mã hướng dẫn với mẫu biểu thức chính quy mong muốn của bạn.

#### H: Làm thế nào tôi có thể bật tìm kiếm biểu thức chính quy cho văn bản?

 A: Tìm kiếm biểu thức chính quy được kích hoạt bằng cách tạo một`TextSearchOptions` đối tượng và thiết lập giá trị của nó thành`true` . Gán đối tượng này cho`TextSearchOptions` tài sản của`TextFragmentAbsorber` Ví dụ. Điều này đảm bảo rằng mẫu biểu thức chính quy được áp dụng trong quá trình tìm kiếm văn bản.

#### H: Làm thế nào để thêm siêu liên kết vào văn bản tìm thấy?

 A: Sau khi xác định các đoạn văn bản bằng cách sử dụng`TextFragmentAbsorber` , hướng dẫn cung cấp một vòng lặp để lặp qua các đoạn văn bản này. Đối với mỗi đoạn văn bản, hướng dẫn trình bày cách đặt màu văn bản thành màu xanh lam và tạo siêu liên kết bằng cách sử dụng`CreateWebLink` phương pháp.

#### H: Các bước để lưu tệp PDF đã chỉnh sửa có chứa siêu liên kết là gì?

 A: Sau khi thêm siêu liên kết vào các đoạn văn bản mong muốn, hãy sử dụng`PdfContentEditor` lớp để lưu tài liệu đã chỉnh sửa. Mã mẫu của hướng dẫn trình bày cách lưu PDF đã chỉnh sửa, đóng trình chỉnh sửa và hiển thị thông báo thành công.