---
title: Đặt phông chữ mặc định trong tệp PDF
linktitle: Đặt phông chữ mặc định trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt phông chữ mặc định trong tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 280
url: /vi/net/programming-with-document/setdefaultfont/
---
Nếu bạn đang làm việc với tài liệu PDF ở định dạng .NET, bạn có thể gặp phải sự cố trong đó phông chữ được sử dụng trong tệp PDF không có sẵn trên hệ thống nơi nó đang được xem hoặc in. Điều này có thể dẫn đến văn bản xuất hiện không chính xác hoặc không hiển thị gì cả. Aspose.PDF for .NET cung cấp giải pháp cho vấn đề này bằng cách cho phép bạn đặt phông chữ mặc định cho tài liệu. Trong ví dụ này, cách đặt phông chữ mặc định bằng Aspose.PDF cho .NET.

## Bước 1: Đặt đường dẫn đến thư mục tài liệu

chúng ta cần đặt đường dẫn đến thư mục chứa tài liệu PDF của chúng ta. Chúng tôi sẽ lưu trữ đường dẫn này trong một biến có tên là "dataDir".

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu PDF

 Chúng ta sẽ bắt đầu bằng cách tải một tài liệu PDF hiện có bị thiếu phông chữ. Trong ví dụ này, chúng tôi giả định rằng tài liệu PDF nằm trong thư mục được chỉ định bởi`dataDir` Biến đổi.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // mã ở đây
}
```

## Bước 3: Đặt phông chữ mặc định

 Tiếp theo, chúng tôi sẽ đặt phông chữ mặc định cho tài liệu PDF bằng cách sử dụng`PdfSaveOptions` lớp học. Trong ví dụ này, chúng tôi sẽ đặt phông chữ mặc định thành "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Bước 4: Lưu tài liệu đã cập nhật

Cuối cùng, chúng tôi sẽ lưu tài liệu đã cập nhật vào một tệp mới. Trong ví dụ này, chúng tôi sẽ lưu tài liệu đã cập nhật vào một tệp có tên "output_out.pdf" trong cùng thư mục với tệp đầu vào.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Mã nguồn ví dụ để đặt phông chữ mặc định bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải tài liệu PDF hiện có bị thiếu phông chữ
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

Đặt phông chữ mặc định trong tài liệu PDF bằng Aspose.PDF cho .NET là cách đơn giản và hiệu quả để đảm bảo văn bản được hiển thị chính xác, ngay cả khi không có phông chữ gốc. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng đặt phông chữ mặc định và tạo tệp PDF mang lại trải nghiệm xem nhất quán và đáng tin cậy trên các môi trường khác nhau. Tính năng này đặc biệt hữu ích trong các trường hợp mà tệp PDF sẽ được xem hoặc in trên nhiều hệ thống khác nhau có thể cài đặt các bộ phông chữ khác nhau.

### Câu hỏi thường gặp về đặt phông chữ mặc định trong tệp PDF

#### Hỏi: Tại sao việc đặt phông chữ mặc định lại quan trọng trong tài liệu PDF?

Đáp: Việc đặt phông chữ mặc định trong tài liệu PDF rất quan trọng vì nó đảm bảo rằng văn bản sẽ được hiển thị chính xác ngay cả khi phông chữ gốc không có sẵn trên hệ thống nơi tệp PDF đang được xem hoặc in. Nó giúp ngăn ngừa các vấn đề như văn bản bị thiếu hoặc bị cắt xén, đảm bảo trải nghiệm xem nhất quán và đáng tin cậy.

#### Câu hỏi: Tôi có thể chọn bất kỳ phông chữ nào làm phông chữ mặc định bằng Aspose.PDF cho .NET không?

 Trả lời: Có, bạn có thể chọn bất kỳ phông chữ nào có sẵn trên hệ thống làm phông chữ mặc định bằng Aspose.PDF cho .NET. Chỉ cần chỉ định tên của phông chữ trong`DefaultFontName` tài sản của`PdfSaveOptions` lớp học.

#### Hỏi: Điều gì xảy ra nếu phông chữ mặc định được chỉ định không có sẵn trên hệ thống?

Trả lời: Nếu phông chữ mặc định được chỉ định không có sẵn trên hệ thống, trình xem PDF sẽ sử dụng phông chữ dự phòng để hiển thị văn bản. Nên chọn font chữ thông dụng như Arial hay Times New Roman để đảm bảo khả năng tương thích trên các hệ thống khác nhau.