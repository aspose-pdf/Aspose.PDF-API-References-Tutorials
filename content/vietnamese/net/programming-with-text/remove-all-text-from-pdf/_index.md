---
title: Xóa tất cả văn bản khỏi PDF
linktitle: Xóa tất cả văn bản khỏi PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách xóa toàn bộ văn bản khỏi tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 290
url: /vi/net/programming-with-text/remove-all-text-from-pdf/
---
 Trong hướng dẫn này, chúng tôi sẽ giải thích cách xóa toàn bộ văn bản khỏi tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Chúng tôi sẽ hướng dẫn từng bước để mở tệp PDF bằng cách sử dụng`TextFragmentAbsorber` để xóa toàn bộ văn bản và lưu tệp PDF đã sửa đổi bằng mã nguồn C# được cung cấp.

## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt thư viện Aspose.PDF cho .NET.
- Hiểu biết cơ bản về lập trình C#.

## Bước 1: Thiết lập thư mục tài liệu

 Đầu tiên, bạn cần thiết lập đường dẫn đến thư mục chứa các tệp PDF của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến tệp PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở Tài liệu PDF

 Tiếp theo, chúng ta mở tài liệu PDF bằng cách sử dụng`Document` lớp từ thư viện Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Bước 3: Xóa toàn bộ văn bản

 Chúng tôi khởi tạo một`TextFragmentAbsorber`đối tượng và sử dụng nó để xóa toàn bộ văn bản đã hấp thụ khỏi tài liệu PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Bước 4: Lưu PDF đã sửa đổi

Cuối cùng, chúng ta lưu tài liệu PDF đã chỉnh sửa vào tệp đầu ra đã chỉ định.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Mã nguồn mẫu để Xóa tất cả văn bản khỏi PDF bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Khởi tạo TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Xóa tất cả văn bản đã hấp thụ
absorber.RemoveAllText(pdfDocument);
// Lưu tài liệu
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Phần kết luận

 Trong hướng dẫn này, bạn đã học cách xóa toàn bộ văn bản khỏi tài liệu PDF bằng thư viện Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và thực thi mã C# được cung cấp, bạn có thể mở tệp PDF, xóa toàn bộ văn bản bằng`TextFragmentAbsorber`và lưu tệp PDF đã sửa đổi.

### Câu hỏi thường gặp

#### H: Mục đích của hướng dẫn "Xóa toàn bộ văn bản khỏi PDF" là gì?

 A: Hướng dẫn "Xóa tất cả văn bản khỏi PDF" cung cấp hướng dẫn về cách sử dụng thư viện Aspose.PDF cho .NET để xóa tất cả văn bản khỏi tài liệu PDF. Hướng dẫn hướng dẫn bạn quy trình mở PDF, sử dụng`TextFragmentAbsorber` để xóa toàn bộ văn bản và lưu tệp PDF đã sửa đổi.

#### H: Tại sao tôi muốn xóa toàn bộ văn bản khỏi tài liệu PDF?

A: Việc xóa toàn bộ văn bản khỏi tài liệu PDF có thể hữu ích trong các trường hợp bạn cần tạo phiên bản tài liệu không có bất kỳ nội dung văn bản nào. Điều này có thể hữu ích vì lý do riêng tư hoặc để tạo biểu diễn trực quan về bố cục của tài liệu mà không hiển thị thông tin văn bản.

#### H: Tôi phải thiết lập thư mục tài liệu như thế nào?

A: Để thiết lập thư mục tài liệu:

1.  Thay thế`"YOUR DOCUMENT DIRECTORY"` trong`dataDir` biến có đường dẫn đến thư mục chứa các tệp PDF của bạn.

#### H: Làm thế nào để xóa toàn bộ văn bản khỏi tài liệu PDF bằng thư viện Aspose.PDF?

A: Hướng dẫn sẽ hướng dẫn bạn từng bước trong quy trình này:

1.  Mở tài liệu PDF bằng cách sử dụng`Document` lớp học.
2.  Khởi tạo một`TextFragmentAbsorber` sự vật.
3. Sử dụng công cụ hấp thụ để xóa toàn bộ văn bản đã hấp thụ khỏi tài liệu PDF.
4. Lưu tài liệu PDF đã chỉnh sửa.

#### H: Tôi có thể xóa văn bản có chọn lọc khỏi các vùng cụ thể của tài liệu không?

A: Hướng dẫn tập trung vào việc xóa toàn bộ văn bản khỏi toàn bộ tài liệu PDF. Nếu bạn muốn xóa có chọn lọc văn bản khỏi các khu vực cụ thể, bạn sẽ cần phải sửa đổi cách tiếp cận và sử dụng logic phức tạp hơn để xác định và xóa các đoạn văn bản cụ thể.

#### Q: Làm thế nào để`TextFragmentAbsorber` work to remove text?

 A: Cái`TextFragmentAbsorber`là một lớp được cung cấp bởi thư viện Aspose.PDF có thể hấp thụ các đoạn văn bản từ một tài liệu PDF. Bằng cách sử dụng`RemoveAllText` phương pháp của`TextFragmentAbsorber` lớp, bạn có thể xóa tất cả các đoạn văn bản đã hấp thụ khỏi tài liệu.

#### H: Kết quả mong đợi khi thực thi mã được cung cấp là gì?

A: Bằng cách làm theo hướng dẫn và chạy mã C# được cung cấp, bạn sẽ xóa toàn bộ văn bản khỏi tài liệu PDF đầu vào và lưu phiên bản đã sửa đổi dưới dạng tệp PDF đầu ra.

#### H: Tôi có thể sửa đổi mã để chỉ xóa văn bản khỏi các trang hoặc khu vực cụ thể không?

A: Có, bạn có thể sửa đổi mã để đạt được điều đó. Để xóa văn bản có chọn lọc, bạn cần điều chỉnh mã để nhắm mục tiêu vào các trang hoặc vùng cụ thể trong tài liệu PDF.

#### H: Có cần Giấy phép Aspose hợp lệ cho hướng dẫn này không?

A: Có, cần phải có Giấy phép Aspose hợp lệ để thực thi mã thành công trong hướng dẫn này. Bạn có thể lấy giấy phép đầy đủ hoặc giấy phép tạm thời 30 ngày từ trang web Aspose.