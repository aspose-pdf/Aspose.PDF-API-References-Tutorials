---
title: 替換 PDF 檔案中的字體
linktitle: 替換 PDF 檔案中的字體
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 取代 PDF 檔案中的字型。
type: docs
weight: 340
url: /zh-hant/net/programming-with-text/replace-fonts/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫來取代 PDF 檔案中的特定字體。我們將使用提供的 C# 原始程式碼逐步完成載入 PDF 文件、搜尋文字片段、識別要替換的字體、替換字體以及保存修改後的 PDF 的過程。

## 先決條件

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定輸入 PDF 檔案所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含 PDF 檔案的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入 PDF 文檔

接下來，我們使用以下命令載入 PDF 文檔`Document`來自 Aspose.PDF 庫的類別。

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 第 3 步：搜尋和替換字體

我們創建一個`TextFragmentAbsorber`物件並設定編輯選項以刪除未使用的字體。然後，我們接受 PDF 文件所有頁面的吸收器來搜尋文字片段。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## 第 4 步：替換字體

我們遍歷吸收器識別的所有文字片段。如果文字片段的字體名稱與要替換的所需字體相符，我們將其替換為新字體。

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## 第5步：儲存修改後的PDF

最後，我們將修改後的PDF文件儲存到指定的輸出檔。

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 取代字型的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//載入來源 PDF 文件
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	//搜尋文字片段並將編輯選項設定為刪除未使用的字體
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	//接受所有頁面的吸收器
	pdfDocument.Pages.Accept(absorber);
	//遍歷所有TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		//如果字體名稱為 ArialMT，則將字體名稱替換為 Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	//儲存更新的文檔
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫替換 PDF 文件中的特定字體。透過遵循逐步指南並執行提供的 C# 程式碼，您可以載入 PDF 文件、搜尋文字片段、識別和替換特定字體以及儲存修改後的 PDF。

### 常見問題解答

#### Q：「替換 PDF 檔案中的字體」教學的目的是什麼？

答：「替換 PDF 檔案中的字型」教學課程示範如何使用 .NET 的 Aspose.PDF 庫取代 PDF 文件中的特定字型。它提供了有關如何載入 PDF 文件、搜尋文字片段、識別要替換的字體、替換字體以及保存修改後的 PDF 的分步指南。

#### Q：為什麼我要替換 PDF 文件中的字型？

答：當您想要標準化文字的外觀或提高文件在不同裝置和平台之間的相容性時，可能需要取代 PDF 文件中的字型。它允許您確保一致的排版和格式。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含輸入 PDF 檔案所在目錄的路徑。

#### Q：如何替換 PDF 文件中的特定字型？

答：本教學將逐步引導您完成整個過程：

1. 使用載入 PDF 文檔`Document`班級。
2. 創建一個`TextFragmentAbsorber`物件並設定編輯選項以刪除未使用的字體。接受所有頁面的吸收器來搜尋文字片段。
3. 遍歷已辨識的文字片段。如果文字片段的字體名稱與您要替換的字體匹配，請將其替換為新字體。

####  Q：使用的目的是什麼`TextFragmentAbsorber` with font replacement options?

答： 的`TextFragmentAbsorber`透過字體替換選項，您可以找到文字片段並同時刪除未使用的字體。這對於確保替換的字體不會作為附加資源添加到 PDF 中非常重要。

#### Q：如何確定要替換的特定字體？

答：透過遍歷吸收器識別的文字片段，您可以存取每個文字片段的字體資訊。如果字體名稱與您要替換的字體匹配，則可以執行替換。

#### Q：如果在文字片段中找不到要替換的字體，會發生什麼事？

答：如果在文字片段中沒有找到要替換的字體，則該文字片段的字體保持不變。僅當字體名稱匹配時才會發生替換。

#### Q：本教學中替換字體有限制嗎？

答：本教學重點在於替換文字片段中的特定字體。如果您需要替換其他上下文中的字體，例如註釋或表單字段，則需要相應地擴展該方法。

#### Q：執行所提供的程式碼的預期結果是什麼？

答：按照教學課程並執行提供的 C# 程式碼，您將替換 PDF 文件中的特定字體。根據您設定的條件識別的字型將替換為您指定的新字型。

#### Q：我可以使用這種方法來替換整個 PDF 文件中的字體嗎？

答：是的，您可以透過遍歷所有文字片段並應用字體替換邏輯來調整程式碼以替換整個 PDF 文件中的字體。