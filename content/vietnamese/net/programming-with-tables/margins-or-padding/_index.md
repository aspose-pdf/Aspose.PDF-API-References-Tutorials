---
title: Lề hoặc phần đệm
linktitle: Lề hoặc phần đệm
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt lề hoặc phần đệm trong bảng bằng Aspose.PDF cho .NET.
type: docs
weight: 140
url: /vi/net/programming-with-tables/margins-or-padding/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước sử dụng Aspose.PDF cho .NET để đặt lề hoặc phần đệm trong bảng. Chúng tôi sẽ cung cấp giải thích và đoạn mã để giúp bạn hiểu và triển khai chức năng này trong mã nguồn C# của bạn.

## Bước 1: Thiết lập Tài liệu và Trang
Để bắt đầu, bạn cần thiết lập tài liệu và trang bằng mã sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Document bằng cách gọi hàm tạo trống của nó
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Bước 2: Tạo bảng
Tiếp theo, chúng ta sẽ tạo một đối tượng bảng bằng lớp Aspose.Pdf.Table:

```csharp
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(tab1);
```

## Bước 3: Đặt độ rộng cột và viền ô mặc định
Để đặt độ rộng cột và đường viền ô mặc định của bảng, hãy sử dụng mã sau:

```csharp
// Đặt độ rộng cột của bảng
tab1. ColumnWidths = "50 50 50";
// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Bước 4: Thiết lập viền bảng và đệm ô
Để đặt đường viền bảng và phần đệm ô, hãy tạo một đối tượng MarginInfo và đặt các thuộc tính của nó:

```csharp
// Tạo một đối tượng MarginInfo và đặt lề trái, dưới, phải và trên cùng của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Đặt phần đệm ô mặc định cho đối tượng MarginInfo
tab1. DefaultCellPadding = margin;

// Đặt đường viền bảng bằng cách sử dụng một đối tượng BorderInfo tùy chỉnh khác
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Bước 5: Thêm hàng và ô
Bây giờ, hãy thêm hàng và ô vào bảng. Chúng ta sẽ tạo một hàng mới và thêm các ô vào đó:

```csharp
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Bước 6: Thêm văn bản vào ô
Để thêm văn bản vào một ô, hãy tạo một đối tượng TextFragment và thêm nó vào ô mong muốn:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Bước 7: Lưu PDF
Để lưu tài liệu PDF, hãy sử dụng đoạn mã sau:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Mã nguồn ví dụ cho Lề hoặc Phần đệm bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Document bằng cách gọi hàm tạo trống của nó
Document doc = new Document();
Page page = doc.Pages.Add();
// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
page.Paragraphs.Add(tab1);
// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "50 50 50";
// Đặt đường viền ô mặc định bằng đối tượng BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Đặt đường viền bảng bằng cách sử dụng đối tượng BorderInfo tùy chỉnh khác
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Tạo đối tượng MarginInfo và đặt lề trái, dưới, phải và trên của nó
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Đặt phần đệm ô mặc định cho đối tượng MarginInfo
tab1.DefaultCellPadding = margin;
// Tạo các hàng trong bảng và sau đó tạo các ô trong các hàng
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 với chuỗi văn bản lớn được đặt bên trong ô");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
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
Chúc mừng! Bạn đã học thành công cách đặt lề hoặc phần đệm trong bảng bằng Aspose.PDF cho .NET. Kiến thức này sẽ giúp bạn nâng cao khả năng định dạng tài liệu và làm cho bảng của bạn trở nên hấp dẫn về mặt trực quan.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể đặt lề hoặc phần đệm khác nhau cho từng ô trong bảng không?

Trả lời: Có, bạn có thể đặt các lề hoặc khoảng đệm khác nhau cho từng ô trong bảng bằng Aspose.PDF cho .NET. Trong ví dụ được cung cấp, chúng tôi đặt phần đệm ô mặc định cho toàn bộ bảng bằng cách sử dụng`DefaultCellPadding` tài sản. Để đặt phần đệm khác nhau cho các ô cụ thể, bạn có thể truy cập vào`MarginInfo` của từng ô riêng lẻ và sửa đổi lề của chúng.

#### Hỏi: Làm cách nào để thay đổi màu đường viền hoặc kiểu của bảng?

 Đáp: Để thay đổi màu đường viền hoặc kiểu dáng của bảng, bạn có thể sửa đổi`Color` Và`Width` thuộc tính của`BorderInfo` sự vật. Trong ví dụ đã cho, chúng tôi đặt màu đường viền thành màu đen và chiều rộng là 1F (một điểm) bằng cách sử dụng`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Bạn có thể điều chỉnh màu sắc và chiều rộng theo yêu cầu của bạn.

#### Hỏi: Có thể thêm đầu trang hoặc chân trang vào bảng không?

Trả lời: Có, bạn có thể thêm đầu trang hoặc chân trang vào bảng bằng Aspose.PDF cho .NET. Đầu trang và chân trang thường là các hàng riêng biệt chứa thông tin bổ sung như nhãn cột, tiêu đề bảng hoặc dữ liệu tóm tắt. Bạn có thể tạo các hàng bổ sung, tạo kiểu cho chúng theo cách khác và thêm chúng vào bên trên hoặc bên dưới nội dung bảng.

#### Câu hỏi: Làm cách nào để điều chỉnh căn chỉnh văn bản trong ô bảng?

 Đáp: Để điều chỉnh căn chỉnh văn bản trong một ô của bảng, bạn có thể sử dụng`HorizontalAlignment` Và`VerticalAlignment` thuộc tính của`TextFragment` sự vật. Ví dụ: để căn giữa văn bản theo chiều ngang, bạn có thể đặt`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Tương tự, bạn có thể thiết lập`mytext.VerticalAlignment` để kiểm soát sự liên kết theo chiều dọc.

#### Câu hỏi: Tôi có thể thêm hình ảnh vào ô của bảng thay vì văn bản không?

 Đáp: Có, bạn có thể thêm hình ảnh vào các ô trong bảng bằng Aspose.PDF cho .NET. Thay vì tạo ra một`TextFragment` đối tượng, bạn có thể tạo một`Image` đối tượng, tải tệp hình ảnh và thêm nó vào ô mong muốn bằng cách sử dụng`cell.Paragraphs.Add(image);` phương pháp. Điều này cho phép bạn chèn hình ảnh vào bảng cùng với nội dung văn bản.