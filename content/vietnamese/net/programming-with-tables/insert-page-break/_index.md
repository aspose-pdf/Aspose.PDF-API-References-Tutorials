---
title: Chèn ngắt trang vào tệp PDF
linktitle: Chèn ngắt trang vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách chèn ngắt trang trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 110
url: /vi/net/programming-with-tables/insert-page-break/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách chèn ngắt trang trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn trong C#. Ở cuối hướng dẫn này, bạn sẽ biết cách thêm dấu ngắt trang sau một số dòng nhất định trong bảng của tài liệu PDF. Hãy bắt đầu!

## Bước 1: Thiết lập môi trường
Đảm bảo bạn đã định cấu hình môi trường phát triển C# của mình bằng Aspose.PDF cho .NET. Thêm tham chiếu vào thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tạo tài liệu và bảng
Chúng tôi tạo một phiên bản Tài liệu mới và thêm một trang vào tài liệu này. Tiếp theo, chúng ta tạo một phiên bản Bảng để thể hiện bảng của mình trong tài liệu PDF. Chúng tôi cũng xác định kiểu đường viền cho bảng.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Bước 3: Thêm hàng vào bảng
Chúng tôi sử dụng vòng lặp để thêm 200 hàng vào mảng. Đối với mỗi hàng, chúng tôi tạo một phiên bản Hàng và thêm hai ô có nội dung văn bản.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Khi thêm 10 dòng, chúng tôi chèn ngắt trang mới
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Bước 4: Thêm bảng vào tài liệu
Chúng tôi thêm bảng vào bộ sưu tập đoạn văn của trang tài liệu.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Bước 5: Lưu tài liệu
Chúng tôi lưu tài liệu PDF có chèn ngắt trang.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Mã nguồn ví dụ cho Chèn ngắt trang bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo phiên bản tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
doc.Pages.Add();
// Tạo phiên bản bảng
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Đặt kiểu đường viền cho bảng
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Đặt kiểu viền mặc định cho bảng có màu viền là Đỏ
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Xác định chiều rộng cột của bảng
tab.ColumnWidths = "100 100";
// Tạo vòng lặp thêm 200 hàng cho bảng
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Khi thêm 10 hàng, hiển thị hàng mới trong trang mới
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Thêm bảng vào bộ sưu tập đoạn văn của tệp PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách chèn ngắt trang trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để thêm ngắt trang sau một số dòng nhất định trong bảng trong tài liệu PDF bằng C#.

### Câu hỏi thường gặp về chèn ngắt trang trong tệp PDF

#### Hỏi: Làm cách nào tôi có thể thay đổi kích thước trang cho các trang mới được tạo sau khi ngắt trang?

 Đáp: Để thay đổi kích thước trang cho các trang mới được tạo sau khi ngắt trang, bạn có thể đặt`PageSize` tài sản của`Page` sự vật. Ví dụ: bạn có thể sử dụng mã sau để đặt kích thước trang thành A4:

```csharp
// Đặt kích thước trang thành A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Hỏi: Tôi có thể kiểm soát lề trang cho các trang mới sau khi ngắt trang không?

 Đáp: Có, bạn có thể kiểm soát lề trang cho các trang mới sau khi ngắt trang. Sử dụng`Margin` tài sản của`Page` đối tượng để đặt lề trang. Ví dụ: để đặt tất cả lề thành 10 điểm, bạn có thể sử dụng mã sau:

```csharp
// Đặt tất cả lề thành 10 điểm
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Hỏi: Có thể thêm đầu trang và chân trang vào trang mới sau khi ngắt trang không?

 Đáp: Có, bạn có thể thêm đầu trang và chân trang vào trang mới sau khi ngắt trang. Sử dụng`Page.Header` Và`Page.Footer` Properties để thêm nội dung vào phần đầu trang và chân trang của trang. Ví dụ:

```csharp
// Thêm tiêu đề vào các trang mới
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Thêm chân trang vào trang mới
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Câu hỏi: Tôi có thể chèn ngắt trang tại các vị trí cụ thể ngoài sau một số hàng nhất định không?

 Đáp: Có, bạn có thể chèn ngắt trang tại các vị trí cụ thể ngoài sau một số hàng nhất định. Bạn có thể thiết lập`IsInNewPage` thuộc tính của một hàng để`true` để buộc bảng bắt đầu một trang mới sau hàng đó.

#### Câu hỏi: Làm cách nào tôi có thể điều chỉnh hành vi ngắt trang dựa trên chiều cao nội dung?

Đáp: Bạn có thể sử dụng`IsBroken` thuộc tính của bảng để bật hoặc tắt tính năng ngắt hàng tự động trên các trang. Khi được đặt thành`true`, nó cho phép các hàng ngắt giữa các trang dựa trên chiều cao nội dung.