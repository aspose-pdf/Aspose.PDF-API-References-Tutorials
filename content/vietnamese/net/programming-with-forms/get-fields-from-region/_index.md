---
title: Lấy các trường từ vùng trong tệp PDF
linktitle: Lấy các trường từ vùng trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng lấy các trường từ một vùng cụ thể trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 130
url: /vi/net/programming-with-forms/get-fields-from-region/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách lấy các trường của một vùng cụ thể trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# từng bước để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tệp PDF

Mở tệp PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Bước 3: Tạo một đối tượng hình chữ nhật để giới hạn vùng

Tạo một đối tượng hình chữ nhật để giới hạn vùng mà bạn muốn lấy các trường:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Bước 4: Nhận mẫu PDF

Nhận dạng PDF của tài liệu:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Bước 5: Lấy các trường trong vùng hình chữ nhật

Lấy các trường nằm trong vùng hình chữ nhật đã chỉ định:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Bước 6: Hiển thị tên trường và giá trị

Lặp lại các trường kết quả và hiển thị tên và giá trị của chúng:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Mã nguồn mẫu để Lấy trường từ vùng bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tệp pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Tạo đối tượng hình chữ nhật để lấy các trường trong khu vực đó
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Nhận mẫu PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Lấy các trường trong vùng hình chữ nhật
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Hiển thị tên và giá trị trường
foreach (Field field in fields)
{
	// Hiển thị thuộc tính vị trí hình ảnh cho tất cả các vị trí
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lấy các trường của một vùng cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng trích xuất các trường nằm trong một vùng hình chữ nhật nhất định của tài liệu PDF bằng Aspose.PDF.

### Câu hỏi thường gặp

#### H: Tôi có thể sử dụng phương pháp này để lấy các trường từ một vùng không phải hình chữ nhật trong tài liệu PDF không?

 A: Không, phương pháp được cung cấp`GetFieldsInRect` được thiết kế riêng để truy xuất các trường nằm trong vùng hình chữ nhật trong tài liệu PDF. Nếu bạn cần trích xuất các trường từ vùng không phải hình chữ nhật, bạn sẽ cần triển khai logic tùy chỉnh để xác định và trích xuất các trường dựa trên các tiêu chí khác, chẳng hạn như tọa độ hoặc tên trường.

#### H: Làm thế nào tôi có thể thay đổi kích thước hoặc vị trí của hình chữ nhật để lấy các trường từ một vùng khác?

 A: Để lấy các trường từ một vùng khác, bạn có thể sửa đổi`Aspose.Pdf.Rectangle` các tham số của đối tượng được sử dụng để xác định hình chữ nhật giới hạn.`Rectangle` hàm tạo có bốn tham số:`x`, `y`, `width` , Và`height`biểu diễn tọa độ góc trên bên trái và kích thước của hình chữ nhật. Việc điều chỉnh các tham số này sẽ thay đổi vùng mà các trường được trích xuất.

#### H: Nếu không có trường nào trong vùng hình chữ nhật được chỉ định thì sao?

 A: Nếu không có trường nào trong vùng hình chữ nhật được chỉ định, thì`GetFieldsInRect` phương pháp sẽ trả về một mảng rỗng. Bạn có thể kiểm tra độ dài của mảng để xác định xem có trường nào trong vùng không.

#### H: Tôi có thể lấy các trường từ các vùng chồng lấn trong tài liệu PDF không?

 A: Có, bạn có thể lấy các trường từ các vùng chồng lấn trong một tài liệu PDF bằng cách tạo nhiều`Aspose.Pdf.Rectangle` các đối tượng và gọi`GetFieldsInRect` phương pháp cho từng vùng. Các vùng chồng lấn sẽ được xử lý độc lập và bạn sẽ nhận được các mảng trường riêng biệt cho từng vùng.

#### H: Có thể lấy các trường từ một trang cụ thể hoặc nhiều trang trong tài liệu PDF không?

A: Có, bạn có thể lấy các trường từ một trang cụ thể hoặc nhiều trang trong một tài liệu PDF. Để thực hiện điều này, bạn có thể tải tài liệu PDF, truy cập các trang mong muốn bằng cách sử dụng`doc.Pages` bộ sưu tập, và sau đó áp dụng`GetFieldsInRect` phương pháp áp dụng cho từng vùng cụ thể của trang.