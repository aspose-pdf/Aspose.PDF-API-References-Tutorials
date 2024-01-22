---
title: Đặt hệ số thu phóng trong tệp PDF
linktitle: Đặt hệ số thu phóng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt hệ số thu phóng trong tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước của chúng tôi.
type: docs
weight: 340
url: /vi/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET là một API mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu PDF trong ứng dụng .NET của họ. Một trong những tính năng mà nó cung cấp là khả năng đặt hệ số thu phóng của tài liệu PDF. Trong hướng dẫn từng bước này, chúng tôi sẽ giải thích cách sử dụng Aspose.PDF cho .NET để đặt hệ số thu phóng của tài liệu PDF bằng mã nguồn C# được cung cấp.

## Bước 1: Đặt đường dẫn đến thư mục tài liệu

 Bước đầu tiên là đặt đường dẫn đến thư mục chứa tài liệu PDF. Điều này có thể được thực hiện bằng cách thiết lập`dataDir` biến theo đường dẫn thư mục. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thư mục thực nơi chứa tài liệu PDF của bạn.

## Bước 2: Khởi tạo một đối tượng Tài liệu mới

 Để làm việc với tài liệu PDF bằng Aspose.PDF cho .NET, chúng ta cần tạo một tài liệu mới`Document` đối tượng và tải tệp PDF vào đó. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Mã này sẽ tạo một cái mới`Document` đối tượng và tải tệp PDF có tên "SetZoomFactor.pdf" từ`dataDir` thư mục vào đó.

## Bước 3: Đặt hệ số thu phóng

 Một khi`Document`đối tượng được tạo, chúng ta có thể đặt hệ số thu phóng của tài liệu PDF. Trong đoạn mã sau, chúng tôi đặt hệ số thu phóng thành 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Mã này đặt hệ số thu phóng thành 50% bằng cách tạo mới`GoToAction` đối tượng và truyền một`XYZExplicitDestination` đối tượng có hệ số thu phóng là 50%. Các`OpenAction` tài sản của`Document` đối tượng sau đó được đặt thành này`GoToAction` sự vật.

## Bước 4: Lưu tài liệu PDF

 Cuối cùng, chúng ta có thể lưu tài liệu PDF đã sửa đổi vào một tệp mới. Trong đoạn mã sau, chúng tôi lưu tài liệu PDF vào một tệp mới có tên "Zoomed_pdf_out.pdf" trong thư mục`dataDir` danh mục.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Mã nguồn ví dụ cho Đặt hệ số thu phóng bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu mới
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Lưu tài liệu
doc.Save(dataDir);
```

## Phần kết luận

Aspose.PDF for .NET cung cấp một cách đơn giản và hiệu quả để đặt hệ số thu phóng của tài liệu PDF bằng mã C#. Bằng cách làm theo các bước trên, bạn có thể dễ dàng sửa đổi hệ số thu phóng của bất kỳ tài liệu PDF nào trong ứng dụng .NET của mình.

### Câu hỏi thường gặp

#### Hỏi: Hệ số thu phóng trong tài liệu PDF là gì và nó ảnh hưởng đến việc xem như thế nào?

Đáp: Hệ số thu phóng trong tài liệu PDF xác định mức độ phóng đại khi xem tài liệu. Nó chỉ định tỷ lệ hiển thị của tài liệu, ảnh hưởng đến mức độ lớn hay nhỏ của nội dung xuất hiện trên màn hình. Hệ số thu phóng 1,0 biểu thị mức thu phóng 100% (kích thước thực), trong khi hệ số lớn hơn 1,0 sẽ phóng to và hệ số nhỏ hơn 1,0 sẽ thu nhỏ.

#### Hỏi: Tôi có thể đặt hệ số thu phóng cụ thể cho các trang khác nhau trong cùng một tài liệu PDF không?

 Trả lời: Có, với Aspose.PDF cho .NET, bạn có thể đặt các hệ số thu phóng khác nhau cho các trang khác nhau trong cùng một tài liệu PDF. Mã nguồn ví dụ được cung cấp minh họa cách đặt hệ số thu phóng cho trang đầu tiên bằng cách sử dụng`GoToAction` sự vật. Bạn có thể sửa đổi mã để đặt các hệ số thu phóng khác nhau cho các trang khác nếu cần.

#### Hỏi: Việc thay đổi hệ số thu phóng ảnh hưởng như thế nào đến việc in và lưu tài liệu PDF?

Trả lời: Việc thay đổi hệ số thu phóng bằng Aspose.PDF cho .NET không ảnh hưởng đến nội dung thực tế của tài liệu PDF. Nó chỉ ảnh hưởng đến trải nghiệm xem khi tài liệu được mở trong trình xem PDF. Hệ số thu phóng được đặt theo chương trình sẽ không ảnh hưởng đến kết quả in hoặc tệp PDF đã lưu.