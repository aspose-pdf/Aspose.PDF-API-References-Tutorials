---
title: Kế thừa phóng to tệp PDF
linktitle: Kế thừa phóng to tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng kế thừa tính năng phóng to dấu trang trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 90
url: /vi/net/programming-with-bookmarks/inherit-zoom/
---
Kế thừa thu phóng trong tệp PDF cho phép bạn chỉ định mức thu phóng mặc định cho dấu trang. Với Aspose.PDF cho .NET, bạn có thể dễ dàng kế thừa tính năng thu phóng bằng cách làm theo mã nguồn sau:

## Bước 1: Nhập thư viện cần thiết

Trước khi bắt đầu, bạn cần nhập các thư viện cần thiết cho dự án C# của mình. Đây là chỉ thị nhập khẩu cần thiết:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Bước 2: Đặt đường dẫn đến thư mục tài liệu

 Trong bước này, bạn cần chỉ định đường dẫn đến thư mục chứa tệp PDF mà bạn muốn kế thừa khả năng thu phóng từ đó. Thay thế`"YOUR DOCUMENT DIRECTORY"`trong đoạn mã sau với đường dẫn thực tế đến thư mục tài liệu của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 3: Mở tài liệu PDF

Bây giờ chúng ta sẽ mở tài liệu PDF mà chúng ta muốn kế thừa tính năng thu phóng bằng mã sau:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Bước 4: Nhận bộ sưu tập dấu trang

 Trong bước này, chúng ta sẽ có được bộ sưu tập dấu trang hoặc điểm mốc của tài liệu bằng cách sử dụng`Outlines` tài sản của`doc` sự vật. Đây là mã tương ứng:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Bước 5: Đặt mức thu phóng

 Bây giờ chúng ta sẽ thiết lập mức thu phóng bằng cách tạo một`XYZExplicitDestination` đối tượng có tọa độ x, y và z được chỉ định. Ở đây chúng tôi sử dụng tọa độ (100, 100, 0) với độ phóng đại là 2. Đây là mã tương ứng:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Bước 6: Thêm mức thu phóng vào dấu trang

 Ở bước này, chúng ta thêm`XYZExplicitDestination` đối tượng như một hành động đối với dấu trang của`item` bộ sưu tập. Đây là mã tương ứng:

```csharp
item. Action = new GoToAction(dest);
```

## Bước 7: Thêm dấu trang đã cập nhật vào tài liệu

 Cuối cùng, chúng tôi thêm các dấu trang đã cập nhật vào bộ sưu tập dấu trang của tài liệu bằng cách sử dụng`Add` phương pháp của`doc.Outlines` sự vật. Đây là mã tương ứng:

```csharp
doc. Outlines. Add(item);
```

## Bước 8: Lưu file cập nhật

 Bây giờ hãy lưu tệp PDF đã cập nhật bằng cách sử dụng`Save` phương pháp của`doc` sự vật. Đây là mã tương ứng:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Kế thừa Zoom bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document doc = new Document(dataDir + "input.pdf");
// Nhận bộ sưu tập phác thảo/đánh dấu của tệp PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Đặt mức thu phóng là 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Thêm XYZExplicitDestination làm hành động để phác thảo bộ sưu tập PDF
item.Action = new GoToAction(dest);
// Thêm mục vào phác thảo bộ sưu tập tệp PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Lưu đầu ra
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã có hướng dẫn từng bước về Kế thừa Zoom bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này để chỉ định mức thu phóng mặc định cho dấu trang trong tài liệu PDF của mình.

Hãy nhớ xem tài liệu Aspose.PDF chính thức để biết thêm thông tin về các tính năng thao tác dấu trang nâng cao.

### Câu hỏi thường gặp về tính năng phóng to kế thừa trong tệp PDF

#### Câu hỏi: Kế thừa thu phóng trong tệp PDF là gì?

Trả lời: Kế thừa thu phóng đề cập đến khả năng chỉ định mức thu phóng mặc định cho dấu trang trong tài liệu PDF. Điều này cho phép điều hướng nhất quán và thân thiện với người dùng khi người dùng tương tác với dấu trang.

#### Hỏi: Tại sao tôi muốn kế thừa mức thu phóng cho dấu trang?

Đáp: Kế thừa mức thu phóng đảm bảo rằng người dùng có trải nghiệm xem nhất quán khi điều hướng qua dấu trang trong tài liệu PDF. Nó có thể đặc biệt hữu ích khi bạn muốn cung cấp chế độ xem cụ thể cho các phần khác nhau của tài liệu.

#### Câu hỏi: Làm cách nào để nhập các thư viện cần thiết cho dự án C# của tôi?

Đáp: Để nhập các thư viện cần thiết cho dự án C# của bạn, hãy bao gồm các lệnh nhập sau:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Những chỉ thị này cho phép bạn truy cập các lớp và phương thức cần thiết để làm việc với các tài liệu PDF và dấu trang.

#### Hỏi: Làm cách nào để chỉ định đường dẫn đến thư mục tài liệu?

 Đáp: Trong mã nguồn được cung cấp, hãy thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tệp PDF mà bạn muốn kế thừa các mức thu phóng.

#### Hỏi: Làm cách nào để mở tài liệu PDF để kế thừa mức thu phóng?

Đáp: Để mở tài liệu PDF kế thừa mức thu phóng, hãy sử dụng mã sau:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Thay thế`"input.pdf"` với tên tập tin thực tế.

#### Hỏi: Làm cách nào để đặt mức thu phóng cho dấu trang?

 Đáp: Để đặt mức thu phóng, hãy tạo một`XYZExplicitDestination` đối tượng có tọa độ và hệ số thu phóng mong muốn. Đây là một ví dụ:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Điều này đặt mức thu phóng thành 2 tại tọa độ (100, 100).

#### Hỏi: Làm cách nào để thêm mức thu phóng vào dấu trang?

 Đáp: Thêm`XYZExplicitDestination` đối tượng như một hành động đối với bộ sưu tập dấu trang:

```csharp
item.Action = new GoToAction(dest);
```

 Ở đâu`item` là một`OutlineItemCollection` đại diện cho một dấu trang.

#### Hỏi: Làm cách nào để lưu tệp PDF đã cập nhật?

 Đáp: Lưu tệp PDF đã cập nhật bằng cách sử dụng`Save` phương pháp của`doc` sự vật:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Hỏi: Tôi có thể tùy chỉnh mức thu phóng cho các dấu trang khác nhau không?

 Đáp: Có, bạn có thể tùy chỉnh mức thu phóng cho các dấu trang khác nhau bằng cách tạo nhiều dấu trang`XYZExplicitDestination` các đối tượng có tọa độ và hệ số thu phóng khác nhau.

#### Câu hỏi: Có giới hạn về số lượng dấu trang mà tôi có thể áp dụng kế thừa thu phóng không?

Đáp: Thông thường không có giới hạn nghiêm ngặt về số lượng dấu trang mà bạn có thể áp dụng kế thừa thu phóng. Tuy nhiên, những tài liệu rất lớn có số lượng dấu trang quá lớn có thể yêu cầu quản lý bộ nhớ hiệu quả.

#### Câu hỏi: Làm cách nào để xác nhận rằng tính kế thừa thu phóng đã được áp dụng?

Trả lời: Mở tệp PDF được tạo để xác minh rằng các mức thu phóng được chỉ định đã được dấu trang kế thừa.