---
title: Thông tin hình ảnh trong tệp PDF
linktitle: Thông tin hình ảnh trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Trích xuất thông tin hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 160
url: /vi/net/programming-with-images/image-information/
---
Hướng dẫn này sẽ hướng dẫn bạn từng bước cách trích xuất thông tin về hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET. Đảm bảo bạn đã thiết lập môi trường của mình và làm theo các bước bên dưới:

## Bước 1: Xác định thư mục tài liệu

 Đảm bảo đặt đúng thư mục tài liệu. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã có đường dẫn đến thư mục chứa tài liệu PDF của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tệp PDF nguồn

 Trong bước này, chúng tôi sẽ tải tệp PDF nguồn bằng cách sử dụng`Document` lớp Aspose.PDF. Sử dụng`Document` constructor và chuyển đường dẫn đến tài liệu PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Bước 3: Đặt độ phân giải mặc định

Ở bước này chúng ta sẽ thiết lập độ phân giải mặc định cho hình ảnh. Trong ví dụ, độ phân giải mặc định được đặt thành 72.

```csharp
int defaultResolution = 72;
```

## Bước 4: Khởi tạo đối tượng và bộ đếm

Ở bước này, chúng ta sẽ khởi tạo các đối tượng và bộ đếm cần thiết để lấy thông tin hình ảnh.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Bước 5: Duyệt qua các toán tử trên trang đầu tiên của tài liệu

Trong bước này, chúng ta sẽ tìm hiểu các toán tử trên trang đầu tiên của tài liệu để xác định các thao tác liên quan đến hình ảnh.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Bước 6: Quản lý toán tử và trích xuất thông tin hình ảnh

Trong bước này, chúng tôi sẽ quản lý các loại toán tử khác nhau và trích xuất thông tin về hình ảnh.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Xử lý các hoạt động GSave và GRestore để chuyển đổi
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Xử lý thao tác ConcatenateMatrix để chuyển đổi
else if (opCtm != null)
{
     // Áp dụng ma trận chuyển đổi
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Xử lý thao tác Do cho hình ảnh
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Truy xuất hình ảnh
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Truy xuất kích thước của hình ảnh
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Tính độ phân giải dựa trên thông tin trên
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Hiển thị thông tin hình ảnh
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Mã nguồn mẫu cho Thông tin hình ảnh bằng Aspose.PDF for .NET 
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải tệp PDF nguồn
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Xác định độ phân giải mặc định cho hình ảnh
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Xác định đối tượng danh sách mảng sẽ chứa tên hình ảnh
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Chèn một đối tượng vào ngăn xếp
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Nhận tất cả các toán tử trên trang đầu tiên của tài liệu
foreach (Operator op in doc.Pages[1].Contents)
{
	// Sử dụng toán tử GSave/GRestore để hoàn nguyên các phép biến đổi về thiết lập trước đó
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Khởi tạo đối tượng ConcatenateMatrix vì nó xác định ma trận chuyển đổi hiện tại.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Tạo toán tử Do để vẽ các đối tượng từ tài nguyên. Nó vẽ các đối tượng Form và đối tượng Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Lưu trạng thái trước đó và đẩy trạng thái hiện tại lên đầu ngăn xếp
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Vứt bỏ trạng thái hiện tại và khôi phục trạng thái trước đó
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Nhân ma trận hiện tại với ma trận trạng thái
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Trong trường hợp đây là toán tử vẽ hình ảnh
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Tạo đối tượng XImage để giữ hình ảnh của trang pdf đầu tiên
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Lấy kích thước hình ảnh
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Nhận thông tin về Chiều cao và Chiều rộng của hình ảnh
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Tính toán độ phân giải dựa trên thông tin trên
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Hiển thị thông tin Kích thước và Độ phân giải của từng hình ảnh
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã học cách trích xuất thông tin hình ảnh trong tệp PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng thông tin này cho các tác vụ xử lý hình ảnh khác nhau trong ứng dụng của mình.

### Câu hỏi thường gặp về thông tin hình ảnh trong tệp PDF

#### Câu hỏi: Mục đích của việc trích xuất thông tin hình ảnh từ tài liệu PDF bằng Aspose.PDF cho .NET là gì?

Đáp: Việc trích xuất thông tin hình ảnh từ tài liệu PDF cung cấp thông tin chi tiết về kích thước, độ phân giải và các thuộc tính khác của hình ảnh trong tài liệu. Thông tin này có thể được sử dụng để xử lý, phân tích hoặc tối ưu hóa hình ảnh.

#### Câu hỏi: Aspose.PDF for .NET hỗ trợ trích xuất thông tin hình ảnh từ tài liệu PDF như thế nào?

Đáp: Aspose.PDF for .NET cung cấp các công cụ để truy cập và phân tích nội dung của tài liệu PDF, bao gồm cả hình ảnh của tài liệu đó. Mã được cung cấp trình bày cách trích xuất và hiển thị thông tin hình ảnh bằng nhiều toán tử khác nhau.

#### Câu hỏi: Loại thông tin hình ảnh nào có thể được trích xuất bằng phương pháp này?

Trả lời: Phương pháp này cho phép bạn trích xuất và hiển thị thông tin như kích thước, độ phân giải và tên hình ảnh được chia tỷ lệ cho hình ảnh trong tài liệu PDF.

#### Câu hỏi: Mã xác định và xử lý các toán tử liên quan đến hình ảnh trong tài liệu PDF như thế nào?

Đáp: Mã lặp qua các toán tử trên một trang được chỉ định của tài liệu PDF. Nó xác định và xử lý các toán tử liên quan đến hoạt động, chuyển đổi và hiển thị hình ảnh.

#### Câu hỏi: Tầm quan trọng của độ phân giải mặc định là gì và nó được sử dụng như thế nào trong mã?

Trả lời: Độ phân giải mặc định được sử dụng làm điểm tham chiếu để tính toán độ phân giải thực tế của hình ảnh. Mã tính toán độ phân giải của từng hình ảnh dựa trên kích thước của nó và cài đặt độ phân giải mặc định.

#### Câu hỏi: Làm cách nào để sử dụng thông tin hình ảnh được trích xuất trong các tình huống thực tế?

Đáp: Thông tin hình ảnh được trích xuất có thể được sử dụng cho các tác vụ như đánh giá chất lượng hình ảnh, tối ưu hóa hình ảnh, tạo hình thu nhỏ của hình ảnh và hỗ trợ quá trình ra quyết định liên quan đến hình ảnh.

#### Câu hỏi: Tôi có thể sửa đổi mã để trích xuất các thuộc tính bổ sung liên quan đến hình ảnh không?

Trả lời: Có, bạn có thể tùy chỉnh mã để trích xuất các thuộc tính bổ sung của hình ảnh, chẳng hạn như không gian màu, độ sâu pixel hoặc loại hình ảnh.

#### Câu hỏi: Quá trình trích xuất thông tin hình ảnh có tốn nhiều tài nguyên hay thời gian không?

Đáp: Quá trình trích xuất thông tin hình ảnh hiệu quả và được tối ưu hóa về hiệu suất, đảm bảo tác động tối thiểu đến việc sử dụng tài nguyên và thời gian xử lý.

#### Hỏi: Các nhà phát triển có thể hưởng lợi như thế nào từ việc xác định và trích xuất thông tin hình ảnh từ tài liệu PDF?

Trả lời: Các nhà phát triển có thể hiểu rõ hơn về đặc điểm của hình ảnh trong tài liệu PDF, cho phép họ đưa ra quyết định sáng suốt về thao tác, xử lý và tối ưu hóa hình ảnh.

#### Hỏi: Phương pháp này có thể được sử dụng để xử lý hàng loạt tài liệu PDF có chứa hình ảnh không?

Đáp: Có, phương pháp này có thể được mở rộng để xử lý hàng loạt bằng cách lặp qua nhiều trang hoặc tài liệu, trích xuất thông tin hình ảnh và thực hiện các tác vụ liên quan đến hình ảnh.