---
title: 提取 PDF 檔案中的邊框
linktitle: 提取 PDF 檔案中的邊框
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 擷取 PDF 檔案中的邊框。
type: docs
weight: 80
url: /zh-hant/net/programming-with-tables/extract-border/
---
在本教學中，我們將學習如何使用 Aspose.PDF for .NET 來擷取 PDF 檔案中的邊框。我們將一步步解釋C#的原始碼。在本教程結束時，您將了解如何從 PDF 文件中提取邊框並將其另存為圖像。讓我們開始吧！

## 第一步：建構環境
首先，請確保您已使用 Aspose.PDF for .NET 設定 C# 開發環境。新增對庫的引用並導入必要的命名空間。

## 步驟2：載入PDF文檔
在此步驟中，我們從指定文件載入 PDF 文件。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在的實際目錄。

## 第三步：邊緣擷取
我們將透過迭代文件中包含的操作來從 PDF 文件中提取邊框。

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
     //處理所有內容操作
     foreach(Operator op in doc.Pages[1].Contents)
     {
         //檢查操作類型
         // ……
         //新增程式碼來處理每個操作
     }
}
```

我們創建一個`graphicsState`用於儲存圖形狀態的堆疊、用於捕獲提取的邊框的點陣圖影像、`GraphicsPath`物件來儲存繪圖路徑，以及其他變數來追蹤狀態和顏色。

## 第四步：交易處理
在這一步驟中，我們處理文件的每個操作以提取邊框。

```csharp
//檢查操作類型
if (opSaveState != null)
{
     //儲存之前的狀態並將目前狀態壓入堆疊頂
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     //刪除目前狀態並恢復先前狀態
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     //檢索目前變換矩陣
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     //將目前矩陣與狀態矩陣相乘
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     //更新最後一個繪圖點
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     //處理直線的繪製
     // ……
     //新增程式碼來處理畫線
}
// ……
//新增 else if 區塊用於其他操作
```

我們使用條件檢查操作類型並為每個操作執行適當的程式碼。

## 第 5 步：備份映像
最後，我們將包含提取邊框的點陣圖影像儲存到指定檔案中。

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

請務必指定正確的目錄和檔案名稱來儲存輸出影像。

### 使用 Aspose.PDF for .NET 擷取邊框的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
//預設 ctm 矩陣值為 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Drawing座標係是基於左上角的，而pdf座標係是基於左下角的，所以我們必須應用逆矩陣
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	//處理所有內容命令
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
			//儲存之前的狀態並將當前狀態推入堆疊頂部
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			//丟棄目前狀態並恢復前一個狀態
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

			//將目前矩陣與狀態矩陣相乘
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

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 從 PDF 文件中提取邊框。您可以使用此逐步指南從其他 PDF 文件中提取邊框。

### PDF 檔案中提取邊框的常見問題解答

#### Q：從 PDF 文件中提取邊框的目的是什麼？

答：從 PDF 文件中提取邊框可用於多種目的。它允許您隔離和分析文件的結構元素，例如表格、圖表或圖形元素。您可以使用擷取的邊框來識別 PDF 文件中內容的佈局、尺寸和位置。

#### Q：我可以提取 PDF 文件中特定頁面或區域的邊框嗎？

答：是的，您可以修改提供的 C# 原始程式碼以從 PDF 文件中的特定頁面或區域提取邊框。透過操縱`doc.Pages`集合並指定自訂標準，您可以選擇從特定頁面或感興趣的區域提取邊框。

#### Q：如何自訂輸出影像格式和品質？

答：在提供的 C# 程式碼中，擷取的邊框會儲存為 PNG 影像。如果要改變輸出影像格式，可以修改`ImageFormat.Png`中的參數`bitmap.Save`方法轉換為其他支援的影像格式，例如 JPEG、BMP 或 GIF。此外，您可以根據您的要求調整影像品質或壓縮設定。

#### Q：擷取的邊框還可以進行哪些操作？

答：將邊框提取為圖像後，您可以使用圖像處理庫或演算法對其進行進一步處理。如果需要，您可以分析影像、套用影像濾鏡、偵測模式或執行 OCR（光學字元辨識）以從影像中擷取文字。

#### Q：從複雜的 PDF 文件中提取邊框時有什麼限製或註意事項嗎？

答：提取過程可能會根據 PDF 文件的複雜程度而有所不同。具有多層、透明度或高級圖形的複雜 PDF 可能需要額外的處理或調整才能準確提取邊框。必須徹底測試各種 PDF 文件的提取過程，以確保結果可靠。