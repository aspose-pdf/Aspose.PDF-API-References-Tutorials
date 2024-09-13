---
title: Lề hoặc đệm
linktitle: Lề hoặc đệm
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thiết lập lề hoặc khoảng đệm trong bảng bằng Aspose.PDF cho .NET.
type: docs
weight: 140
url: /vi/net/programming-with-tables/margins-or-padding/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước sử dụng Aspose.PDF cho .NET để thiết lập lề hoặc đệm trong bảng. Chúng tôi sẽ cung cấp các giải thích và đoạn mã để giúp bạn hiểu và triển khai chức năng này trong mã nguồn C# của bạn.

## Bước 1: Thiết lập Tài liệu và Trang
Để bắt đầu, bạn cần thiết lập tài liệu và trang bằng mã sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Document bằng cách gọi hàm tạo rỗng của nó
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 2: Tạo bảng
Tiếp theo, chúng ta sẽ tạo một đối tượng bảng bằng cách sử dụng lớp Aspose.Pdf.Table:

```csharp
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(tab1);
```

## Bước 3: Thiết lập độ rộng cột và đường viền ô mặc định
Để thiết lập độ rộng cột và đường viền ô mặc định của bảng, hãy sử dụng mã sau:

```csharp
// Đặt độ rộng cột của bảng
tab1. ColumnWidths = "50 50 50";
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Bước 4: Thiết lập đường viền bảng và khoảng đệm ô
Để thiết lập đường viền bảng và khoảng đệm ô, hãy tạo đối tượng MarginInfo và thiết lập các thuộc tính của nó:

```csharp
// Tạo một đối tượng MarginInfo và thiết lập lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Đặt khoảng đệm ô mặc định thành đối tượng MarginInfo
tab1. DefaultCellPadding = margin;

// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Bước 5: Thêm Hàng và Ô
Bây giờ, hãy thêm hàng và ô vào bảng. Chúng ta sẽ tạo một hàng mới và thêm ô vào đó:

```csharp
//Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Bước 6: Thêm văn bản vào ô
Để thêm văn bản vào ô, hãy tạo đối tượng TextFragment và thêm nó vào ô mong muốn:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Bước 7: Lưu PDF
Để lưu tài liệu PDF, hãy sử dụng mã sau:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Lưu PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Mã nguồn ví dụ cho Margins Or Padding sử dụng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Document bằng cách gọi hàm tạo rỗng của nó
Document doc = new Document();
Page page = doc.Pages.Add();
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(tab1);
// Thiết lập với chiều rộng cột của bảng
tab1.ColumnWidths = "50 50 50";
// Đặt đường viền ô mặc định bằng cách sử dụng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Tạo đối tượng MarginInfo và thiết lập lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Đặt khoảng đệm ô mặc định thành đối tượng MarginInfo
tab1.DefaultCellPadding = margin;
//Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 với chuỗi văn bản lớn sẽ được đặt bên trong ô");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Hàng1.Ô[2].Đoạn văn[0].Chiều rộng cố định= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách thiết lập lề hoặc đệm trong bảng bằng Aspose.PDF cho .NET. Kiến thức này sẽ giúp bạn nâng cao khả năng định dạng tài liệu và làm cho bảng của bạn hấp dẫn về mặt trực quan.

### Câu hỏi thường gặp

#### H: Tôi có thể thiết lập lề hoặc khoảng đệm khác nhau cho từng ô trong bảng không?

 A: Có, bạn có thể thiết lập các lề hoặc khoảng đệm khác nhau cho từng ô trong bảng bằng Aspose.PDF cho .NET. Trong ví dụ được cung cấp, chúng tôi thiết lập khoảng đệm ô mặc định cho toàn bộ bảng bằng cách sử dụng`DefaultCellPadding` thuộc tính. Để thiết lập phần đệm khác nhau cho các ô cụ thể, bạn có thể truy cập`MarginInfo` của từng tế bào riêng lẻ và sửa đổi biên của chúng.

#### H: Làm thế nào để thay đổi màu viền hoặc kiểu dáng của bảng?

 A: Để thay đổi màu viền hoặc kiểu của bảng, bạn có thể sửa đổi`Color` Và`Width` tính chất của`BorderInfo` đối tượng. Trong ví dụ đã cho, chúng tôi đặt màu đường viền thành màu đen và chiều rộng là 1F (một điểm) bằng cách sử dụng`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Bạn có thể điều chỉnh màu sắc và chiều rộng theo yêu cầu của bạn.

#### H: Có thể thêm tiêu đề hoặc chân trang vào bảng không?

A: Có, bạn có thể thêm tiêu đề hoặc chân trang vào bảng bằng Aspose.PDF cho .NET. Tiêu đề và chân trang thường là các hàng riêng biệt chứa thông tin bổ sung như nhãn cột, tiêu đề bảng hoặc dữ liệu tóm tắt. Bạn có thể tạo thêm các hàng, định dạng chúng theo cách khác và thêm chúng ở trên hoặc dưới nội dung bảng.

#### H: Làm thế nào để căn chỉnh văn bản trong ô của bảng?

 A: Để điều chỉnh căn chỉnh văn bản trong một ô bảng, bạn có thể sử dụng`HorizontalAlignment` Và`VerticalAlignment` tính chất của`TextFragment` đối tượng. Ví dụ, để căn giữa văn bản theo chiều ngang, bạn có thể thiết lập`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Tương tự như vậy, bạn có thể thiết lập`mytext.VerticalAlignment` để kiểm soát sự căn chỉnh theo chiều dọc.

#### H: Tôi có thể thêm hình ảnh vào ô bảng thay vì văn bản không?

 A: Có, bạn có thể thêm hình ảnh vào các ô bảng bằng Aspose.PDF cho .NET. Thay vì tạo`TextFragment` đối tượng, bạn có thể tạo ra một`Image` đối tượng, tải tệp hình ảnh và thêm nó vào ô mong muốn bằng cách sử dụng`cell.Paragraphs.Add(image);`Phương pháp này cho phép bạn chèn hình ảnh vào bảng cùng với nội dung văn bản.