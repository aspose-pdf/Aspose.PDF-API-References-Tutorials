---
title: Thêm văn bản với màu đổ bóng trong tệp PDF
linktitle: Thêm văn bản với màu đổ bóng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm văn bản có tô màu vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 80
url: /vi/net/programming-with-text/add-text-with-shading-colors/
---
Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm văn bản có màu đổ bóng vào tệp PDF bằng Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết.

## Yêu cầu
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ trình biên dịch C# nào khác được cài đặt trên máy của bạn.
- Aspose.PDF cho thư viện .NET. Bạn có thể tải xuống từ trang web chính thức của Aspose hoặc sử dụng trình quản lý gói như NuGet để cài đặt.

## Bước 1: Thiết lập dự án
1. Tạo một dự án C# mới trong môi trường phát triển mà bạn thích.
2. Thêm tham chiếu đến thư viện Aspose.PDF cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong tệp mã mà bạn muốn thêm văn bản có màu đổ bóng, hãy thêm lệnh using sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Bước 3: Thiết lập thư mục tài liệu
 Trong mã, hãy xác định vị trí dòng ghi`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục lưu trữ tài liệu của bạn.

## Bước 4: Tải tài liệu PDF
 Tải tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và cung cấp đường dẫn đến tệp tài liệu.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Mã nằm ở đây...
}
```

## Bước 5: Tìm văn bản để sửa đổi
 Sử dụng`TextFragmentAbsorber` để tìm văn bản mong muốn trong tài liệu. Trong mã được cung cấp, nó sẽ tìm kiếm văn bản "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Bước 6: Thiết lập màu đổ bóng cho văn bản
 Tạo một cái mới`Color` đối tượng có không gian màu mẫu và chỉ định màu đổ bóng gradient. Gán màu này cho`ForegroundColor` tài sản của`TextState` của`TextFragment` sự vật.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Bước 7: Áp dụng định dạng văn bản bổ sung (tùy chọn)
 Bạn có thể áp dụng định dạng bổ sung cho đoạn văn bản, chẳng hạn như gạch chân, bằng cách sửa đổi các thuộc tính của`TextState` sự vật.

```csharp
textFragment.TextState.Underline = true;
```

## Bước 8: Lưu tài liệu PDF đã sửa đổi
 Lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Mã nguồn mẫu cho Thêm văn bản có màu đổ bóng bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Tạo màu mới với không gian màu mẫu
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Phần kết luận
Bạn đã thêm thành công văn bản có màu đổ bóng vào tài liệu PDF của mình bằng Aspose.PDF cho .NET. Tệp PDF kết quả hiện có thể được tìm thấy tại đường dẫn tệp đầu ra đã chỉ định.

### Câu hỏi thường gặp

#### H: Trọng tâm chính của hướng dẫn này là gì?

A: Hướng dẫn này hướng dẫn bạn quy trình thêm văn bản có màu đổ bóng vào tệp PDF bằng thư viện Aspose.PDF cho .NET. Mã nguồn C# được cung cấp sẽ trình bày các bước cần thiết để thực hiện việc này.

#### H: Tôi cần nhập những không gian tên nào cho hướng dẫn này?

A: Trong tệp mã mà bạn muốn thêm văn bản có màu đổ bóng, hãy nhập các không gian tên sau vào đầu tệp:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### H: Làm thế nào để chỉ định thư mục tài liệu?

 A: Trong mã, xác định vị trí dòng`string dataDir = "YOUR DOCUMENT DIRECTORY";` và thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

#### H: Làm thế nào để tải một tài liệu PDF có sẵn?

 A: Ở Bước 4, bạn sẽ tải một tài liệu PDF hiện có bằng cách sử dụng`Document` hàm tạo và cung cấp đường dẫn đến tệp tài liệu:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Mã nằm ở đây...
}
```

#### H: Làm thế nào để tìm và sửa đổi văn bản cụ thể trong tài liệu PDF?

 A: Ở Bước 5, bạn sẽ sử dụng`TextFragmentAbsorber`để tìm văn bản mong muốn trong tài liệu. Sau đó, bạn có thể sửa đổi các thuộc tính của nó:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### H: Làm thế nào để thiết lập màu tô bóng cho văn bản?

 A: Ở Bước 6, bạn sẽ tạo một`Color` đối tượng có không gian màu mẫu và chỉ định màu đổ bóng gradient. Gán màu này cho`ForegroundColor` tài sản của`TextState` của`TextFragment` sự vật:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### H: Tôi có thể áp dụng định dạng văn bản bổ sung cho văn bản đã sửa đổi không?

 A: Có, ở Bước 7, bạn có thể áp dụng định dạng văn bản bổ sung như gạch chân bằng cách sửa đổi các thuộc tính của`TextState` sự vật:

```csharp
textFragment.TextState.Underline = true;
```

#### H: Làm thế nào để lưu tài liệu PDF đã chỉnh sửa?

 A: Ở Bước 8, bạn sẽ lưu tài liệu PDF đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### H: Nội dung chính rút ra từ hướng dẫn này là gì?

A: Bằng cách làm theo hướng dẫn này, bạn đã học thành công cách cải thiện tài liệu PDF của mình bằng cách thêm văn bản có màu đổ bóng bằng Aspose.PDF cho .NET. Điều này có thể đặc biệt hữu ích để làm nổi bật và nhấn mạnh nội dung văn bản cụ thể trong tệp PDF của bạn.