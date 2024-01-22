---
title: 在 PDF 檔案中嵌入字體
linktitle: 在 PDF 檔案中嵌入字體
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中嵌入字體。確保您的文件在任何裝置上都能正確顯示。
type: docs
weight: 120
url: /zh-hant/net/programming-with-document/embedfont/
---
在本教學中，我們將討論如何使用 Aspose.PDF for .NET 在 PDF 檔案中嵌入字體。 Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、編輯和操作 PDF 文件。該庫提供了廣泛的處理 PDF 文件的功能，包括添加文字、圖像、表格等。對於想要確保 PDF 文件在不同裝置上正確顯示的開發人員來說，在 PDF 文件中嵌入字體是一個常見要求，無論這些裝置上是否安裝了所需的字體。

## 步驟 1：建立一個新的 C# 控制台應用程式
首先，在 Visual Studio 中建立一個新的 C# 控制台應用程式。您可以將其命名為任何您喜歡的名稱。建立專案後，您需要新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入Aspose.PDF命名空間
在 C# 檔案頂部新增以下程式碼行以匯入 Aspose.PDF 命名空間：

```csharp
using Aspose.Pdf;
```

## 第 3 步：載入現有 PDF 文件
要將字體嵌入到現有 PDF 文件中，您需要使用 Document 類別載入該文件。以下程式碼示範如何載入現有的 PDF 檔案：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：遍歷所有頁面
載入 PDF 文件後，您需要遍歷文件中的所有頁面。對於每個頁面，您需要檢查是否使用了任何字體，如果是，則需要嵌入這些字體。以下程式碼示範如何遍歷 PDF 文件中的所有頁面並嵌入字體：

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            //檢查字體是否已嵌入
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    //檢查 Form 對象
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                //檢查字體是否嵌入
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## 第5步：儲存PDF文檔
將所有字體嵌入 PDF 文件後，您需要儲存文件。以下程式碼示範如何儲存PDF檔案：

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 嵌入字體的範例原始碼

以下是使用 Aspose.PDF for .NET 嵌入字體的完整原始碼。


```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");

//遍歷所有頁面
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			//檢查字體是否已嵌入
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	//檢查 Form 對象
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				//檢查字體是否嵌入
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## 結論 在 PDF 檔案中嵌入字體
在本文中，我們討論如何使用 Aspose.PDF for .NET 在 PDF 檔案中嵌入字體。 Aspose.PDF for .NET 提供了一個簡單易用的 API 來處理 PDF 文檔，包括新增和嵌入字體。在 PDF 檔案中嵌入字體是確保文件在不同裝置上正確顯示的重要步驟，無論這些裝置上是否安裝了所需的字體

### 常見問題解答

#### Q：為什麼在 PDF 檔案中嵌入字體很重要？

答：在 PDF 文件中嵌入字體對於確保文件在不同裝置和系統上正確顯示至關重要。嵌入字體後，它們將成為 PDF 文件的一部分，從而消除了對查看設備上安裝的外部字體的依賴。

#### Q：我可以嵌入 PDF 文件中使用的所有字體嗎？

答：是的，您可以嵌入 PDF 文件中使用的所有字體。 Aspose.PDF for .NET 提供了一種簡單的方法來迭代 PDF 文件中使用的所有字體並嵌入它們，以確保在各種裝置上準確呈現。

#### Q：Aspose.PDF for .NET 是否相容於不同的字體格式？

答：是的，Aspose.PDF for .NET 支援各種字型格式，包括 TrueType、OpenType、Type 1 和 CFF 字型。它可以在 PDF 文件中嵌入字體，無論其格式如何。

#### Q：嵌入字體是否會增加 PDF 文件的文件大小？

答：是的，在 PDF 文件中嵌入字體會增加文件大小，因為字體資料包含在 PDF 文件本身中。但是，這可以確保文件的外觀保持一致，無論查看裝置上的字體是否可用。

#### Q：我可以自訂字體嵌入過程嗎？

答：是的，Aspose.PDF for .NET 可讓您自訂字體嵌入過程。您可以選擇要嵌入的字體、排除特定字體或僅嵌入字體的特定子集以最佳化檔案大小。