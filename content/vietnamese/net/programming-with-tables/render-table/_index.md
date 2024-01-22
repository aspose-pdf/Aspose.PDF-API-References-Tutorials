---
title: Bảng kết xuất trong tài liệu PDF
linktitle: Bảng kết xuất trong tài liệu PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách hiển thị bảng trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 170
url: /vi/net/programming-with-tables/render-table/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước cách hiển thị bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai mã đó.

## Bước 1: Tạo tài liệu
Đầu tiên, chúng ta sẽ tạo một tài liệu PDF mới:

```csharp
// Đường dẫn đến thư mục tài liệu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo một tài liệu mới
Document doc = new Document();
```

## Bước 2: Định cấu hình lề và hướng trang
Tiếp theo, chúng tôi sẽ định cấu hình lề trang và đặt hướng thành chế độ ngang:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Bước 3: Tạo bảng và cột
Bây giờ hãy tạo một bảng và đặt độ rộng cột:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Bước 4: Thêm hàng và ô vào bảng
Tiếp theo, chúng ta sẽ thêm hàng và ô vào bảng bằng vòng lặp:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Bước 5: Thêm bảng vào trang
Bây giờ hãy thêm bảng vào trang tài liệu:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Bước 6: Hiển thị bảng trên trang mới
Tiếp theo, chúng ta sẽ tạo một bảng mới và đặt thuộc tính "IsInNewPage" thành "true" để hiển thị bảng trên một trang mới:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Bước 7: Lưu PDF
Cuối cùng, chúng tôi lưu tài liệu PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Mã nguồn ví dụ cho Bảng kết xuất bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Đã thêm trang.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Tôi muốn giữ bảng 1 ở trang tiếp theo...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học cách hiển thị bảng trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách tạo tài liệu, định cấu hình lề và hướng trang, thêm bảng và hiển thị bảng trên trang mới. Bây giờ bạn có thể áp dụng kiến thức này vào dự án của riêng mình.

### Câu hỏi thường gặp về bảng kết xuất trong tài liệu PDF

#### Câu hỏi: Làm cách nào tôi có thể sửa đổi hình thức của bảng, chẳng hạn như thay đổi màu ô hoặc thêm đường viền?

Đáp: Để sửa đổi hình thức của bảng, bạn có thể đặt các thuộc tính khác nhau của`Aspose.Pdf.Table` và tế bào của nó. Ví dụ: bạn có thể đặt`BackgroundColor` thuộc tính của ô để thay đổi màu nền của chúng. Bạn cũng có thể thiết lập`Border` thuộc tính của bảng hoặc các ô riêng lẻ để thêm đường viền. Ngoài ra, bạn có thể tùy chỉnh phông chữ, màu văn bản và căn chỉnh nội dung bảng bằng cách sửa đổi`TextState` sau đó`TextFragment` các đối tượng được thêm vào ô.

#### Hỏi: Tôi có thể thêm đầu trang hoặc chân trang vào bảng không?

Trả lời: Có, bạn có thể thêm đầu trang hoặc chân trang vào bảng bằng cách tạo thêm hàng ở đầu hoặc cuối bảng và đặt nội dung phù hợp trong các ô. Bạn có thể tùy chỉnh đầu trang hoặc chân trang một cách độc lập với phần còn lại của nội dung bảng bằng cách thêm các kiểu hoặc nội dung khác nhau vào các hàng cụ thể này.

#### Hỏi: Làm cách nào tôi có thể kiểm soát vị trí của bảng trên trang?

 Đáp: Để kiểm soát vị trí của bảng trên trang, bạn có thể điều chỉnh`MarginInfo` sau đó`PageInfo` sự vật. Các`MarginInfo`cho phép bạn đặt lề trái, phải, trên và dưới của trang, điều này ảnh hưởng đến không gian có sẵn cho bảng. Bạn cũng có thể sử dụng`PositioningType` tài sản của`Aspose.Pdf.Table` để kiểm soát sự căn chỉnh theo chiều ngang và chiều dọc của nó trong vùng nội dung của trang.

#### Hỏi: Tôi có thể xuất bảng sang các định dạng tệp khác nhau, chẳng hạn như Excel hoặc CSV không?

Đáp: Aspose.PDF for .NET được thiết kế chủ yếu để làm việc với các tài liệu PDF. Mặc dù nó có thể xuất tài liệu PDF dưới dạng hình ảnh hoặc XPS nhưng nó không hỗ trợ trực tiếp xuất bảng sang các định dạng như Excel hoặc CSV. Để xuất dữ liệu bảng sang các định dạng tệp khác nhau, bạn có thể cần sử dụng các thư viện hoặc phương pháp bổ sung để chuyển đổi nội dung PDF sang định dạng mong muốn.

#### Hỏi: Làm cách nào tôi có thể thêm siêu kết nối vào các ô của bảng?

 Đáp: Để thêm siêu liên kết vào các ô của bảng, bạn có thể sử dụng`Aspose.Pdf.WebHyperlink` lớp để tạo một siêu liên kết và sau đó thêm nó làm điểm neo vào`TextFragment`bên trong tế bào. Điều này cho phép bạn liên kết một URL hoặc mục tiêu liên kết với văn bản hoặc nội dung cụ thể trong ô, tạo ra các siêu liên kết có thể nhấp vào.