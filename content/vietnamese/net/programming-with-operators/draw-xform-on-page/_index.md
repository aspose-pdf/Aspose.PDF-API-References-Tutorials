---
title: Vẽ XForm Trên Trang
linktitle: Vẽ XForm Trên Trang
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để vẽ biểu mẫu XForm trên trang PDF bằng Aspose.PDF cho .NET. Thêm và định vị biểu mẫu trên trang.
type: docs
weight: 10
url: /vi/net/programming-with-operators/draw-xform-on-page/
---
Trong hướng dẫn này, chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước về cách vẽ XForm trên một trang bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Bằng cách sử dụng các toán tử do Aspose.PDF cung cấp, bạn có thể thêm và định vị biểu mẫu XForm trên trang PDF hiện có.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Visual Studio được cài đặt với .NET framework.
2. Thư viện Aspose.PDF cho .NET.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống thư viện từ trang web chính thức của Aspose và cài đặt nó trên máy của mình.

## Bước 2: Nhập các không gian tên cần thiết

Trong tệp mã C# của bạn, hãy nhập các vùng tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Bước 3: Thiết lập đường dẫn file

Xác định đường dẫn tệp cho ảnh nền, tệp PDF đầu vào và tệp PDF đầu ra:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Đảm bảo chỉ định đường dẫn tệp thực tế trên máy của bạn.

## Bước 4: Tải tệp PDF đầu vào

Sử dụng đoạn mã sau để tải tệp PDF đầu vào:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Đoạn mã sau sử dụng toán tử GSave/GRestore
// Mã này sử dụng toán tử ContatenateMatrix để định vị XForm
// Đoạn mã sử dụng toán tử Do để vẽ XForm trên trang
// Toán tử GSave/GRestore bao bọc nội dung hiện có
// việc này được thực hiện để có được trạng thái đồ họa ban đầu ở cuối nội dung hiện có
// nếu không thì có thể có những chuyển đổi không mong muốn còn sót lại ở cuối chuỗi các toán tử hiện có
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Thêm toán tử GSave để đặt lại trạng thái đồ họa đúng cách sau các lệnh mới
pageContents. Add(new GSave());

// Tạo XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Đặt chiều rộng và chiều cao của hình ảnh
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Tải hình ảnh vào một luồng
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Thêm hình ảnh vào bộ sưu tập hình ảnh tài nguyên XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Sử dụng toán tử Do: toán tử này vẽ hình ảnh
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Định vị XForm tại tọa độ x=100 và y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Vẽ XForm bằng toán tử Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Định vị XForm tại tọa độ x=100 và y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Vẽ XForm bằng toán tử Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Khôi phục trạng thái đồ họa bằng GRestore sau GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Đảm bảo chỉ định đường dẫn tệp thực tế và điều chỉnh số trang cũng như vị trí XForm nếu cần.

### Mã nguồn mẫu cho Draw XForm On Page bằng Aspose.PDF for .NET
 
```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Mẫu chứng minh
	// Cách sử dụng toán tử GSave/GRestore
	// Cách sử dụng toán tử ContatenateMatrix để định vị xForm
	// Sử dụng toán tử để vẽ xForm trên trang
	// Gói nội dung hiện có bằng cặp toán tử GSave/GRestore
	// điều này là để có được trạng thái đồ họa ban đầu tại và của nội dung hiện có
	// nếu không thì có thể vẫn còn một số chuyển đổi không mong muốn ở cuối chuỗi toán tử hiện tại
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Thêm toán tử lưu trạng thái đồ họa để xóa trạng thái đồ họa đúng cách sau các lệnh mới
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Tạo xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Xác định chiều rộng và chiều cao của hình ảnh
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Tải hình ảnh vào luồng
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Thêm hình ảnh vào bộ sưu tập Hình ảnh của Tài nguyên XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Sử dụng toán tử Do: toán tử này vẽ hình ảnh
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Đặt biểu mẫu vào tọa độ x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Vẽ biểu mẫu bằng toán tử Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Đặt biểu mẫu vào tọa độ x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Vẽ biểu mẫu bằng toán tử Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Khôi phục trạng thái đồ họa bằng GRestore sau GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách vẽ biểu mẫu XForm trên trang PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước được mô tả, bạn sẽ có thể thêm và định vị biểu mẫu XForm trên một trang hiện có, do đó mang lại sự linh hoạt hơn cho tài liệu PDF của bạn.

### Câu hỏi thường gặp về vẽ XForm trên trang

#### Câu hỏi: XForm trong Aspose.PDF là gì?

Đáp: XForm là một đối tượng đồ họa có thể tái sử dụng trong một tài liệu PDF. Nó cho phép bạn xác định và vẽ đồ họa, hình ảnh hoặc văn bản phức tạp có thể được sử dụng lại nhiều lần trên các trang khác nhau.

#### Câu hỏi: Làm cách nào để nhập các vùng tên cần thiết cho Aspose.PDF?

 Đáp: Trong tệp mã C# của bạn, hãy sử dụng`using` chỉ thị nhập các không gian tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Câu hỏi: Mục đích của các toán tử GSave và GRestore là gì?

 Đáp: Cái`GSave` Và`GRestore`các toán tử trong Aspose.PDF được sử dụng để lưu và khôi phục trạng thái đồ họa. Chúng giúp đảm bảo rằng các chuyển đổi và cài đặt được áp dụng cho một phần nội dung không ảnh hưởng đến các phần tiếp theo.

#### Câu hỏi: Làm cách nào để xác định XForm bằng Aspose.PDF?

 Đáp: Để tạo một XForm, hãy sử dụng`XForm.CreateNewForm` phương thức và thêm nó vào`Resources.Forms` bộ sưu tập của một trang cụ thể. Sau đó bạn có thể thêm nội dung vào XForm`Contents` tài sản.

#### Câu hỏi: Làm cách nào tôi có thể vẽ một hình ảnh trong XForm?

 A: Tải hình ảnh vào một luồng và thêm nó vào`Resources.Images` bộ sưu tập XForm. Sử dụng`Do` toán tử trong XForm`Contents` để vẽ hình ảnh.

#### Câu hỏi: Làm cách nào để định vị XForm trên trang PDF?

 Đáp: Để định vị một XForm trên một trang, hãy sử dụng`ConcatenateMatrix` toán tử trong trang`Contents`. Điều chỉnh các tham số ma trận để xác định sự dịch chuyển (vị trí) và tỷ lệ của XForm.

#### Hỏi: Tôi có thể vẽ nhiều XForms trên cùng một trang không?

 Đáp: Có, bạn có thể vẽ nhiều XForms trên cùng một trang bằng cách điều chỉnh`ConcatenateMatrix`các tham số để định vị từng XForm ở các tọa độ khác nhau.

#### Câu hỏi: Tôi có thể sửa đổi nội dung của XForm sau khi nó được tạo không?

 Đáp: Có, bạn có thể sửa đổi nội dung của XForm sau khi tạo bằng cách thêm các toán tử bổ sung vào`Contents` tài sản.

#### Câu hỏi: Điều gì xảy ra nếu tôi bỏ qua toán tử GSave và GRestore?

Trả lời: Việc bỏ qua các toán tử GSave và GRestore có thể dẫn đến các chuyển đổi hoặc cài đặt không mong muốn được áp dụng cho nội dung tiếp theo. Sử dụng chúng giúp duy trì trạng thái đồ họa rõ ràng.

#### Hỏi: Tôi có thể sử dụng lại XForms trên các trang khác nhau của tài liệu PDF không?

 Đáp: Có, bạn có thể sử dụng lại XForms trên nhiều trang bằng cách thêm cùng một XForm vào`Resources.Forms` tập hợp các trang khác nhau.

#### Câu hỏi: Có giới hạn nào về số lượng XForms tôi có thể tạo không?

Đáp: Mặc dù không có giới hạn nghiêm ngặt về số lượng XForms bạn có thể tạo, hãy nhớ rằng quá nhiều XForms có thể ảnh hưởng đến hiệu suất và việc sử dụng bộ nhớ. Hãy sử dụng chúng một cách thận trọng.

#### Câu hỏi: Tôi có thể xoay XForm hoặc áp dụng các phép biến đổi khác không?

 Đ: Có, bạn có thể sử dụng`ConcatenateMatrix`toán tử để áp dụng các phép biến đổi như xoay, chia tỷ lệ và dịch sang XForm.
