---
title: Tạo hình chữ nhật với màu Alpha
linktitle: Tạo hình chữ nhật với màu Alpha
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tạo hình chữ nhật có màu trong suốt bằng Aspose.PDF cho .NET. Hướng dẫn từng bước để tùy chỉnh độ trong suốt.
type: docs
weight: 60
url: /vi/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# sau để tạo hình chữ nhật có màu alpha bằng Aspose.PDF cho .NET.

Đảm bảo bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình trước khi bắt đầu. Ngoài ra còn có kiến thức cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã nguồn được cung cấp, bạn cần chỉ định thư mục mà bạn muốn lưu tệp PDF kết quả. Thay đổi biến "dataDir" thành thư mục mong muốn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo đối tượng tài liệu và thêm trang

Chúng tôi tạo một thể hiện của lớp Tài liệu và thêm một trang vào tài liệu này.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Bước 3: Tạo đối tượng đồ thị và hình chữ nhật

Chúng ta tạo một đối tượng Graph với các kích thước được chỉ định và một hình chữ nhật với các kích thước cụ thể.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Bước 4: Thiết lập màu alpha cho hình chữ nhật

Chúng ta có thể chỉ định màu alpha cho hình chữ nhật bằng phương thức FromArgb của lớp System.draw.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Bước 5: Thêm hình chữ nhật vào đối tượng đồ thị

Chúng ta thêm hình chữ nhật vào bộ sưu tập hình dạng của đối tượng Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Bước 6: Tạo hình chữ nhật thứ hai với màu alpha khác

Chúng ta tạo một hình chữ nhật thứ hai với các kích thước cụ thể và một màu alpha khác.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Bước 7: Thêm đối tượng đồ thị vào trang

Chúng tôi thêm đối tượng Graph vào bộ sưu tập Đoạn văn của đối tượng Trang.

```csharp
page.Paragraphs.Add(canvas);
```

## Bước 8: Lưu tệp PDF kết quả

Cuối cùng, chúng tôi lưu tệp PDF kết quả có tên "CreatRectangleWithAlphaColor_out.pdf" trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Mã nguồn mẫu để Tạo hình chữ nhật bằng màu Alpha bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Khởi tạo phiên bản tài liệu
Document doc = new Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Tạo phiên bản đồ thị
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tạo đối tượng hình chữ nhật với kích thước cụ thể
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Đặt màu tô biểu đồ từ cấu trúc System.draw.Color từ giá trị ARGB 32 bit
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Thêm đối tượng hình chữ nhật vào bộ sưu tập hình dạng của phiên bản Biểu đồ
canvas.Shapes.Add(rect);
// Tạo đối tượng hình chữ nhật thứ hai
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Thêm phiên bản biểu đồ vào bộ sưu tập đoạn của đối tượng trang
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Lưu tệp PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách tạo hình chữ nhật có màu alpha bằng Aspose.PDF cho .NET. Bây giờ bạn có thể sử dụng kiến thức này để tạo các hình dạng hình học với màu sắc trong suốt trong tệp PDF của mình.

## Câu hỏi thường gặp

#### Hỏi: Mục đích của hướng dẫn này là gì?

Đáp: Hướng dẫn này nhằm mục đích hướng dẫn bạn trong quá trình tạo hình chữ nhật có màu alpha bằng Aspose.PDF cho .NET. Bạn sẽ tìm hiểu cách thêm các hình dạng hình học có màu trong suốt vào tệp PDF của mình.

#### Hỏi: Những điều kiện tiên quyết nào được yêu cầu trước khi bắt đầu?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã cài đặt thư viện Aspose.PDF và thiết lập môi trường phát triển của mình. Ngoài ra, nên có hiểu biết cơ bản về lập trình C#.

#### Hỏi: Làm cách nào để chỉ định thư mục lưu tệp PDF?

Trả lời: Trong mã nguồn được cung cấp, bạn có thể sửa đổi biến "dataDir" để chỉ ra thư mục mà bạn muốn lưu tệp PDF kết quả.

#### Câu hỏi: Mục đích của đối tượng Graph và Rectangle là gì?

Đáp: Đối tượng Biểu đồ hoạt động như một vùng chứa để vẽ các phần tử, trong khi Hình chữ nhật biểu thị hình dạng hình học mà bạn sẽ thêm vào tệp PDF.

#### Câu hỏi: Làm cách nào để thiết lập màu alpha cho hình chữ nhật?

Đáp: Bạn có thể chỉ định màu alpha cho hình chữ nhật bằng cách sử dụng`FillColor` tài sản của`GraphInfo` đối tượng và`Color.FromRgb` phương thức có giá trị ARGB.

#### Câu hỏi: Tôi có thể tạo nhiều hình chữ nhật với các màu alpha khác nhau không?

Đáp: Có, bạn có thể tạo nhiều hình chữ nhật với các màu alpha khác nhau bằng cách làm theo các bước tương tự như được minh họa trong hướng dẫn.

#### Hỏi: Làm cách nào để lưu tệp PDF thu được sau khi tạo hình chữ nhật có màu alpha?

 Đáp: Sau khi tạo các hình chữ nhật có màu alpha, bạn có thể lưu tệp PDF thu được bằng cách sử dụng`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` dòng trong mã nguồn được cung cấp.