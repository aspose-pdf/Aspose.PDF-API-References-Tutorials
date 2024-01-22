---
title: Xóa phông chữ không sử dụng trong tệp PDF
linktitle: Xóa phông chữ không sử dụng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách xóa phông chữ không sử dụng trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 300
url: /vi/net/programming-with-text/remove-unused-fonts/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách xóa phông chữ không sử dụng trong tệp PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ thực hiện quy trình từng bước để tải tệp PDF, xác định và xóa các phông chữ không sử dụng cũng như lưu tệp PDF cập nhật bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Trước tiên, bạn cần đặt đường dẫn đến thư mục chứa tệp PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến bằng đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải nguồn PDF

 Tiếp theo, chúng tôi tải tài liệu PDF nguồn bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Bước 3: Xác định và xóa phông chữ không sử dụng

 Chúng tôi tạo ra một`TextFragmentAbsorber` đối tượng với`TextEditOptions` tham số được đặt thành`TextEditOptions.FontReplace.RemoveUnusedFonts` . Tùy chọn này cho phép chúng tôi xác định và xóa các phông chữ không sử dụng trong tài liệu PDF. Sau đó chúng tôi lặp lại tất cả các`TextFragments` và đặt phông chữ thành phông chữ mong muốn.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Bước 4: Lưu bản PDF đã cập nhật

Cuối cùng, chúng tôi lưu tài liệu PDF đã cập nhật vào tệp đầu ra được chỉ định.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Mã nguồn mẫu để Xóa phông chữ không sử dụng bằng Aspose.PDF cho .NET 
```csharp
try
{
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Tải tập tin PDF nguồn
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Lặp lại qua tất cả các TextFragments
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

Trong hướng dẫn này, bạn đã học cách xóa các phông chữ không sử dụng khỏi tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể tải tệp PDF, xác định và xóa các phông chữ không sử dụng cũng như lưu tệp PDF đã cập nhật.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn "Xóa phông chữ không sử dụng trong tệp PDF" là gì?

Trả lời: Hướng dẫn "Xóa phông chữ không sử dụng trong tệp PDF" giải thích cách sử dụng thư viện Aspose.PDF cho .NET để xóa phông chữ không sử dụng khỏi tài liệu PDF. Hướng dẫn sẽ hướng dẫn bạn qua quá trình tải tệp PDF, xác định và xóa các phông chữ không sử dụng cũng như lưu tệp PDF đã cập nhật.

#### Hỏi: Tại sao tôi muốn xóa các phông chữ không sử dụng khỏi tài liệu PDF?

Đáp: Việc xóa các phông chữ không sử dụng khỏi tài liệu PDF có thể giúp giảm kích thước tệp và tối ưu hóa tài liệu để có hiệu suất tốt hơn. Điều này đặc biệt hữu ích khi xử lý các tệp PDF có chứa phông chữ nhúng không thực sự được sử dụng trong nội dung tài liệu.

#### Hỏi: Làm cách nào để thiết lập thư mục tài liệu?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` bên trong`dataDir` biến bằng đường dẫn đến thư mục chứa tệp PDF của bạn.

#### Câu hỏi: Làm cách nào để xóa các phông chữ không sử dụng khỏi tài liệu PDF bằng thư viện Aspose.PDF?

Đáp: Hướng dẫn sẽ hướng dẫn bạn thực hiện từng bước quy trình:

1.  Mở tài liệu PDF bằng cách sử dụng`Document` lớp học.
2.  Tạo một`TextFragmentAbsorber` đối tượng với`TextEditOptions` đặt thành`FontReplace.RemoveUnusedFonts`.
3. Chấp nhận bộ hấp thụ để xác định và xóa các phông chữ không sử dụng khỏi tệp PDF.
4.  Lặp lại tất cả`TextFragments` và đặt phông chữ thành phông chữ mong muốn.
5. Lưu tài liệu PDF đã cập nhật.

####  Hỏi: Mục đích của việc này là gì?`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 Đáp: Cái`TextEditOptions.FontReplace.RemoveUnusedFonts` tham số hướng dẫn`TextFragmentAbsorber` để xác định và xóa các phông chữ không sử dụng khỏi tài liệu PDF.

#### Hỏi: Tôi có thể thay thế các phông chữ không sử dụng bằng phông chữ tôi chọn không?

Trả lời: Có, bạn có thể sửa đổi mã để thay thế các phông chữ không sử dụng bằng phông chữ bạn chọn. Trong mã mẫu được cung cấp, phông chữ "Arial, Bold" được sử dụng để thay thế.

####  Hỏi: Làm thế nào`TextFragmentAbsorber` work to remove unused fonts?

 Đáp: Cái`TextFragmentAbsorber` được cấu hình với`TextEditOptions.FontReplace.RemoveUnusedFonts` tham số xác định các phông chữ không được sử dụng trong các đoạn văn bản của tệp PDF. Sau khi hấp thụ, bạn có thể lặp qua`TextFragments` và đặt phông chữ của họ thành phông chữ thay thế mong muốn.

#### Câu hỏi: Kết quả mong đợi của việc thực thi mã được cung cấp là gì?

Đáp: Bằng cách làm theo hướng dẫn và chạy mã C# được cung cấp, bạn sẽ xóa các phông chữ không sử dụng khỏi tài liệu PDF đầu vào và lưu phiên bản cập nhật làm tệp PDF đầu ra.

#### Hỏi: Tôi có thể sửa đổi mã để chỉ xóa phông chữ khỏi các trang hoặc khu vực cụ thể không?

Đáp: Mã được cung cấp tập trung vào việc xóa các phông chữ không sử dụng khỏi toàn bộ tài liệu PDF. Nếu bạn muốn nhắm mục tiêu các trang hoặc khu vực cụ thể để xóa phông chữ, bạn cần phải sửa đổi cách tiếp cận và sử dụng logic phức tạp hơn để xác định các phông chữ không được sử dụng trong các khu vực đó.