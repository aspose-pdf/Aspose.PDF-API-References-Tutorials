---
title: XPS sang PDF
linktitle: XPS sang PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước chuyển đổi tệp XPS sang PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 350
url: /vi/net/document-conversion/xps-to-pdf/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách chuyển đổi tệp XPS sang PDF bằng thư viện Aspose.PDF cho .NET từng bước. Chúng tôi sẽ trình bày chi tiết về mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ có thể dễ dàng chuyển đổi tệp XPS thành tài liệu PDF.

## Bước 1: Đặt thư mục tài liệu
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn nơi bạn đã lưu tệp của mình.

## Bước 2: Khởi tạo đối tượng LoadOptions bằng XPS Load Options
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Tạo một thể hiện của đối tượng LoadOptions bằng các tùy chọn tải XPS.

## Bước 3: Tạo đối tượng tài liệu
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Tạo một đối tượng Document chỉ định tệp XPS đầu vào và các tùy chọn tải.

## Bước 4: Lưu tài liệu PDF kết quả
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Lưu tài liệu PDF thu được vào thư mục được chỉ định.

### Mã nguồn ví dụ cho XPS sang PDF bằng Aspose.PDF for .NET

```csharp
try
{
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Khởi tạo đối tượng LoadOption bằng tùy chọn tải XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Tạo đối tượng tài liệu
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Lưu tài liệu PDF kết quả
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách chuyển đổi tệp XPS sang PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng thực hiện chuyển đổi này trong các ứng dụng của riêng mình. Nhận kết quả chính xác và chuyên nghiệp khi chuyển đổi tệp XPS sang PDF.

### Câu hỏi thường gặp

#### Hỏi: XPS là gì và tại sao tôi muốn chuyển đổi nó sang PDF?

Trả lời: XPS (Đặc tả giấy XML) là định dạng tài liệu có bố cục cố định được phát triển bởi Microsoft. Chuyển đổi XPS sang PDF cho phép bạn làm cho tài liệu dễ truy cập hơn và tương thích rộng rãi hơn vì PDF là định dạng được hỗ trợ phổ biến trên các nền tảng và thiết bị khác nhau.

#### Câu hỏi: Thư viện Aspose.PDF có hỗ trợ các định dạng tệp khác ngoài XPS không?

Trả lời: Có, Aspose.PDF for .NET hỗ trợ nhiều định dạng tệp khác để chuyển đổi, chẳng hạn như HTML, EPUB, SVG, XML, v.v. Nó cũng cho phép bạn tạo và thao tác các tài liệu PDF theo chương trình.

#### H: Tôi có thể tùy chỉnh quy trình chuyển đổi PDF, chẳng hạn như cài đặt kích thước trang, lề hoặc các tùy chọn khác không?

Trả lời: Có, bạn có thể tùy chỉnh quy trình chuyển đổi PDF bằng Aspose.PDF cho .NET. Thư viện cung cấp nhiều tùy chọn để kiểm soát kích thước trang, lề, nén hình ảnh, nhúng phông chữ và các cài đặt liên quan đến PDF khác để đáp ứng các yêu cầu cụ thể của bạn.

#### Câu hỏi: Có sẵn phiên bản dùng thử của Aspose.PDF cho .NET để thử nghiệm không?

Trả lời: Có, bạn có thể tải xuống và dùng thử phiên bản dùng thử của Aspose.PDF cho .NET từ trang web chính thức của Aspose. Phiên bản dùng thử cho phép bạn khám phá các tính năng của thư viện trước khi mua hàng.

#### Hỏi: Tôi có thể chuyển đổi nhiều tệp XPS sang PDF trong một quy trình hàng loạt không?

Đáp: Có, bạn có thể chuyển đổi nhiều tệp XPS sang PDF theo quy trình hàng loạt bằng cách triển khai vòng lặp hoặc duyệt qua danh sách tệp XPS và chuyển đổi từng tệp sang PDF bằng mã được cung cấp.