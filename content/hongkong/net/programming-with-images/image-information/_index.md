---
title: PDF 檔案中的影像訊息
linktitle: PDF 檔案中的影像訊息
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 擷取 PDF 檔案中的影像資訊。
type: docs
weight: 160
url: /zh-hant/net/programming-with-images/image-information/
---
本指南將逐步指導您如何使用 Aspose.PDF for .NET 提取 PDF 文件中的圖像資訊。確保您已設定環境並按照以下步驟操作：

## 步驟1：定義文檔目錄

確保設定正確的文件目錄。代替`"YOUR DOCUMENT DIRECTORY"`在程式碼中新增 PDF 文件所在目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入來源 PDF 文件

在此步驟中，我們將使用以下命令載入來源 PDF 文件`Document` Aspose.PDF 類別。使用`Document`建構函數並傳遞 PDF 文件的路徑。

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 步驟 3：設定預設分辨率

在此步驟中，我們將設定影像的預設解析度。在範例中，預設解析度設定為 72。

```csharp
int defaultResolution = 72;
```

## 第 4 步：初始化物件和計數器

在此步驟中，我們將初始化檢索影像資訊所需的物件和計數器。

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 步驟 5：循環瀏覽文件首頁上的運算符

在此步驟中，我們將遍歷文件第一頁上的運算子來識別與影像相關的操作。

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 步驟6：管理算子並提取影像資訊

在這一步驟中，我們將管理不同類型的運算子並提取有關圖像的資訊。

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//處理轉換的 GSave 和 GRestore 操作
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
//處理 ConcatenateMatrix 轉換操作
else if (opCtm != null)
{
     //應用變換矩陣
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
//處理影像的Do操作
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         //檢索影像
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         //檢索影像的尺寸
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         //根據以上資訊計算分辨率
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         //顯示影像訊息
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### 使用 Aspose.PDF for .NET 的圖像資訊範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//載入來源 PDF 文件
Document doc = new Document(dataDir+ "ImageInformation.pdf");
//定義影像的預設分辨率
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
//定義將保存影像名稱的陣列清單對象
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
//將物件插入堆疊
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
//取得文件第一頁上的所有運算符
foreach (Operator op in doc.Pages[1].Contents)
{
	//使用 GSave/GRestore 運算子將轉換還原到先前設定
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	//實例化 ConcatenateMatrix 對象，因為它定義目前變換矩陣。
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	//建立從資源中提取物件的 Do 運算子。它繪製 Form 物件和 Image 對象
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//儲存之前的狀態並將當前狀態推入堆疊頂部
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		//丟棄目前狀態並恢復前一個狀態
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
		//將目前矩陣與狀態矩陣相乘
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		//如果這是一個影像繪製操作員
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			//建立 XImage 物件來保存第一個 pdf 頁的圖像
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			//取得影像尺寸
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			//獲取圖像的高度和寬度信息
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			//根據以上資訊計算分辨率
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			//顯示每張影像的尺寸和解析度訊息
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 結論

恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 來擷取 PDF 檔案中的影像資訊。您可以將此資訊用於應用程式中的各種影像處理任務。

### PDF 檔案中影像資訊的常見問題解答

#### Q：使用 Aspose.PDF for .NET 從 PDF 文件中擷取影像資訊的目的為何？

答：從 PDF 文件中提取影像資訊可以深入了解文件中影像的尺寸、解析度和其他屬性。此資訊可用於影像處理、分析或優化任務。

#### Q：Aspose.PDF for .NET 如何協助從 PDF 文件中擷取影像資訊？

答：Aspose.PDF for .NET 提供了存取和分析 PDF 文件內容（包括影像）的工具。提供的程式碼示範如何使用各種運算符來提取和顯示圖像資訊。

#### 問：該方法可以提取哪些影像資訊？

答：此方法可讓您提取並顯示 PDF 文件中圖像的信息，例如縮放尺寸、解析度和圖像名稱。

#### Q：程式碼如何識別和處理 PDF 文件中與影像相關的運算符？

答：程式碼會迭代 PDF 文件指定頁面上的運算子。它識別並處理與圖像操作、轉換和渲染相關的運算符。

#### Q：預設解析的意義是什麼，在程式碼中是如何使用的？

A：以預設解析度為參考點來計算影像的實際解析度。程式碼根據每個影像的尺寸和預設解析度設定計算其解析度。

#### Q：擷取的影像資訊如何應用於現實場景？

答：擷取的影像資訊可用於影像品質評估、影像優化、產生影像縮圖以及促進影像相關決策過程等任務。

#### Q：我可以修改程式碼來提取其他與圖像相關的屬性嗎？

答：是的，您可以自訂程式碼來提取影像的其他屬性，例如色彩空間、像素深度或影像類型。

#### Q：影像資訊擷取過程是否佔用資源或耗時？

答：影像資訊擷取過程高效且針對效能進行了最佳化，確保對資源使用和處理時間的影響最小。

#### Q：開發人員如何從 PDF 文件中識別和提取影像資訊中受益？

答：開發人員可以深入了解 PDF 文件中影像的特徵，使他們能夠就影像操作、處理和優化做出明智的決策。

#### Q：該方法可以用於批次處理包含影像的PDF文件嗎？

答：是的，該方法可以透過迭代多個頁面或文件、提取影像資訊以及執行與影像相關的任務來擴展批次處理。