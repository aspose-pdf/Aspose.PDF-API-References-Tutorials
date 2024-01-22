---
title: Trích xuất đường viền trong tệp PDF
linktitle: Trích xuất đường viền trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất đường viền trong tệp PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 80
url: /vi/net/programming-with-tables/extract-border/
---
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách trích xuất đường viền trong tệp PDF bằng Aspose.PDF cho .NET. Chúng tôi sẽ giải thích từng bước về mã nguồn trong C#. Khi kết thúc hướng dẫn này, bạn sẽ biết cách trích xuất đường viền từ tài liệu PDF và lưu nó dưới dạng hình ảnh. Hãy bắt đầu!

## Bước 1: Thiết lập môi trường
Trước tiên, hãy đảm bảo bạn đã thiết lập môi trường phát triển C# của mình với Aspose.PDF cho .NET. Thêm tham chiếu vào thư viện và nhập các không gian tên cần thiết.

## Bước 2: Tải tài liệu PDF
Trong bước này, chúng tôi tải tài liệu PDF từ tệp được chỉ định.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Đảm bảo thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng thư mục thực nơi chứa tệp PDF của bạn.

## Bước 3: Khai thác cạnh
Chúng tôi sẽ trích xuất đường viền từ tài liệu PDF bằng cách lặp lại các thao tác có trong tài liệu.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Xử lý mọi hoạt động nội dung
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Kiểm tra loại hoạt động
         // ...
         // Thêm mã để xử lý từng thao tác
     }
}
```

 Chúng tôi tạo ra một`graphicsState` ngăn xếp để lưu trữ trạng thái đồ họa, hình ảnh bitmap để chụp đường viền được trích xuất,`GraphicsPath` đối tượng để lưu trữ đường dẫn vẽ và các biến khác để theo dõi trạng thái và màu sắc.

## Bước 4: Xử lý giao dịch
Ở bước này chúng ta xử lý từng thao tác trên tài liệu để trích xuất đường viền.

```csharp
// Kiểm tra loại hoạt động
if (opSaveState != null)
{
     // Lưu trạng thái trước đó và đẩy trạng thái hiện tại lên đầu ngăn xếp
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Xóa trạng thái hiện tại và khôi phục trạng thái trước đó
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Truy xuất ma trận chuyển đổi hiện tại
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Nhân ma trận hiện tại với ma trận trạng thái
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Cập nhật điểm vẽ cuối cùng
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Xử lý việc vẽ đường
     // ...
     // Thêm mã để xử lý việc vẽ một đường
}
// ...
// Thêm các khối else if cho các hoạt động khác
```

Chúng tôi kiểm tra loại hoạt động bằng cách sử dụng các điều kiện và chạy mã thích hợp cho từng hoạt động.

## Bước 5: Sao lưu ảnh
Cuối cùng, chúng ta lưu hình ảnh bitmap chứa đường viền được trích xuất vào một tệp được chỉ định.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Đảm bảo chỉ định đúng thư mục và tên tệp để lưu hình ảnh đầu ra.

### Mã nguồn ví dụ cho Extract Border bằng Aspose.PDF for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Giá trị ma trận ctm mặc định là 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Hệ tọa độ System.draw nằm trên cùng bên trái, trong khi hệ tọa độ pdf dựa trên bên trái thấp, vì vậy chúng ta phải áp dụng ma trận đảo ngược
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Xử lý tất cả các lệnh nội dung
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Lưu trạng thái trước đó và đẩy trạng thái hiện tại lên đầu ngăn xếp
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Vứt bỏ trạng thái hiện tại và khôi phục trạng thái trước đó
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách trích xuất đường viền từ tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng hướng dẫn từng bước này để trích xuất đường viền từ các tài liệu PDF khác.

### Câu hỏi thường gặp về trích xuất đường viền trong tệp PDF

#### Hỏi: Mục đích của việc trích xuất đường viền từ tệp PDF là gì?

Trả lời: Việc trích xuất đường viền từ tệp PDF có thể hữu ích cho nhiều mục đích khác nhau. Nó cho phép bạn tách biệt và phân tích các thành phần cấu trúc của tài liệu, chẳng hạn như bảng, sơ đồ hoặc thành phần đồ họa. Bạn có thể sử dụng đường viền được trích xuất để xác định bố cục, kích thước và vị trí của nội dung trong tài liệu PDF.

#### Hỏi: Tôi có thể trích xuất đường viền từ các trang hoặc khu vực cụ thể trong tài liệu PDF không?

Trả lời: Có, bạn có thể sửa đổi mã nguồn C# được cung cấp để trích xuất đường viền từ các trang hoặc vùng cụ thể trong tài liệu PDF. Bằng cách thao tác`doc.Pages` tập hợp và chỉ định tiêu chí tùy chỉnh, bạn có thể chọn trích xuất đường viền từ các trang hoặc khu vực quan tâm cụ thể.

#### Hỏi: Làm cách nào tôi có thể tùy chỉnh định dạng và chất lượng hình ảnh đầu ra?

 Trả lời: Trong mã C# được cung cấp, đường viền được trích xuất sẽ được lưu dưới dạng hình ảnh PNG. Nếu bạn muốn thay đổi định dạng hình ảnh đầu ra, bạn có thể sửa đổi`ImageFormat.Png` tham số trong`bitmap.Save` sang các định dạng hình ảnh được hỗ trợ khác, chẳng hạn như JPEG, BMP hoặc GIF. Ngoài ra, bạn có thể điều chỉnh chất lượng hình ảnh hoặc cài đặt nén dựa trên yêu cầu của mình.

#### Câu hỏi: Tôi có thể thực hiện những thao tác nào khác trên đường viền được trích xuất?

Đáp: Sau khi đã trích xuất đường viền dưới dạng hình ảnh, bạn có thể xử lý thêm đường viền đó bằng cách sử dụng các thư viện hoặc thuật toán xử lý hình ảnh. Bạn có thể phân tích hình ảnh, áp dụng bộ lọc hình ảnh, phát hiện mẫu hoặc thực hiện OCR (Nhận dạng ký tự quang học) để trích xuất văn bản từ hình ảnh nếu cần.

#### Câu hỏi: Có bất kỳ hạn chế hoặc cân nhắc nào khi trích xuất đường viền từ các tài liệu PDF phức tạp không?

Trả lời: Quá trình trích xuất có thể khác nhau tùy thuộc vào độ phức tạp của tài liệu PDF. Các tệp PDF phức tạp có nhiều lớp, độ trong suốt hoặc đồ họa nâng cao có thể yêu cầu xử lý hoặc điều chỉnh bổ sung để trích xuất chính xác đường viền. Điều cần thiết là phải kiểm tra kỹ lưỡng quá trình trích xuất trên nhiều tài liệu PDF khác nhau để đảm bảo kết quả đáng tin cậy.