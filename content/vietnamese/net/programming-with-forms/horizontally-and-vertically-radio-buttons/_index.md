---
title: Nút radio theo chiều ngang và chiều dọc
linktitle: Nút radio theo chiều ngang và chiều dọc
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo các nút radio căn chỉnh theo chiều ngang và chiều dọc trong PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 180
url: /vi/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Giới thiệu

Tạo biểu mẫu PDF tương tác có thể cải thiện đáng kể trải nghiệm của người dùng, đặc biệt là khi thu thập thông tin. Một trong những thành phần biểu mẫu phổ biến nhất là nút radio, cho phép người dùng chọn một tùy chọn từ một tập hợp. Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo nút radio căn chỉnh theo chiều ngang và chiều dọc bằng Aspose.PDF cho .NET. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn từng bước trong quy trình, đảm bảo bạn hiểu rõ từng phần.

## Điều kiện tiên quyết

Trước khi bắt đầu viết mã, bạn cần có một số điều kiện tiên quyết sau:

1.  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF. Bạn có thể tải xuống từ[địa điểm](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Môi trường phát triển nơi bạn có thể viết và kiểm tra mã của mình.
3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu các đoạn mã tốt hơn.

## Nhập gói

Để bắt đầu, bạn cần nhập các gói cần thiết vào dự án C# của mình. Sau đây là cách bạn có thể thực hiện:

### Tạo một dự án mới

Mở Visual Studio và tạo một dự án C# mới. Bạn có thể chọn Ứng dụng Console để đơn giản hơn.

### Thêm tham chiếu Aspose.PDF

1. Nhấp chuột phải vào dự án của bạn trong Solution Explorer.
2. Chọn "Quản lý gói NuGet".
3. Tìm kiếm "Aspose.PDF" và cài đặt phiên bản mới nhất.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Bây giờ bạn đã thiết lập mọi thứ, hãy phân tích mã để tạo các nút radio căn chỉnh theo chiều ngang và chiều dọc.

## Bước 1: Thiết lập thư mục tài liệu

Ở bước này, chúng tôi sẽ xác định đường dẫn đến thư mục lưu trữ tài liệu PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế mà bạn muốn lưu tệp PDF của mình. Điều này rất quan trọng vì nó cho chương trình biết nơi tìm tệp đầu vào và nơi lưu tệp đầu ra.

## Bước 2: Tải tài liệu PDF hiện có

 Tiếp theo, chúng ta cần tải tài liệu PDF mà chúng ta sẽ làm việc. Điều này được thực hiện bằng cách sử dụng`FormEditor` lớp học.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Ở đây, chúng ta tạo một thể hiện của`FormEditor` và liên kết nó với một tệp PDF hiện có có tên`input.pdf`. Đảm bảo rằng tập tin này tồn tại trong thư mục bạn chỉ định.

## Bước 3: Cấu hình Thuộc tính Nút Radio

Bây giờ, hãy thiết lập một số thuộc tính cho các nút radio của chúng ta. Bao gồm khoảng cách giữa các nút, hướng của chúng và kích thước của chúng.

```csharp
formEditor.RadioGap = 4; // Khoảng cách giữa các tùy chọn nút radio
formEditor.RadioHoriz = true; // Đặt thành true để căn chỉnh theo chiều ngang
formEditor.RadioButtonItemSize = 20; // Kích thước của nút radio
formEditor.Facade.BorderWidth = 1; // Chiều rộng đường viền
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Màu viền
```

 Các thuộc tính này sẽ giúp xác định cách các nút radio sẽ xuất hiện trong PDF.`RadioGap` thuộc tính kiểm soát khoảng cách giữa các nút, trong khi`RadioHoriz` xác định cách bố trí của chúng.

## Bước 4: Thêm nút radio ngang

Bây giờ, chúng ta hãy thêm các nút tùy chọn nằm ngang vào PDF.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 Trong mã này, chúng tôi xác định các mục cho các nút radio và thêm chúng vào PDF.`AddField`phương pháp này sử dụng một số tham số, bao gồm loại trường, tên trường và tọa độ để đặt.

## Bước 5: Thêm nút radio dọc

Tiếp theo, chúng ta sẽ thêm các nút radio dọc. Để làm điều này, chúng ta cần thay đổi hướng trở lại theo chiều dọc.

```csharp
formEditor.RadioHoriz = false; // Đặt thành false để căn chỉnh theo chiều dọc
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Giống như trước, chúng ta xác định các mục và thêm chúng vào PDF, nhưng lần này chúng sẽ được căn chỉnh theo chiều dọc.

## Bước 6: Lưu tài liệu PDF

Cuối cùng, chúng ta cần lưu tài liệu PDF đã chỉnh sửa.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Mã này lưu PDF với các nút radio mới được thêm vào. Hãy đảm bảo kiểm tra thư mục đã chỉ định cho tệp đầu ra.

## Phần kết luận

Tạo các nút radio trong PDF bằng Aspose.PDF cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng thêm cả các nút radio được căn chỉnh theo chiều ngang và chiều dọc vào biểu mẫu PDF của mình. Điều này không chỉ tăng cường tính tương tác của tài liệu mà còn cải thiện trải nghiệm người dùng nói chung. Vì vậy, hãy thử xem!

## Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?
Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu PDF theo chương trình.

### Tôi có thể sử dụng Aspose.PDF miễn phí không?
 Có, Aspose cung cấp phiên bản dùng thử miễn phí mà bạn có thể sử dụng để đánh giá thư viện. Bạn có thể tải xuống[đây](https://releases.aspose.com/).

### Làm thế nào để tôi nhận được hỗ trợ cho Aspose.PDF?
 Bạn có thể nhận được hỗ trợ bằng cách truy cập[Diễn đàn Aspose](https://forum.aspose.com/c/pdf/10).

### Có thể tạo các thành phần biểu mẫu khác bằng Aspose.PDF không?
Chắc chắn rồi! Aspose.PDF hỗ trợ nhiều thành phần biểu mẫu khác nhau, bao gồm trường văn bản, hộp kiểm và danh sách thả xuống.

### Tôi có thể mua Aspose.PDF cho .NET ở đâu?
 Bạn có thể mua Aspose.PDF cho .NET từ[trang mua hàng](https://purchase.aspose.com/buy).