---
title: 從 PDF 文件中的欄位取得值
linktitle: 從 PDF 文件中的欄位取得值
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆取得 PDF 文件中表單欄位的值。
type: docs
weight: 140
url: /zh-hant/net/programming-with-forms/get-value-from-field/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 取得表單欄位的值。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：開啟文檔

開啟 PDF 文件：

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## 第 3 步：取得字段

取得所需的表單欄位（在本範例中，我們使用「textbox1」欄位）：

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 第四步：取得欄位值

使用以下命令取得欄位值`Value`財產：

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### 使用 Aspose.PDF for .NET 從欄位取得值的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
//取得一個字段
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//取得欄位值
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 取得表單欄位的值。透過執行下列步驟，您可以使用 Aspose.PDF 輕鬆擷取 PDF 文件中特定表單欄位的值。

### 常見問題解答

#### Q：我可以在不事先知道表單欄位名稱的情況下取得表單欄位的值嗎？

答：不可以，您需要知道表單欄位的名稱或部分名稱才能使用 Aspose.PDF for .NET 取得其值。這`pdfDocument.Form["fieldname"]`語法需要表單欄位的確切名稱或部分名稱才能存取其屬性（包括值）。

#### Q：如果PDF文件中不存在表單欄位怎麼辦？

 A：如果PDF文件中不存在表單域，則`pdfDocument.Form["fieldname"]`語法將返回`null`。透過檢查來處理此類情況非常重要`null`在存取表單欄位的屬性之前以避免異常。

#### Q：如何處理不同類型的表單欄位（例如複選框、單選按鈕）以取得它們的值？

答：要處理不同類型的表單字段，您可以使用 Aspose.PDF for .NET 中提供的適當字段類別。例如，使用`CheckBoxField`使用複選框和`RadioButtonField`使用單選按鈕。一旦獲得正確的欄位對象，您就可以存取其屬性，包括值。

#### Q：我可以一次取得多個表單欄位的值嗎？

答：是的，您可以透過使用循環或 LINQ 查詢迭代表單欄位集合來一次取得多個表單欄位的值。這樣，您就可以透過程式設計方式存取 PDF 文件中每個表單欄位的值。

#### Q：是否可以修改表單欄位的值並將變更儲存回 PDF 文件？

答：是的，您可以使用 Aspose.PDF for .NET 修改表單欄位的值，並將變更儲存回 PDF 文件。更新後`Value`表單欄位的屬性，您可以使用`pdfDocument.Save()`方法將變更儲存到原始 PDF 文件。