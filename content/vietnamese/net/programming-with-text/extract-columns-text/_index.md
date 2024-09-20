---
title: Trích xuất văn bản cột trong tệp PDF
linktitle: Trích xuất văn bản cột trong tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách trích xuất các cột văn bản từ tệp PDF bằng Aspose.PDF cho .NET. Hướng dẫn này phân tích từng bước với các ví dụ về mã và giải thích.
type: docs
weight: 150
url: /vi/net/programming-with-text/extract-columns-text/
---
## Giới thiệu

Bạn đang làm việc với các tệp PDF và cần trích xuất văn bản theo định dạng cột cụ thể? Cho dù bạn đang xử lý hóa đơn, báo cáo hay bất kỳ tài liệu có cấu trúc nào, việc trích xuất văn bản chính xác từ PDF có thể là một công việc khó khăn. Đây là nơi Aspose.PDF cho .NET bước vào để đơn giản hóa quy trình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách trích xuất các cột văn bản từ tệp PDF một cách dễ dàng. 

## Điều kiện tiên quyết

Trước khi tìm hiểu về mã, chúng ta hãy cùng tìm hiểu những điều cần thiết mà bạn sẽ cần:

-  Aspose.PDF cho .NET: Đảm bảo bạn đã cài đặt phiên bản mới nhất của Aspose.PDF cho .NET. Nếu không, bạn có thể[tải xuống ở đây](https://releases.aspose.com/pdf/net/).
- Môi trường phát triển: Bạn sẽ cần Visual Studio hoặc môi trường phát triển .NET khác để làm việc với mã.
- Tài liệu PDF: Chuẩn bị sẵn một tài liệu PDF mẫu, tốt nhất là tài liệu có nhiều cột văn bản vì chúng ta sẽ trích xuất văn bản từ đó.

 Nếu bạn chưa cài đặt Aspose.PDF cho .NET, bạn có thể tải xuống[dùng thử miễn phí](https://releases.aspose.com/) hoặc[mua giấy phép](https://purchase.aspose.com/buy) để có đầy đủ tính năng. Bạn cũng có thể đăng ký[giấy phép tạm thời](https://purchase.aspose.com/temporary-license) nếu cần.

## Nhập không gian tên

Để sử dụng Aspose.PDF cho .NET trong dự án của bạn, bạn sẽ cần nhập các không gian tên sau:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Hướng dẫn từng bước: Trích xuất các cột văn bản từ PDF

Bây giờ, chúng ta hãy phân tích từng phần của mã để hiểu rõ hơn cách thức hoạt động của nó. Hãy theo dõi khi chúng tôi thực hiện từng bước, giải thích từng phân đoạn của quy trình.

## Bước 1: Tải Tài liệu PDF

 Điều đầu tiên bạn cần làm là tải tệp PDF của bạn vào`Document`đối tượng. Đây là cách Aspose.PDF tương tác với tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 Trong bước này, chúng tôi chỉ đơn giản xác định thư mục nơi lưu trữ tài liệu PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến tệp PDF cục bộ của bạn.`Document` đối tượng tải PDF vào bộ nhớ, giúp có thể truy cập để xử lý thêm.

## Bước 2: Thiết lập Trình hấp thụ đoạn văn bản

 Tiếp theo, chúng ta sẽ sử dụng một`TextFragmentAbsorber` để hấp thụ hoặc thu thập toàn bộ văn bản từ tệp PDF. Lớp hấp thụ này được thiết kế để trích xuất các đoạn văn bản từ các khu vực cụ thể trong tệp PDF của bạn, giúp trích xuất các cột văn bản trở nên lý tưởng.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Ở đây, chúng ta tạo một thể hiện của`TextFragmentAbsorber` và áp dụng nó cho tất cả các trang của PDF bằng cách sử dụng`Accept()` . Các`TextFragmentCollection` lưu trữ văn bản đã trích xuất và từ bộ sưu tập này, chúng ta có thể thao tác hoặc trích xuất văn bản khi cần.

## Bước 3: Điều chỉnh kích thước phông chữ của văn bản đã trích xuất

Sau khi bạn đã chụp các đoạn văn bản, bạn có thể muốn giảm kích thước phông chữ của chúng, đặc biệt là khi văn bản gốc quá lớn. Trong ví dụ này, chúng tôi đang giảm kích thước phông chữ xuống 70%.

```csharp
foreach (TextFragment tf in tfc)
{
    // Giảm kích thước phông chữ xuống 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Mã này lặp qua từng`TextFragment` trong bộ sưu tập và giảm kích thước phông chữ của nó đi 70%. Điều chỉnh kích thước phông chữ có thể giúp quản lý văn bản được trích xuất dễ dàng hơn, đặc biệt nếu bạn định dạng nó cho các mục đích khác nhau.

## Bước 4: Lưu tài liệu vào luồng bộ nhớ

 Sau khi sửa đổi văn bản, chúng tôi lưu PDF vào một`MemoryStream`. Điều này cho phép chúng ta lưu giữ tài liệu trong bộ nhớ để xử lý thêm mà không cần phải ghi lại vào đĩa.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Ở đây, chúng tôi lưu PDF vào luồng bộ nhớ và sau đó tải lại tài liệu. Phương pháp này hữu ích khi bạn làm việc với các tệp lớn và muốn tránh các thao tác đĩa không cần thiết.

## Bước 5: Trích xuất toàn bộ văn bản bằng Text Absorber

 Bây giờ chúng ta đã chuẩn bị xong PDF, đã đến lúc trích xuất văn bản. Chúng ta sẽ sử dụng`TextAbsorber` để lấy toàn bộ văn bản trong tài liệu.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 Trong bước này,`TextAbsorber` hấp thụ tất cả các văn bản từ PDF và văn bản được trích xuất được lưu trữ trong`extractedText` chuỗi. Đây chính là nơi phép thuật xảy ra—các cột văn bản của bạn giờ đây ở định dạng văn bản thuần túy!

## Bước 6: Lưu văn bản đã trích xuất vào một tệp

 Cuối cùng, chúng tôi lưu văn bản đã trích xuất vào một`.txt` tập tin để dễ dàng truy cập và sử dụng sau này.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Mã này ghi văn bản đã trích xuất vào một văn bản mới`.txt` và lưu nó vào thư mục bạn chỉ định. Một thông báo sẽ hiển thị trong bảng điều khiển để xác nhận rằng quá trình đã thành công.

## Phần kết luận

Bạn đã có nó rồi! Trích xuất các cột văn bản từ tệp PDF bằng Aspose.PDF cho .NET dễ hơn bạn nghĩ. Chỉ với một vài dòng mã, bạn có thể tải tệp PDF, trích xuất văn bản cụ thể, điều chỉnh định dạng và lưu kết quả vào tệp văn bản.

Kỹ thuật này cực kỳ hữu ích để xử lý các tài liệu có cấu trúc như bảng, báo cáo hoặc bất kỳ nội dung nào được sắp xếp theo cột. Cho dù bạn cần tự động trích xuất dữ liệu hay xử lý các tài liệu hàng loạt, Aspose.PDF đều cung cấp các công cụ để thực hiện hiệu quả.

## Câu hỏi thường gặp

### Tôi có thể trích xuất văn bản từ các trang cụ thể của tệp PDF không?  
 Vâng! Bạn có thể sửa đổi`TextFragmentAbsorber` để nhắm mục tiêu các trang cụ thể bằng cách sử dụng`pdfDocument.Pages[pageIndex].Accept(tfa);` phương pháp.

### Có thể trích xuất văn bản chỉ từ một cột trong tệp PDF có nhiều cột không?  
 Có, nhưng bạn sẽ cần phải làm việc với tọa độ của các đoạn văn bản bằng cách sử dụng`TextFragment.Rectangle` để nhắm mục tiêu vào các khu vực cụ thể của tài liệu.

### Làm thế nào để cải thiện độ chính xác của việc trích xuất văn bản?  
 Để có độ chính xác cao hơn, hãy đảm bảo cấu trúc của PDF được xác định rõ ràng và tránh các tài liệu có bố cục phức tạp. Bạn cũng có thể tinh chỉnh`TextFragmentAbsorber` để trích xuất văn bản dựa trên kiểu phông chữ, kích thước hoặc vùng.

### Aspose.PDF có hỗ trợ trích xuất văn bản từ tài liệu được quét không?  
Có, nhưng bạn sẽ cần sử dụng công nghệ OCR (Nhận dạng ký tự quang học). Aspose cũng cung cấp các công cụ cho mục đích này.

### Làm thế nào để xử lý các tập tin PDF lớn có hàng nghìn trang?  
Đối với các tệp PDF lớn, hãy xử lý tài liệu thành từng phần bằng cách trích xuất văn bản từ một vài trang cùng một lúc để tránh sử dụng nhiều bộ nhớ.