---
title: 使用 Dot Net Regex 搜尋文本
linktitle: 使用 Dot Net Regex 搜尋文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中使用 .NET 正規表示式搜尋文字。
type: docs
weight: 480
url: /zh-hant/net/programming-with-text/search-text-with-dot-net-regex/
---
本教學課程說明如何使用 Aspose.PDF for .NET 在 PDF 文件中使用 .NET 正規表示式搜尋文字。提供的 C# 原始程式碼逐步演示了該過程。

## 先決條件

在繼續學習本教學之前，請確保您具備以下條件：

- C# 程式語言的基礎知識。
- 安裝了 Aspose.PDF for .NET 函式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

## 第 1 步：設定項目

首先在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入必要的命名空間

在 C# 檔案的開頭新增以下 using 指令以匯入所需的命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄路徑

使用以下命令設定文檔目錄的路徑`dataDir`多變的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 步驟 4：建立 .NET Regex 對象

創建一個`.NET Regex`定義搜尋模式的對象：

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

代替`@"[\S]+"`與您想要的正規表示式模式。

## 第 5 步：載入 PDF 文檔

使用載入 PDF 文檔`Document`班級：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

代替`"SearchTextRegex.pdf"`與您的 PDF 檔案的實際名稱。

## 步驟6：取得特定頁面

取得文件所需的頁面：

```csharp
Page page = document.Pages[1];
```

代替`1`與所需的頁碼（從 1 開始的索引）。

## 步驟7：建立一個TextFragmentAbsorber

創建一個`TextFragmentAbsorber`物件尋找輸入正規表示式的所有實例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## 第 8 步：接受頁面的吸收器

接受頁面的吸收器：

```csharp
page.Accept(textFragmentAbsorber);
```

## 步驟9：檢索擷取的文字片段

使用以下命令獲取提取的文字片段`TextFragments`的財產`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 10 步：循環遍歷文字片段

循環檢索到的文字片段並執行所需的操作：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

如果需要，修改循環內的程式碼以對每個文字片段執行進一步的操作。

### 使用 Aspose.PDF for .NET 使用 Dot Net Regex 搜尋文字的範例原始碼 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立 Regex 物件來尋找所有單字
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
//開啟文件
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
//取得特定頁面
Page page = document.Pages[1];
//建立 TextAbsorber 物件以尋找輸入正規表示式的所有實例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
//接受頁面的吸收器
page.Accept(textFragmentAbsorber);
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循環遍歷片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件中使用 .NET 正規表示式搜尋文字。本教程提供了從設定項目到訪問提取的文本片段的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以在 PDF 文件中執行高級文字搜尋。

### 常見問題解答

#### Q：「使用 Dot Net Regex 搜尋文字」教學的目的為何？

答：「使用 Dot Net Regex 搜尋文字」教學課程旨在指導使用者使用 Aspose.PDF .NET 函式庫，使用 .NET 正規表示式在 PDF 文件中搜尋文字。本教程提供逐步說明和 C# 程式碼範例來演示該過程。

#### Q：本教學如何幫助您在 PDF 中使用 .NET 正規表示式搜尋文字？

答：本教學幫助使用者了解如何利用 Aspose.PDF for .NET 的功能在 PDF 文件中使用 .NET 正規表示式搜尋文字。透過遵循提供的步驟和程式碼範例，使用者可以有效地搜尋與其指定的正規表示式相符的文字模式。

#### Q：學習本教程需要滿足哪些先決條件？

答：在開始本教學之前，您應該對 C# 程式語言有基本的了解。此外，您需要安裝 Aspose.PDF for .NET 程式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

#### Q：如何設定我的專案來遵循本教學？

答：首先，在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。這將使您能夠利用庫的功能來搜尋和處理 PDF 文件。

#### Q：我可以使用本教學使用 .NET 正規表示式搜尋任何特定類型的文字嗎？

答：是的，本教學提供如何在 PDF 文件中使用 .NET 正規表示式搜尋文字的說明。您可以自訂`.NET Regex`物件來定義您要使用的特定搜尋模式。

#### Q：如何指定本教學課程中要搜尋的 .NET 正規表示式模式？

答：若要指定要搜尋的 .NET 正規表示式模式，請建立一個`.NET Regex`物件並使用適當的正規表示式語法設定其模式。替換預設值`@"[\S]+"`在教學課程的程式碼中加入您所需的正規表示式。

#### Q：如何檢索擷取的文字片段的屬性？

答：接受後`TextFragmentAbsorber`對於 PDF 的特定頁面，您可以使用以下命令檢索提取的文字片段`TextFragments`吸收體對象的屬性。這提供了對與指定 .NET 正規表示式相符的文字片段集合的存取。

#### Q：我可以自訂程式碼以對每個提取的文字片段執行其他操作嗎？

答：當然可以。本教程的範例程式碼包括一個循環，用於迭代檢索到的文字片段。您可以自訂此循環中的程式碼，以根據您的專案要求對每個提取的文字片段執行其他操作。

#### Q：擷取文字片段後如何儲存修改後的PDF文件？

答：本教學主要著重於使用 .NET 正規表示式搜尋文字並檢索文字片段。如果您打算對 PDF 進行修改，您可以參考其他 Aspose.PDF 文檔，以了解如何根據您的特定需求操作和儲存文檔。