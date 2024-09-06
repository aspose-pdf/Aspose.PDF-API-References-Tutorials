---
title: Nhận Hệ số Phóng to trong Tệp PDF
linktitle: Nhận Hệ số Phóng to trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để có được hệ số thu phóng trong tệp PDF với hướng dẫn từng bước này.
type: docs
weight: 210
url: /vi/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET là một thư viện thao tác PDF cung cấp nhiều tính năng để thực hiện nhiều thao tác khác nhau trên tài liệu PDF. Một trong những tính năng này là khả năng lấy hệ số thu phóng trong tệp PDF. Trong hướng dẫn này, chúng tôi sẽ giải thích cách sử dụng Aspose.PDF for .NET để lấy hệ số thu phóng trong tệp PDF bằng mã nguồn C#.


## Bước 1: Khởi tạo đối tượng Document mới

 Bước đầu tiên để có được hệ số thu phóng của tệp PDF bằng Aspose.PDF cho .NET là tạo một tệp mới`Document` đối tượng. Các`Document` đối tượng biểu thị một tài liệu PDF có thể được tải từ một tệp hoặc một luồng.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu mới
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Trong đoạn mã trên, chúng tôi đã tạo ra một`Document` đối tượng bằng cách truyền đường dẫn của tệp PDF đến trình xây dựng của`Document` lớp. Bạn cần thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế của thư mục chứa tệp PDF của bạn.

## Bước 2: Tạo đối tượng GoToAction

 Bước tiếp theo là tạo ra một`GoToAction` đối tượng. A`GoToAction`đối tượng biểu thị một hành động đi đến một đích cụ thể trong tài liệu PDF. Trong trường hợp của chúng tôi, chúng tôi muốn có hệ số thu phóng của tệp PDF, vì vậy chúng tôi sẽ sử dụng`OpenAction` tài sản của`Document` đối tượng để có được`GoToAction` sự vật.

```csharp
// Tạo đối tượng GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Trong đoạn mã trên, chúng tôi đã tạo ra một`GoToAction` đối tượng bằng cách đúc`OpenAction` tài sản của`Document` phản đối`GoToAction`.

## Bước 3: Lấy hệ số Zoom của tệp PDF

 Bước thứ ba là lấy hệ số thu phóng của tệp PDF. Chúng ta có thể lấy hệ số thu phóng của tệp PDF bằng cách truy cập`Destination` tài sản của`GoToAction` đối tượng và sau đó chuyển nó thành`XYZExplicitDestination` . Các`XYZExplicitDestination` lớp biểu thị đích đến trong tài liệu PDF, chỉ định tọa độ và hệ số thu phóng cần đến.

```csharp
// Lấy hệ số thu phóng của tệp PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Giá trị thu phóng tài liệu;
```

 Trong đoạn mã trên, chúng ta đã truy cập`Destination` tài sản của`GoToAction` đối tượng và sau đó chuyển nó sang`XYZExplicitDestination` . Sau đó, chúng tôi đã truy cập`Zoom` tài sản của`XYZExplicitDestination` đối tượng để có được hệ số thu phóng của tệp PDF.

## Bước 4: Xuất hệ số Zoom

 Bước cuối cùng là xuất hệ số thu phóng của tệp PDF. Chúng ta có thể sử dụng`System.Console.WriteLine`

```csharp
// Lấy hệ số thu phóng của tệp PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Giá trị thu phóng tài liệu;
```        

### Mã nguồn ví dụ để lấy hệ số thu phóng bằng Aspose.PDF cho .NET

Sau đây là mã nguồn ví dụ đầy đủ cho Get Zoom Factor sử dụng Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu mới
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Tạo đối tượng GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Lấy hệ số thu phóng của tệp PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Giá trị thu phóng tài liệu;
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng Aspose.PDF cho .NET để lấy hệ số thu phóng của tệp PDF. Hệ số thu phóng là một khía cạnh quan trọng của tài liệu PDF, vì nó xác định kích thước hiển thị ban đầu khi mở trong trình xem. Bằng cách truy cập và sử dụng hệ số thu phóng, các nhà phát triển có thể tùy chỉnh trải nghiệm xem cho người dùng cuối. Aspose.PDF cho .NET cung cấp API đơn giản và hiệu quả để lấy hệ số thu phóng và các thông tin liên quan đến điều hướng khác từ tài liệu PDF, trao quyền cho các nhà phát triển xây dựng các ứng dụng PDF giàu tính năng và tương tác.

### Câu hỏi thường gặp để có được hệ số thu phóng trong tệp PDF

#### H: Hệ số thu phóng trong tệp PDF là bao nhiêu?

A: Hệ số thu phóng trong tệp PDF đề cập đến mức độ phóng đại được áp dụng cho tài liệu khi xem. Nó xác định kích thước hiển thị ban đầu của tệp PDF trên màn hình. Hệ số thu phóng 1,0 biểu thị kích thước thực tế (thu phóng 100%), trong khi hệ số thu phóng lớn hơn 1,0 biểu thị mức phóng to và hệ số thu phóng nhỏ hơn 1,0 biểu thị mức thu nhỏ.

#### H: Tôi có thể sử dụng thông tin về hệ số thu phóng trong ứng dụng của mình như thế nào?

A: Bạn có thể sử dụng thông tin hệ số thu phóng để tùy chỉnh kích thước hiển thị ban đầu của tài liệu PDF khi mở trong trình xem. Ví dụ: bạn có thể đặt hệ số thu phóng cụ thể để đảm bảo PDF được hiển thị ở kích thước cụ thể hoặc vừa với toàn bộ trang trong cửa sổ trình xem.

#### H: Tôi có thể tự động thay đổi hệ số thu phóng của tài liệu PDF bằng Aspose.PDF cho .NET không?

 A: Có, bạn có thể sửa đổi hệ số thu phóng của tài liệu PDF theo chương trình bằng cách sử dụng Aspose.PDF cho .NET. Bạn có thể đặt hệ số thu phóng cho các hành động cụ thể, chẳng hạn như`GoToAction` hoặc`GoToRemoteAction`để kiểm soát cách hiển thị tài liệu khi người dùng tương tác với các liên kết hoặc dấu trang.

#### H: Có cách nào khác để điều hướng đến các vị trí cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET không?

 A: Có, Aspose.PDF cho .NET cung cấp nhiều tính năng khác nhau để điều hướng đến các vị trí cụ thể trong tài liệu PDF. Bên cạnh việc sử dụng`GoToAction` , bạn có thể sử dụng các hành động khác như`GoToURIAction` để mở một URL,`GoToEmbeddedAction` để điều hướng đến các tập tin nhúng và`GoToNamedAction` để đi đến các đích được đặt tên trong tài liệu PDF.