---
title: Làm phẳng các biểu mẫu trong tài liệu PDF
linktitle: Làm phẳng các biểu mẫu trong tài liệu PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng làm phẳng các biểu mẫu trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 100
url: /vi/net/programming-with-forms/flatten-forms/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách làm phẳng biểu mẫu bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn C# để hướng dẫn bạn thực hiện quy trình này.

## Bước 1: Chuẩn bị

Trước tiên, hãy đảm bảo bạn đã nhập các thư viện cần thiết và đặt đường dẫn đến thư mục tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải mẫu PDF nguồn

Tải mẫu PDF nguồn:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 3: Làm phẳng các hình thức

Trước tiên hãy kiểm tra xem có bất kỳ trường biểu mẫu nào trong tài liệu không. Nếu vậy, hãy lặp qua từng trường và áp dụng làm phẳng:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Bước 4: Lưu tài liệu đã cập nhật

Lưu tài liệu PDF đã cập nhật:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Flatten Forms bằng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải mẫu PDF nguồn
Document doc = new Document(dataDir + "input.pdf");
// Làm phẳng các hình thức
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Lưu tài liệu đã cập nhật
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách làm phẳng biểu mẫu bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng làm phẳng các biểu mẫu trong tài liệu PDF của mình, làm cho các trường không thể chỉnh sửa và hợp nhất các chú thích với nội dung tài liệu.

### Câu hỏi thường gặp

#### Câu hỏi: "Dạng phẳng" nghĩa là gì trong Aspose.PDF dành cho .NET?

Trả lời: Làm phẳng biểu mẫu trong Aspose.PDF cho .NET đề cập đến quá trình tạo các trường biểu mẫu trong tài liệu PDF không thể chỉnh sửa và hợp nhất các chú thích (chẳng hạn như trường biểu mẫu, chú thích và chữ ký điện tử) với nội dung của tài liệu. Khi biểu mẫu được làm phẳng, người dùng không thể sửa đổi các trường biểu mẫu và giao diện trực quan của các trường biểu mẫu sẽ trở thành một phần nội dung tĩnh của tài liệu PDF.

#### Câu hỏi: Tôi có thể đảo ngược quá trình làm phẳng và làm cho các trường biểu mẫu có thể chỉnh sửa lại được không?

Trả lời: Không, sau khi các trường biểu mẫu được làm phẳng, quy trình này sẽ không thể đảo ngược khi sử dụng Aspose.PDF cho .NET. Việc làm phẳng sẽ hợp nhất vĩnh viễn giao diện của trường biểu mẫu với nội dung của tệp PDF và các thành phần trường biểu mẫu riêng lẻ không thể truy cập hoặc chỉnh sửa được nữa.

#### Câu hỏi: Khi nào tôi nên làm phẳng biểu mẫu trong tài liệu PDF?

Đáp: Làm phẳng biểu mẫu rất hữu ích khi bạn muốn giữ nguyên hình thức trực quan của các trường biểu mẫu và chú thích trong tài liệu PDF đồng thời ngăn người dùng sửa đổi dữ liệu. Điều này thường được thực hiện khi bạn muốn chia sẻ tài liệu PDF với dữ liệu biểu mẫu điền sẵn hoặc chú thích mà người nhận không nên thay đổi.

#### Câu hỏi: Các biểu mẫu làm phẳng có ảnh hưởng đến các chú thích khác, chẳng hạn như chữ ký điện tử không?

Đáp: Có, các biểu mẫu làm phẳng sẽ hợp nhất tất cả các chú thích, bao gồm cả chữ ký điện tử, với nội dung của PDF. Sau khi các biểu mẫu được làm phẳng, mọi chữ ký điện tử hiện có sẽ trở thành một phần vĩnh viễn của tài liệu và người dùng không thể sửa đổi hoặc xóa chúng.

#### Câu hỏi: Tôi có thể làm phẳng có chọn lọc các trường biểu mẫu cụ thể và để các trường khác có thể chỉnh sửa được không?

Đáp: Có, bạn có thể làm phẳng có chọn lọc các trường biểu mẫu cụ thể trong tài liệu PDF trong khi vẫn để các trường khác có thể chỉnh sửa. Thay vì sử dụng mã để làm phẳng tất cả các trường biểu mẫu, bạn có thể chọn chỉ làm phẳng các trường biểu mẫu mong muốn dựa trên tên của chúng hoặc các tiêu chí khác.