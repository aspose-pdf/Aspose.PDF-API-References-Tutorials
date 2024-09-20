---
title: 刪除 PDF 檔案中未使用的字體
linktitle: 刪除 PDF 檔案中未使用的字體
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 輕鬆從 PDF 檔案中刪除未使用的字型。提高效能並減小檔案大小。
type: docs
weight: 300
url: /zh-hant/net/programming-with-text/remove-unused-fonts/
---
## 介紹

嘿！您是否厭倦了臃腫的 PDF 文件，其中充滿了佔用不必要空間的字體？你並不孤單！管理 PDF 中的字體使用可能很麻煩，尤其是當您希望文件乾淨且有效率時。好消息是，使用 Aspose.PDF for .NET，您可以輕鬆地從 PDF 文件中刪除未使用的字體，從而提高效能並減少檔案大小。在本教程中，我們將逐步完成該過程，以便您可以簡化 PDF 文件管理。

## 先決條件

在我們開始之前，請確保您已進行以下設定以充分利用本教學：

1. 已安裝 Visual Studio：您需要一個開發環境來執行 .NET 程式碼。 Visual Studio（任何版本）都是不錯的選擇。
2.  Aspose.PDF for .NET：請確定您已安裝此程式庫。你可以下載它[這裡](https://releases.aspose.com/pdf/net/).
3. 對 C# 的基本了解：由於我們將在本範例中使用 C#，因此熟悉語言將會派上用場。
4. PDF 檔案：準備好範例 PDF 檔案。您可以建立自己的 PDF 或使用任何現有的 PDF。只要確保它被命名即可`ReplaceTextPage.pdf`並儲存在您的文件目錄中。
5. 有效許可證：雖然您可以使用免費試用版，但建議使用有效許可證以獲得完整的功能。如果您需要臨時許可證，您可以獲得它[這裡](https://purchase.aspose.com/temporary-license/).

## 導入包

現在我們已經具備了先決條件，讓我們將必要的套件匯入到我們的 C# 專案中。這是您需要的：

Aspose.PDF 命名空間：它提供了處理 PDF 檔案的所有基本功能。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

若要匯入這些內容，請將以上行新增至 C# 檔案的頂部。這將授予您存取我們將用來操作 PDF 文件的類別和方法的權限。

## 第 1 步：設定您的專案環境

首先要事第一！您需要在 Visual Studio 中建立一個新的控制台應用程式。請依照下列步驟操作：

- 打開視覺工作室。
- 點選“檔案”>“新建”>“專案”。
- 選擇控制台應用程式 (.NET Framework) 並為其命名（例如，`PdfFontCleaner`）。
- 按一下“建立”。

現在您有一個新項目可以使用！

## 第2步：新增Aspose.PDF庫

接下來，您將把 Aspose.PDF 庫加入您的專案中。您可以透過 NuGet 執行此操作：

1. 在解決方案資源管理器中，以滑鼠右鍵按一下您的專案。
2. 選擇管理 NuGet 套件。
3. 搜尋`Aspose.PDF`並安裝它。

## 第 3 步：載入 PDF 文檔

讓我們載入您要處理的文件。具體做法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY/"; //將此更新為您的路徑
//載入來源 PDF 文件
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

代替`"YOUR DOCUMENT DIRECTORY/"`與儲存 PDF 檔案的實際路徑。此步驟至關重要，因為它允許 Aspose 存取您的 PDF 文件。 

## 第 4 步：設定文字片段吸收器

接下來，我們將設定一個處理器，幫助我們識別並刪除 PDF 中未使用的字體。這是執行此操作的程式碼：

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorber);
```

這行程式碼創建了一個`TextFragmentAbsorber`配置為刪除未使用的字體的物件。透過致電`doc.Pages.Accept(absorber)`，我們告訴 Aspose 瀏覽文件中的所有頁面並識別文字片段。

## 第 5 步：迭代文字片段並替換字體

識別文字片段後，是時候迭代它們並替換任何未使用的字體了。新增此程式碼：

```csharp
//遍歷所有 TextFragment
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

在此循環中，您將更改每個的字體`TextFragment`到“Arial，粗體”。您可以選擇任何適合您需求的字體。這才是真正神奇的地方，因為它確保 PDF 保留乾淨、定義良好的字體。

## 步驟6：儲存更新後的文檔

現在我們已經進行了必要的更改，讓我們儲存更新的 PDF！新增以下程式碼：

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
//儲存更新的文檔
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
```

在這裡，我們建立一個新文件，名為`RemoveUnusedFonts_out.pdf`在同一目錄中。這將為您提供原始 PDF 的備份，同時仍為您提供簡化版本。

## 第7步：處理異常

最後，建立錯誤處理始終是一個好主意。這是一個簡單的 try-catch 區塊來包裝您的程式碼：

```csharp
try
{
    // ……（之前的程式碼）
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30-day temporary license from https://購買.aspose.com。
}
```

這將捕獲過程中發生的任何異常並提供用戶友好的錯誤訊息。告知使用者要求非常重要，例如需要有效的 Aspose 許可證。

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 從 PDF 檔案中刪除未使用的字體。透過執行上述步驟，您可以使 PDF 檔案更精簡、更整潔，確保它們更有效率且使用者友好。不要忘記探索 Aspose.PDF 的其他功能，以進一步增強您的文件處理能力！

## 常見問題解答

### 我可以使用免費版本的 Aspose.PDF 來完成此任務嗎？
是的，您可以使用免費試用版，但建議使用完整授權以獲得最佳效能。

### 如果沒有可用的替代字體，字體會怎麼樣？
如果沒有找到替換字體，文字可能無法正確顯示，因此請務必選擇常用字體。

### 如何獲得臨時許可證？
您可以向以下機構申請臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 刪除未使用的字體會影響文件的外觀嗎？
它可以，這取決於刪除哪些字體以及如何替換文字片段；鼓勵測試。

### 有沒有其他方法可以刪除未使用的字體？
儘管其他程式庫或工具可能提供類似的功能，但 Aspose.PDF for .NET 對於此目的非常有效。