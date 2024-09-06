---
title: Thêm hình ảnh vào tệp PDF
linktitle: Thêm hình ảnh vào tệp PDF
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Dễ dàng thêm hình ảnh vào tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-images/add-image/
---
Hướng dẫn này sẽ hướng dẫn bạn từng bước cách thêm hình ảnh vào tệp PDF bằng Aspose.PDF cho .NET. Đảm bảo bạn đã thiết lập môi trường của mình và làm theo các bước dưới đây:

## Bước 1: Xác định thư mục tài liệu

Trước khi bắt đầu, hãy đảm bảo bạn thiết lập đúng thư mục cho các tài liệu. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã có đường dẫn đến thư mục chứa tài liệu PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở tài liệu

 Trong bước này, chúng ta sẽ mở tài liệu PDF bằng cách sử dụng`Document` lớp Aspose.PDF. Sử dụng`Document` hàm tạo và truyền đường dẫn đến tài liệu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Bước 3: Thiết lập tọa độ hình ảnh

 Đặt tọa độ của hình ảnh bạn muốn thêm. Các biến`lowerLeftX`, `lowerLeftY`, `upperRightX` Và`upperRightY` thể hiện tọa độ của góc dưới bên trái và góc trên bên phải của hình ảnh tương ứng.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Bước 4: Lấy trang nơi hình ảnh cần được thêm vào

Để thêm hình ảnh vào một trang cụ thể của tài liệu PDF, trước tiên chúng ta cần lấy trang đó. Trong ví dụ này, chúng ta thêm hình ảnh vào trang thứ hai (chỉ mục 1) của tài liệu.

```csharp
Page page = pdfDocument.Pages[1];
```

## Bước 5: Tải hình ảnh từ luồng

 Bây giờ chúng ta sẽ tải hình ảnh mà chúng ta muốn thêm vào tài liệu PDF. Ví dụ này giả định bạn có một tệp hình ảnh có tên`aspose-logo.jpg` trong cùng thư mục với tài liệu của bạn. Thay thế tên tệp nếu cần thiết.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Bước 6: Thêm hình ảnh vào Tài sản trang

Để sử dụng hình ảnh trong tài liệu PDF, chúng ta cần thêm hình ảnh đó vào bộ sưu tập hình ảnh tài nguyên của trang.

```csharp
page.Resources.Images.Add(imageStream);
```

## Bước 7: Lưu trạng thái đồ họa hiện tại

 Trước khi vẽ hình ảnh, chúng ta cần lưu trạng thái đồ họa hiện tại bằng cách sử dụng`GSave` Người vận hành. Điều này đảm bảo rằng những thay đổi về trạng thái đồ họa có thể được khôi phục sau này.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Bước 8: Tạo các đối tượng Hình chữ nhật và Ma trận

 Bây giờ chúng ta sẽ tạo ra một`Rectangle` đối tượng và một`Matrix` đối tượng. Hình chữ nhật biểu thị vị trí và kích thước của hình ảnh, trong khi ma trận xác định cách đặt hình ảnh.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Bước 9: Ghép ma trận để đặt hình ảnh

 Để chỉ định cách hình ảnh sẽ được đặt trong hình chữ nhật, chúng ta sử dụng`ConcatenateMatrix` Toán tử này định nghĩa ma trận chuyển đổi ánh xạ không gian tọa độ của hình ảnh sang không gian tọa độ của trang.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Bước 10: Vẽ hình ảnh

 Trong bước này chúng ta sẽ vẽ hình ảnh trên trang bằng cách sử dụng`Do` nhà điều hành.`Do`Người vận hành lấy tên hình ảnh từ tài nguyên và kéo nó vào trang.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Bước 11: Khôi phục trạng thái đồ họa

 Sau khi vẽ hình ảnh, chúng ta cần khôi phục trạng thái đồ họa trước đó bằng cách sử dụng`GRestore` người điều hành.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Bước 12: Lưu tài liệu đã cập nhật

 Cuối cùng, chúng tôi sẽ lưu tài liệu đã cập nhật vào một tệp mới. Cập nhật`dataDir` biến có thư mục đầu ra và tên tệp mong muốn.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Mã nguồn mẫu cho Thêm hình ảnh bằng Aspose.PDF cho .NET 
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
// Lấy trang cần thêm hình ảnh
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
// Sử dụng toán tử ConcatenateMatrix (ma trận nối): xác định cách hình ảnh phải được đặt
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

Trong hướng dẫn này, chúng ta đã học cách thêm hình ảnh vào tài liệu PDF bằng Aspose.PDF cho .NET. Chúng tôi đã trình bày chi tiết từng bước, từ việc mở tài liệu đến việc lưu phiên bản đã cập nhật. Bằng cách làm theo hướng dẫn này, giờ đây bạn có thể nhúng hình ảnh vào tệp PDF theo chương trình bằng C# và Aspose.PDF.

### Câu hỏi thường gặp khi thêm hình ảnh vào tệp PDF

#### H: Tại sao tôi muốn thêm hình ảnh vào tài liệu PDF?

A: Việc thêm hình ảnh vào tài liệu PDF có thể làm tăng nội dung trực quan, cung cấp thêm bối cảnh hoặc bao gồm logo và đồ họa vào tệp PDF của bạn.

#### H: Tôi có thể thêm hình ảnh vào các trang cụ thể trong tài liệu PDF không?

A: Có, bạn có thể chỉ định trang bạn muốn thêm hình ảnh. Trong mã được cung cấp, hình ảnh được thêm vào trang thứ hai của tài liệu PDF.

#### H: Làm thế nào để điều chỉnh vị trí và kích thước của hình ảnh được thêm vào?

 A: Bạn có thể sửa đổi`lowerLeftX`, `lowerLeftY`, `upperRightX` , Và`upperRightY` các biến trong mã để thiết lập tọa độ của hình ảnh và kiểm soát kích thước cũng như vị trí của hình ảnh trên trang.

#### H: Tôi có thể thêm loại định dạng hình ảnh nào bằng phương pháp này?

A: Ví dụ mã được cung cấp giả định rằng bạn đang tải một hình ảnh JPG (`aspose-logo.jpg`). Aspose.PDF cho .NET hỗ trợ nhiều định dạng hình ảnh, bao gồm PNG, BMP, GIF, v.v.

#### H: Làm sao để đảm bảo hình ảnh được thêm vào nằm trong tọa độ đã chỉ định?

 A: Hãy đảm bảo điều chỉnh tọa độ và kích thước của`Rectangle` sự vật (`rectangle`) để phù hợp với kích thước của hình ảnh và vị trí mong muốn của hình ảnh trên trang.

#### H: Tôi có thể thêm nhiều hình ảnh vào một trang PDF không?

A: Có, bạn có thể thêm nhiều hình ảnh vào một trang PDF bằng cách lặp lại quy trình cho từng hình ảnh và điều chỉnh tọa độ cũng như các thông số khác cho phù hợp.

####  Q: Làm thế nào để`GSave` and `GRestore` operator work in the code?

 A: Cái`GSave` toán tử lưu trạng thái đồ họa hiện tại, cho phép bạn thực hiện thay đổi mà không ảnh hưởng đến bối cảnh đồ họa tổng thể.`GRestore` Người vận hành khôi phục trạng thái đồ họa trước đó sau khi thực hiện thay đổi.

#### H: Điều gì xảy ra nếu không tìm thấy tệp hình ảnh ở đường dẫn đã chỉ định?

A: Nếu tệp hình ảnh không được tìm thấy ở đường dẫn đã chỉ định, mã sẽ ném ngoại lệ khi cố gắng tải luồng hình ảnh. Đảm bảo tệp hình ảnh nằm trong đúng thư mục.

#### H: Tôi có thể tùy chỉnh thêm vị trí và giao diện của hình ảnh không?

 A: Có, bạn có thể tùy chỉnh giao diện hình ảnh bằng cách sửa đổi`Matrix` đối tượng và điều chỉnh các toán tử khác trong mã. Tham khảo tài liệu Aspose.PDF để biết tùy chỉnh nâng cao.

#### H: Làm sao tôi có thể kiểm tra xem hình ảnh đã được thêm vào PDF thành công hay chưa?

A: Sau khi áp dụng mã được cung cấp để thêm hình ảnh, hãy mở tệp PDF đã chỉnh sửa và xác minh rằng hình ảnh được hiển thị trên trang đã chỉ định với vị trí chính xác.

#### H: Việc thêm hình ảnh có ảnh hưởng đến nội dung gốc của tài liệu PDF không?

A: Việc thêm hình ảnh không ảnh hưởng đến nội dung gốc của tài liệu PDF. Nó làm tăng giá trị của tài liệu bằng cách thêm các yếu tố trực quan.