---
title: Đặt Thuộc Tính Callout Trong Tệp PDF
linktitle: Đặt Thuộc Tính Callout Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách thiết lập thuộc tính chú thích trong tệp PDF bằng Aspose.PDF cho .NET trong hướng dẫn chi tiết từng bước này.
type: docs
weight: 130
url: /vi/net/annotations/setcalloutproperty/
---
## Giới thiệu

Việc tạo các tài liệu PDF chuyên nghiệp và hấp dẫn về mặt hình ảnh thường đòi hỏi phải thêm các chú thích để thu hút sự chú ý vào nội dung cụ thể. Một trong những chú thích như vậy là chú thích chú thích, giống như các bong bóng lời thoại mà bạn thấy trong truyện tranh. Chúng giúp làm rõ hoặc nhấn mạnh văn bản trong PDF của bạn. Aspose.PDF cho .NET giúp bạn thêm các chú thích như vậy vào tài liệu của mình một cách cực kỳ dễ dàng và trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách đặt thuộc tính chú thích chú thích trong tệp PDF bằng thư viện mạnh mẽ này. Cho dù bạn là một nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, thì khi đọc hết hướng dẫn này, bạn sẽ hiểu rõ cách làm việc với các chú thích chú thích trong tệp PDF.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, chúng ta hãy tìm hiểu những điều cần thiết để bắt đầu.

1.  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/net/).
2. IDE: Môi trường phát triển như Visual Studio.
3. .NET Framework: Đảm bảo rằng bạn đã cài đặt .NET trên máy của mình.
4. Giấy phép tạm thời: Nếu bạn muốn dùng thử đầy đủ các tính năng của Aspose.PDF mà không có giới hạn, hãy lấy[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

## Nhập gói

Trước khi bắt đầu viết mã, bạn cần nhập các gói cần thiết cho phép bạn làm việc với các tệp PDF và chú thích.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Các lệnh nhập này sẽ cung cấp cho bạn tất cả các lớp và phương thức cần thiết để thao tác với tài liệu PDF và tạo chú thích như chú thích.

## Bước 1: Khởi tạo Tài liệu PDF

Bước đầu tiên trong hành trình của chúng ta là khởi tạo một tài liệu PDF mới, nơi chúng ta sẽ thêm chú thích chú thích của mình. Hãy nghĩ về điều này như việc thiết lập một khung vẽ trống nơi bạn có thể bắt đầu thêm các thành phần.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một tài liệu PDF mới
Document doc = new Document();
```
 Ở đây, chúng tôi đang tạo ra một cái mới`Document` đối tượng sẽ đóng vai trò là tệp PDF của chúng tôi.`dataDir` biến được đặt thành thư mục mà bạn muốn lưu tệp PDF sau khi hoàn tất.

## Bước 2: Thêm trang mới vào tài liệu

Một tài liệu PDF có thể có nhiều trang và trong bước này, chúng ta sẽ thêm một trang mới vào tài liệu của mình. Trang này sẽ là nơi chú thích chú thích của chúng ta được đặt.

```csharp
//Thêm một trang mới vào tài liệu
Page page = doc.Pages.Add();
```
 Các`Pages.Add()`phương pháp được sử dụng để thêm một trang mới vào`doc` đối tượng. Trang mới được lưu trữ trong`page` biến mà chúng ta sẽ sử dụng sau khi thêm chú thích.

## Bước 3: Xác định Giao diện Mặc định

Chú thích, giống như chú thích, có giao diện trực quan mà bạn có thể tùy chỉnh. Trong bước này, chúng ta sẽ xác định văn bản trong chú thích sẽ trông như thế nào.

```csharp
// Xác định giao diện mặc định cho chú thích
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Chúng tôi tạo ra một`DefaultAppearance` đối tượng xác định màu chữ và cỡ chữ. Ở đây, chữ sẽ có màu đỏ và cỡ chữ được đặt thành 10. Giao diện này sẽ được áp dụng cho chú thích chú thích.

## Bước 4: Tạo chú thích văn bản tự do

Bây giờ là lúc tạo chú thích thực tế. Chú thích văn bản tự do cho phép chúng ta thêm chú thích với văn bản và kiểu dáng cụ thể.

```csharp
// Tạo FreeTextAnnotation với chú thích
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Chúng tôi tạo ra một`FreeTextAnnotation` đối tượng có tọa độ cụ thể, xác định vị trí của nó trên trang.`Intent` được thiết lập để`FreeTextCallout` , cho biết đây là chú thích chú thích.`EndingStyle` được thiết lập để`OpenArrow`nghĩa là dòng chú thích sẽ kết thúc bằng một mũi tên mở.

## Bước 5: Xác định các điểm dòng chú thích

Chú thích chú thích có một đường thẳng trỏ đến khu vực quan tâm. Ở đây, chúng ta sẽ xác định các điểm tạo nên đường thẳng này.

```csharp
// Xác định các điểm cho dòng chú thích
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 Các`Callout` thuộc tính là một mảng của`Point` các đối tượng, mỗi đối tượng đại diện cho một tọa độ trên trang. Các điểm này xác định đường dẫn của dòng chú thích, tạo cho nó hình dạng bong bóng lời thoại cổ điển.

## Bước 6: Thêm chú thích vào trang

Sau khi tạo và cấu hình chú thích, bước tiếp theo là thêm chú thích vào trang.

```csharp
// Thêm chú thích vào trang
page.Annotations.Add(fta);
```
 Các`Annotations.Add()` phương pháp này được sử dụng để đặt chú thích trên trang chúng ta đã tạo trước đó. Bước này thực sự "vẽ" chú thích trên trang PDF.

## Bước 7: Thiết lập Nội dung Văn bản Giàu

Chú thích chú thích có thể bao gồm văn bản phong phú, cho phép định dạng nội dung trong bong bóng. Hãy thêm một số văn bản mẫu.

```csharp
// Đặt văn bản phong phú cho chú thích
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Đây là một mẫu</span></p></body>";
```
 Các`RichText` thuộc tính được thiết lập với nội dung HTML. Điều này cho phép định dạng chi tiết trong chú thích, chẳng hạn như chỉ định kích thước phông chữ, màu sắc và kiểu chữ.

## Bước 8: Lưu tài liệu PDF

Cuối cùng, sau khi thiết lập mọi thứ, chúng ta cần lưu tài liệu. Bước này hoàn tất việc tạo PDF với chú thích chú thích.

```csharp
// Lưu tài liệu
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 Các`Save()` phương pháp này lưu tài liệu vào thư mục được chỉ định với tên tệp "SetCalloutProperty.pdf". Bước này kết thúc quá trình tạo PDF của chúng tôi.

## Phần kết luận

Và bạn đã có nó! Bạn vừa tạo một tài liệu PDF với chú thích chú thích bằng Aspose.PDF cho .NET. Chú thích này có thể cực kỳ hữu ích để làm nổi bật hoặc giải thích các phần cụ thể trong tài liệu của bạn. Aspose.PDF cung cấp một API mạnh mẽ giúp thao tác PDF trở nên đơn giản và linh hoạt. Cho dù bạn đang thêm chú thích, chuyển đổi tài liệu hay xử lý các tác vụ PDF phức tạp, Aspose.PDF đều có thể giúp bạn.

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh thêm giao diện của chú thích không?

Hoàn toàn được! Bạn có thể tùy chỉnh nhiều khía cạnh khác nhau như màu đường kẻ, độ dày và kiểu phông chữ cũng như kiểu chữ của văn bản.

### Có thể thêm nhiều chú thích trên cùng một trang không?

Có, bạn có thể thêm bao nhiêu chú thích tùy ý bằng cách lặp lại các bước cho từng chú thích.

### Làm thế nào để thay đổi vị trí của chú thích?

 Chỉ cần sửa đổi tọa độ trong`Rectangle` Và`Callout` thuộc tính để định vị lại chú thích.

### Tôi có thể thêm các loại chú thích khác bằng Aspose.PDF không?

Có, Aspose.PDF hỗ trợ nhiều loại chú thích khác nhau, bao gồm đánh dấu, đóng dấu và đính kèm tệp.

### Nội dung văn bản phong phú có giới hạn ở HTML không?

 Các`RichText` Thuộc tính này hỗ trợ một tập hợp con của HTML, cho phép bạn đưa vào văn bản có kiểu và định dạng cơ bản.