---
title: Nhận kích thước SVG
linktitle: Nhận kích thước SVG
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để lấy kích thước SVG bằng Aspose.PDF cho .NET.
type: docs
weight: 40
url: /vi/net/document-conversion/get-svg-dimensions/
---
## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình lấy kích thước của tệp SVG bằng Aspose.PDF cho .NET. SVG (Đồ họa vectơ có thể mở rộng) là định dạng hình ảnh dựa trên XML được sử dụng để thể hiện đồ họa vector. Sử dụng các bước bên dưới, bạn sẽ có thể lấy kích thước của tệp SVG và lưu chúng dưới dạng PDF.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tải tệp SVG
Trong bước này, chúng tôi sẽ tải tệp SVG bằng Aspose.PDF cho .NET. Thực hiện theo mã dưới đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực nơi chứa tệp SVG của bạn.

## Bước 2: Điều chỉnh kích thước trang
Bây giờ chúng ta đã tải tệp SVG, chúng ta có thể điều chỉnh kích thước trang để phù hợp với nội dung SVG. Sử dụng mã sau đây:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Đoạn mã trên đặt lề trang về 0, cho phép kích thước trang điều chỉnh dựa trên nội dung SVG.

## Bước 3: Lưu tệp PDF kết quả
Sau khi điều chỉnh kích thước trang, bây giờ chúng ta có thể lưu tài liệu PDF thu được. Đây là bước cuối cùng:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục mong muốn nơi bạn muốn lưu tệp PDF đầu ra.
  
### Mã nguồn mẫu cho Nhận kích thước SVG bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước để lấy kích thước của tệp SVG bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, giờ đây bạn có thể lấy kích thước của tệp SVG và lưu chúng vào Định dạng PDF. Tính năng này có thể hữu ích khi bạn cần đo kích thước của đồ họa vector.

### Câu hỏi thường gặp

#### Hỏi: SVG là gì?

Trả lời: SVG (Đồ họa vectơ có thể mở rộng) là định dạng hình ảnh dựa trên XML được sử dụng để thể hiện đồ họa vector. Không giống như hình ảnh raster, tệp SVG không phụ thuộc vào độ phân giải và có thể thu nhỏ mà không làm giảm chất lượng. SVG được sử dụng rộng rãi để hiển thị đồ họa trên web và có thể được chỉnh sửa và thao tác dễ dàng.

#### Câu hỏi: Tại sao nên sử dụng Aspose.PDF for .NET để chuyển đổi SVG sang PDF?

Trả lời: Aspose.PDF for .NET cung cấp một cách đáng tin cậy và hiệu quả để xử lý các tệp SVG và chuyển đổi chúng sang định dạng PDF. Nó cung cấp nhiều tùy chọn và cài đặt khác nhau để tùy chỉnh quá trình chuyển đổi, chẳng hạn như điều chỉnh kích thước trang, lề và các thuộc tính khác để đảm bảo thể hiện chính xác trong PDF.

#### Hỏi: Tôi có thể chuyển đổi các tệp SVG có đồ họa và văn bản phức tạp không?

Trả lời: Có, Aspose.PDF cho .NET có thể xử lý các tệp SVG có các phần tử đồ họa, văn bản và vectơ phức tạp. Nó bảo toàn chính xác các chi tiết và chất lượng của nội dung SVG trong quá trình chuyển đổi, mang lại tài liệu PDF chất lượng cao.

#### Câu hỏi: Có thể trích xuất văn bản từ tệp SVG bằng Aspose.PDF cho .NET không?

Trả lời: Có, Aspose.PDF for .NET cho phép bạn trích xuất văn bản từ tệp SVG. Bạn có thể sử dụng các tính năng trích xuất văn bản của thư viện để trích xuất các thành phần văn bản từ SVG và lưu chúng riêng biệt để xử lý thêm.