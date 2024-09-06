---
title: Thêm Xóa Javascript Vào Tài Liệu PDF
linktitle: Thêm Xóa Javascript Vào Tài Liệu
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thêm và xóa JavaScript vào tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với hướng dẫn mã cho tập lệnh cấp tài liệu.
type: docs
weight: 30
url: /vi/net/programming-with-document/addremovejavascripttodoc/
---
## Giới thiệu

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách sử dụng Aspose.PDF cho .NET để chèn JavaScript vào tệp PDF và cách xóa JavaScript khi cần thiết. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ cách thao tác JavaScript trong tệp PDF một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, bạn cần thiết lập một số thứ sau:

1.  Aspose.PDF cho .NET: Bạn sẽ cần thư viện Aspose.PDF cho .NET được cài đặt trong dự án của bạn. Nếu bạn chưa có, hãy lấy thư viện từ[Trang tải xuống Aspose.PDF cho .NET](https://releases.aspose.com/pdf/net/).
2. IDE hoặc Trình soạn thảo văn bản: Bạn có thể sử dụng bất kỳ IDE nào tương thích với .NET như Visual Studio.
3. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn đã thành thạo C# và quen thuộc với thao tác PDF.
4. Giấy phép: Đảm bảo áp dụng giấy phép hợp lệ để tránh các hạn chế. Bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).

## Nhập gói

Để bắt đầu sử dụng Aspose.PDF cho .NET, bạn sẽ cần nhập các không gian tên cần thiết vào dự án của mình. Sau đây là cách thực hiện:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 Hai không gian tên này rất cần thiết.`Aspose.Pdf` cho phép bạn làm việc với các tài liệu PDF, trong khi`System.Collections` sẽ được sử dụng để xử lý các khóa JavaScript.

Chúng ta hãy chia nhỏ toàn bộ quá trình thêm và xóa JavaScript khỏi PDF thành các bước dễ thực hiện.

## Bước 1: Khởi tạo một tài liệu PDF mới

Điều đầu tiên bạn cần làm là tạo một tài liệu PDF mới. Tài liệu này sẽ đóng vai trò là khung trống để thêm JavaScript.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 Ở đây, chúng ta đang khởi tạo một cái mới`Document` đối tượng và thêm một trang trống vào đó. Hãy coi đây là nền tảng cho PDF của bạn.

## Bước 2: Thêm JavaScript vào PDF

Bây giờ chúng ta đã có một tài liệu, đã đến lúc thêm một số JavaScript vào đó. JavaScript trong PDF có thể được sử dụng để thêm các hành vi tùy chỉnh, chẳng hạn như cảnh báo hoặc xác thực biểu mẫu.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

Trong đoạn mã này, chúng tôi đang thêm hai hàm JavaScript (`func1` Và`func2` ) vào PDF. Các hàm này có thể thực hiện nhiều tác vụ khác nhau, tùy thuộc vào nhu cầu của bạn. Ở đây, chúng tôi chỉ gọi một hàm giữ chỗ có tên là`hello()`.

## Bước 3: Lưu PDF bằng JavaScript

Sau khi đã thêm JavaScript mong muốn, đã đến lúc lưu PDF.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 Điều này sẽ lưu tài liệu bằng JavaScript dưới tên`AddJavascript.pdf` trong thư mục được chỉ định (`dataDir`).

## Bước 4: Tải và xem JavaScript trong PDF hiện có

Giả sử bạn cần kiểm tra hoặc sửa đổi các hàm JavaScript trong một tệp PDF hiện có. Bước đầu tiên là tải tệp PDF và truy cập các khóa JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 Chúng tôi đang tải các hiện có`AddJavascript.pdf` và lưu trữ các khóa JavaScript trong một danh sách.`Keys` thuộc tính trả về tên của tất cả các hàm JavaScript được đính kèm vào tài liệu.

## Bước 5: Hiển thị các hàm JavaScript

Tiếp theo, chúng ta có thể lặp lại các hàm JavaScript để xem những gì có sẵn trong tài liệu.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

Lệnh này sẽ in ra tên từng hàm JavaScript và mã tương ứng của nó vào bảng điều khiển. Lệnh này hữu ích nếu bạn muốn xác minh những hàm nào hiện có trong tài liệu.

## Bước 6: Xóa JavaScript khỏi PDF

 Bây giờ, giả sử bạn muốn xóa một hàm JavaScript cụ thể, như`func1`. Sau đây là cách bạn có thể thực hiện điều đó:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 Các`Remove` phương thức này lấy tên hàm JavaScript làm đối số và xóa nó khỏi tài liệu.

## Bước 7: Xác minh việc xóa JavaScript

 Sau khi xóa JavaScript, bạn có thể in lại các hàm còn lại để xác nhận rằng`func1` đã được xóa thành công.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

Phần cuối cùng của mã này đảm bảo mọi thứ đều đúng vị trí và các hàm JavaScript được cập nhật chính xác.

## Phần kết luận

Xin chúc mừng! Bạn vừa học cách thêm và xóa JavaScript khỏi tài liệu PDF bằng Aspose.PDF cho .NET. Tính năng mạnh mẽ này có thể được sử dụng cho nhiều tác vụ khác nhau, từ thêm tin nhắn động đến thực hiện các phép tính hoặc xác thực tùy chỉnh. Bằng cách thao tác JavaScript trong PDF, bạn có thể cải thiện đáng kể trải nghiệm của người dùng.

## Câu hỏi thường gặp

### Tôi có thể thêm nhiều hàm JavaScript vào một tệp PDF không?
 Chắc chắn rồi! Bạn có thể thêm nhiều hàm JavaScript tùy theo nhu cầu bằng cách sử dụng`doc.JavaScript` bộ sưu tập.

### Điều gì xảy ra nếu tôi cố xóa một hàm JavaScript không tồn tại?
 Nếu chức năng không tồn tại,`Remove` phương pháp này sẽ không gây ra lỗi, nhưng nó cũng không xóa bất cứ thứ gì.

### Có thể chạy JavaScript ngay khi mở tệp PDF không?
Có! Bạn có thể cấu hình JavaScript để chạy trên một số kích hoạt nhất định, chẳng hạn như mở tài liệu hoặc nhấp vào nút.

### Tôi có thể chỉnh sửa JavaScript sau khi đã thêm vào PDF không?
Có, bạn có thể tải tệp PDF hiện có, truy cập JavaScript của tệp đó, sửa đổi mã và lưu lại tài liệu.

### Việc xóa JavaScript có ảnh hưởng đến phần còn lại của nội dung PDF không?
Không, việc xóa JavaScript chỉ ảnh hưởng đến tập lệnh. Nội dung của PDF vẫn không thay đổi.