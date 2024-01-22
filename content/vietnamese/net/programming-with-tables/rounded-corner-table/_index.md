---
title: Bàn góc tròn trong tài liệu PDF
linktitle: Bàn góc tròn trong tài liệu PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách tạo bảng góc tròn trong tài liệu PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 190
url: /vi/net/programming-with-tables/rounded-corner-table/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước tạo bảng góc tròn trong tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai mã đó.

## Bước 1: Tạo bảng
Đầu tiên, chúng ta sẽ tạo bảng bằng đoạn mã sau:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Bước 2: Thiết lập kiểu góc tròn
Tiếp theo, chúng ta sẽ định cấu hình kiểu góc bo tròn cho bảng:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Bước 3: Thiết lập viền bảng
Để tạo cho bảng một đường viền góc tròn, chúng ta cần tạo một đối tượng BorderInfo và cấu hình nó với các tham số phù hợp:

```csharp
// Tạo đối tượng GraphInfo để đặt màu đường viền
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Tạo một đối tượng BorderInfo trống
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Đặt bán kính của đường viền tròn thành 15
bInfo.RoundedBorderRadius = 15;

// Áp dụng thông tin đường viền cho bảng
tab1.Border = bInfo;
```

### Mã nguồn mẫu cho Bảng góc tròn sử dụng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Tạo một đối tượng BorderInfo trống
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Đặt đường viền thành đường viền tròn hơn trong đó bán kính hình tròn là 15
bInfo.RoundedBorderRadius = 15;
// Đặt kiểu Góc của bảng là Tròn.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Đặt thông tin viền bảng
tab1.Border = bInfo;
```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã học cách tạo bảng góc tròn trong tài liệu PDF bằng Aspose.PDF cho .NET. Hướng dẫn từng bước này chỉ cho bạn cách thiết lập kiểu góc tròn và đường viền bảng. Bây giờ bạn có thể áp dụng kiến thức này vào dự án của riêng mình.

### Câu hỏi thường gặp về bàn góc tròn trong tài liệu PDF

#### Hỏi: Tôi có thể tùy chỉnh bán kính các góc bo tròn cho bàn được không?

Đáp: Có, bạn có thể tùy chỉnh bán kính của các góc tròn cho bảng bằng cách sửa đổi giá trị của`bInfo.RoundedBorderRadius` thuộc tính trong mã nguồn C# được cung cấp. Chỉ cần đặt giá trị bán kính mong muốn (tính theo điểm) để đạt được hình dạng góc tròn mong muốn.

#### Câu hỏi: Tôi có thể áp dụng các góc tròn cho từng ô trong bảng không?

Đáp: Không, kiểu góc bo tròn được áp dụng cho toàn bộ bàn. Aspose.PDF cho .NET hiện không cung cấp hỗ trợ tích hợp để áp dụng các góc tròn cho từng ô trong bảng.

#### Hỏi: Tôi có thể thay đổi màu của đường viền góc bo tròn không?

 Trả lời: Có, bạn có thể thay đổi màu của đường viền góc tròn bằng cách sửa đổi giá trị của`graph.Color` thuộc tính trong mã nguồn C#. Đơn giản chỉ cần cung cấp màu sắc mong muốn, chẳng hạn như`Aspose.Pdf.Color.Red` hoặc bất kỳ đại diện màu hợp lệ nào khác.

#### Câu hỏi: Có thể áp dụng các kiểu góc khác nhau (ví dụ: hình vuông và hình tròn) cho các bảng khác nhau trong cùng một tài liệu PDF không?

Đáp: Có, có thể áp dụng các kiểu góc khác nhau cho các bảng khác nhau trong cùng một tài liệu PDF. Bạn có thể tạo nhiều bảng và định cấu hình các kiểu góc của chúng riêng lẻ dựa trên yêu cầu của bạn.

#### Hỏi: Tôi có thể điều chỉnh độ dày của đường viền góc bo tròn không?

 Đáp: Có, bạn có thể điều chỉnh độ dày của đường viền góc tròn bằng cách sửa đổi`BorderInfo` thuộc tính của đối tượng trong mã nguồn C#. Ví dụ: bạn có thể đặt`bInfo.Width` thuộc tính để điều chỉnh độ dày của đường viền.