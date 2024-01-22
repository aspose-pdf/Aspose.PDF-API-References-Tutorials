---
title: Đặt ngày hết hạn trong tệp PDF
linktitle: Đặt ngày hết hạn trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách đặt ngày hết hạn trong tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 300
url: /vi/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET là một thư viện mạnh mẽ cung cấp nhiều tính năng khác nhau để làm việc với các tệp PDF. Một tính năng như vậy là khả năng đặt ngày hết hạn cho tài liệu PDF. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình đặt ngày hết hạn cho tài liệu PDF bằng Aspose.PDF cho .NET. 

## Bước 1: Đặt đường dẫn đến thư mục tài liệu

Trước khi bắt đầu, chúng ta cần đặt đường dẫn đến thư mục chứa tài liệu PDF của chúng ta. Chúng tôi sẽ lưu trữ đường dẫn này trong một biến có tên là "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu PDF mới

 Để tạo một tài liệu PDF mới, chúng ta cần khởi tạo một tài liệu PDF mới`Aspose.Pdf.Document` sự vật. Chúng ta có thể làm điều này bằng cách sử dụng đoạn mã sau:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Bước 3: Thêm trang mới vào tài liệu PDF

Khi chúng tôi đã tạo tài liệu PDF, chúng tôi có thể thêm một trang mới vào đó. Chúng ta có thể làm điều này bằng cách sử dụng đoạn mã sau:

```csharp
doc.Pages.Add();
```

## Bước 4: Thêm văn bản vào tài liệu PDF

Sau khi thêm một trang vào tài liệu PDF, chúng ta có thể thêm văn bản vào đó bằng cách sử dụng`Paragraphs` bộ sưu tập. Chúng ta có thể làm điều này bằng cách sử dụng đoạn mã sau:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Bước 5: Đặt ngày hết hạn của PDF bằng JavaScript

Để đặt ngày hết hạn của PDF, chúng ta cần tạo một đối tượng JavaScript. Chúng ta có thể làm điều này bằng cách sử dụng đoạn mã sau:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Đặt JavaScript làm hành động mở PDF
doc.OpenAction = javaScript;
```

Trong mã này, chúng tôi đang đặt ngày hết hạn là tháng 5 năm 2017.

## Bước 6: Lưu tệp PDF

 Sau khi đã đặt ngày hết hạn, bạn cần lưu file PDF. Để làm điều này, bạn có thể sử dụng`Save` phương pháp của`Document` object và chuyển vào đường dẫn đến nơi bạn muốn lưu tệp PDF đã cập nhật.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);
```

### Mã nguồn mẫu cho Đặt ngày hết hạn bằng Aspose.PDF cho .NET

Đây là mã nguồn ví dụ hoàn chỉnh để đặt ngày hết hạn bằng Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo đối tượng Tài liệu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Thêm trang vào bộ sưu tập trang của tệp PDF
doc.Pages.Add();
// Thêm đoạn văn bản vào bộ sưu tập đoạn văn của đối tượng trang
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Tạo đối tượng JavaScript để đặt ngày hết hạn của PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Đặt JavaScript làm hành động mở PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Lưu tài liệu PDF
doc.Save(dataDir);
```

## Phần kết luận

Đặt ngày hết hạn cho tài liệu PDF bằng Aspose.PDF for .NET là một tính năng hữu ích để đảm bảo rằng tài liệu chỉ có hiệu lực trong một khoảng thời gian nhất định. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng đặt ngày hết hạn và tạo các tệp PDF có hiệu lực trong thời gian giới hạn. Tính năng này có thể đặc biệt hữu ích đối với các tài liệu cần được truy cập hoặc phân phối trong một khoảng thời gian giới hạn.

### Câu hỏi thường gặp về đặt ngày hết hạn trong tệp PDF

#### Hỏi: Tôi có thể đặt ngày hết hạn khác cho tài liệu PDF không?

 Đáp: Có, bạn có thể đặt ngày hết hạn khác cho tài liệu PDF bằng cách sửa đổi mã JavaScript ở Bước 5. Trong ví dụ được cung cấp, ngày hết hạn được đặt thành tháng 5 năm 2017. Để đặt ngày hết hạn khác, bạn cần sửa đổi`year` Và`month` các biến trong mã JavaScript theo năm và tháng mong muốn.

#### Hỏi: Điều gì xảy ra khi tài liệu PDF hết hạn?

Trả lời: Khi tài liệu PDF hết hạn, như được chỉ định trong mã JavaScript, người xem sẽ hiển thị thông báo cảnh báo cho biết tệp đã hết hạn và người dùng cần một tệp mới. Thông báo cảnh báo này sẽ được hiển thị khi tệp PDF được mở.

#### Hỏi: Tôi có thể sử dụng thời gian cụ thể cho ngày hết hạn thay vì chỉ ngày không?

 Trả lời: Có, bạn có thể đặt thời gian cụ thể cho ngày hết hạn trong mã JavaScript. Bằng cách sửa đổi`expiry` trong mã JavaScript để bao gồm thời gian mong muốn, bạn có thể đặt thời gian cụ thể cho ngày hết hạn.