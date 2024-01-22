---
title: Tự động vừa với cửa sổ
linktitle: Tự động vừa với cửa sổ
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để sử dụng Aspose.PDF cho .NET và tự động điều chỉnh cửa sổ khi tạo PDF.
type: docs
weight: 50
url: /vi/net/programming-with-tables/auto-fit-to-window/
---
Bài viết sau đây là hướng dẫn từng bước về cách sử dụng mã nguồn C# được cung cấp để đạt được chức năng Auto Fit To Window bằng thư viện Aspose.PDF cho .NET. Chức năng Auto Fit To Window cho phép bạn tạo các tệp PDF có bố cục phù hợp với cửa sổ xem. Tính năng này đặc biệt hữu ích khi bạn muốn tài liệu PDF của mình tự động điều chỉnh theo kích thước của cửa sổ trình đọc PDF mà người dùng sử dụng.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, bạn cần cài đặt thư viện Aspose.PDF cho .NET trên máy của mình. Đồng thời đảm bảo nhập các không gian tên cần thiết vào dự án của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo tài liệu PDF

 Để bắt đầu, bạn cần tạo một`Document` đối tượng bằng cách gọi hàm tạo mặc định của nó.

```csharp
Document doc = new Document();
```

 Tiếp theo, tạo một phần trong`Pdf` sự vật.

```csharp
Page sec1 = doc.Pages.Add();
```

## Bước 3: Thêm bảng vào tài liệu

 Trong bước này, chúng tôi sẽ thêm một bảng vào tài liệu PDF của mình. Đầu tiên tạo một`Table` sự vật.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Tiếp theo, thêm bảng vào bộ sưu tập đoạn văn của phần.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Bước 4: Tùy chỉnh giao diện bảng

Bạn có thể tùy chỉnh giao diện của bảng bằng cách đặt các thuộc tính như viền ô và lề.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Bước 4: Thêm hàng và ô vào bảng

Bây giờ hãy thêm hàng và ô vào bảng của chúng ta. Bắt đầu bằng cách tạo một hàng và thêm ô vào hàng đó.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Bước 5: Lưu tài liệu

Cuối cùng, chỉ định đường dẫn tệp đầu ra và lưu tài liệu.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn ví dụ cho Auto Fit To Window bằng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Pdf bằng cách gọi hàm tạo trống của nó
Document doc = new Document();
// Tạo phần trong đối tượng Pdf
Page sec1 = doc.Pages.Add();

// Khởi tạo một đối tượng bảng
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Thêm bảng vào bộ sưu tập đoạn văn của phần mong muốn
sec1.Paragraphs.Add(tab1);

// Đặt độ rộng cột của bảng
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Lưu tài liệu cập nhật chứa đối tượng bảng
doc.Save(dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.PDF cho .NET để tạo tệp PDF có tính năng Tự động khớp với cửa sổ. Tính năng này cực kỳ hữu ích khi bạn muốn tài liệu PDF của mình tự động điều chỉnh theo kích thước của cửa sổ xem. Aspose.PDF for .NET cung cấp nhiều tính năng mạnh mẽ khác để tạo và thao tác với tệp PDF. Tôi khuyến khích bạn khám phá thêm thư viện này để khám phá tất cả các khả năng của nó.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của tính năng Auto Fit To Window trong quá trình tạo PDF là gì?

Trả lời: Tính năng Auto Fit To Window trong quá trình tạo PDF đảm bảo rằng bố cục của tài liệu PDF tự động điều chỉnh theo kích thước của cửa sổ trình đọc PDF mà người dùng sử dụng. Điều này cho phép xem tốt hơn và đảm bảo rằng nội dung phù hợp hoàn hảo trong khu vực xem có sẵn.

#### Hỏi: Tôi có thể tùy chỉnh hình thức của bảng, chẳng hạn như cỡ chữ và màu sắc không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của bảng trong tài liệu PDF bằng Aspose.PDF for .NET. Đoạn mã được cung cấp minh họa cách đặt các thuộc tính như viền ô, lề và độ rộng cột. Bạn có thể tùy chỉnh thêm kích thước phông chữ, màu sắc và các khía cạnh kiểu dáng khác của bảng cũng như nội dung của bảng.

#### Câu hỏi: Làm cách nào để tích hợp Aspose.PDF cho .NET vào dự án C# của tôi?

Đáp: Để sử dụng Aspose.PDF cho .NET trong dự án C# của bạn, trước tiên bạn cần cài đặt thư viện Aspose.PDF cho .NET trên máy của mình. Sau đó, bạn có thể thêm tham chiếu đến thư viện trong dự án C# của mình. Cuối cùng, nhập các không gian tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp cho .NET.

#### Câu hỏi: Aspose.PDF cho .NET có tương thích với các ứng dụng .NET Core không?

Trả lời: Có, Aspose.PDF cho .NET tương thích với các ứng dụng .NET Core. Nó hỗ trợ nhiều nền tảng .NET khác nhau, bao gồm .NET Framework, .NET Core và .NET 5.0+.

#### Hỏi: Tôi có thể thêm nhiều bảng vào tài liệu PDF không?

Đáp: Có, bạn có thể thêm nhiều bảng vào tài liệu PDF bằng cách làm theo các bước tương tự như được minh họa trong đoạn mã. Đơn giản chỉ cần tạo các phiên bản mới của`Aspose.Pdf.Table` lớp và thêm chúng vào các phần hoặc trang khác nhau của tài liệu PDF.