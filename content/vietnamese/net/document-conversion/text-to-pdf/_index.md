---
title: Chuyển văn bản sang PDF
linktitle: Chuyển văn bản sang PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Chuyển đổi tệp văn bản sang PDF đơn giản và hiệu quả bằng Aspose.PDF for .NET.
type: docs
weight: 300
url: /vi/net/document-conversion/text-to-pdf/
---
Hướng dẫn này sẽ hướng dẫn bạn các bước để chuyển đổi tệp văn bản thành tệp PDF bằng Aspose.PDF cho .NET. Aspose.PDF cung cấp giải pháp đơn giản và hiệu quả để chuyển đổi văn bản thuần túy sang PDF trong khi vẫn giữ nguyên định dạng và cách trình bày văn bản. Thực hiện theo các bước dưới đây để thực hiện chuyển đổi này.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Đọc file văn bản
 Bước đầu tiên là đọc nội dung của tệp văn bản bằng cách sử dụng`StreamReader` lớp học. Sử dụng mã sau đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Đọc tập tin văn bản
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"`với thư mục thực nơi chứa tệp văn bản của bạn.

## Bước 2: Tạo tài liệu PDF
 Bước thứ hai là tạo một`Document` đối tượng sẽ đại diện cho tài liệu PDF cuối cùng. Sử dụng mã sau đây:

```csharp
// Tạo một đối tượng Tài liệu
Document doc = new Document();
```

## Bước 3: Thêm văn bản vào tài liệu
Bước thứ ba là thêm văn bản đã đọc vào trang của tài liệu PDF. Sử dụng mã sau đây:

```csharp
//Thêm một trang mới vào tài liệu
Page page = doc.Pages.Add();

// Tạo một đối tượng TextFragment và chuyển văn bản đã đọc làm đối số
TextFragment text = new TextFragment(tr.ReadToEnd());

// Thêm đoạn văn bản vào trang
page.Paragraphs.Add(text);
```

## Bước 4: Lưu tệp PDF
Cuối cùng, lưu tệp PDF kết quả bằng cách chỉ định đường dẫn và tên tệp mong muốn. Sử dụng mã sau đây:

```csharp
// Lưu tệp PDF kết quả
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Đảm bảo chỉ định đường dẫn và tên tệp mong muốn cho tệp PDF kết quả.

### Mã nguồn ví dụ cho Chuyển văn bản sang PDF bằng Aspose.PDF for .NET

```csharp
try
{
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Đọc tệp văn bản nguồn
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Khởi tạo một đối tượng Tài liệu bằng cách gọi hàm tạo trống của nó
	Document doc = new Document();

	// Thêm một trang mới trong bộ sưu tập Trang của Tài liệu
	Page page = doc.Pages.Add();

	// Tạo một phiên bản của TextFragmet và chuyển văn bản từ đối tượng trình đọc sang hàm tạo của nó làm đối số
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Thêm một đoạn văn bản mới trong bộ sưu tập đoạn văn và truyền đối tượng TextFragment
	page.Paragraphs.Add(text);

	// Lưu tệp PDF kết quả
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách chuyển đổi tệp văn bản thành tệp PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước nêu trên, bạn có thể dễ dàng thực hiện chuyển đổi này. Sử dụng phương pháp này để chuyển đổi tệp văn bản của bạn sang PDF và tận hưởng tính linh hoạt cũng như chất lượng của Aspose.PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng C#. Nó cung cấp nhiều chức năng khác nhau, bao gồm chuyển đổi văn bản thuần túy sang PDF.

#### Hỏi: Tại sao tôi muốn chuyển đổi tệp văn bản thành PDF?

Đáp: Việc chuyển đổi tệp văn bản sang định dạng PDF cho phép quản lý, chia sẻ và phân phối tài liệu tốt hơn. Các tệp PDF cung cấp định dạng nhất quán trên các thiết bị và hệ điều hành khác nhau.

#### Câu hỏi: Làm cách nào tôi có thể tải tệp văn bản và chuyển đổi nó thành PDF bằng Aspose.PDF cho .NET?

Đáp: Để tải một tập tin văn bản, bạn có thể sử dụng`StreamReader` class để đọc nội dung của tập tin. Sau đó, tạo một`Document` đối tượng đại diện cho tài liệu PDF. Thêm một trang mới và một`TextFragment` chứa văn bản từ tệp văn bản. Cuối cùng, lưu tệp PDF thu được bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của văn bản trong PDF không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện của văn bản trong tệp PDF thu được, chẳng hạn như kiểu phông chữ, kích thước, màu sắc và căn chỉnh.

#### Hỏi: Định dạng văn bản có được giữ nguyên trong tệp PDF thu được không?

Trả lời: Có, Aspose.PDF cho .NET giữ nguyên định dạng và bố cục văn bản trong quá trình chuyển đổi văn bản sang PDF, đảm bảo thể hiện chính xác nội dung gốc.