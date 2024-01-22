---
title: 展開 PDF 檔案中的書籤
linktitle: 展開 PDF 檔案中的書籤
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆擴充 PDF 檔案中的書籤以改善導航。
type: docs
weight: 50
url: /zh-hant/net/programming-with-bookmarks/expand-bookmarks/
---
預設情況下，展開 PDF 檔案中的書籤將顯示所有開啟的書籤。使用Aspose.PDF for .NET，您可以透過以下原始程式碼輕鬆擴充書籤：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。這是必要的導入指令：

```csharp
using Aspose.Pdf;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要展開其書籤的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 3：開啟 PDF 文檔

現在我們將使用以下程式碼開啟要擴展其書籤的PDF文件：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：設定頁面顯示模式

在這一步驟中，我們將頁面顯示模式設定為預設顯示書籤。我們使用`PageMode`的財產`doc`物件設定所需的頁面模式。這是對應的程式碼：

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 第 5 步：瀏覽書籤並展開它們

現在我們將循環遍歷文件書籤集合中的每個書籤項，並將每個項的開啟狀態設為`true`預設情況下展開它們。這是對應的程式碼：

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 第 6 步：儲存更新的文件

最後，我們使用以下命令儲存更新後的 PDF 文件`Save`的方法`doc`目的。這是對應的程式碼：

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 展開書籤的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document doc = new Document(dataDir + "input.pdf");
//設定頁面檢視模式，即顯示縮圖、全螢幕、顯示附件面板
doc.PageMode = PageMode.UseOutlines;
//遍歷 PDF 檔案輪廓集合中的每個 Ouline 項目
foreach (OutlineItemCollection item in doc.Outlines)
{
	//設定大綱項目的開啟狀態
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
//保存輸出
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## 結論

恭喜！您現在已經有了使用 Aspose.PDF for .NET 開發書籤的逐步指南。您可以使用此程式碼顯示 PDF 文件中的所有預設書籤。

請務必查看官方 Aspose.PDF 文檔，以獲取有關高級書籤操作功能的更多資訊。

### PDF 檔案中展開書籤的常見問題解答

#### Q：PDF 文件中的書籤是什麼？

答：PDF 文件中的書籤是一種導航輔助工具，允許使用者快速跳到文件中的特定部分或頁面。它們提供了存取文件不同部分的便捷方法。

#### Q：為什麼我要在 PDF 文件中展開書籤？

答：展開書籤可以提高使用者體驗，所有書籤預設以展開狀態顯示。這使用戶可以清楚地了解文件的結構，並允許他們輕鬆導航到不同的部分。

#### Q：如何導入 C# 專案所需的庫？

答：要匯入 C# 專案所需的函式庫，請使用下列導入指令：

```csharp
using Aspose.Pdf;
```

此指令可讓您利用 Aspose.PDF for .NET 提供的類別和方法。

#### Q：如何指定文件資料夾的路徑？

 A：在提供的源代碼中，替換`"YOUR DOCUMENT DIRECTORY"`包含您要使用的 PDF 檔案的資料夾的實際路徑。這可確保程式碼可以找到目標 PDF 檔案。

#### Q：如何開啟 PDF 文件以展開其書籤？

答：要開啟 PDF 文件以展開書籤，請使用以下程式碼：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

代替`"input.pdf"`與實際的檔案名稱。

#### Q：如何設定頁面顯示方式預設顯示書籤？

A：若要將頁面顯示模式設定為預設顯示書籤，請使用`PageMode`的財產`doc`目的：

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Q：如何展開PDF文件中的所有書籤？

答：要展開所有書籤，請循環瀏覽文件大綱集合中的每個書籤項目並設定`Open`財產給`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Q：如果書籤有嵌套子書籤會怎樣？

答：如果書籤有嵌套的子書籤，則展開父書籤也會展開其子書籤，從而提供文檔結構的全面視圖。

#### Q：展開書籤後如何儲存更新的PDF檔案？

答：要在展開書籤後儲存更新的 PDF 文件，請使用以下程式碼：

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Q：我可以自訂展開書籤的外觀嗎？

答：雖然本教學預設重點介紹擴充書籤，但您可以使用 Aspose.PDF 的其他功能和屬性自訂書籤的外觀。