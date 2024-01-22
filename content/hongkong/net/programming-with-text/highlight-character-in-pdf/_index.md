---
title: 突出顯示 PDF 文件中的字符
linktitle: 突出顯示 PDF 文件中的字符
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 來反白 PDF 檔案中的字元。
type: docs
weight: 240
url: /zh-hant/net/programming-with-text/highlight-character-in-pdf/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫來反白 PDF 檔案中的字元。我們將使用提供的 C# 原始程式碼逐步完成突出顯示 PDF 中的字元的過程。

## 要求

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定輸入 PDF 檔案所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在裡面`dataDir`變數包含 PDF 檔案的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入 PDF 文檔

接下來，我們使用以下命令加載輸入 PDF 文檔`Aspose.Pdf.Document`班級。

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## 步驟 3：將 PDF 轉換為影像

為了突出顯示字符，我們使用以下命令將 PDF 文件轉換為圖像：`PdfConverter`班級。我們設定轉換的解析度並將影像檢索為`Bitmap`目的。

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## 第四步：突出顯示角色

我們循環遍歷 PDF 文件的每一頁並使用`TextFragmentAbsorber`物件查找頁面中的所有單字。然後，我們迭代文字片段、段落和字符，以使用矩形突出顯示它們。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //設定比例和變換
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     //循環瀏覽頁面
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //尋找頁面中的所有單字
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         //循環遍歷文字片段
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 //突出顯示字符
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 //循環遍歷段
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     //亮點片段
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     //循環遍歷字符
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         //突出顯示字符
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## 第5步：儲存輸出影像

最後，我們將修改後的圖像與突出顯示的字元儲存到指定的輸出檔案中。

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### 使用 Aspose.PDF for .NET 在 PDF 中反白顯示字元的範例原始程式碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				//建立 TextAbsorber 物件來尋找所有單字
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				//取得擷取的文字片段
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				//循環遍歷片段
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫來反白 PDF 文件中的字元。透過遵循逐步指南並執行提供的 C# 程式碼，您可以反白 PDF 中的字元並將輸出儲存為影像。

### 常見問題解答

#### Q：「突出顯示 PDF 文件中的字元」教學的目的是什麼？

答：「反白 PDF 檔案中的字元」教學課程介紹如何使用 .NET 的 Aspose.PDF 庫來反白 PDF 文件中的字元。本教程提供了實現此目的的逐步指南和 C# 原始程式碼。

#### Q：為什麼我要突出顯示 PDF 文件中的字元？

答：突出顯示 PDF 文件中的字元可用於多種目的，例如強調特定內容或使某些文字更加明顯且易於區分。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在裡面`dataDir`變數包含輸入 PDF 檔案所在目錄的路徑。

#### Q：如何載入 PDF 文件並將其轉換為圖像？

答：在教程中，`Aspose.Pdf.Document`類別用於載入輸入 PDF 文件。然後，`PdfConverter`類別用於將 PDF 文件轉換為圖像。設定影像的分辨率，並將影像檢索為`Bitmap`目的。

#### Q：如何突出顯示 PDF 文件影像中的字元？

答：本教學將引導您完成循環瀏覽 PDF 文件的每一頁、使用搜尋引擎尋找單字的過程。`TextFragmentAbsorber`，並迭代文字片段、段落和字元以使用矩形突出顯示它們。

#### Q：我可以自訂突出顯示的字元和片段的外觀嗎？

答：是的，您可以透過修改繪圖操作中使用的顏色和樣式來自訂突出顯示的字元和段的外觀。

#### Q：如何儲存修改後的帶有突出顯示字元的圖像？

答：本教學示範如何使用以下命令將修改後的帶有突出顯示字元的圖像儲存到指定的輸出檔案：`Save`的方法`Bitmap`班級。

#### Q：本教學需要有效的 Aspose 授權嗎？

答：是的，本教學需要有效的 Aspose 許可證才能正常運作。您可以從 Aspose 網站購買完整許可證或取得 30 天的臨時許可證。