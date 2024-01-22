---
title: Thêm hình ảnh vào tệp PDF
linktitle: Thêm hình ảnh vào tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Dễ dàng thêm hình ảnh vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-images/add-image/
---
Hướng dẫn này sẽ hướng dẫn bạn từng bước cách thêm hình ảnh vào tệp PDF bằng Aspose.PDF cho .NET. Đảm bảo bạn đã thiết lập môi trường của mình và làm theo các bước bên dưới:

## Bước 1: Xác định thư mục tài liệu

 Trước khi bắt đầu, hãy đảm bảo bạn đặt đúng thư mục cho tài liệu. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã có đường dẫn đến thư mục chứa tài liệu PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở tài liệu

Trong bước này, chúng tôi sẽ mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF. Sử dụng`Document` constructor và chuyển đường dẫn đến tài liệu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Bước 3: Đặt tọa độ hình ảnh

 Đặt tọa độ của hình ảnh bạn muốn thêm. Các biến`lowerLeftX`, `lowerLeftY`, `upperRightX` Và`upperRightY` lần lượt biểu thị tọa độ của góc dưới bên trái và góc trên bên phải của hình ảnh.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Bước 4: Nhận trang nơi hình ảnh sẽ được thêm vào

Để thêm hình ảnh vào một trang cụ thể của tài liệu PDF, trước tiên chúng ta cần truy xuất trang đó. Trong ví dụ này, chúng tôi thêm hình ảnh vào trang thứ hai (chỉ mục 1) của tài liệu.

```csharp
Page page = pdfDocument.Pages[1];
```

## Bước 5: Tải hình ảnh từ luồng

 Bây giờ chúng tôi sẽ tải hình ảnh mà chúng tôi muốn thêm vào tài liệu PDF. Ví dụ này giả sử bạn có một tệp hình ảnh có tên`aspose-logo.jpg` trong cùng thư mục với tài liệu của bạn. Thay thế tên tập tin nếu cần thiết.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Bước 6: Thêm hình ảnh vào nội dung trang

Để sử dụng hình ảnh trong tài liệu PDF, chúng ta cần thêm hình ảnh đó vào bộ sưu tập hình ảnh tài nguyên của trang.

```csharp
page.Resources.Images.Add(imageStream);
```

## Bước 7: Lưu trạng thái đồ họa hiện tại

 Trước khi vẽ hình, chúng ta cần lưu lại trạng thái đồ họa hiện tại bằng cách sử dụng`GSave` nhà điều hành. Điều này đảm bảo rằng những thay đổi về trạng thái đồ họa có thể được khôi phục sau đó.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Bước 8: Tạo đối tượng Hình chữ nhật và Ma trận

 Bây giờ chúng ta sẽ tạo một`Rectangle` đối tượng và một`Matrix`sự vật. Hình chữ nhật biểu thị vị trí và kích thước của hình ảnh, trong khi ma trận xác định cách đặt hình ảnh.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Bước 9: Ghép ma trận để sắp xếp hình ảnh

 Để chỉ định cách đặt hình ảnh trong hình chữ nhật, chúng ta sử dụng`ConcatenateMatrix` nhà điều hành. Toán tử này xác định ma trận biến đổi ánh xạ không gian tọa độ của hình ảnh sang không gian tọa độ của trang.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Bước 10: Vẽ hình ảnh

 Trong bước này chúng ta sẽ vẽ hình ảnh trên trang bằng cách sử dụng`Do` nhà điều hành. Các`Do` toán tử lấy tên hình ảnh từ các tài nguyên và vẽ nó lên trang.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Bước 11: Khôi phục trạng thái đồ họa

 Sau khi vẽ hình, chúng ta cần khôi phục lại trạng thái đồ họa trước đó bằng cách sử dụng`GRestore` nhà điều hành.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Bước 12: Lưu tài liệu đã cập nhật

 Cuối cùng, chúng tôi sẽ lưu tài liệu đã cập nhật vào một tệp mới. Cập nhật`dataDir` biến có thư mục đầu ra và tên tệp mong muốn.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu để Thêm hình ảnh bằng Aspose.PDF cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Đặt tọa độ
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//Lấy trang cần thêm hình ảnh
Page page = pdfDocument.Pages[1];
// Tải hình ảnh vào luồng
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Thêm hình ảnh vào bộ sưu tập Hình ảnh của Tài nguyên Trang
page.Resources.Images.Add(imageStream);
// Sử dụng toán tử GSave: toán tử này lưu trạng thái đồ họa hiện tại
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Tạo các đối tượng Hình chữ nhật và Ma trận
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Sử dụng toán tử ConcatenateMatrix (ma trận nối): xác định cách đặt hình ảnh
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Sử dụng toán tử Do: toán tử này vẽ hình ảnh
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Sử dụng toán tử GRestore: toán tử này khôi phục trạng thái đồ họa
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Lưu tài liệu đã cập nhật
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách thêm hình ảnh vào tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi đã trình bày chi tiết từng bước, từ mở tài liệu đến lưu phiên bản cập nhật. Bằng cách làm theo hướng dẫn này, giờ đây bạn có thể nhúng hình ảnh vào tệp PDF của mình theo chương trình bằng C# và Aspose.PDF.

### Câu hỏi thường gặp về thêm hình ảnh vào tệp PDF

#### Hỏi: Tại sao tôi muốn thêm hình ảnh vào tài liệu PDF?

Đáp: Việc thêm hình ảnh vào tài liệu PDF có thể nâng cao nội dung trực quan, cung cấp ngữ cảnh bổ sung hoặc đưa biểu trưng và đồ họa vào tệp PDF của bạn.

#### Hỏi: Tôi có thể thêm hình ảnh vào các trang cụ thể trong tài liệu PDF không?

Đáp: Có, bạn có thể chỉ định trang mà bạn muốn thêm hình ảnh. Trong mã được cung cấp, hình ảnh sẽ được thêm vào trang thứ hai của tài liệu PDF.

#### Hỏi: Làm cách nào để điều chỉnh vị trí và kích thước của hình ảnh được thêm vào?

 Đáp: Bạn có thể sửa đổi`lowerLeftX`, `lowerLeftY`, `upperRightX` , Và`upperRightY` các biến trong mã để đặt tọa độ của hình ảnh và kiểm soát kích thước cũng như vị trí của nó trên trang.

#### Câu hỏi: Tôi có thể thêm loại định dạng hình ảnh nào bằng phương pháp này?

Đáp: Ví dụ về mã được cung cấp giả sử bạn đang tải một hình ảnh JPG (`aspose-logo.jpg`). Aspose.PDF for .NET hỗ trợ nhiều định dạng hình ảnh khác nhau, bao gồm PNG, BMP, GIF, v.v.

#### Hỏi: Làm cách nào để đảm bảo rằng hình ảnh được thêm vào vừa với tọa độ đã chỉ định?

 Đáp: Đảm bảo điều chỉnh tọa độ và kích thước của`Rectangle` sự vật (`rectangle`để phù hợp với kích thước của hình ảnh và vị trí mong muốn của nó trên trang.

#### Hỏi: Tôi có thể thêm nhiều hình ảnh vào một trang PDF không?

Đáp: Có, bạn có thể thêm nhiều hình ảnh vào một trang PDF bằng cách lặp lại quy trình cho từng hình ảnh và điều chỉnh tọa độ cũng như các thông số khác cho phù hợp.

####  Hỏi: Làm thế nào`GSave` and `GRestore` operator work in the code?

 Đáp: Cái`GSave` toán tử lưu trạng thái đồ họa hiện tại, cho phép bạn thực hiện các thay đổi mà không ảnh hưởng đến bối cảnh đồ họa tổng thể. Các`GRestore` toán tử khôi phục trạng thái đồ họa trước đó sau khi thực hiện thay đổi.

#### Hỏi: Điều gì xảy ra nếu không tìm thấy tệp hình ảnh ở đường dẫn đã chỉ định?

Trả lời: Nếu không tìm thấy tệp hình ảnh tại đường dẫn đã chỉ định, mã sẽ đưa ra một ngoại lệ khi cố tải luồng hình ảnh. Hãy chắc chắn rằng tập tin hình ảnh nằm trong thư mục chính xác.

#### Hỏi: Tôi có thể tùy chỉnh thêm vị trí và hình thức của hình ảnh không?

 Trả lời: Có, bạn có thể tùy chỉnh hình thức của hình ảnh bằng cách sửa đổi`Matrix`đối tượng và điều chỉnh các toán tử khác trong mã. Tham khảo tài liệu Aspose.PDF để biết tùy chỉnh nâng cao.

#### Hỏi: Làm cách nào để kiểm tra xem hình ảnh đã được thêm thành công vào tệp PDF hay chưa?

Đáp: Sau khi áp dụng mã được cung cấp để thêm hình ảnh, hãy mở tệp PDF đã sửa đổi và xác minh rằng hình ảnh được hiển thị trên trang được chỉ định với vị trí chính xác.

#### Hỏi: Việc thêm hình ảnh có ảnh hưởng đến nội dung gốc của tài liệu PDF không?

Đáp: Việc thêm hình ảnh không ảnh hưởng đến nội dung gốc của tài liệu PDF. Nó nâng cao tài liệu bằng cách bao gồm các yếu tố trực quan.