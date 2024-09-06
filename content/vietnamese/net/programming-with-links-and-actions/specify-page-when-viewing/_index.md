---
title: Chỉ định trang khi xem
linktitle: Chỉ định trang khi xem
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách chỉ định trang khi xem PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 110
url: /vi/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Tìm hiểu cách chỉ định trang khi xem tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.

## Bước 1: Thiết lập môi trường

Hãy đảm bảo rằng bạn đã thiết lập môi trường phát triển của mình với dự án C# và các tham chiếu Aspose.PDF phù hợp.

## Bước 2: Tải tệp PDF

Thiết lập đường dẫn thư mục tài liệu của bạn và tải tệp PDF lên bằng mã sau:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Tải tệp PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Bước 3: Xác định trang đích

Lấy phiên bản trang đích bằng cách sử dụng mã sau:

```csharp
Page page2 = doc.Pages[2];
```

 Bạn có thể điều chỉnh chỉ số`[2]` để chọn trang mong muốn.

## Bước 4: Cấu hình cài đặt thu phóng

Tạo một biến để thiết lập hệ số thu phóng trang mục tiêu:

```csharp
double zoom = 1;
```

Bạn có thể điều chỉnh giá trị thu phóng theo nhu cầu của mình.

## Bước 5: Tạo hành động điều hướng

Tạo một phiên bản của hành động điều hướng bằng cách sử dụng trang đích đã chỉ định:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Bước 6: Thiết lập điểm đến

Đặt đích đến để đi đến trang đích bằng cách sử dụng tọa độ và thu phóng:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Bước 7: Cấu hình Hành động Mở Tài liệu

Thiết lập hành động mở tài liệu bằng hành động điều hướng đã tạo:

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
// Tải tệp PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Lấy ví dụ về trang thứ hai của tài liệu
Page page2 = doc.Pages[2];
// Tạo biến để thiết lập hệ số thu phóng của trang đích
double zoom = 1;
// Tạo phiên bản GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Đi tới trang 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Thiết lập hành động mở tài liệu
doc.OpenAction = action;
// Lưu tài liệu đã cập nhật
doc.Save(dataDir + "goto2page_out.pdf");
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã biết cách chỉ định một trang khi xem PDF bằng Aspose.PDF cho .NET. Sử dụng kiến thức này để tùy chỉnh trải nghiệm xem của người dùng trong tài liệu PDF của bạn.

Bây giờ bạn đã hoàn thành hướng dẫn này, bạn có thể áp dụng những khái niệm này vào các dự án của riêng mình và khám phá thêm các tính năng mà Aspose.PDF cung cấp cho .NET.

### Câu hỏi thường gặp 

#### H: Mục đích của việc chỉ định trang đích khi xem tệp PDF là gì?

A: Chỉ định trang đích cho phép bạn kiểm soát trang nào của tài liệu PDF được hiển thị khi tệp được mở. Điều này có thể nâng cao trải nghiệm của người dùng bằng cách hướng họ đến trang cụ thể mà họ quan tâm.

#### H: Việc chỉ định trang đích có thể hữu ích như thế nào trong tài liệu PDF?

A: Việc chỉ định trang đích sẽ có lợi khi bạn muốn hướng dẫn người dùng đến một phần hoặc nội dung cụ thể trong tài liệu PDF mà không yêu cầu họ phải điều hướng thủ công qua các trang.

#### H: Aspose.PDF cho .NET hỗ trợ việc chỉ định trang đích để xem như thế nào?

A: Aspose.PDF cho .NET cung cấp các API cho phép bạn thiết lập chế độ xem ban đầu của tài liệu PDF, bao gồm trang đích, mức thu phóng và các thuộc tính hiển thị khác.

#### H: Tôi có thể chỉ định bất kỳ trang nào làm trang mục tiêu không?

A: Có, bạn có thể chỉ định bất kỳ trang nào trong tài liệu PDF làm trang đích để xem. Chỉ cần sử dụng chỉ mục thích hợp để chọn trang mong muốn.

#### H: Hệ số thu phóng có ý nghĩa gì khi chỉ định trang mục tiêu?

A: Hệ số thu phóng xác định mức độ phóng đại được áp dụng cho trang đích khi tài liệu PDF được mở. Nó kiểm soát lượng nội dung được hiển thị trong khung nhìn.

#### H: Tôi có thể thiết lập các hệ số thu phóng khác nhau cho các trang mục tiêu khác nhau không?

A: Có, bạn có thể thiết lập các hệ số thu phóng khác nhau cho các trang mục tiêu khác nhau bằng cách tạo riêng`GoToAction` các trường hợp và cấu hình đích đến của chúng cho phù hợp.

#### H: Có hạn chế nào khi chỉ định trang mục tiêu không?

A: Việc chỉ định trang đích chỉ giới hạn ở việc kiểm soát chế độ xem ban đầu khi PDF được mở. Nó không ảnh hưởng đến tương tác hoặc điều hướng của người dùng sau khi PDF được hiển thị.

#### H: Tôi có thể sử dụng tính năng này để tạo bài thuyết trình trong tài liệu PDF không?

A: Có, bạn có thể sử dụng tính năng này để tạo trải nghiệm giống như bài thuyết trình trong tài liệu PDF, hướng dẫn người dùng qua các phần hoặc chủ đề khác nhau.

#### H: Tôi có thể tùy chỉnh các khía cạnh khác của giao diện ban đầu, chẳng hạn như bố cục trang không?

A: Có, Aspose.PDF cho .NET cung cấp các thuộc tính để tùy chỉnh các khía cạnh khác của chế độ xem ban đầu, bao gồm bố cục trang, chế độ trang, v.v.

#### H: Làm sao tôi có thể kiểm tra xem trang đích và hệ số thu phóng đã chỉ định có hoạt động như mong muốn không?

A: Sau khi áp dụng mã được cung cấp để chỉ định trang đích và hệ số thu phóng, hãy mở tệp PDF đã sửa đổi và xác minh rằng tệp mở với đúng trang và mức thu phóng.