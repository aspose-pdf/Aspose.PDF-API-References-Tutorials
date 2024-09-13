---
title: Ký số có dấu thời gian trong tệp PDF
linktitle: Ký số có dấu thời gian trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách ký số vào PDF có dấu thời gian bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này bao gồm các điều kiện tiên quyết, thiết lập chứng chỉ, dấu thời gian và nhiều hơn nữa.
type: docs
weight: 50
url: /vi/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Giới thiệu

Bạn đã bao giờ cần ký số vào PDF và thêm dấu thời gian để tăng thêm tính bảo mật chưa? Cho dù bạn đang làm việc trên các tài liệu pháp lý, hợp đồng hay bất kỳ thứ gì yêu cầu xác thực an toàn, chữ ký số có dấu thời gian sẽ tăng thêm một lớp độ tin cậy. Trong hướng dẫn này, chúng tôi sẽ chia nhỏ cách bạn có thể sử dụng Aspose.PDF cho .NET để thêm chữ ký số cùng với dấu thời gian vào tài liệu PDF của mình. Đừng lo lắng, chúng tôi sẽ hướng dẫn từng bước!

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, có một số điều bạn cần thiết lập để theo dõi. Sau đây là danh sách kiểm tra nhanh các điều kiện tiên quyết để bạn bắt đầu:

-  Aspose.PDF cho Thư viện .NET: Bạn sẽ cần thư viện Aspose.PDF cho .NET được cài đặt trong dự án của bạn. Bạn có thể[tải phiên bản mới nhất tại đây](https://releases.aspose.com/pdf/net/) hoặc thêm nó vào dự án của bạn thông qua NuGet.
- Tài liệu PDF: Bạn sẽ cần một tệp PDF mẫu để làm việc. Đảm bảo có tệp trong thư mục dự án mà bạn muốn ký.
-  Chứng chỉ số (tệp PFX): Đảm bảo bạn có chứng chỉ số (một`.pfx` tệp) để ký kỹ thuật số vào tài liệu.
- URL đóng dấu thời gian: Đây là dịch vụ đóng dấu thời gian trực tuyến sẽ được sử dụng để đính kèm dấu thời gian vào chữ ký số. 
- Kiến thức cơ bản về C#: Bạn không cần phải là chuyên gia, nhưng việc biết những kiến thức cơ bản về C# sẽ giúp bạn hiểu và tùy chỉnh mã.

Khi bạn đã đánh dấu vào tất cả các ô này, bạn đã sẵn sàng để bắt đầu viết mã!

## Nhập gói

Để bắt đầu, bạn sẽ cần nhập các không gian tên sau vào dự án C# của mình. Điều này đảm bảo bạn có quyền truy cập vào các lớp và hàm Aspose.PDF có liên quan.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Bước 1: Tải Tài liệu PDF

Điều đầu tiên chúng ta cần làm là tải tài liệu PDF mà chúng ta muốn ký. Đây là cách bạn thực hiện:

```csharp
// Xác định đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Bước này khá đơn giản. Chúng tôi chỉ cần xác định đường dẫn đến tài liệu mà chúng tôi muốn ký.`Document` lớp từ Aspose.PDF xử lý việc tải tệp.

## Bước 2: Thiết lập chữ ký số

Tiếp theo, chúng ta sẽ tạo chữ ký số bằng lớp PKCS7 và tải tệp PFX. Tệp PFX này chứa chứng chỉ và khóa riêng của bạn, cần thiết để ký tài liệu.

```csharp
// Đường dẫn đến tệp .pfx của bạn
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Khởi tạo đối tượng chữ ký
PdfFileSignature signature = new PdfFileSignature(document);

// Tải tệp PFX bằng mật khẩu
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 Tại thời điểm này, bạn đang yêu cầu Aspose sử dụng chứng chỉ số của bạn để ký tài liệu.`PKCS7`object sẽ xử lý toàn bộ công việc mã hóa cho bạn, do đó bạn không cần phải lo lắng về những chi tiết cụ thể.

## Bước 3: Thêm Cài đặt Dấu thời gian

Một trong những thành phần chính của chữ ký số mạnh mẽ là dấu thời gian. Điều này đảm bảo rằng chữ ký của tài liệu có thể được xác minh ngay cả sau khi chứng chỉ đã hết hạn. Hãy thiết lập dấu thời gian bằng cách sử dụng cơ quan đóng dấu thời gian trực tuyến.

```csharp
// Xác định cài đặt dấu thời gian
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "người dùng:mật khẩu");

// Thêm cài đặt dấu thời gian vào đối tượng PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Tại đây, bạn chỉ định URL cho dịch vụ đóng dấu thời gian, dịch vụ này sẽ tự động cung cấp thời gian và ngày tháng cho chữ ký của bạn. Điều này có thể được thực hiện có hoặc không có xác thực.

## Bước 4: Xác định vị trí và hình thức chữ ký

Bây giờ, chúng ta sẽ xác định vị trí chữ ký sẽ xuất hiện trong PDF và kích thước của nó. Bạn có thể tùy chỉnh vị trí của hộp chữ ký trên trang cũng như kích thước.

```csharp
//Xác định hình thức và vị trí chữ ký (trang 1, có hình chữ nhật được chỉ định)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Tại đây, chúng tôi sẽ xác định một hình chữ nhật đặt chữ ký tại tọa độ (100, 100) trên trang đầu tiên của tệp PDF, với chiều rộng là 200 và chiều cao là 100. Bạn có thể thay đổi các giá trị này để phù hợp với thiết kế của mình.

## Bước 5: Ký vào Tài liệu PDF

Khi mọi thứ đã được thiết lập, đã đến lúc thực sự áp dụng chữ ký số vào PDF. Bước này kết hợp chứng chỉ, dấu thời gian và vị trí thành một lệnh đơn giản.

```csharp
// Ký vào tài liệu ở trang đầu tiên
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Sau đây là những gì đang xảy ra:
- 1: Điều này có nghĩa là chữ ký phải được áp dụng cho trang đầu tiên.
- "Lý do ký": Đây là nơi bạn có thể nêu rõ lý do bạn ký tài liệu.
- “Liên hệ”: Nhập thông tin liên hệ của người ký.
- "Vị trí": Chỉ rõ vị trí của người ký.
- true: Giá trị boolean này cho biết chữ ký có hiển thị trong tài liệu hay không.
- rect: Hình chữ nhật mà chúng ta đã xác định trước đó chỉ định kích thước và vị trí của chữ ký.
- pkcs: Đối tượng PKCS7 chứa chứng chỉ kỹ thuật số và cài đặt dấu thời gian.

## Bước 6: Lưu PDF đã ký

Sau khi tài liệu đã được ký, tất cả những gì còn lại cần làm là lưu nó. Bạn có thể chọn tên tệp mới để giữ cả phiên bản gốc và phiên bản đã ký.

```csharp
// Lưu tài liệu PDF đã ký
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Tệp PDF mới được ký và đóng dấu thời gian của bạn hiện đã được lưu vào thư mục đã chỉ định!

## Phần kết luận

Và bạn đã có nó! Bạn đã ký thành công một tệp PDF có dấu thời gian bằng Aspose.PDF cho .NET. Quy trình này đảm bảo tính xác thực và toàn vẹn của tài liệu, mang lại sự an tâm cho cả bạn và người nhận. Chữ ký số ngày càng trở nên thiết yếu trong thế giới kỹ thuật số ngày nay, vì vậy việc thành thạo quy trình này chắc chắn là một kỹ năng đáng có.

## Câu hỏi thường gặp

### Tôi có thể sử dụng định dạng tệp khác cho chứng chỉ không?  
Có, nhưng hướng dẫn này tập trung vào việc sử dụng tệp PFX, đây là định dạng phổ biến nhất cho chứng chỉ kỹ thuật số.

### Tôi có cần kết nối Internet để áp dụng dấu thời gian không?  
Có, vì dấu thời gian được lấy từ cơ quan đóng dấu thời gian trực tuyến nên bạn sẽ cần có kết nối internet.

### Tôi có thể ký nhiều trang trong một tệp PDF không?  
 Chắc chắn rồi! Bạn có thể sửa đổi`signature.Sign()` phương pháp nhắm mục tiêu nhiều trang hoặc lặp qua tất cả các trang.

### Điều gì xảy ra nếu mật khẩu tệp PFX không đúng?  
Bạn sẽ nhận được thông báo ngoại lệ nếu mật khẩu sai, vì vậy hãy đảm bảo nhập đúng mật khẩu.

### Tôi có thể làm chữ ký ẩn đi được không?  
 Vâng, bạn có thể vượt qua`false` đến`Sign` tham số hiển thị của phương thức để làm cho chữ ký trở nên vô hình.