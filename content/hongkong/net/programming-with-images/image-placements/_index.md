---
title: 圖片展示位置
linktitle: 圖片展示位置
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將影像放入 PDF 文件中。
type: docs
weight: 170
url: /zh-hant/net/programming-with-images/image-placements/
---
在本教學中，我們將使用 .NET 的 Aspose.PDF 庫來處理 PDF 文件並對影像執行操作。我們將加載 PDF 文檔，提取圖像位置信息，並檢索尺寸可見的圖像。

## 第一步：建構環境
在開始之前，請確保您已使用以下內容設定開發環境：
- Aspose.PDF for .NET 安裝在您的電腦上。
- AC# 項目可供使用。

## 第 2 步：載入 PDF 文檔
首先，我們需要載入要處理的 PDF 文件。確保您擁有包含 PDF 文件的目錄的正確路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//載入來源PDF文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`包含 PDF 檔案的文檔目錄的實際路徑。

## 步驟 3：從影像中擷取位置資訊
現在我們已經加載了 PDF 文檔，我們可以從圖像中提取位置資訊。我們將使用`ImagePlacementAbsorber`從文件的第一頁吸收影像位置。

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//載入第一頁的內容
doc.Pages[1].Accept(abs);
```

我們現在已經從文件的第一頁中提取了圖像放置資訊。

## 步驟 4：檢索具有可見尺寸的影像
現在，我們將從先前提取的放置資訊中檢索影像及其可見尺寸。

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //取得影像屬性
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     //檢索具有可見尺寸的影像
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         //從資源中取得圖片
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         //建立具有實際尺寸的影像
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

在此循環中，我們檢索每個影像的屬性，例如寬度、高度、左下角的 X 和 Y 座標以及水平和垂直解析度。然後，我們使用放置資訊來檢索每個影像及其可見尺寸。

### 使用 Aspose.PDF for .NET 進行影像放置的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//載入來源PDF文檔
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//載入第一頁的內容
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	//取得影像屬性
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	//檢索具有可見尺寸的影像
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		//從資源中檢索影像
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//建立具有實際尺寸的點陣圖
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## 結論
恭喜！現在您已經了解如何使用 Aspose.PDF for .NET 在 PDF 文件中執行影像放置。我們解釋了提供的 C# 原始程式碼，它允許您載入 PDF 文件、從圖像中提取位置資訊以及檢索尺寸可見的圖像。請隨意嘗試更多 Aspose.PDF 以探索它的許多其他功能。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 從 PDF 文件中擷取影像位置資訊的目的為何？

答：擷取影像位置資訊可讓您檢索 PDF 文件中影像的位置、尺寸和解析度。這些資訊對於精確的影像處理和分析至關重要。

#### Q：Aspose.PDF for .NET 如何促進從 PDF 文件中提取影像放置資訊？

答：Aspose.PDF for .NET 提供了`ImagePlacementAbsorber`類，可用於從 PDF 文件中吸收影像放置細節。提供的程式碼示範如何利用此類來檢索影像放置資訊。

#### Q：影像放置資訊在現實場景中可以用來做什麼？

答：影像放置資訊對於確保準確的影像對齊、計算影像尺寸、驗證影像品質以及生成 PDF 文件中影像使用情況的報告等任務非常有價值。

#### Q：程式碼範例如何保證圖片投放資訊的準確擷取？

答：程式碼範例採用了`ImagePlacementAbsorber`類別來遍歷指定頁面的內容、識別圖像位置並檢索其屬性，例如寬度、高度、座標和解析度。

#### Q：程式碼可以擴展以處理跨多個頁面或文件的圖像嗎？

答：是的，可以透過迭代多個頁面或文件來擴展程式碼，以提取圖像放置資訊並執行與圖像相關的任務。

#### Q：程式碼如何根據放置資訊檢索影像及其可見尺寸？

答：程式碼範例從資源中提取圖像數據，建立具有實際尺寸的點陣圖圖像，並提供寬度、高度、座標和解析度等屬性。

#### Q：這種方法對於包含大量影像的大型 PDF 文件有效嗎？

答：是的，Aspose.PDF for .NET 針對效能和資源使用進行了最佳化。它甚至可以從大型 PDF 文件中有效地提取影像位置資訊。

#### Q：開發人員如何從理解和利用影像放置資訊中受益？

答：開發人員可以確保 PDF 文件中精確的影像操作、對齊和分析。這些資訊使他們能夠創建用於影像處理、報告和品質保證的應用程式。

#### Q：是否可以自訂程式碼以提取其他與圖像相關的屬性或元資料？

答：當然，可以利用 Aspose.PDF for .NET 提供的適當類別和方法來增強程式碼以提取其他屬性，例如影像類型、色彩空間、壓縮等。

#### Q：本教程中提供的結論有何意義？

答：結論總結了教程的內容，並鼓勵進一步探索 Aspose.PDF for .NET，以利用其圖像放置之外的功能，為各種 PDF 相關任務打開大門。