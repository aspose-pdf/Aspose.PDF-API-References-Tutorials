---
title: 從 PDF 文件中的所有欄位取得值
linktitle: 從 PDF 文件中的所有欄位取得值
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆取得 PDF 文件中所有表單欄位的值。
type: docs
weight: 150
url: /zh-hant/net/programming-with-forms/get-values-from-all-fields/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 取得 PDF 文件中所有表單欄位的值。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：開啟文檔

開啟 PDF 文件：

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## 步驟 3：取得所有欄位的值

循環遍歷文件中的所有表單欄位並取得它們的名稱和值：

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### 使用 Aspose.PDF for .NET 從所有欄位取得值的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
//從所有欄位獲取值
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 取得 PDF 文件中所有表單欄位的值。透過執行這些步驟，您可以使用 Aspose.PDF 輕鬆地從 PDF 文件中提取所有表單欄位的值。

### 常見問題解答

#### Q：我可以在使用 Aspose.PDF for .NET 檢索表單欄位的值時修改它們嗎？

答：是的，您可以在使用 Aspose.PDF for .NET 檢索表單欄位的同時修改它們的值。一旦你擁有了`Field`代表表單欄位的對象，您可以更新其`Value`具有所需價值的財產。進行必要的變更後，您可以儲存更新的 PDF 文件以反映變更。

#### Q：如何根據類型（例如文字欄位、複選框）篩選和檢索特定表單欄位？

答：若要根據類型檢索特定的表單字段，您可以使用條件語句或 LINQ 查詢來篩選感興趣的欄位。您可以使用欄位的欄位檢查每個表單欄位的類型`FieldType`屬性，然後相應地檢索值。

#### Q：如果 PDF 文件沒有表單欄位會怎樣？

答：如果 PDF 文件不包含任何表單字段，則`pdfDocument.Form`屬性將傳回一個空集合。在這種情況下，檢索值的循環將不會執行，並且不會顯示任何值。

#### Q：我可以按特定順序提取表單欄位值或按字母順序排序嗎？

答：檢索表單欄位的順序取決於 PDF 文件的底層結構。 Aspose.PDF for .NET 依照表單欄位新增至文件的順序傳回表單欄位。如果您想要按特定順序顯示或處理表單字段，您可以根據您的要求實現自訂排序邏輯。

#### Q：如何處理帶有受密碼保護的表單欄位的加密 PDF 文件？

答：Aspose.PDF for .NET 提供了處理加密 PDF 文件和受密碼保護的表單欄位的功能。在載入文件之前，您可以使用以下命令設定密碼`pdfDocument.Password`屬性來存取受保護的 PDF 文件及其表單欄位。