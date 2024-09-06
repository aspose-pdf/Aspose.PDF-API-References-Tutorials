---
title: Lấy lại trường biểu mẫu theo thứ tự tab
linktitle: Lấy lại trường biểu mẫu theo thứ tự tab
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách lấy các trường biểu mẫu theo thứ tự tab bằng Aspose.PDF cho .NET.
type: docs
weight: 240
url: /vi/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Khi làm việc với các tài liệu PDF trong C# bằng Aspose.PDF cho .NET, bạn có thể gặp phải tình huống cần truy xuất các trường biểu mẫu theo thứ tự tab cụ thể. Điều này có thể hữu ích khi bạn muốn thực hiện các thao tác trên các trường biểu mẫu dựa trên trình tự tab của chúng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách truy xuất các trường biểu mẫu theo thứ tự tab bằng Aspose.PDF cho .NET.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng đủ các điều kiện tiên quyết sau:

- Visual Studio được cài đặt trên hệ thống của bạn
- Đã cài đặt thư viện Aspose.PDF cho .NET

Bây giờ, chúng ta hãy tìm hiểu các bước để lấy các trường biểu mẫu theo thứ tự tab.

## Bước 1: Thiết lập thư mục tài liệu

 Để bắt đầu, bạn cần thiết lập thư mục tài liệu nơi tài liệu PDF của bạn được lưu trữ. Bạn có thể thực hiện việc này bằng cách chỉ định đường dẫn đến thư mục trong`dataDir` biến đổi.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải tài liệu PDF

 Trong bước này, chúng tôi sẽ tải tài liệu PDF bằng Aspose.PDF cho .NET.`Document` Lớp này cung cấp khả năng tải và thao tác với các tài liệu PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Đây,`"Test2.pdf"`là tên của tài liệu PDF bạn muốn tải. Đảm bảo tài liệu có trong thư mục tài liệu đã chỉ định.

## Bước 3: Lấy các trường biểu mẫu theo thứ tự tab

 Để lấy các trường biểu mẫu theo thứ tự tab, chúng ta cần truy cập`FieldsInTabOrder` tài sản của`Page` lớp. Thuộc tính này trả về danh sách các trường biểu mẫu được sắp xếp theo trình tự tab của chúng.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Trong đoạn mã trên, chúng tôi lấy các trường biểu mẫu từ trang thứ hai (`doc.Pages[1]` ) và lặp lại qua từng trường để nối các tên một phần của chúng vào`s` biến. Bạn có thể sửa đổi đoạn mã này dựa trên các yêu cầu cụ thể của mình.

## Bước 4: Sửa đổi thứ tự Tab

 Nếu bạn muốn sửa đổi thứ tự tab của các trường biểu mẫu, bạn có thể thực hiện bằng cách truy cập`TabOrder` thuộc tính của mỗi trường và gán giá trị thứ tự tab mới. Sau đây là một ví dụ:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Trong đoạn mã trên, chúng tôi gán các giá trị thứ tự tab mới cho ba trường biểu mẫu (`doc.Form[3]`, `doc.Form[1]` , Và`doc.Form[2]`). Điều chỉnh chỉ số trường và giá trị thứ tự tab theo yêu cầu cụ thể của bạn.

## Bước 5: Lưu tài liệu đã sửa đổi

 Sau khi sửa đổi thứ tự tab của các trường biểu mẫu, bạn cần lưu tài liệu đã sửa đổi. Bạn có thể thực hiện việc này bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Đây,`"39522_out.pdf"` là tên của tệp đầu ra nơi tài liệu đã sửa đổi sẽ được lưu. Chỉ định tên và vị trí mong muốn cho tệp đầu ra.

### Mã nguồn mẫu cho Lấy trường biểu mẫu theo thứ tự tab bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lấy các trường biểu mẫu theo thứ tự tab bằng Aspose.PDF cho .NET. Chúng tôi đã đề cập đến các bước liên quan đến việc tải tài liệu PDF, lấy các trường biểu mẫu theo thứ tự tab, sửa đổi thứ tự tab và lưu tài liệu đã sửa đổi. Bằng cách làm theo các bước này, bạn có thể làm việc hiệu quả với các trường biểu mẫu và tùy chỉnh trình tự tab của chúng theo yêu cầu của bạn.


### Câu hỏi thường gặp

#### H: Làm thế nào tôi có thể sử dụng các trường biểu mẫu đã lấy trong mã C# của mình để xử lý thêm?

 A: Bạn có thể sử dụng các trường biểu mẫu đã truy xuất trong mã C# của mình bằng cách truy cập các thuộc tính của chúng như`Value`, `Name`, `Rect`v.v. Các thuộc tính này cho phép bạn đọc và sửa đổi dữ liệu trường biểu mẫu khi cần.

#### H: Tôi có thể lấy các trường biểu mẫu từ tất cả các trang của tài liệu PDF theo thứ tự tab không?

 A: Có, bạn có thể lấy các trường biểu mẫu từ tất cả các trang của tài liệu PDF bằng cách lặp qua từng trang và truy cập`FieldsInTabOrder` thuộc tính như được hiển thị trong hướng dẫn. Điều này sẽ cung cấp cho bạn các trường biểu mẫu được sắp xếp theo trình tự tab của chúng trên tất cả các trang.

#### H: Có thể chỉ lấy các loại trường biểu mẫu cụ thể, chẳng hạn như trường văn bản hoặc hộp kiểm, theo thứ tự tab không?

A: Có, bạn có thể lọc các trường biểu mẫu dựa trên loại của chúng, chẳng hạn như trường văn bản hoặc hộp kiểm, sau khi truy xuất chúng theo thứ tự tab. Bạn có thể sử dụng các câu lệnh có điều kiện để kiểm tra loại của từng trường biểu mẫu và xử lý chúng cho phù hợp.

#### H: Tôi có thể lấy các trường biểu mẫu dựa trên tên thay vì thứ tự tab không?

 A: Có, bạn có thể lấy các trường biểu mẫu dựa trên tên của chúng bằng cách sử dụng`doc.Form` bộ sưu tập và chỉ định tên trường làm chỉ mục. Ví dụ,`doc.Form["fieldName"]`sẽ lấy trường biểu mẫu có tên đã chỉ định.

#### H: Aspose.PDF cho .NET có hỗ trợ làm việc với các tài liệu PDF được mã hóa không?

A: Có, Aspose.PDF for .NET cung cấp hỗ trợ làm việc với các tài liệu PDF được mã hóa. Bạn có thể tải và thao tác các tệp PDF được mã hóa bằng các tham số mật khẩu phù hợp.