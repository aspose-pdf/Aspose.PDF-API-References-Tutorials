---
title: 組合框
linktitle: 組合框
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中輕鬆建立組合框清單。
type: docs
weight: 30
url: /zh-hant/net/programming-with-forms/combo-box/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 建立組合方塊清單。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

首先，確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立文檔對象

建立一個 Document 物件來保存 PDF 表單：

```csharp
Document doc = new Document();
```

## 第 3 步：新增頁面

新增頁面至文件：

```csharp
doc.Pages.Add();
```

## 第 4 步：實例化 ComboBoxField 對象

實例化具有所需尺寸的 ComboBoxField 物件：

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 步驟 5：將選項新增至下拉列表

將所需的選項新增至下拉清單：

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## 步驟 6：將組合方塊清單新增至表單中

將 ComboBoxField 物件新增至文件表單欄位集合：

```csharp
doc.Form.Add(combo);
```

## 步驟7：儲存文檔

儲存 PDF 文件：

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的組合方塊範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//建立文檔對象
	Document doc = new Document();
	//將頁面新增至文檔對象
	doc.Pages.Add();
	//實例化 ComboBox Field 對象
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	//將選項新增至組合框
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	//新增組合框物件以形成文檔物件的欄位集合
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	//儲存 PDF 文件
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 建立組合方塊清單。透過執行以下步驟，您可以使用 Aspose.PDF 輕鬆地將組合框清單新增至 PDF 文件中。

### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 自訂組合框清單的外觀嗎？

答：是的，您可以使用 Aspose.PDF for .NET 自訂組合方塊清單的外觀。您可以設定字體大小、顏色、背景顏色、邊框樣式等屬性，以配合您所需的外觀和感覺。

#### Q：我可以在組合框清單中設定預設選擇的選項嗎？

答：是的，您可以使用 Aspose.PDF for .NET 在組合方塊清單中設定預設選取選項。您可以使用`Selected`的財產`ComboBoxField`物件將一個或多個選項標記為預設選擇。

#### Q：使用者做出選擇後，如何從組合框清單中檢索所選值？

答：您可以使用 Aspose.PDF for .NET 從組合方塊清單中擷取所選值。用戶做出選擇後，您可以訪問`Value`的財產`ComboBoxField`物件來取得選定的值。

#### Q：是否可以將事件處理程序或操作新增至組合框清單？

答：是的，Aspose.PDF for .NET 允許您將事件處理程序或操作新增至組合框清單。您可以關聯 JavaScript 操作，例如`OnValueChanged`，到組合框清單以在使用者選擇選項時執行特定操作。

#### Q：我可以為組合框清單中的選項新增工具提示或說明嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將工具提示或描述新增至組合框清單中的選項。您可以設定`AlternateName`每個選項的屬性，以提供當使用者將滑鼠懸停在選項上時將顯示的工具提示或說明。