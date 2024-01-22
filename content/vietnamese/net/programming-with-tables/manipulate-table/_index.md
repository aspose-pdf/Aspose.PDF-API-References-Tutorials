---
title: Thao tác bảng trong file PDF
linktitle: Thao tác bảng trong file PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng thao tác bảng trong tệp PDF với Aspose.PDF cho .NET.
type: docs
weight: 130
url: /vi/net/programming-with-tables/manipulate-table/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước thao tác các bảng trong tệp PDF bằng Aspose.PDF cho .NET. Bảng là một thành phần phổ biến trong tài liệu PDF và việc có thể sửa đổi nội dung của chúng theo chương trình có thể rất có lợi trong nhiều trường hợp khác nhau. Chúng tôi sẽ sử dụng mã nguồn C# được cung cấp để minh họa quy trình.

## Yêu cầu

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác được cài đặt.
- Thư viện Aspose.PDF cho .NET được thêm làm tài liệu tham khảo cho dự án của bạn.

Bây giờ, hãy đi sâu vào các bước cần thiết để thao tác các bảng trong tài liệu PDF bằng Aspose.PDF cho .NET.

## Bước 1: Tải tài liệu PDF

Bước đầu tiên là tải tài liệu PDF hiện có vào ứng dụng C# của bạn. Bạn cần cung cấp đường dẫn đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục chứa tài liệu PDF của bạn.

## Bước 2: Tìm bảng trong tài liệu

Để thao tác với các bảng, chúng ta cần tìm chúng trong tài liệu PDF. Aspose.PDF for .NET cung cấp lớp TableAbsorber cho phép chúng ta trích xuất các bảng từ tài liệu. Chúng ta sẽ tạo một thể hiện của lớp TableAbsorber và truy cập trang mong muốn của tài liệu.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

Trong ví dụ này, chúng ta đang truy cập trang đầu tiên của tài liệu. Bạn có thể thay đổi số trang theo yêu cầu của bạn.

## Bước 3: Truy cập ô bảng và đoạn văn bản

Sau khi có các bảng, chúng ta có thể truy cập vào các ô và đoạn văn bản của chúng để thao tác. Trong mã nguồn được cung cấp, chúng ta đang truy cập vào bảng đầu tiên, ô đầu tiên của hàng đầu tiên và đoạn văn bản thứ hai trong ô đó.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

Bạn có thể sửa đổi mã để nhắm mục tiêu các bảng, ô hoặc đoạn văn bản khác nhau dựa trên nhu cầu cụ thể của mình.

## Bước 4: Thao tác với văn bản bảng

Với đoạn văn bản được truy cập, giờ đây chúng ta có thể sửa đổi nội dung của nó. Trong ví dụ đã cho, chúng tôi đang thay đổi văn bản thành "hi world".

```csharp
fragment.Text = "hi world";
```

Vui lòng thay thế "hi world" bằng văn bản bạn muốn.

## Bước 5: Lưu tài liệu đã sửa đổi

Sau khi thực hiện các sửa đổi mong muốn, chúng ta cần lưu tài liệu PDF đã sửa đổi.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Đảm bảo bạn cung cấp đường dẫn và tên tệp cho tài liệu đã sửa đổi.


### Mã nguồn ví dụ cho Bảng thao tác bằng Aspose.PDF cho .NET

```csharp
try
{
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Tải tệp PDF hiện có
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Tạo đối tượng TableAbsorber để tìm bảng
	TableAbsorber absorber = new TableAbsorber();

	// Truy cập trang đầu tiên với chất hấp thụ
	absorber.Visit(pdfDocument.Pages[1]);

	// Có quyền truy cập vào bảng đầu tiên trên trang, ô đầu tiên và đoạn văn bản trong đó
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Thay đổi văn bản của đoạn văn bản đầu tiên trong ô
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thao tác các bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể dễ dàng tải tài liệu PDF, tìm bảng, truy cập các ô và đoạn văn bản, sửa đổi nội dung bảng và lưu tài liệu đã sửa đổi. Cách tiếp cận này mang lại sự linh hoạt và hiệu quả khi xử lý thao tác bảng trong tài liệu PDF.

### Câu hỏi thường gặp về thao tác bảng trong tệp PDF

#### Câu hỏi: Tôi có thể thao tác với bảng trong tài liệu PDF nhiều trang không?

Đáp: Có, bạn có thể thao tác với các bảng trong tài liệu PDF nhiều trang bằng Aspose.PDF dành cho .NET. Trong ví dụ được cung cấp, chúng tôi đã truy cập trang đầu tiên của tài liệu (`pdfDocument.Pages[1]`), nhưng bạn có thể lặp qua tất cả các trang và thao tác với các bảng trên mỗi trang nếu cần.

#### Câu hỏi: Làm cách nào tôi có thể thêm hàng hoặc cột mới vào bảng hiện có?

 Trả lời: Để thêm hàng hoặc cột mới vào bảng hiện có, bạn có thể sử dụng API do Aspose.PDF cung cấp cho .NET. Bạn có thể truy cập`RowList` Và`CellList` thuộc tính của`TableAbsorber.TableList` để thêm hàng và ô mới theo chương trình. Tham khảo tài liệu Aspose.PDF for .NET để biết thông tin chi tiết và ví dụ về mã.

#### Câu hỏi: Có thể xóa bảng khỏi tài liệu PDF không?

 Trả lời: Có, bạn có thể xóa bảng khỏi tài liệu PDF bằng Aspose.PDF cho .NET. Để đạt được điều này, bạn có thể loại bỏ các mục cụ thể`Table` đối tượng từ`Page.Paragraphs` bộ sưu tập. Bạn có thể xác định bảng cần xóa bằng cách sử dụng các thuộc tính như`Table.NumberOfColumns`, `Table.NumberOfRows`và các số nhận dạng duy nhất khác.

#### Hỏi: Tôi có thể thay đổi định dạng (phông chữ, màu sắc, căn chỉnh) của văn bản trong bảng không?

 Trả lời: Có, bạn có thể thay đổi định dạng văn bản trong bảng bằng Aspose.PDF cho .NET. Bạn có thể truy cập`TextState` tài sản của`TextFragment` đối tượng để sửa đổi phông chữ, cỡ chữ, màu sắc và căn chỉnh của văn bản.

#### Câu hỏi: Aspose.PDF for .NET có hỗ trợ làm việc với các bảng ở dạng PDF (AcroForms) không?

Trả lời: Có, Aspose.PDF for .NET hỗ trợ làm việc với các bảng ở dạng PDF (AcroForms). Bạn có thể truy cập và thao tác các thành phần bảng ở dạng PDF tương tự như cách tiếp cận được trình bày trong hướng dẫn này. Aspose.PDF for .NET cung cấp hỗ trợ rộng rãi để làm việc với AcroForms và các trường biểu mẫu.