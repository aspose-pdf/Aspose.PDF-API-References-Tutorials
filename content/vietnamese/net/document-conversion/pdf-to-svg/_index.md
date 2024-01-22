---
title: PDF sang SVG
linktitle: PDF sang SVG
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để chuyển đổi PDF sang SVG bằng Aspose.PDF cho .NET.
type: docs
weight: 180
url: /vi/net/document-conversion/pdf-to-svg/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi định dạng PDF sang SVG bằng Aspose.PDF cho .NET. SVG (Đồ họa vectơ có thể mở rộng) là định dạng hình ảnh vector giúp duy trì chất lượng và tỷ lệ đồ họa. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể chuyển đổi tệp PDF sang định dạng SVG.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tải tài liệu PDF
Trong bước này, chúng tôi sẽ tải tệp PDF nguồn bằng Aspose.PDF cho .NET. Thực hiện theo mã dưới đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực tế nơi chứa tệp PDF của bạn.

## Bước 2: Khởi tạo các tùy chọn lưu SVG
Sau khi tải tệp PDF, chúng tôi sẽ khởi tạo các tùy chọn lưu SVG. Sử dụng mã sau đây:

```csharp
// Khởi tạo một đối tượng SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Không nén hình ảnh SVG trong kho lưu trữ Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Bước 3: Lưu tệp SVG kết quả
Bây giờ chúng ta sẽ lưu tệp PDF đã chuyển đổi ở định dạng SVG. Sử dụng mã sau đây:

```csharp
// Lưu đầu ra vào tệp SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Đoạn mã trên lưu định dạng PDF đã chuyển đổi sang SVG với tên tệp`"PDFToSVG_out.svg"`.

### Mã nguồn ví dụ cho PDF sang SVG bằng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tài liệu PDF
Document doc = new Document(dataDir + "input.pdf");
// Khởi tạo một đối tượng của SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Không nén ảnh SVG vào kho lưu trữ Zip
saveOptions.CompressOutputToZipArchive = false;
// Lưu đầu ra trong tệp SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước chuyển đổi tệp PDF sang định dạng SVG bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, giờ đây bạn có thể chuyển đổi tệp PDF sang định dạng SVG. Tính năng này hữu ích khi bạn muốn duy trì chất lượng đồ họa và tỷ lệ khi chuyển đổi sang hình ảnh vector.

### Câu hỏi thường gặp

#### Hỏi: Tôi có thể kiểm soát độ phân giải hoặc kích thước của tệp SVG thu được trong quá trình chuyển đổi PDF sang SVG không?

 Trả lời: Có, bạn có thể kiểm soát độ phân giải hoặc kích thước của tệp SVG thu được trong quá trình chuyển đổi PDF sang SVG bằng Aspose.PDF for .NET. Các`SvgSaveOptions` lớp cung cấp các thuộc tính như`PageSavingCallback` Và`SaveFormat` cho phép bạn đặt độ phân giải, kích thước trang hoặc các tham số khác liên quan đến đầu ra SVG. Bạn có thể tùy chỉnh các tùy chọn này theo yêu cầu của mình để kiểm soát chất lượng và kích thước của tệp SVG.

#### Câu hỏi: Aspose.PDF cho .NET có hỗ trợ chuyển đổi các tệp PDF được mã hóa hoặc bảo vệ bằng mật khẩu sang SVG không?

Trả lời: Có, Aspose.PDF for .NET hỗ trợ chuyển đổi các tệp PDF được mã hóa hoặc bảo vệ bằng mật khẩu sang định dạng SVG. Khi bạn tải một tệp PDF được bảo vệ bằng mật khẩu, bạn có thể cung cấp mật khẩu bằng cách sử dụng`Document` hàm tạo của lớp hoặc bằng cách thiết lập`Password` thuộc tính trước khi tải tệp PDF. Aspose.PDF for .NET sẽ xử lý việc giải mã trong quá trình chuyển đổi PDF sang SVG.

#### Hỏi: Tôi có thể chỉ chuyển đổi các trang cụ thể của PDF sang SVG thay vì toàn bộ tài liệu không?

Trả lời: Có, bạn chỉ có thể chuyển đổi các trang cụ thể của PDF sang SVG thay vì toàn bộ tài liệu bằng Aspose.PDF cho .NET. Trước khi lưu đầu ra dưới dạng tệp SVG, bạn có thể chọn các trang bạn muốn chuyển đổi bằng cách chỉ định số trang hoặc phạm vi trang của chúng. Bằng cách này, bạn chỉ có thể trích xuất và chuyển đổi các trang mong muốn từ định dạng PDF sang SVG.

#### Câu hỏi: Aspose.PDF for .NET có tương thích với tất cả các phiên bản SVG không?

Trả lời: Aspose.PDF cho .NET được thiết kế để tương thích với thông số kỹ thuật SVG 1.1 (Đồ họa vectơ có thể mở rộng). Nó hỗ trợ tạo tệp SVG theo tiêu chuẩn SVG 1.1. Tuy nhiên, xin lưu ý rằng SVG 2.0 đã được giới thiệu là phiên bản mới nhất của đặc tả SVG. Mặc dù Aspose.PDF cho .NET vẫn có thể hoạt động tốt với SVG 2.0 trong nhiều trường hợp, nhưng bạn nên kiểm tra tính tương thích và các hạn chế tiềm ẩn với các tính năng SVG cụ thể mà bạn định sử dụng.