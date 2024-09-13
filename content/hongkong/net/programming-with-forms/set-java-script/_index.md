---
title: 設定Java腳本
linktitle: 設定Java腳本
second_title: Aspose.PDF for .NET API 參考
description: 釋放 Aspose.PDF for .NET 的強大功能。透過我們的逐步指南了解如何在表單欄位上設定 JavaScript。
type: docs
weight: 270
url: /zh-hant/net/programming-with-forms/set-java-script/
---
## 介紹

建立動態和互動式 PDF 可以顯著增強使用者體驗，尤其是在文件中整合表單和欄位時。 Aspose.PDF for .NET 是一個功能強大的函式庫，可以實現這一點。在本文中，我們將深入研究使用 Aspose.PDF 為表單欄位設定 JavaScript，確保您的 PDF 不僅看起來不錯，而且功能也很漂亮。

## 先決條件

在我們開始編碼之前，讓我們確保您擁有順利進行編碼所需的一切：

- Visual Studio（或任何 .NET IDE）：確保已正確安裝並設定它。
  
-  Aspose.PDF Library：您需要該程式庫的最新版本。你可以下載它[這裡](https://releases.aspose.com/pdf/net/).

- C#基礎知識：熟悉C#程式設計將有助於您更好地理解程式碼片段。

-  PDF 檔案：您應該有一個可供測試的 PDF 檔案。在我們的範例中，我們將使用一個名為`SetJavaScript.pdf`.

- 您的文件目錄：了解文件檔案的儲存位置。我們將在程式碼中引用此路徑。

一旦準備好這些先決條件，我們將利用哪些工具？讓我們來探索一下 Aspose.PDF 的功能。

## 導入包

首先，您需要在 C# 專案中包含必要的命名空間。開啟主 C# 檔案並新增以下導入語句：

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

這些命名空間提供對 Aspose.PDF 庫中 PDF 和表單相關功能的存取。

準備好讓您的 PDF 具有互動性了嗎？拿起你的編碼帽，讓我們一步步分解它！

## 第 1 步：定義文檔路徑

首先，我們需要指定 PDF 檔案的位置。這為接下來的一切奠定了基礎。操作方法如下：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與您的 PDF 檔案所在的實際路徑。將此視為設定藏寶圖的座標 - 您需要知道「X」標記位置的位置！

## 第 2 步：載入 PDF 文檔

定義目錄後，我們將載入 PDF 檔案。 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

此行打開您指定的 PDF 文件並準備對其進行操作。 

## 第 3 步：存取表單字段

接下來，我們要存取將套用 JavaScript 的表單欄位。 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

在這裡，我們假設您的 PDF 中有一個名為`textbox1`。如果您沒有具有此名稱的字段，您可以重新命名它或相應地調整代碼。 

## 第 4 步：設定 JavaScript 操作

現在，讓我們為文字方塊添加一些功能！我們將設定在某些事件上觸發的 JavaScript 操作。 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

這是發生的事情：
- OnModifyCharacter：此 JavaScript 函數指定修改字元時欄位的行為方式。在這種情況下，數字後面允許有兩位小數，不帶分隔符號。
- OnFormat：這確保當使用者格式化數字時，它遵循相同的規則。

透過設定這些動作，我們實質上是給了文字框個性——就像教它跳舞一樣！

## 第5步：初始化欄位值

接下來，讓我們透過設定初始值來為文字方塊提供一個起點。 

```csharp
field.Value = "123";
```

此行將「123」設定為文字方塊中的預填值。這就像為表演準備舞台一樣。

## 第6步：儲存修改後的PDF

最後，我們需要在進行所有這些更改後保存文件。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

這將使用您的變更更新原始檔案並將其另存為`Restricted_out.pdf`。將此視為決定了 PDF 的命運 — 一旦保存，它就可以面向全世界了！

## 第7步：確認成功

最後，讓我們檢查一下一切是否順利。 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

運行此訊息將使您確信操作已成功完成，就像在一場精彩的表演後收到觀眾的掌聲一樣。

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功地為 PDF 中的表單欄位設定了 JavaScript。本教學不僅為您提供了增強使用者互動的工具，還使您能夠像專業人士一樣個性化您的文件。無論您使用的是發票、調查或其他互動式 PDF 中的表單，可能性都是無限的。

### 常見問題解答

### 什麼是 Aspose.PDF for .NET？  
Aspose.PDF 是一個旨在在 .NET 應用程式中建立、編輯和操作 PDF 文件的程式庫，提供強大的 PDF 功能。

### 我需要許可證才能使用 Aspose.PDF 嗎？  
雖然可以免費試用，但需要許可證才能不受限制地完全使用。您可以購買許可證[這裡](https://purchase.aspose.com/buy).

### 我可以在其他類型的表單欄位上設定 JavaScript 嗎？  
絕對地！ Aspose.PDF 允許在各種表單欄位（例如複選框、單選按鈕和下拉式清單）上執行 JavaScript 操作。

### 如何獲得 Aspose.PDF 問題的支援？  
您可以透過他們獲得支持[論壇](https://forum.aspose.com/c/pdf/10)如有任何疑問或問題。

### 有沒有一種方法可以在不購買的情況下測試Aspose.PDF？  
是的！ Aspose 提供了一個[免費試用](https://releases.aspose.com/)在購買之前測試圖書館的功能。