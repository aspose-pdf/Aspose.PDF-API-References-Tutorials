---
title: 設定Java腳本
linktitle: 設定Java腳本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案的表單欄位中設定 JavaScript。
type: docs
weight: 270
url: /zh-hant/net/programming-with-forms/set-java-script/
---
在本指南中，我們將逐步解釋如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件的表單欄位中定義 JavaScript。我們將向您展示如何配置 JavaScript 操作以在文字欄位上執行特定操作。

## 先決條件

在開始之前，請確保您具備以下條件：

- 您的系統上安裝了 .NET 開發環境。
- 適用於 .NET 的 Aspose.PDF 庫。您可以從Aspose官方網站下載。

## 步驟1：配置文檔目錄

第一步是配置您要處理的 PDF 文件所在的文檔目錄。您可以使用`dataDir`變數來指定目錄路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與文檔目錄的實際路徑。

## 第 2 步：載入輸入 PDF 文件

在此步驟中，我們將使用以下命令載入輸入 PDF 文件`Document`Aspose.PDF 類別。

```csharp
//加載輸入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

確保輸入的 PDF 檔案存在於指定的文件目錄中。

## 第 3 步：存取文字方塊字段

要將 JavaScript 應用於特定文字字段，我們首先需要存取該字段。在此範例中，我們假設文字欄位稱為“textbox1”。使用`doc.Form["textbox1"]`方法取得對應的`TextBoxField`目的。

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

確保輸入 PDF 文件中存在指定的文字欄位。

## 第 4 步：配置 JavaScript 操作

現在我們已經存取了文字字段，我們可以配置與該字段關聯的 JavaScript 操作。在此範例中，我們將使用兩個操作：`OnModifyCharacter`和`OnFormat` 。這些操作將使用定義`JavascriptAction`對象。

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

請務必根據您的需求自訂 JavaScript 操作。

## 步驟5：設定初始欄位值

在儲存產生的 PDF 之前，我們可以為文字欄位設定初始值。在此範例中，我們將為該欄位設定值「123」。

```csharp
field.Value = "123";
```

根據您的需求自訂該值。

## 第 6 步：儲存產生的 PDF

現在我們已經完成了文字欄位和 JavaScript 操作的設置，我們可以使用以下命令保存生成的 PDF：`Save`的方法`Document`班級。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
//儲存生成的 PDF
doc.Save(dataDir);
```

請務必指定產生的 PDF 的完整路徑和檔案名稱。


### 使用 Aspose.PDF for .NET 設定 Java 腳本的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加載輸入 PDF 文件
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
//點後2位數字
//無分隔符
//負風格 = 減號
//沒有貨幣
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
//設定初始欄位值
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
//儲存生成的 PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## 結論

在本指南中，我們學習如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件的表單欄位中設定 JavaScript。透過執行概述的步驟，您可以自訂 JavaScript 操作以在文字欄位上執行各種操作。請隨意進一步探索 Aspose.PDF for .NET 的功能，以擴充處理 PDF 檔案的可能性。


### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 將 JavaScript 新增到其他表單元素（例如複選框和單選按鈕）嗎？

答：是的，Aspose.PDF for .NET 可讓您將 JavaScript 新增至各種表單元素，包括核取方塊、單選按鈕和下拉清單。您可以使用`JavascriptAction`類別來定義不同表單元素的 JavaScript 操作。

#### Q：是否可以在表單欄位中使用 JavaScript 驗證使用者輸入？

答：是的，您可以使用 JavaScript 來驗證表單欄位中的使用者輸入。透過定義 JavaScript 操作，例如`OnBlur`或者`OnKeystroke`對於表單字段，您可以驗證輸入的資料並在必要時顯示錯誤訊息。

#### Q：我可以使用 Aspose.PDF for .NET 執行複雜的 JavaScript 函數嗎？

答：是的，您可以使用 Aspose.PDF for .NET 執行複雜的 JavaScript 函數。您可以靈活地定義自訂 JavaScript 函數並在`JavascriptAction`.

#### Q：Aspose.PDF for .NET 是否支援本教學中提到的 JavaScript 事件？

答：是的，Aspose.PDF for .NET 支援廣泛的 JavaScript 事件，包括`OnMouseEnter`, `OnMouseExit`, `OnMouseDown`， 和`OnMouseUp`等。您可以使用這些事件根據使用者互動觸發 JavaScript 操作。

#### Q：我可以使用 Aspose.PDF for .NET 從現有 PDF 文件中提取 JavaScript 程式碼嗎？

答：Aspose.PDF for .NET 提供了從現有 PDF 文件中提取 JavaScript 程式碼的功能。您可以使用`JavascriptAction`類別和其他相關方法來存取和分析 PDF 表單中的 JavaScript 操作。