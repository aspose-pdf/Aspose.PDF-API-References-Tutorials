---
title: Đặt Java Script
linktitle: Đặt Java Script
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Mở khóa sức mạnh của Aspose.PDF cho .NET. Tìm hiểu cách thiết lập JavaScript trên các trường biểu mẫu với hướng dẫn từng bước của chúng tôi.
type: docs
weight: 270
url: /vi/net/programming-with-forms/set-java-script/
---
## Giới thiệu

Việc tạo PDF động và tương tác có thể cải thiện đáng kể trải nghiệm của người dùng, đặc biệt là khi tích hợp các biểu mẫu và trường trong một tài liệu. Một thư viện mạnh mẽ giúp thực hiện điều này là Aspose.PDF cho .NET. Trong bài viết này, chúng ta sẽ đi sâu vào việc thiết lập JavaScript cho các trường biểu mẫu bằng Aspose.PDF, đảm bảo PDF của bạn không chỉ đẹp mà còn hoạt động tốt.

## Điều kiện tiên quyết

Trước khi bắt đầu viết mã, hãy đảm bảo rằng bạn có mọi thứ cần thiết để theo dõi một cách suôn sẻ:

- Visual Studio (hoặc bất kỳ .NET IDE nào): Đảm bảo bạn đã cài đặt và thiết lập đúng cách.
  
-  Thư viện Aspose.PDF: Bạn sẽ muốn có phiên bản mới nhất của thư viện này. Bạn có thể tải xuống[đây](https://releases.aspose.com/pdf/net/).

- Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# sẽ giúp bạn hiểu rõ hơn các đoạn mã.

-  Tệp PDF: Bạn nên chuẩn bị một tệp PDF để thử nghiệm. Trong ví dụ của chúng tôi, chúng tôi sẽ sử dụng một tệp có tên`SetJavaScript.pdf`.

- Thư mục tài liệu của bạn: Biết nơi lưu trữ các tệp tài liệu của bạn. Chúng tôi sẽ tham chiếu đường dẫn này trong mã của chúng tôi.

Sau khi bạn đã chuẩn bị xong những điều kiện tiên quyết này, chúng ta sẽ tận dụng những công cụ nào? Hãy cùng khám phá những gì Aspose.PDF có thể làm.

## Nhập gói

Để bắt đầu, bạn cần bao gồm các không gian tên cần thiết trong dự án C# của mình. Mở tệp C# chính của bạn và thêm các câu lệnh nhập sau:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Các không gian tên này cung cấp quyền truy cập vào PDF và chức năng liên quan đến biểu mẫu trong thư viện Aspose.PDF.

Bạn đã sẵn sàng để biến PDF của mình thành tương tác chưa? Hãy lấy mũ mã hóa của bạn và cùng chúng tôi phân tích từng bước nhé!

## Bước 1: Xác định Đường dẫn Tài liệu

Đầu tiên, chúng ta cần chỉ định vị trí tệp PDF của mình. Điều này thiết lập bối cảnh cho mọi thứ tiếp theo. Sau đây là cách bạn thực hiện:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tệp PDF của bạn nằm. Hãy nghĩ về điều này như việc thiết lập tọa độ cho bản đồ kho báu—bạn cần biết vị trí đánh dấu 'X'!

## Bước 2: Tải Tài liệu PDF

Sau khi xác định được thư mục, chúng ta sẽ tải tệp PDF lên. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Dòng này mở tệp PDF bạn chỉ định và chuẩn bị cho thao tác. 

## Bước 3: Truy cập vào Trường biểu mẫu

Tiếp theo, chúng ta muốn truy cập vào trường biểu mẫu nơi chúng ta sẽ áp dụng JavaScript. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Ở đây, chúng tôi giả sử có một hộp văn bản trong tệp PDF của bạn có tên`textbox1`. Nếu bạn không có trường nào có tên này, bạn có thể đổi tên hoặc điều chỉnh mã cho phù hợp. 

## Bước 4: Thiết lập hành động JavaScript

Bây giờ, hãy thêm một số chức năng vào hộp văn bản của chúng ta! Chúng ta sẽ thiết lập các hành động JavaScript sẽ được kích hoạt trên các sự kiện nhất định. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Sau đây là những gì đang xảy ra:
- OnModifyCharacter: Hàm JavaScript này chỉ định cách trường sẽ hoạt động khi một ký tự được sửa đổi. Trong trường hợp này, nó cho phép hai dấu thập phân sau số mà không có dấu phân cách.
- OnFormat: Điều này đảm bảo rằng khi người dùng định dạng số, số đó sẽ tuân theo cùng một quy tắc.

Bằng cách thiết lập những hành động này, về cơ bản chúng ta đang mang lại cho hộp văn bản một cá tính—giống như dạy nó một động tác nhảy vậy!

## Bước 5: Khởi tạo giá trị trường

Tiếp theo, hãy thiết lập điểm bắt đầu cho hộp văn bản bằng cách đặt giá trị ban đầu. 

```csharp
field.Value = "123";
```

Dòng này đặt "123" làm giá trị được điền sẵn trong hộp văn bản. Giống như chuẩn bị sân khấu cho một buổi biểu diễn.

## Bước 6: Lưu PDF đã sửa đổi

Cuối cùng, chúng ta cần lưu tài liệu sau khi thực hiện tất cả những thay đổi này.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Thao tác này cập nhật tệp gốc với các thay đổi của bạn và lưu nó dưới dạng`Restricted_out.pdf`. Hãy nghĩ về điều này như việc đóng dấu số phận của tệp PDF của chúng ta—một khi đã lưu, nó đã sẵn sàng để chia sẻ với thế giới!

## Bước 7: Xác nhận thành công

Cuối cùng, hãy kiểm tra xem mọi việc có diễn ra suôn sẻ không. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Chạy tin nhắn này sẽ giúp bạn yên tâm rằng hoạt động đã hoàn tất thành công, giống như nhận được tràng pháo tay từ khán giả sau một màn trình diễn tuyệt vời.

## Phần kết luận

Xin chúc mừng! Bạn đã thiết lập thành công JavaScript cho các trường biểu mẫu trong PDF bằng Aspose.PDF cho .NET. Hướng dẫn này không chỉ cung cấp cho bạn các công cụ để nâng cao tương tác của người dùng mà còn trao quyền cho bạn cá nhân hóa tài liệu của mình như một chuyên gia. Cho dù bạn đang làm việc với các biểu mẫu trong hóa đơn, khảo sát hay các PDF tương tác khác, khả năng thực sự là vô tận.

### Câu hỏi thường gặp

### Aspose.PDF dành cho .NET là gì?  
Aspose.PDF là một thư viện được thiết kế để tạo, chỉnh sửa và thao tác các tệp PDF trong các ứng dụng .NET, cung cấp các chức năng PDF mạnh mẽ.

### Tôi có cần giấy phép để sử dụng Aspose.PDF không?  
 Trong khi có bản dùng thử miễn phí, bạn cần có giấy phép để sử dụng đầy đủ mà không bị giới hạn. Bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy).

### Tôi có thể cài đặt JavaScript trên các loại trường biểu mẫu khác không?  
Hoàn toàn đúng! Aspose.PDF cho phép các hành động JavaScript trên nhiều trường biểu mẫu như hộp kiểm, nút radio và danh sách thả xuống.

### Tôi có thể nhận được hỗ trợ cho các vấn đề liên quan đến Aspose.PDF như thế nào?  
 Bạn có thể truy cập hỗ trợ thông qua họ[diễn đàn](https://forum.aspose.com/c/pdf/10) cho bất kỳ thắc mắc hoặc vấn đề nào.

### Có cách nào để dùng thử Aspose.PDF mà không cần mua không?  
Có! Aspose cung cấp một[dùng thử miễn phí](https://releases.aspose.com/) để kiểm tra các tính năng của thư viện trước khi quyết định mua.