---
title: Đặt tên phông chữ mặc định
linktitle: Đặt tên phông chữ mặc định
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách đặt tên phông chữ mặc định khi kết xuất PDF thành hình ảnh bằng Aspose.PDF cho .NET. Hướng dẫn này bao gồm các điều kiện tiên quyết, hướng dẫn từng bước và Câu hỏi thường gặp.
type: docs
weight: 270
url: /vi/net/document-conversion/set-default-font-name/
---
## Giới thiệu

Bạn đã bao giờ thử kết xuất một tài liệu PDF thành hình ảnh nhưng thấy phông chữ trông không ổn chưa? Có thể văn bản bị méo hoặc có thể phông chữ gốc không được hỗ trợ. Đây chính là lúc thiết lập phông chữ mặc định có thể cứu vãn tình hình! Sử dụng Aspose.PDF cho .NET, bạn có thể dễ dàng thiết lập phông chữ mặc định cho bản kết xuất PDF của mình, đảm bảo tài liệu của bạn trông sắc nét và chuyên nghiệp. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thiết lập tên phông chữ mặc định khi kết xuất PDF thành hình ảnh. Đến cuối hướng dẫn này, bạn sẽ có đủ kỹ năng để giải quyết mọi thách thức kết xuất PDF mà bạn gặp phải. Sẵn sàng chưa? Hãy cùng bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, bạn cần chuẩn bị một số thứ sau:

- Aspose.PDF cho .NET: Thư viện mạnh mẽ này là thứ chúng ta sẽ sử dụng để thao tác tài liệu PDF của mình. Bạn có thể tải xuống từ[Trang web Aspose](https://releases.aspose.com/pdf/net/).
- Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Đây sẽ là môi trường phát triển của chúng tôi.
- .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework. Aspose.PDF cho .NET hỗ trợ nhiều phiên bản khác nhau, vì vậy hãy kiểm tra tài liệu để phù hợp với nhu cầu của bạn.
- Tài liệu PDF: Bạn sẽ cần một tài liệu PDF mẫu để làm việc. Nếu bạn không có, hãy tạo một tệp PDF đơn giản hoặc tải xuống mẫu trực tuyến.

Khi bạn đã thiết lập mọi thứ, chúng ta đã sẵn sàng để bắt đầu viết mã!

## Nhập gói

Trước khi đi sâu vào mã, điều cần thiết là phải nhập các gói cần thiết. Điều này đảm bảo rằng chúng ta có quyền truy cập vào tất cả các lớp và phương thức cần thiết cho dự án của mình.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Những lệnh nhập này rất quan trọng vì chúng đưa vào các không gian tên cần thiết để xử lý thao tác PDF, kết xuất hình ảnh và hoạt động truyền tệp.

## Bước 1: Thiết lập dự án và đường dẫn tài liệu của bạn

Trước tiên, hãy thiết lập đường dẫn thư mục nơi tài liệu PDF của bạn được lưu trữ. Đây sẽ là điểm bắt đầu để bạn thao tác với tệp PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Đây,`dataDir` là thư mục nơi tài liệu PDF của bạn nằm. Hãy đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn. Điều này rất cần thiết vì mã cần biết nơi để lấy tệp PDF.

## Bước 2: Tải Tài liệu PDF

Bây giờ chúng ta đã có đường dẫn tài liệu, bước tiếp theo là tải tài liệu PDF vào bộ nhớ để chúng ta có thể bắt đầu làm việc trên đó.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Chúng tôi sử dụng`Document` lớp từ thư viện Aspose.PDF để tải tệp PDF của chúng tôi. Lớp này cung cấp nhiều phương pháp và thuộc tính khác nhau để làm việc với tài liệu PDF.`"input.pdf"` nên được thay thế bằng tên tệp thực tế của PDF của bạn. Tệp này sẽ được sử dụng làm đầu vào để kết xuất.

## Bước 3: Tạo luồng hình ảnh cho đầu ra

Sau khi tài liệu được tải, chúng ta cần thiết lập luồng để lưu hình ảnh đã kết xuất. Đây là nơi hình ảnh đầu ra sẽ được lưu trữ.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 Các`FileStream`lớp được sử dụng để tạo một tệp mới nơi hình ảnh được kết xuất sẽ được lưu. Trong ví dụ này, chúng tôi đang lưu hình ảnh dưới dạng`"SetDefaultFontName.png"` . Các`FileMode.Create` đảm bảo rằng một tập tin mới được tạo hoặc một tập tin hiện có được ghi đè.

## Bước 4: Thiết lập độ phân giải cho hình ảnh

Trước khi kết xuất PDF thành hình ảnh, điều quan trọng là phải thiết lập độ phân giải. Điều này quyết định chất lượng và độ rõ nét của hình ảnh đầu ra.

```csharp
Resolution resolution = new Resolution(300);
```
 Các`Resolution` lớp thiết lập độ phân giải của hình ảnh đầu ra. Ở đây, chúng tôi đã chọn độ phân giải 300 DPI (chấm trên inch), đây là độ phân giải tiêu chuẩn cho hình ảnh chất lượng cao. Điều này đảm bảo rằng văn bản và đồ họa trong PDF của bạn được hiển thị rõ ràng mà không mất chi tiết.

## Bước 5: Cấu hình thiết bị PNG

Tiếp theo, chúng ta cần cấu hình thiết bị sẽ xử lý việc hiển thị PDF thành hình ảnh PNG.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 Các`PngDevice` lớp chịu trách nhiệm chuyển đổi tài liệu PDF thành hình ảnh PNG. Bằng cách chuyển`resolution` phản đối nó, chúng tôi đảm bảo rằng hình ảnh được tạo ra với DPI đã chỉ định.

## Bước 6: Đặt Tên Phông Chữ Mặc Định

Đây là phần quan trọng – thiết lập tên phông chữ mặc định. Đây sẽ là phông chữ dự phòng trong trường hợp phông chữ gốc trong PDF không khả dụng.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Chúng tôi tạo ra một trường hợp của`RenderingOptions` và thiết lập nó`DefaultFontName` tài sản để`"Arial"`. Điều này có nghĩa là nếu không tìm thấy phông chữ gốc trong PDF, Arial sẽ được sử dụng thay thế. Bước này rất quan trọng để duy trì khả năng đọc và giao diện của văn bản trong hình ảnh được hiển thị.

## Bước 7: Kết xuất trang PDF thành hình ảnh

Cuối cùng, khi mọi thứ đã được thiết lập xong, chúng ta có thể hiển thị trang đầu tiên của tài liệu PDF thành hình ảnh và lưu nó bằng luồng tệp đã tạo trước đó.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 Các`Process` phương pháp của`PngDevice` lớp được sử dụng để hiển thị trang PDF được chỉ định (trong trường hợp này là trang đầu tiên) thành hình ảnh. Sau đó, đầu ra được lưu vào`imageStream`. Bước này chuyển đổi trang PDF thành hình ảnh PNG với độ phân giải và phông chữ mặc định đã chỉ định.

## Bước 8: Đóng luồng tệp và tài liệu PDF

Sau khi kết xuất hình ảnh, điều quan trọng là phải đóng luồng tệp và tài liệu PDF để giải phóng tài nguyên.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Đóng cửa`imageStream` đảm bảo rằng tập tin được lưu đúng cách và không có dữ liệu nào bị mất. Xử lý`pdfDocument` giải phóng bộ nhớ và tài nguyên, ngăn ngừa mọi rò rỉ bộ nhớ tiềm ẩn.

## Phần kết luận

Và bạn đã có nó! Chỉ với một vài dòng mã, bạn đã học cách đặt tên phông chữ mặc định khi kết xuất PDF thành hình ảnh bằng Aspose.PDF cho .NET. Kỹ năng này cực kỳ hữu ích, đặc biệt là khi xử lý các tệp PDF có thể chứa phông chữ không được hỗ trợ. Bằng cách đặt phông chữ mặc định, bạn đảm bảo rằng hình ảnh được kết xuất của mình duy trì khả năng đọc và giao diện chuyên nghiệp.

## Câu hỏi thường gặp

### Điều gì xảy ra nếu phông chữ mặc định được chỉ định không được cài đặt trên hệ thống?
 Nếu phông chữ mặc định được chỉ định trong`RenderingOptions` không được cài đặt trên hệ thống, Aspose.PDF sẽ sử dụng phông chữ dự phòng do hệ thống xác định.

### Tôi có thể sử dụng phông chữ khác ngoài Arial làm phông chữ mặc định không?
Hoàn toàn được! Bạn có thể đặt bất kỳ phông chữ nào được cài đặt trên hệ thống của bạn làm phông chữ mặc định.

### Có thể chuyển nhiều trang PDF thành hình ảnh cùng một lúc không?
Có, bạn có thể lặp qua các trang PDF và hiển thị từng trang riêng lẻ bằng cùng một quy trình.

### Việc thiết lập độ phân giải cao có ảnh hưởng đến hiệu suất kết xuất PDF không?
Đúng, độ phân giải cao hơn sẽ tạo ra tệp hình ảnh lớn hơn và có thể làm tăng thời gian hiển thị, nhưng chúng cũng sẽ tạo ra hình ảnh rõ nét hơn.

### Tôi có thể chuyển đổi PDF sang các định dạng hình ảnh khác ngoài PNG không?
Có, Aspose.PDF hỗ trợ hiển thị nhiều định dạng hình ảnh khác nhau như JPEG, BMP và TIFF.