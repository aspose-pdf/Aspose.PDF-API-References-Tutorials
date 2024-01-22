---
title: Thêm tập lệnh Java vào tệp PDF
linktitle: Thêm tệp PDF Java Script
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách thêm JavaScript vào tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước với các hướng dẫn về mã cho tập lệnh ở cấp độ trang và tài liệu.
type: docs
weight: 10
url: /vi/net/programming-with-document/addjavascripttopage/
---
Để thêm JavaScript vào tệp PDF, chúng tôi sẽ sử dụng Aspose.PDF cho .NET. Thư viện này cung cấp một cách đơn giản và hiệu quả để làm việc với các tệp PDF trong các ứng dụng .NET. Các bước sau sẽ hướng dẫn bạn quy trình thêm JavaScript vào tệp PDF bằng Aspose.PDF cho .NET.

## Bước 1: Tải tệp PDF

 Bước đầu tiên là tải tệp PDF mà bạn muốn thêm JavaScript vào. Bạn có thể thực hiện việc này bằng cách sử dụng`Document` lớp được cung cấp bởi Aspose.PDF cho .NET. Các`Document` lớp cung cấp các phương thức để tải, lưu và thao tác với tệp PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tệp PDF hiện có
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 2: Thêm JavaScript ở cấp độ tài liệu

Để thêm JavaScript ở cấp tài liệu, chúng tôi sẽ sử dụng`JavascriptAction` lớp được cung cấp bởi Aspose.PDF cho .NET. Lớp này cho phép bạn chỉ định câu lệnh JavaScript mà bạn muốn thêm vào tệp PDF.

```csharp
// Thêm JavaScript ở cấp độ tài liệu
// Khởi tạo JavascriptAction bằng câu lệnh JavaScript mong muốn
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Gán đối tượng JavascriptAction cho hành động mong muốn của Tài liệu
doc.OpenAction = javaScript;
```

Trong hướng dẫn này, chúng tôi đang thêm một câu lệnh JavaScript sẽ in tệp PDF với các tùy chọn được chỉ định khi tài liệu được mở.

## Bước 3: Thêm JavaScript ở cấp trang

 Để thêm JavaScript ở cấp độ trang, chúng tôi sẽ sử dụng`JavascriptAction` lớp học và`Actions` thuộc tính được cung cấp bởi Aspose.PDF cho .NET. Thuộc tính này cho phép bạn chỉ định các câu lệnh JavaScript sẽ được thực thi khi trang được mở hoặc đóng.

```csharp
// Thêm JavaScript ở cấp trang
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Trong hướng dẫn này, chúng tôi đang thêm các câu lệnh JavaScript sẽ hiển thị thông báo cảnh báo khi trang được mở hoặc đóng.

## Bước 4: Lưu tệp PDF

Sau khi thêm JavaScript vào tệp PDF, bạn cần lưu tệp đã sửa đổi. Bạn có thể thực hiện việc này bằng cách sử dụng`Save` phương pháp được cung cấp bởi`Document` lớp học.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Mã này sẽ lưu tệp PDF đã sửa đổi vào thư mục được chỉ định.

### Mã nguồn mẫu cho Thêm tập lệnh Java vào trang bằng Aspose.PDF cho .NET

```csharp
            
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tệp PDF hiện có
Document doc = new Document(dataDir + "input.pdf");

// Thêm JavaScript ở cấp độ tài liệu
// Khởi tạo JavascriptAction bằng câu lệnh JavaScript mong muốn
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Gán đối tượng JavascriptAction cho hành động mong muốn của Tài liệu
doc.OpenAction = javaScript;

// Thêm JavaScript ở cấp trang
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Phần kết luận

Trong bài viết này, chúng tôi đã giải thích cách thêm JavaScript vào tệp PDF ở cả cấp độ tài liệu và cấp độ trang bằng Aspose.PDF cho .NET. Chúng tôi đã cung cấp hướng dẫn từng bước và bao gồm mã nguồn đầy đủ cho từng ví dụ. Với kiến thức này, bạn có thể thêm JavaScript vào tệp PDF của mình và tùy chỉnh hành vi của chúng theo nhu cầu của bạn.


### Câu hỏi thường gặp về thêm tập lệnh java vào tệp PDF

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PDF trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để tạo, sửa đổi và thao tác các tài liệu PDF.

#### Câu hỏi: Tôi có thể thêm JavaScript vào tài liệu PDF bằng Aspose.PDF cho .NET không?

Trả lời: Có, Aspose.PDF cho .NET cho phép bạn thêm JavaScript vào cả cấp độ tài liệu và cấp độ trang của tệp PDF, cho phép bạn tạo các tài liệu PDF động và tương tác.

#### Câu hỏi: Làm cách nào để tải tệp PDF hiện có bằng Aspose.PDF cho .NET?

 Đáp: Bạn có thể tải tệp PDF hiện có bằng cách sử dụng`Document` lớp và các phương thức của nó, như được hiển thị trong hướng dẫn từng bước.

#### Câu hỏi: Tôi có thể thêm những loại hành động JavaScript nào vào tài liệu PDF?

Trả lời: Với Aspose.PDF cho .NET, bạn có thể thêm nhiều tác vụ JavaScript khác nhau, chẳng hạn như in, thông báo cảnh báo, thao tác trường biểu mẫu, v.v.

#### Câu hỏi: Aspose.PDF cho .NET có phù hợp với các dự án thương mại không?

Trả lời: Có, Aspose.PDF cho .NET là một thư viện mạnh mẽ và đáng tin cậy, thường được sử dụng trong các dự án thương mại để thao tác và tạo các tác vụ PDF.

