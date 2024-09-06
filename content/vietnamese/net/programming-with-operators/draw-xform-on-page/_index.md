---
title: Vẽ XForm Trên Trang
linktitle: Vẽ XForm Trên Trang
second_title: Tài liệu tham khảo Aspose.PDF cho API .NET
description: Hướng dẫn từng bước để vẽ biểu mẫu XForm trên trang PDF bằng Aspose.PDF cho .NET. Thêm và định vị biểu mẫu trên trang.
type: docs
weight: 10
url: /vi/net/programming-with-operators/draw-xform-on-page/
---
Trong hướng dẫn này, chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước về cách vẽ XForm trên một trang bằng Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi tài liệu PDF theo chương trình. Sử dụng các toán tử do Aspose.PDF cung cấp, bạn có thể thêm và định vị biểu mẫu XForm trên trang PDF hiện có.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Visual Studio được cài đặt với .NET framework.
2. Thư viện Aspose.PDF dành cho .NET.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm tham chiếu đến thư viện Aspose.PDF cho .NET. Bạn có thể tải xuống thư viện từ trang web chính thức của Aspose và cài đặt trên máy của mình.

## Bước 2: Nhập các không gian tên cần thiết

Trong tệp mã C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Bước 3: Thiết lập đường dẫn tệp

Xác định đường dẫn tệp cho hình nền, tệp PDF đầu vào và tệp PDF đầu ra:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Hãy chắc chắn rằng bạn chỉ định đúng đường dẫn tệp trên máy của mình.

## Bước 4: Tải tệp PDF đầu vào

Sử dụng mã sau để tải tệp PDF đầu vào:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Mã sau đây sử dụng các toán tử GSave/GRestore
// Mã sử dụng toán tử ContatenateMatrix để định vị XForm
// Mã sử dụng toán tử Do để vẽ XForm trên trang
// Các toán tử GSave/GRestore bao bọc nội dung hiện có
//điều này được thực hiện để có được trạng thái đồ họa ban đầu ở cuối nội dung hiện có
// nếu không có thể có những chuyển đổi không mong muốn còn sót lại ở cuối chuỗi các toán tử hiện có
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Thêm toán tử GSave để thiết lập lại trạng thái đồ họa đúng cách sau lệnh mới
pageContents. Add(new GSave());

// Tạo XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Thiết lập chiều rộng và chiều cao của hình ảnh
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Tải hình ảnh vào luồng
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Thêm hình ảnh vào bộ sưu tập hình ảnh tài nguyên XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Sử dụng toán tử Do: toán tử này vẽ hình ảnh
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Đặt XForm tại tọa độ x=100 và y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Vẽ XForm bằng toán tử Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Đặt XForm tại tọa độ x=100 và y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Vẽ XForm bằng toán tử Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Khôi phục trạng thái đồ họa với GRestore sau GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Hãy đảm bảo chỉ định đường dẫn tệp thực tế và điều chỉnh số trang và vị trí XForm nếu cần.

### Mã nguồn mẫu để Vẽ XForm Trên Trang bằng Aspose.PDF cho .NET
 
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
	// Sử dụng toán tử GSave/GRestore
	// Sử dụng toán tử ContatenateMatrix để định vị xForm
	//Sử dụng toán tử để vẽ xForm trên trang
	// Bao bọc nội dung hiện có bằng cặp toán tử GSave/GRestore
	// đây là để có được trạng thái đồ họa ban đầu tại và của nội dung hiện có
	// nếu không có thể vẫn còn một số chuyển đổi không mong muốn ở cuối chuỗi nhà điều hành hiện tại
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Thêm toán tử lưu trạng thái đồ họa để xóa đúng trạng thái đồ họa sau các lệnh mới
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
	// Thêm hình ảnh vào bộ sưu tập Hình ảnh của Tài nguyên XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Sử dụng toán tử Do: toán tử này vẽ hình ảnh
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Đặt biểu mẫu vào tọa độ x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Vẽ biểu mẫu với toán tử Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Đặt biểu mẫu vào tọa độ x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Vẽ biểu mẫu với toán tử Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Khôi phục trạng thái đồ họa bằng GRestore sau GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách vẽ biểu mẫu XForm trên trang PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo các bước được mô tả, bạn sẽ có thể thêm và định vị biểu mẫu XForm trên trang hiện có, do đó mang lại sự linh hoạt hơn cho tài liệu PDF của bạn.

### Câu hỏi thường gặp về cách vẽ XForm trên trang

#### H: XForm trong Aspose.PDF là gì?

A: XForm là một đối tượng đồ họa có thể tái sử dụng trong tài liệu PDF. Nó cho phép bạn xác định và vẽ đồ họa, hình ảnh hoặc văn bản phức tạp có thể được tái sử dụng nhiều lần trên các trang khác nhau.

#### H: Làm thế nào để nhập các không gian tên cần thiết cho Aspose.PDF?

 A: Trong tệp mã C# của bạn, hãy sử dụng`using` chỉ thị để nhập các không gian tên cần thiết để truy cập các lớp và phương thức do Aspose.PDF cung cấp:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### H: Mục đích của toán tử GSave và GRestore là gì?

 A: Cái`GSave` Và`GRestore` Các toán tử trong Aspose.PDF được sử dụng để lưu và khôi phục trạng thái đồ họa. Chúng giúp đảm bảo rằng các chuyển đổi và cài đặt được áp dụng cho một phần của nội dung không ảnh hưởng đến các phần tiếp theo.

#### H: Làm thế nào để định nghĩa XForm bằng Aspose.PDF?

 A: Để tạo XForm, hãy sử dụng`XForm.CreateNewForm` phương pháp và thêm nó vào`Resources.Forms` bộ sưu tập của một trang cụ thể. Sau đó, bạn có thể thêm nội dung vào XForm`Contents` tài sản.

#### H: Làm thế nào tôi có thể vẽ hình ảnh trong XForm?

A: Tải hình ảnh vào một luồng và thêm nó vào`Resources.Images` bộ sưu tập của XForm. Sử dụng`Do` toán tử trong XForm`Contents` để vẽ hình ảnh.

#### H: Làm thế nào để định vị XForm trên trang PDF?

 A: Để định vị XForm trên một trang, hãy sử dụng`ConcatenateMatrix` toán tử trong trang`Contents`. Điều chỉnh các tham số ma trận để xác định phép tịnh tiến (vị trí) và tỷ lệ của XForm.

#### H: Tôi có thể vẽ nhiều XForm trên cùng một trang không?

 A: Có, bạn có thể vẽ nhiều XForm trên cùng một trang bằng cách điều chỉnh`ConcatenateMatrix` các tham số để định vị từng XForm ở các tọa độ khác nhau.

#### H: Tôi có thể sửa đổi nội dung của XForm sau khi đã tạo không?

 A: Có, bạn có thể sửa đổi nội dung của XForm sau khi tạo bằng cách thêm các toán tử bổ sung vào đó.`Contents` tài sản.

#### H: Điều gì xảy ra nếu tôi bỏ qua các toán tử GSave và GRestore?

A: Việc bỏ qua các toán tử GSave và GRestore có thể dẫn đến việc áp dụng các chuyển đổi hoặc cài đặt không mong muốn cho nội dung tiếp theo. Sử dụng chúng giúp duy trì trạng thái đồ họa sạch.

#### H: Tôi có thể sử dụng lại XForms trên nhiều trang khác nhau của tài liệu PDF không?

 A: Có, bạn có thể sử dụng lại XForms trên nhiều trang bằng cách thêm cùng một XForm vào`Resources.Forms` bộ sưu tập các trang khác nhau.

#### H: Có giới hạn số lượng XForm tôi có thể tạo không?

A: Mặc dù không có giới hạn nghiêm ngặt về số lượng XForms bạn có thể tạo, hãy lưu ý rằng quá nhiều XForms có thể ảnh hưởng đến hiệu suất và việc sử dụng bộ nhớ. Hãy sử dụng chúng một cách thận trọng.

#### H: Tôi có thể xoay XForm hoặc áp dụng các phép biến đổi khác không?

 A: Có, bạn có thể sử dụng`ConcatenateMatrix` toán tử để áp dụng các phép biến đổi như xoay, thay đổi tỷ lệ và tịnh tiến cho XForm.
