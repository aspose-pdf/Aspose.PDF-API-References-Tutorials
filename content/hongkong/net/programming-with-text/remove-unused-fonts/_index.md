---
title: 刪除 PDF 檔案中未使用的字體
linktitle: 刪除 PDF 檔案中未使用的字體
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 刪除 PDF 檔案中未使用的字型。
type: docs
weight: 300
url: /zh-hant/net/programming-with-text/remove-unused-fonts/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫刪除 PDF 檔案中未使用的字體。我們將逐步完成載入 PDF、識別和刪除未使用的字體以及使用提供的 C# 原始碼儲存更新的 PDF 的過程。

## 要求

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定 PDF 檔案所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含 PDF 檔案的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入來源 PDF

接下來，我們使用以下命令來載入來源 PDF 文檔`Document`來自 Aspose.PDF 庫的類別。

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 步驟 3：識別並刪除未使用的字體

我們創建一個`TextFragmentAbsorber`對象與`TextEditOptions`參數設定為`TextEditOptions.FontReplace.RemoveUnusedFonts`。此選項可讓我們識別並刪除 PDF 文件中未使用的字體。然後我們迭代所有的`TextFragments`並將字體設定為所需的字體。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 第 4 步：儲存更新後的 PDF

最後，我們將更新的 PDF 文件儲存到指定的輸出檔案中。

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 刪除未使用的字型的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//載入來源 PDF 文件
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	//遍歷所有 TextFragment
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	//儲存更新的文檔
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 結論

在本教學中，您學習如何使用 .NET 的 Aspose.PDF 庫從 PDF 文件中刪除未使用的字體。透過遵循逐步指南並執行提供的 C# 程式碼，您可以載入 PDF、識別和刪除未使用的字體以及儲存更新的 PDF。

### 常見問題解答

#### Q：「刪除 PDF 檔案中未使用的字體」教學的目的為何？

答：「刪除 PDF 檔案中未使用的字體」教學課程介紹如何使用 .NET 的 Aspose.PDF 庫從 PDF 文件中刪除未使用的字體。本教學將引導您完成載入 PDF、識別和刪除未使用的字體以及儲存更新的 PDF 的過程。

#### Q：為什麼我要從 PDF 文件中刪除未使用的字體？

答：從 PDF 文件中刪除未使用的字體有助於減小文件大小並優化文件以獲得更好的效能。這在處理包含文件內容中實際未使用的嵌入字體的 PDF 時特別有用。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含 PDF 檔案所在目錄的路徑。

#### Q：如何使用 Aspose.PDF 庫從 PDF 文件中刪除未使用的字型？

答：本教學將逐步引導您完成整個過程：

1. 使用以下命令開啟 PDF 文檔`Document`班級。
2. 創建一個`TextFragmentAbsorber`對象與`TextEditOptions`設定為`FontReplace.RemoveUnusedFonts`.
3. 接受吸收器以識別並刪除 PDF 中未使用的字體。
4. 遍歷所有`TextFragments`並將字體設定為所需的字體。
5. 儲存更新的 PDF 文件。

####  Q：這樣做的目的是什麼`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

答： 的`TextEditOptions.FontReplace.RemoveUnusedFonts`參數指示`TextFragmentAbsorber`識別並刪除 PDF 文件中未使用的字體。

#### Q：我可以用我選擇的字體替換未使用的字體嗎？

答：是的，您可以修改程式碼，將未使用的字體替換為您選擇的字體。在提供的範例程式碼中，使用字體“Arial, Bold”作為替換。

#### 問：如何`TextFragmentAbsorber` work to remove unused fonts?

答： 的`TextFragmentAbsorber`配置為`TextEditOptions.FontReplace.RemoveUnusedFonts`參數，用於標識 PDF 文字片段中未使用的字體。吸收後，可以迭代`TextFragments`並將其字體設定為所需的替換字體。

#### Q：執行所提供的程式碼的預期結果是什麼？

答：透過遵循教學課程並執行提供的 C# 程式碼，您將從輸入 PDF 文件中刪除未使用的字體，並將更新的版本儲存為輸出 PDF 檔案。

#### Q：我可以修改程式碼以僅從特定頁面或區域刪除字體嗎？

答：提供的程式碼重點是從整個 PDF 文件中刪除未使用的字體。如果您想要針對特定頁面或區域進行字體刪除，則需要修改方法並使用更複雜的邏輯來識別這些區域中未使用的字體。