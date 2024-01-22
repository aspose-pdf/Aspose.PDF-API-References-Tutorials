---
title: 新增刪除 Javascript 到 PDF 文檔
linktitle: 新增刪除 Javascript 到文檔
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中新增和刪除 JavaScript。包含文檔層級腳本編寫程式碼教學的逐步指南。
type: docs
weight: 30
url: /zh-hant/net/programming-with-document/addremovejavascripttodoc/
---
若要為 PDF 文件新增和刪除 JavaScript，我們將利用 Aspose.PDF for .NET 程式庫。這個強大的程式庫允許我們在.NET應用程式中操作PDF檔案。請依照以下逐步說明使用 Aspose.PDF for .NET 新增和刪除 JavaScript。

## 第 1 步：建立新的 PDF 文檔

首先建立一個新實例`Document` Aspose.PDF for .NET 提供的類別。這將作為 PDF 文檔，我們將在其中添加 JavaScript。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## 步驟 2：在文件層級新增 JavaScript

若要在文件層級新增 JavaScript，請使用`JavaScript`的財產`Document`班級。將 JavaScript 函數指派給 JavaScript 字典中的鍵。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

在本教程中，我們新增了兩個 JavaScript 函數，`func1`和`func2`，到 PDF 文件。

## 第 3 步：刪除文檔級 JavaScript

要在文件層級刪除 JavaScript，請載入 PDF 文件並訪問`JavaScript`字典。迭代這些鍵並刪除所需的 JavaScript 函數。

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

在本教程中，我們刪除`func1`PDF 文件中的 JavaScript 函數。

## 第 4 步：儲存並驗證更改

儲存修改後的 PDF 文件並驗證變更。

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

此程式碼將保存修改後的 PDF 文件並顯示成功訊息。

### 使用 Aspose.PDF for .NET 從 PDF 文件中新增和刪除 Javascript 的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

//刪除文檔級 JavaScript
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## 結論

在本文中，我們提供了使用 Aspose.PDF for .NET 在 PDF 文件中新增和刪除 JavaScript 的逐步指南。透過遵循說明並利用提供的程式碼教學課程，您可以輕鬆地將 JavaScript 合併到 PDF 文件中，並在需要時將其刪除。 JavaScript 可在 PDF 檔案中實現動態功能和互動性，進而增強使用者體驗。


### 新增刪除 JavaScript 到 PDF 文件的常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在.NET 應用程式中有效地操作 PDF 檔案。它提供了以程式設計方式處理 PDF 文件的廣泛功能。

#### Q：如何使用 Aspose.PDF for .NET 將 JavaScript 新增至 PDF 文件？

答：您可以使用以下命令在文件層級新增 JavaScript`JavaScript`的財產`Document`班級。只需將 JavaScript 函數指派給 JavaScript 字典中的鍵即可。

#### Q：我可以使用 Aspose.PDF for .NET 從 PDF 文件中刪除 JavaScript 嗎？

答：是的，您可以透過存取從 PDF 文件中刪除 JavaScript`JavaScript`字典並刪除所需的 JavaScript 函數。

#### Q：Aspose.PDF for .NET 適合專業專案嗎？

答：當然，Aspose.PDF for .NET 廣泛應用於 PDF 操作和生成任務的專業專案。它提供高性能和可靠的功能。

#### Q：將 JavaScript 加入 PDF 文件有什麼好處？

答：將 JavaScript 新增至 PDF 文件可讓您建立互動式動態 PDF 檔案。您可以實現表單驗證、執行計算並添加各種互動功能來增強使用者體驗。