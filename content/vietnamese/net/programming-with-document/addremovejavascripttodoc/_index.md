---
title: Thêm vào Xóa Javascript vào tài liệu PDF
linktitle: Thêm Xóa Javascript vào tài liệu
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm và xóa JavaScript vào tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với hướng dẫn mã cho tập lệnh ở cấp độ tài liệu.
type: docs
weight: 30
url: /vi/net/programming-with-document/addremovejavascripttodoc/
---
Để thêm và xóa JavaScript vào tài liệu PDF, chúng tôi sẽ sử dụng thư viện Aspose.PDF cho .NET. Thư viện mạnh mẽ này cho phép chúng ta thao tác với các tệp PDF trong các ứng dụng .NET. Hãy làm theo hướng dẫn từng bước bên dưới để thêm và xóa JavaScript bằng Aspose.PDF cho .NET.

## Bước 1: Tạo một tài liệu PDF mới

 Bắt đầu bằng cách tạo một phiên bản mới của`Document` lớp được cung cấp bởi Aspose.PDF cho .NET. Đây sẽ đóng vai trò là tài liệu PDF nơi chúng tôi sẽ thêm JavaScript.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Bước 2: Thêm JavaScript ở cấp độ tài liệu

 Để thêm JavaScript ở cấp tài liệu, hãy sử dụng`JavaScript` tài sản của`Document` lớp học. Gán các hàm JavaScript cho các khóa trong từ điển JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 Trong hướng dẫn này, chúng tôi đã thêm hai hàm JavaScript,`func1` Và`func2`, vào tài liệu PDF.

## Bước 3: Xóa JavaScript cấp tài liệu

 Để xóa JavaScript ở cấp tài liệu, hãy tải tài liệu PDF và truy cập vào`JavaScript`từ điển. Lặp lại các phím và loại bỏ chức năng JavaScript mong muốn.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 Trong hướng dẫn này, chúng tôi loại bỏ`func1` Hàm JavaScript từ tài liệu PDF.

## Bước 4: Lưu và xác minh thay đổi

Lưu tài liệu PDF đã sửa đổi và xác minh các thay đổi.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Mã này sẽ lưu tài liệu PDF đã sửa đổi và hiển thị thông báo thành công.

### Mã nguồn ví dụ cho Thêm Xóa Javascript khỏi tài liệu PDF bằng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Xóa JavaScript cấp tài liệu
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Phần kết luận

Trong bài viết này, chúng tôi đã cung cấp hướng dẫn từng bước để thêm và xóa JavaScript khỏi tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn và sử dụng các hướng dẫn về mã được cung cấp, bạn có thể dễ dàng kết hợp JavaScript vào tài liệu PDF của mình và xóa nó khi cần. JavaScript kích hoạt chức năng động và tính tương tác trong tệp PDF của bạn, nâng cao trải nghiệm người dùng.


### Câu hỏi thường gặp về thêm xóa javascript vào tài liệu PDF

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Trả lời: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác các tệp PDF trong ứng dụng .NET một cách hiệu quả. Nó cung cấp các tính năng mở rộng để làm việc với các tài liệu PDF theo chương trình.

#### Câu hỏi: Làm cách nào tôi có thể thêm JavaScript vào tài liệu PDF bằng Aspose.PDF cho .NET?

 Đáp: Bạn có thể thêm JavaScript ở cấp độ tài liệu bằng cách sử dụng`JavaScript` tài sản của`Document` lớp học. Chỉ cần gán các hàm JavaScript cho các khóa trong từ điển JavaScript.

#### Câu hỏi: Tôi có thể xóa JavaScript khỏi tài liệu PDF bằng Aspose.PDF cho .NET không?

 Đáp: Có, bạn có thể xóa JavaScript khỏi tài liệu PDF bằng cách truy cập vào`JavaScript` từ điển và loại bỏ chức năng JavaScript mong muốn.

#### Câu hỏi: Aspose.PDF cho .NET có phù hợp với các dự án chuyên nghiệp không?

Trả lời: Hoàn toàn có thể, Aspose.PDF cho .NET được sử dụng rộng rãi trong các dự án chuyên nghiệp cho các tác vụ tạo và thao tác PDF. Nó cung cấp hiệu suất cao và chức năng đáng tin cậy.

#### Câu hỏi: Việc thêm JavaScript vào tài liệu PDF mang lại lợi ích gì?

Trả lời: Việc thêm JavaScript vào tài liệu PDF cho phép bạn tạo các tệp PDF động và tương tác. Bạn có thể triển khai xác thực biểu mẫu, thực hiện tính toán và thêm các tính năng tương tác khác nhau để nâng cao trải nghiệm người dùng.