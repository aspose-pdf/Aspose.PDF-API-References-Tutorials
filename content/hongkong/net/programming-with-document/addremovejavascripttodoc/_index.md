---
title: 新增刪除 Javascript 到 PDF 文檔
linktitle: 新增刪除 Javascript 到文檔
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中新增和刪除 JavaScript。包含文檔層級腳本編寫程式碼教學的逐步指南。
type: docs
weight: 30
url: /zh-hant/net/programming-with-document/addremovejavascripttodoc/
---
## 介紹

在本指南中，我們將介紹如何使用 Aspose.PDF for .NET 將 JavaScript 插入 PDF 檔案以及如何在必要時將其刪除。學完本教學後，您將清楚地了解如何輕鬆操作 PDF 中的 JavaScript。

## 先決條件

在我們深入研究程式碼之前，您需要設定一些內容：

1.  Aspose.PDF for .NET：您需要在專案中安裝 Aspose.PDF for .NET 程式庫。如果您還沒有，請從以下位置取得該庫：[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net/).
2. IDE 或文字編輯器：您可以使用任何與 .NET 相容的 IDE，例如 Visual Studio。
3. 基本 C# 知識：本教學假設您熟悉 C# 並熟悉 PDF 操作。
4. 許可證：確保應用有效的許可證以避免限制。您可以從以下地址取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

## 導入包

要開始使用 Aspose.PDF for .NET，您需要將必要的命名空間匯入到您的專案中。方法如下：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

這兩個命名空間是必不可少的。`Aspose.Pdf`允許您處理 PDF 文檔，同時`System.Collections`將用於處理 JavaScript 鍵。

讓我們將在 PDF 中新增和刪除 JavaScript 的整個過程分解為易於遵循的步驟。

## 步驟 1：初始化一個新的 PDF 文檔

您需要做的第一件事是建立一個新的 PDF 文件。該文件將作為我們添加 JavaScript 的空白畫布。

```csharp
Document doc = new Document();
doc.Pages.Add();
```

在這裡，我們正在初始化一個新的`Document`物件並向其添加空白頁。將此視為 PDF 的基礎。

## 第 2 步：將 JavaScript 新增至 PDF

現在我們有了一個文檔，是時候在其中添加一些 JavaScript 了。 PDF 中的 JavaScript 可用於新增自訂行為，例如警報或表單驗證。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

在此程式碼片段中，我們新增兩個 JavaScript 函數（`func1`和`func2` ) 到 PDF。這些函數可以根據您的需求執行各種任務。在這裡，我們只是呼叫一個佔位符函數`hello()`.

## 第 3 步：使用 JavaScript 儲存 PDF

新增所需的 JavaScript 後，就可以儲存 PDF 了。

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

這會將帶有 JavaScript 的文檔保存在該名稱下`AddJavascript.pdf`在指定目錄中（`dataDir`）。

## 第 4 步：在現有 PDF 中載入並查看 JavaScript

假設您需要檢查或修改現有 PDF 中的 JavaScript 函數。第一步是載入 PDF 檔案並存取 JavaScript 金鑰。

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

我們正在加載現有的`AddJavascript.pdf`並將 JavaScript 鍵儲存在清單中。這`Keys`屬性傳回附加到文件的所有 JavaScript 函數的名稱。

## 第 5 步：顯示 JavaScript 函數

接下來，我們可以迭代 JavaScript 函數來查看文件中可用的內容。

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

這會將每個 JavaScript 函數名稱及其對應的程式碼列印到控制台。如果您想驗證文件中目前有哪些功能，它會很有用。

## 第 6 步：從 PDF 中刪除 JavaScript

現在，假設您要刪除特定的 JavaScript 函數，例如`func1`。您可以按照以下方法執行此操作：

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

這`Remove`方法將 JavaScript 函數的名稱作為參數並將其從文件中刪除。

## 第 7 步：驗證 JavaScript 刪除情況

刪除 JavaScript 後，您可以重新列印剩餘的函數來確認`func1`已成功刪除。

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

程式碼的最後一部分確保一切就緒並且 JavaScript 函數得到正確更新。

## 結論

恭喜！您剛剛學習如何使用 Aspose.PDF for .NET 在 PDF 文件中新增和刪除 JavaScript。這項強大的功能可用於多種任務，從新增動態消息到執行自訂計算或驗證。透過在 PDF 中操作 JavaScript，您可以顯著增強使用者體驗。

## 常見問題解答

### 我可以將多個 JavaScript 函數新增到單一 PDF 中嗎？
絕對地！您可以使用以下命令新增任意數量的 JavaScript 函數`doc.JavaScript`收藏。

### 如果我嘗試刪除不存在的 JavaScript 函數會發生什麼？
如果該函數不存在，則`Remove`方法不會拋出錯誤，但也不會刪除任何內容。

### 是否可以在開啟 PDF 後立即執行 JavaScript？
是的！您可以將 JavaScript 配置為在某些觸發器上執行，例如開啟文件或按一下按鈕。

### 新增到 PDF 後我可以編輯 JavaScript 嗎？
是的，您可以載入現有 PDF、存取其 JavaScript、修改程式碼並再次儲存文件。

### 刪除 JavaScript 是否會影響 PDF 的其餘內容？
不，刪除 JavaScript 只會影響腳本。 PDF 的內容保持不變。