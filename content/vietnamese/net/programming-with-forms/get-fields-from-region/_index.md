---
title: Nhận các trường từ khu vực trong tệp PDF
linktitle: Nhận các trường từ khu vực trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng lấy các trường từ một vùng cụ thể trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 130
url: /vi/net/programming-with-forms/get-fields-from-region/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách lấy các trường của một vùng cụ thể trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu của mình:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Mở tệp PDF

Mở tệp PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Bước 3: Tạo đối tượng hình chữ nhật để giới hạn vùng

Tạo một đối tượng hình chữ nhật để giới hạn vùng mà bạn muốn lấy các trường:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Bước 4: Lấy mẫu PDF

Lấy dạng PDF của tài liệu:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Bước 5: Lấy các trường trong vùng hình chữ nhật

Lấy các trường nằm trong vùng hình chữ nhật được chỉ định:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Bước 6: Hiển thị tên và giá trị trường

Lặp lại qua các trường kết quả và hiển thị tên cũng như giá trị của chúng:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Mã nguồn mẫu cho Nhận trường từ khu vực bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tập tin pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Tạo đối tượng hình chữ nhật để lấy các trường trong khu vực đó
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Nhận mẫu PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Nhận các trường trong khu vực hình chữ nhật
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Hiển thị tên và giá trị trường
foreach (Field field in fields)
{
	// Hiển thị thuộc tính vị trí hình ảnh cho tất cả các vị trí
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách lấy các trường của một vùng cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng trích xuất các trường nằm trong khu vực hình chữ nhật nhất định của tài liệu PDF bằng Aspose.PDF.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể sử dụng phương pháp này để lấy các trường từ vùng không phải hình chữ nhật trong tài liệu PDF không?

 A: Không, phương pháp được cung cấp`GetFieldsInRect` được thiết kế đặc biệt để truy xuất các trường nằm trong vùng hình chữ nhật trong tài liệu PDF. Nếu cần trích xuất các trường từ một vùng không phải hình chữ nhật, bạn sẽ cần triển khai logic tùy chỉnh để xác định và trích xuất các trường dựa trên các tiêu chí khác, chẳng hạn như tọa độ hoặc tên trường.

#### Câu hỏi: Làm cách nào tôi có thể sửa đổi kích thước hoặc vị trí của hình chữ nhật để lấy các trường từ một vùng khác?

 Đáp: Để lấy các trường từ một khu vực khác, bạn có thể sửa đổi`Aspose.Pdf.Rectangle` các tham số của đối tượng được sử dụng để xác định hình chữ nhật bao quanh. Các`Rectangle` hàm tạo có bốn tham số:`x`, `y`, `width` , Và`height`đại diện cho tọa độ góc trên bên trái và kích thước của hình chữ nhật. Việc điều chỉnh các tham số này sẽ thay đổi vùng mà các trường được trích xuất.

#### Câu hỏi: Điều gì sẽ xảy ra nếu không có trường nào trong vùng hình chữ nhật được chỉ định?

 A: Nếu không có trường nào trong vùng hình chữ nhật được chỉ định,`GetFieldsInRect` phương thức sẽ trả về một mảng trống. Bạn có thể kiểm tra độ dài của mảng để xác định xem có trường nào trong vùng không.

#### Câu hỏi: Tôi có thể lấy các trường từ các vùng chồng chéo trong tài liệu PDF không?

 Đáp: Có, bạn có thể lấy các trường từ các vùng chồng chéo trong tài liệu PDF bằng cách tạo nhiều trường`Aspose.Pdf.Rectangle` các đối tượng và gọi`GetFieldsInRect` phương pháp cho từng người trong số họ. Các vùng chồng chéo sẽ được xử lý độc lập và bạn sẽ nhận được các mảng trường riêng biệt cho từng vùng.

#### Hỏi: Có thể lấy các trường từ một trang cụ thể hoặc nhiều trang trong tài liệu PDF không?

Đáp: Có, bạn có thể lấy các trường từ một trang cụ thể hoặc nhiều trang trong tài liệu PDF. Để đạt được điều này, bạn có thể tải tài liệu PDF, truy cập các trang mong muốn bằng cách sử dụng`doc.Pages` thu thập, sau đó áp dụng`GetFieldsInRect` phương pháp cho khu vực cụ thể của mỗi trang.