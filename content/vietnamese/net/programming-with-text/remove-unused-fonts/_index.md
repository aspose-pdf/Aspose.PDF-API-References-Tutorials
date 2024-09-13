---
title: Xóa Phông Chữ Không Sử Dụng Trong Tệp PDF
linktitle: Xóa Phông Chữ Không Sử Dụng Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xóa phông chữ không sử dụng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 300
url: /vi/net/programming-with-text/remove-unused-fonts/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách xóa phông chữ không sử dụng trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ thực hiện từng bước quy trình tải PDF, xác định và xóa phông chữ không sử dụng và lưu PDF đã cập nhật bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục chứa các tệp PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải PDF nguồn

 Tiếp theo, chúng tôi tải tài liệu PDF nguồn bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Bước 3: Xác định và xóa các phông chữ không sử dụng

 Chúng tôi tạo ra một`TextFragmentAbsorber` đối tượng với`TextEditOptions` tham số được đặt thành`TextEditOptions.FontReplace.RemoveUnusedFonts` . Tùy chọn này cho phép chúng tôi xác định và xóa các phông chữ không sử dụng trong tài liệu PDF. Sau đó, chúng tôi lặp lại tất cả các`TextFragments` và thiết lập phông chữ theo phông chữ mong muốn.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Bước 4: Lưu PDF đã cập nhật

Cuối cùng, chúng ta lưu tài liệu PDF đã cập nhật vào tệp đầu ra đã chỉ định.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu cho Xóa phông chữ không sử dụng bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tệp PDF nguồn
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Lặp lại tất cả các TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Lưu tài liệu đã cập nhật
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách xóa phông chữ không sử dụng khỏi tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tải PDF, xác định và xóa phông chữ không sử dụng và lưu PDF đã cập nhật.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Xóa phông chữ không sử dụng trong tệp PDF" là gì?

A: Hướng dẫn "Xóa phông chữ không sử dụng trong tệp PDF" giải thích cách sử dụng thư viện Aspose.PDF cho .NET để xóa phông chữ không sử dụng khỏi tài liệu PDF. Hướng dẫn hướng dẫn bạn quy trình tải PDF, xác định và xóa phông chữ không sử dụng và lưu PDF đã cập nhật.

#### H: Tại sao tôi muốn xóa các phông chữ không sử dụng khỏi tài liệu PDF?

A: Việc xóa các phông chữ không sử dụng khỏi tài liệu PDF có thể giúp giảm kích thước tệp và tối ưu hóa tài liệu để có hiệu suất tốt hơn. Điều này đặc biệt hữu ích khi xử lý các tệp PDF có chứa các phông chữ nhúng không thực sự được sử dụng trong nội dung của tài liệu.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục chứa các tệp PDF của bạn.

#### H: Làm thế nào để xóa các phông chữ không sử dụng khỏi tài liệu PDF bằng thư viện Aspose.PDF?

A: Hướng dẫn sẽ hướng dẫn bạn từng bước trong quy trình này:

1.  Mở tài liệu PDF bằng cách sử dụng`Document` lớp học.
2.  Tạo một`TextFragmentAbsorber` đối tượng với`TextEditOptions` đặt thành`FontReplace.RemoveUnusedFonts`.
3. Chấp nhận trình hấp thụ để xác định và xóa các phông chữ không sử dụng khỏi PDF.
4.  Lặp lại tất cả`TextFragments` và thiết lập phông chữ theo phông chữ mong muốn.
5. Lưu tài liệu PDF đã cập nhật.

####  Q: Mục đích của việc này là gì?`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: Cái`TextEditOptions.FontReplace.RemoveUnusedFonts` tham số hướng dẫn`TextFragmentAbsorber`để xác định và xóa các phông chữ không sử dụng khỏi tài liệu PDF.

#### H: Tôi có thể thay thế phông chữ không sử dụng bằng phông chữ tôi chọn không?

A: Có, bạn có thể sửa đổi mã để thay thế phông chữ không sử dụng bằng phông chữ bạn chọn. Trong mã mẫu được cung cấp, phông chữ "Arial, Bold" được sử dụng để thay thế.

#### Q: Làm thế nào để`TextFragmentAbsorber` work to remove unused fonts?

 A: Cái`TextFragmentAbsorber` được cấu hình với`TextEditOptions.FontReplace.RemoveUnusedFonts` tham số, xác định các phông chữ chưa sử dụng trong các đoạn văn bản của PDF. Sau khi hấp thụ, bạn có thể lặp lại qua`TextFragments` và thiết lập phông chữ thay thế mong muốn.

#### H: Kết quả mong đợi khi thực thi mã được cung cấp là gì?

A: Bằng cách làm theo hướng dẫn và chạy mã C# được cung cấp, bạn sẽ xóa các phông chữ không sử dụng khỏi tài liệu PDF đầu vào và lưu phiên bản cập nhật dưới dạng tệp PDF đầu ra.

#### H: Tôi có thể sửa đổi mã để chỉ xóa phông chữ khỏi các trang hoặc khu vực cụ thể không?

A: Mã được cung cấp tập trung vào việc xóa phông chữ không sử dụng khỏi toàn bộ tài liệu PDF. Nếu bạn muốn nhắm mục tiêu vào các trang hoặc vùng cụ thể để xóa phông chữ, bạn sẽ cần sửa đổi phương pháp tiếp cận và sử dụng logic phức tạp hơn để xác định phông chữ không sử dụng trong các vùng đó.