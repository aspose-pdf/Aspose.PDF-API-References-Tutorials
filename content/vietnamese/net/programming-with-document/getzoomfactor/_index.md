---
title: Nhận hệ số thu phóng trong tệp PDF
linktitle: Nhận hệ số thu phóng trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để lấy hệ số thu phóng trong tệp PDF với hướng dẫn từng bước này.
type: docs
weight: 210
url: /vi/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET là thư viện thao tác PDF cung cấp nhiều tính năng để thực hiện các thao tác khác nhau trên tài liệu PDF. Một trong những tính năng này là khả năng lấy hệ số thu phóng trong tệp PDF. Trong hướng dẫn này, chúng tôi sẽ giải thích cách sử dụng Aspose.PDF cho .NET để lấy hệ số thu phóng trong tệp PDF bằng mã nguồn C#.


## Bước 1: Khởi tạo đối tượng Tài liệu mới

 Bước đầu tiên để lấy hệ số thu phóng của tệp PDF bằng Aspose.PDF cho .NET là tạo một tệp PDF mới`Document` sự vật. Các`Document` đối tượng đại diện cho một tài liệu PDF có thể được tải từ một tệp hoặc luồng.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu mới
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Trong đoạn mã trên, chúng tôi đã tạo một`Document` đối tượng bằng cách chuyển đường dẫn của tệp PDF tới hàm tạo của`Document` lớp học. Bạn cần thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế của thư mục chứa tệp PDF của bạn.

## Bước 2: Tạo đối tượng GoToAction

 Bước tiếp theo là tạo một`GoToAction` sự vật. MỘT`GoToAction`đối tượng đại diện cho một hành động đi đến một đích cụ thể trong tài liệu PDF. Trong trường hợp của chúng tôi, chúng tôi muốn lấy hệ số thu phóng của tệp PDF, vì vậy chúng tôi sẽ sử dụng`OpenAction` tài sản của`Document` đối tượng để có được`GoToAction` sự vật.

```csharp
// Tạo đối tượng GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Trong đoạn mã trên, chúng tôi đã tạo một`GoToAction` đối tượng bằng cách truyền`OpenAction` tài sản của`Document` chủ đề`GoToAction`.

## Bước 3: Lấy hệ số Zoom của file PDF

 Bước thứ ba là lấy hệ số thu phóng của tệp PDF. Chúng ta có thể lấy hệ số thu phóng của tệp PDF bằng cách truy cập`Destination` tài sản của`GoToAction` đối tượng và sau đó truyền nó tới`XYZExplicitDestination` . Các`XYZExplicitDestination` lớp đại diện cho một đích đến trong tài liệu PDF chỉ định tọa độ và hệ số thu phóng cần đi tới.

```csharp
// Lấy hệ số thu phóng của tệp PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Giá trị thu phóng tài liệu;
```

 Trong đoạn mã trên, chúng ta đã truy cập vào`Destination` tài sản của`GoToAction` đối tượng và sau đó truyền nó tới`XYZExplicitDestination` . Sau đó, chúng tôi đã truy cập vào`Zoom` tài sản của`XYZExplicitDestination` object để lấy hệ số thu phóng của tệp PDF.

## Bước 4: Xuất hệ số Zoom

 Bước cuối cùng là xuất hệ số thu phóng của tệp PDF. Chúng ta có thể sử dụng`System.Console.WriteLine`

```csharp
// Lấy hệ số thu phóng của tệp PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Giá trị thu phóng tài liệu;
```        

### Mã nguồn ví dụ để lấy hệ số thu phóng bằng Aspose.PDF cho .NET

Đây là mã nguồn mẫu hoàn chỉnh cho Get Zoom Factor bằng Aspose.PDF for .NET:

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

Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng Aspose.PDF cho .NET để lấy hệ số thu phóng của tệp PDF. Hệ số thu phóng là một khía cạnh quan trọng của tài liệu PDF vì nó xác định kích thước hiển thị ban đầu khi được mở trong trình xem. Bằng cách truy cập và sử dụng hệ số thu phóng, nhà phát triển có thể tùy chỉnh trải nghiệm xem cho người dùng cuối. Aspose.PDF for .NET cung cấp API đơn giản và hiệu quả để truy xuất hệ số thu phóng và thông tin liên quan đến điều hướng khác từ tài liệu PDF, trao quyền cho các nhà phát triển xây dựng các ứng dụng PDF tương tác và giàu tính năng.

### Câu hỏi thường gặp về lấy hệ số thu phóng trong tệp PDF

#### Hỏi: Hệ số thu phóng trong tệp PDF là gì?

Đáp: Hệ số thu phóng trong tệp PDF đề cập đến mức độ phóng đại được áp dụng cho tài liệu khi nó được xem. Nó xác định kích thước hiển thị ban đầu của tệp PDF trên màn hình. Hệ số thu phóng 1,0 biểu thị kích thước thực tế (thu phóng 100%), trong khi hệ số thu phóng lớn hơn 1,0 biểu thị mức phóng to và hệ số thu phóng nhỏ hơn 1,0 biểu thị mức thu nhỏ.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng thông tin hệ số thu phóng trong ứng dụng của mình?

Đáp: Bạn có thể sử dụng thông tin hệ số thu phóng để tùy chỉnh kích thước hiển thị ban đầu của tài liệu PDF khi tài liệu đó được mở trong trình xem. Ví dụ: bạn có thể đặt hệ số thu phóng cụ thể để đảm bảo rằng tệp PDF được hiển thị ở kích thước cụ thể hoặc vừa với toàn bộ trang trong cửa sổ của người xem.

#### Câu hỏi: Tôi có thể sửa đổi hệ số thu phóng của tài liệu PDF theo chương trình bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể sửa đổi hệ số thu phóng của tài liệu PDF theo chương trình bằng cách sử dụng Aspose.PDF cho .NET. Bạn có thể đặt hệ số thu phóng cho các hành động cụ thể, chẳng hạn như`GoToAction` hoặc`GoToRemoteAction`để kiểm soát cách tài liệu được hiển thị khi người dùng tương tác với các liên kết hoặc dấu trang.

#### Câu hỏi: Có cách nào khác để điều hướng đến các vị trí cụ thể trong tài liệu PDF bằng Aspose.PDF cho .NET không?

 Đáp: Có, Aspose.PDF for .NET cung cấp nhiều tính năng khác nhau để điều hướng đến các vị trí cụ thể trong tài liệu PDF. Bên cạnh việc sử dụng`GoToAction` , bạn có thể sử dụng các hành động khác như`GoToURIAction` để mở một URL,`GoToEmbeddedAction` để điều hướng đến các tập tin nhúng và`GoToNamedAction` để đi tới các đích được đặt tên trong tài liệu PDF.