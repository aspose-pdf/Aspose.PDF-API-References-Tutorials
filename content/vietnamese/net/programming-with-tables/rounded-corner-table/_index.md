---
title: Bảng góc bo tròn trong tài liệu PDF
linktitle: Bảng góc bo tròn trong tài liệu PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Tìm hiểu cách tạo bảng có góc bo tròn trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 190
url: /vi/net/programming-with-tables/rounded-corner-table/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để tạo bảng góc bo tròn trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai.

## Bước 1: Tạo bảng
Đầu tiên, chúng ta sẽ tạo bảng bằng đoạn mã sau:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Bước 2: Thiết lập kiểu góc bo tròn
Tiếp theo, chúng ta sẽ cấu hình kiểu góc bo tròn cho bảng:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Bước 3: Thiết lập đường viền bảng
Để tạo đường viền góc bo tròn cho bảng, chúng ta cần tạo đối tượng BorderInfo và cấu hình nó với các tham số thích hợp:

```csharp
// Tạo một đối tượng GraphInfo để thiết lập màu đường viền
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Tạo một đối tượng BorderInfo trống
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Đặt bán kính của đường viền tròn là 15
bInfo.RoundedBorderRadius = 15;

// Áp dụng thông tin đường viền vào bảng
tab1.Border = bInfo;
```

### Mã nguồn ví dụ cho Bảng góc tròn sử dụng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Tạo một đối tượng BorderInfo trống
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Đặt đường viền tròn hơn với bán kính tròn là 15
bInfo.RoundedBorderRadius = 15;
// Đặt kiểu góc của bảng là Tròn.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Thiết lập thông tin đường viền bảng
tab1.Border = bInfo;
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học được cách tạo bảng góc bo tròn trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách thiết lập kiểu góc bo tròn và đường viền bảng. Bây giờ bạn có thể áp dụng kiến thức này vào các dự án của riêng mình.

### Câu hỏi thường gặp về bảng góc bo tròn trong tài liệu PDF

#### H: Tôi có thể tùy chỉnh bán kính của các góc bo tròn cho bảng không?

A: Có, bạn có thể tùy chỉnh bán kính của các góc bo tròn cho bảng bằng cách sửa đổi giá trị của`bInfo.RoundedBorderRadius` thuộc tính trong mã nguồn C# được cung cấp. Chỉ cần đặt giá trị bán kính mong muốn (tính bằng điểm) để đạt được góc bo tròn mong muốn.

#### H: Tôi có thể áp dụng góc bo tròn cho từng ô trong bảng không?

A: Không, kiểu góc bo tròn được áp dụng cho toàn bộ bảng. Aspose.PDF cho .NET hiện không cung cấp hỗ trợ tích hợp để áp dụng góc bo tròn cho từng ô trong bảng.

#### H: Tôi có thể thay đổi màu của đường viền góc bo tròn không?

 A: Có, bạn có thể thay đổi màu của đường viền góc bo tròn bằng cách sửa đổi giá trị của`graph.Color` thuộc tính trong mã nguồn C#. Chỉ cần cung cấp màu mong muốn, chẳng hạn như`Aspose.Pdf.Color.Red` hoặc bất kỳ biểu diễn màu hợp lệ nào khác.

#### H: Có thể áp dụng các kiểu góc khác nhau (ví dụ: vuông và bo tròn) cho các bảng khác nhau trong cùng một tài liệu PDF không?

A: Có, bạn có thể áp dụng nhiều kiểu góc khác nhau cho nhiều bảng khác nhau trong cùng một tài liệu PDF. Bạn có thể tạo nhiều bảng và cấu hình kiểu góc riêng lẻ theo yêu cầu của mình.

#### H: Tôi có thể điều chỉnh độ dày của đường viền góc bo tròn không?

 A: Có, bạn có thể điều chỉnh độ dày của đường viền góc bo tròn bằng cách sửa đổi`BorderInfo` thuộc tính của đối tượng trong mã nguồn C#. Ví dụ, bạn có thể thiết lập`bInfo.Width` Thuộc tính để điều chỉnh độ dày của đường viền.