---
title: Đặt Phông chữ Mặc định Trong Tệp PDF
linktitle: Đặt Phông chữ Mặc định Trong Tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách đặt phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 280
url: /vi/net/programming-with-document/setdefaultfont/
---
Nếu bạn đang làm việc với các tài liệu PDF trong .NET, bạn có thể gặp phải sự cố khi phông chữ được sử dụng trong PDF không khả dụng trên hệ thống nơi nó đang được xem hoặc in. Điều này có thể khiến văn bản xuất hiện không chính xác hoặc không hiển thị. Aspose.PDF cho .NET cung cấp giải pháp cho sự cố này bằng cách cho phép bạn đặt phông chữ mặc định cho tài liệu. Trong ví dụ này, cách đặt phông chữ mặc định bằng Aspose.PDF cho .NET.

## Bước 1: Đặt đường dẫn đến thư mục tài liệu

chúng ta cần thiết lập đường dẫn đến thư mục nơi tài liệu PDF của chúng ta được lưu trữ. Chúng ta sẽ lưu trữ đường dẫn này trong một biến có tên là "dataDir".

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu PDF

 Chúng tôi sẽ bắt đầu bằng cách tải một tài liệu PDF hiện có bị thiếu phông chữ. Trong ví dụ này, chúng tôi sẽ giả sử rằng tài liệu PDF nằm trong thư mục được chỉ định bởi`dataDir` biến đổi.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // mã đi ở đây
}
```

## Bước 3: Đặt phông chữ mặc định

 Tiếp theo, chúng ta sẽ thiết lập phông chữ mặc định cho tài liệu PDF bằng cách sử dụng`PdfSaveOptions`lớp. Trong ví dụ này, chúng ta sẽ đặt phông chữ mặc định là "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Bước 4: Lưu tài liệu đã cập nhật

Cuối cùng, chúng ta sẽ lưu tài liệu đã cập nhật vào một tệp mới. Trong ví dụ này, chúng ta sẽ lưu tài liệu đã cập nhật vào một tệp có tên "output_out.pdf" trong cùng thư mục với tệp đầu vào.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Mã nguồn ví dụ để thiết lập phông chữ mặc định bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải một tài liệu PDF hiện có bị thiếu phông chữ
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Chỉ định tên phông chữ mặc định
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Phần kết luận

Thiết lập phông chữ mặc định trong tài liệu PDF bằng Aspose.PDF cho .NET là một cách đơn giản và hiệu quả để đảm bảo văn bản được hiển thị chính xác, ngay cả khi phông chữ gốc không khả dụng. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, các nhà phát triển có thể dễ dàng thiết lập phông chữ mặc định và tạo PDF cung cấp trải nghiệm xem nhất quán và đáng tin cậy trên nhiều môi trường khác nhau. Tính năng này đặc biệt hữu ích trong các tình huống mà PDF sẽ được xem hoặc in trên nhiều hệ thống có thể cài đặt các bộ phông chữ khác nhau.

### Câu hỏi thường gặp về việc thiết lập phông chữ mặc định trong tệp PDF

#### H: Tại sao việc thiết lập phông chữ mặc định lại quan trọng trong tài liệu PDF?

A: Việc thiết lập phông chữ mặc định trong tài liệu PDF rất quan trọng vì nó đảm bảo văn bản sẽ được hiển thị chính xác ngay cả khi phông chữ gốc không có sẵn trên hệ thống nơi PDF đang được xem hoặc in. Nó giúp ngăn ngừa các sự cố như văn bản bị thiếu hoặc bị bóp méo, đảm bảo trải nghiệm xem nhất quán và đáng tin cậy.

#### H: Tôi có thể chọn bất kỳ phông chữ nào làm phông chữ mặc định khi sử dụng Aspose.PDF cho .NET không?

 A: Có, bạn có thể chọn bất kỳ phông chữ nào có sẵn trên hệ thống làm phông chữ mặc định bằng cách sử dụng Aspose.PDF cho .NET. Chỉ cần chỉ định tên phông chữ trong`DefaultFontName` tài sản của`PdfSaveOptions` lớp học.

#### H: Điều gì xảy ra nếu phông chữ mặc định được chỉ định không có sẵn trên hệ thống?

A: Nếu phông chữ mặc định đã chỉ định không khả dụng trên hệ thống, trình xem PDF sẽ sử dụng phông chữ dự phòng để hiển thị văn bản. Nên chọn phông chữ phổ biến như Arial hoặc Times New Roman để đảm bảo khả năng tương thích trên các hệ thống khác nhau.