---
title: Chỉ định trang khi xem
linktitle: Chỉ định trang khi xem
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách chỉ định một trang khi xem tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 110
url: /vi/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Tìm hiểu cách chỉ định một trang khi xem tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.

## Bước 1: Thiết lập môi trường

Đảm bảo rằng bạn đã thiết lập môi trường phát triển của mình với dự án C# và các tài liệu tham khảo Aspose.PDF thích hợp.

## Bước 2: Tải tệp PDF

Đặt đường dẫn thư mục của tài liệu của bạn và tải tệp PDF lên bằng mã sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Tải tập tin PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Bước 3: Chỉ định trang đích

Lấy phiên bản trang đích bằng mã sau:

```csharp
Page page2 = doc.Pages[2];
```

 Bạn có thể điều chỉnh chỉ số`[2]` để chọn trang mong muốn.

## Bước 4: Định cấu hình cài đặt thu phóng

Tạo một biến để đặt hệ số thu phóng trang đích:

```csharp
double zoom = 1;
```

Bạn có thể điều chỉnh giá trị thu phóng theo nhu cầu của mình.

## Bước 5: Tạo hành động điều hướng

Tạo một phiên bản của hành động điều hướng bằng cách sử dụng trang đích được chỉ định:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Bước 6: Thiết lập điểm đến

Đặt đích đến để đi đến trang đích bằng cách sử dụng tọa độ và thu phóng:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Bước 7: Định cấu hình hành động mở tài liệu

Đặt hành động mở tài liệu với hành động điều hướng đã tạo:

```csharp
doc. OpenAction = action;
```

## Bước 8: Lưu tài liệu đã cập nhật

 Lưu tài liệu đã cập nhật bằng cách sử dụng`Save` phương pháp:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Mã nguồn mẫu cho Chỉ định trang khi xem bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải tập tin PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Lấy ví dụ của trang thứ hai của tài liệu
Page page2 = doc.Pages[2];
// Tạo biến để đặt hệ số thu phóng của trang đích
double zoom = 1;
// Tạo phiên bản GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Tới trang 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Đặt hành động mở tài liệu
doc.OpenAction = action;
// Lưu tài liệu đã cập nhật
doc.Save(dataDir + "goto2page_out.pdf");
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã biết cách chỉ định một trang khi xem tệp PDF bằng Aspose.PDF cho .NET. Sử dụng kiến thức này để tùy chỉnh trải nghiệm xem của người dùng trong tài liệu PDF của bạn.

Bây giờ bạn đã hoàn thành hướng dẫn này, bạn có thể áp dụng các khái niệm này cho các dự án của riêng mình và khám phá thêm các tính năng do Aspose.PDF cung cấp cho .NET.

### Câu hỏi thường gặp 

#### Hỏi: Mục đích của việc chỉ định trang đích khi xem tệp PDF là gì?

Đáp: Việc chỉ định trang đích cho phép bạn kiểm soát trang nào của tài liệu PDF được hiển thị khi tệp được mở. Điều này có thể nâng cao trải nghiệm người dùng bằng cách hướng họ đến một trang cụ thể mà họ quan tâm.

#### Câu hỏi: Việc chỉ định trang đích có thể hữu ích như thế nào trong tài liệu PDF?

Đáp: Việc chỉ định trang đích sẽ có ích khi bạn muốn hướng dẫn người dùng đến một phần hoặc nội dung cụ thể trong tài liệu PDF mà không yêu cầu họ điều hướng qua các trang theo cách thủ công.

#### Câu hỏi: Aspose.PDF cho .NET hỗ trợ việc chỉ định trang mục tiêu để xem như thế nào?

Trả lời: Aspose.PDF for .NET cung cấp các API cho phép bạn đặt chế độ xem ban đầu của tài liệu PDF, bao gồm trang đích, mức thu phóng và các thuộc tính hiển thị khác.

#### Hỏi: Tôi có thể chỉ định bất kỳ trang nào làm trang đích không?

Đáp: Có, bạn có thể chỉ định bất kỳ trang nào trong tài liệu PDF làm trang mục tiêu để xem. Đơn giản chỉ cần sử dụng chỉ mục thích hợp để chọn trang mong muốn.

#### Hỏi: Tầm quan trọng của hệ số thu phóng khi chỉ định trang mục tiêu là gì?

Đáp: Hệ số thu phóng xác định mức độ phóng đại được áp dụng cho trang đích khi mở tài liệu PDF. Nó kiểm soát lượng nội dung được hiển thị trong khung nhìn.

#### Hỏi: Tôi có thể đặt các hệ số thu phóng khác nhau cho các trang mục tiêu khác nhau không?

Đáp: Có, bạn có thể đặt các hệ số thu phóng khác nhau cho các trang mục tiêu khác nhau bằng cách tạo riêng biệt`GoToAction` các phiên bản và cấu hình đích đến của chúng cho phù hợp.

#### Hỏi: Có bất kỳ hạn chế nào trong việc chỉ định trang đích không?

Trả lời: Việc chỉ định trang đích bị giới hạn trong việc kiểm soát chế độ xem ban đầu khi mở tệp PDF. Nó không ảnh hưởng đến tương tác hoặc điều hướng của người dùng khi tệp PDF được hiển thị.

#### Hỏi: Tôi có thể sử dụng tính năng này để tạo bản trình bày trong tài liệu PDF không?

Đáp: Có, bạn có thể sử dụng tính năng này để tạo trải nghiệm giống như bản trình bày trong tài liệu PDF, hướng dẫn người dùng qua các phần hoặc chủ đề khác nhau.

#### Câu hỏi: Tôi có thể tùy chỉnh các khía cạnh khác của chế độ xem ban đầu, chẳng hạn như bố cục trang không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp các thuộc tính để tùy chỉnh các khía cạnh khác của chế độ xem ban đầu, bao gồm bố cục trang, chế độ trang, v.v.

#### Hỏi: Làm cách nào tôi có thể kiểm tra xem trang mục tiêu và hệ số thu phóng được chỉ định có hoạt động như dự kiến hay không?

Trả lời: Sau khi áp dụng mã được cung cấp để chỉ định trang đích và hệ số thu phóng, hãy mở tệp PDF đã sửa đổi và xác minh rằng nó mở đúng trang và mức thu phóng.