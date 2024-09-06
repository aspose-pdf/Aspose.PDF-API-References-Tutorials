---
title: 按 Tab 鍵順序擷取表單字段
linktitle: 按 Tab 鍵順序擷取表單字段
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 依 Tab 鍵順序擷取表單欄位。
type: docs
weight: 240
url: /zh-hant/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
當使用 Aspose.PDF for .NET 在 C# 中處理 PDF 文件時，您可能會遇到需要以特定 Tab 鍵順序擷取表單欄位的情況。當您想要根據表單欄位的選項卡順序對表單欄位執行操作時，這會很有用。在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 依 Tab 鍵順序擷取表單欄位。

## 要求

在我們開始之前，請確保您具備以下先決條件：

- 您的系統上安裝了 Visual Studio
- 安裝了 Aspose.PDF for .NET 函式庫

現在，讓我們深入了解按 Tab 鍵順序檢索表單欄位的步驟。

## 步驟1：設定文檔目錄

首先，您需要設定 PDF 文件所在的文件目錄。您可以透過指定目錄的路徑來完成此操作`dataDir`多變的。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 步驟2：載入PDF文檔

在此步驟中，我們將使用 Aspose.PDF for .NET 載入 PDF 文件。這`Document`類別提供載入和操作 PDF 文件的能力。

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

這裡，`"Test2.pdf"`是您要載入的 PDF 文件的名稱。確保該文檔存在於指定的文檔目錄中。

## 步驟 3：按 Tab 鍵順序檢索表單字段

要按 Tab 鍵順序檢索表單字段，我們需要訪問`FieldsInTabOrder`的財產`Page`班級。此屬性傳回按選項卡順序排序的表單欄位清單。

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

在上面的程式碼片段中，我們從第二頁（`doc.Pages[1]` ）並迭代每個字段以將其部分名稱連接到`s`多變的。您可以根據您的具體要求修改此程式碼片段。

## 第 4 步：修改 Tab 鍵順序

如果您想要修改表單欄位的 Tab 鍵順序，可以透過存取`TabOrder`每個欄位的屬性並指派新的 Tab 鍵順序值。這是一個例子：

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

在上面的程式碼片段中，我們將新的 Tab 鍵順序值指派給三個表單欄位（`doc.Form[3]`, `doc.Form[1]`， 和`doc.Form[2]`）。根據您的特定要求調整欄位索引和 Tab 鍵順序值。

## 第五步：儲存修改後的文檔

修改表單欄位的 Tab 鍵順序後，您需要儲存修改後的文件。您可以使用`Save`的方法`Document`班級。

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

這裡，`"39522_out.pdf"`是將儲存修改後的文件的輸出檔案的名稱。指定輸出檔案所需的名稱和位置。

### 使用 Aspose.PDF for .NET 依 Tab 鍵順序擷取表單欄位的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 以 Tab 鍵順序擷取表單欄位。我們介紹了載入 PDF 文件、按 Tab 鍵順序檢索表單欄位、修改 Tab 鍵順序以及保存修改後的文件所涉及的步驟。透過執行這些步驟，您可以有效地使用表單欄位並根據您的要求自訂其標籤順序。


### 常見問題解答

#### Q：如何在 C# 程式碼中使用檢索到的表單欄位進行進一步處理？

答：您可以透過存取 C# 程式碼中檢索到的表單欄位的屬性來使用它們，例如`Value`, `Name`, `Rect`等等。

#### Q：我可以按 Tab 鍵順序從 PDF 文件的所有頁面檢索表單欄位嗎？

答：是的，您可以透過迭代每個頁面並存取 PDF 文件的所有頁面來檢索表單欄位。`FieldsInTabOrder`屬性如教程所示。這將為您提供按所有頁面的選項卡順序排序的表單欄位。

#### Q：是否可以按 Tab 鍵順序僅檢索特定類型的表單字段，例如文字欄位或複選框？

答：是的，您可以在按 Tab 鍵順序檢索表單欄位後，根據其類型（例如文字欄位或複選框）過濾表單欄位。您可以使用條件語句來檢查每個表單欄位的類型並進行相應的處理。

#### Q：我可以根據表單欄位的名稱而不是 Tab 鍵順序來檢索表單欄位嗎？

答：是的，您可以使用以下命令根據名稱檢索表單字段`doc.Form`集合並指定欄位名稱作為索引。例如，`doc.Form["fieldName"]`將檢索具有指定名稱的表單欄位。

#### Q：Aspose.PDF for .NET 支援處理加密的 PDF 文件嗎？

答：是的，Aspose.PDF for .NET 提供加密 PDF 文件的支援。您可以使用適當的密碼參數載入和操作加密的 PDF 檔案。