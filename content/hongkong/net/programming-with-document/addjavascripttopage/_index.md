---
title: 將 Java 腳本新增至 PDF 文件
linktitle: 新增 Java 腳本 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將 JavaScript 新增至 PDF 檔案。包含文件和頁面層級腳本編寫程式碼教學的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document/addjavascripttopage/
---
要將 JavaScript 新增至 PDF 文件，我們將使用 Aspose.PDF for .NET。該庫提供了一種在 .NET 應用程式中處理 PDF 文件的簡單而有效的方法。以下步驟將引導您完成使用 Aspose.PDF for .NET 將 JavaScript 新增至 PDF 檔案的過程。

## 第 1 步：載入 PDF 文件

第一步是載入要新增 JavaScript 的 PDF 檔案。您可以使用`Document`Aspose.PDF for .NET 提供的類別。這`Document`類別提供載入、儲存和操作 PDF 檔案的方法。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 第 2 步：在文件層級新增 JavaScript

要在文件層級新增 JavaScript，我們將使用`JavascriptAction`Aspose.PDF for .NET 提供的類別。此類別可讓您指定要新增至 PDF 檔案的 JavaScript 語句。

```csharp
//在文件層級新增 JavaScript
//使用所需的 JavaScript 語句實例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//將 JavascriptAction 物件指派給文件所需的操作
doc.OpenAction = javaScript;
```

在本教學中，我們將新增一條 JavaScript 語句，該語句將在開啟文件時使用指定選項列印 PDF 檔案。

## 第 3 步：在頁面層級新增 JavaScript

要在頁面層級新增 JavaScript，我們將使用`JavascriptAction`類和`Actions`由 Aspose.PDF for .NET 提供的屬性。此屬性可讓您指定開啟或關閉頁面時將執行的 JavaScript 語句。

```csharp
//在頁面層級新增 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

在本教程中，我們將新增 JavaScript 語句，以便在開啟或關閉頁面時顯示警報訊息。

## 步驟 4：儲存 PDF 文件

將 JavaScript 新增至 PDF 檔案後，您需要儲存修改後的檔案。您可以使用`Save`提供的方法`Document`班級。

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

此程式碼將修改後的PDF檔案儲存到指定目錄。

### 使用 Aspose.PDF for .NET 新增 Java 腳本到頁面的範例原始碼

```csharp
            
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");

//在文件層級新增 JavaScript
//使用所需的 JavaScript 語句實例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//將 JavascriptAction 物件指派給文件所需的操作
doc.OpenAction = javaScript;

//在頁面層級新增 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## 結論

在本文中，我們解釋如何使用 Aspose.PDF for .NET 在文件層級和頁面層級將 JavaScript 新增至 PDF 檔案。我們提供了逐步說明，並包含每個範例的完整原始程式碼。有了這些知識，您就可以將 JavaScript 添加到 PDF 文件中，並根據您的需求自訂其行為。


### 將 Java 腳本新增至 PDF 檔案的常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中處理 PDF 檔案。它提供了用於建立、修改和操作 PDF 文件的廣泛功能。

#### Q：我可以使用 Aspose.PDF for .NET 將 JavaScript 新增到 PDF 文件嗎？

答：是的，Aspose.PDF for .NET 允許您將 JavaScript 添加到 PDF 文件的文檔級別和頁面級別，從而使您能夠創建動態和互動式 PDF 文件。

#### Q：如何使用 Aspose.PDF for .NET 載入現有 PDF 檔案？

答：您可以使用以下命令載入現有的 PDF 文件`Document`類別及其方法，如逐步指南所示。

#### Q：我可以在 PDF 文件中新增哪些類型的 JavaScript 操作？

答：使用 Aspose.PDF for .NET，您可以新增各種 JavaScript 操作，例如列印、警報訊息、表單欄位操作等。

#### Q：Aspose.PDF for .NET 適合商業項目嗎？

答：是的，Aspose.PDF for .NET 是一個可靠且強大的函式庫，通常用於商業專案中的 PDF 操作和生成任務。

