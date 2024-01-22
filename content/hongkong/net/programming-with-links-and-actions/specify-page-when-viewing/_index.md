---
title: 查看時指定頁面
linktitle: 查看時指定頁面
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 檢視 PDF 時指定頁面。
type: docs
weight: 110
url: /zh-hant/net/programming-with-links-and-actions/specify-page-when-viewing/
---
透過此逐步指南，了解如何在使用 Aspose.PDF for .NET 檢視 PDF 檔案時指定頁面。

## 第一步：建構環境

請確定您已使用 C# 專案和適當的 Aspose.PDF 參考設定開發環境。

## 第 2 步：載入 PDF 文件

使用以下程式碼設定文件的目錄路徑並上傳 PDF 檔案：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//載入 PDF 文件
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 第三步：指定目標頁面

使用以下程式碼取得目標頁面實例：

```csharp
Page page2 = doc.Pages[2];
```

您可以調整索引`[2]`選擇所需的頁面。

## 步驟 4：配置縮放設置

建立一個變數來設定目標頁面縮放係數：

```csharp
double zoom = 1;
```

您可以根據需要調整縮放值。

## 第 5 步：建立導航操作

使用指定的目標頁面建立導航操作的實例：

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 第 6 步：設定目的地

使用座標和縮放設定目的地以前往目標頁面：

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 步驟 7：設定文檔開啟操作

使用建立的導航操作設定文件開啟操作：

```csharp
doc. OpenAction = action;
```

## 步驟 8：儲存更新後的文檔

使用儲存更新的文檔`Save`方法：

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### 使用 Aspose.PDF for .NET 檢視時指定頁面的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//載入 PDF 文件
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
//取得文件第二頁的實例
Page page2 = doc.Pages[2];
//建立變數來設定目標頁面的縮放係數
double zoom = 1;
//建立GoToAction實例
GoToAction action = new GoToAction(doc.Pages[2]);
//轉到第 2 頁
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
//設定文檔開啟動作
doc.OpenAction = action;
//儲存更新的文檔
doc.Save(dataDir + "goto2page_out.pdf");
```

## 結論

恭喜！現在您知道如何使用 Aspose.PDF for .NET 檢視 PDF 時指定頁面。使用這些知識來客製化 PDF 文件中的使用者查看體驗。

現在您已經完成了本指南，您可以將這些概念應用到您自己的專案中，並進一步探索 Aspose.PDF for .NET 提供的功能。

### 常見問題解答 

#### Q：查看PDF檔案時指定目標頁面的作用是什麼？

答：指定目標頁面可讓您控制開啟 PDF 文件時顯示的頁面。這可以透過將使用者引導至感興趣的特定頁面來增強使用者體驗。

#### Q：在 PDF 文件中指定目標頁面有何用處？

答：當您想要引導使用者到達 PDF 文件中的特定部分或內容而不要求他們手動瀏覽頁面時，指定目標頁面非常有用。

#### Q：Aspose.PDF for .NET 如何方便指定要查看的目標頁面？

答：Aspose.PDF for .NET 提供的 API 可讓您設定 PDF 文件的初始視圖，包括目標頁面、縮放等級和其他顯示屬性。

#### Q：我可以指定任意頁面作為目標頁面嗎？

答：是的，您可以指定PDF文件中的任意頁面作為檢視的目標頁面。只需使用適當的索引來選擇所需的頁面即可。

#### Q：指定目標頁面時縮放係數有何意義？

答：縮放係數決定開啟 PDF 文件時套用於目標頁面的放大程度。它控制視窗中顯示的內容量。

#### Q：我可以為不同的目標頁面設定不同的縮放係數嗎？

A：是的，您可以透過建立單獨的目標頁面來為不同的目標頁面設定不同的縮放係數`GoToAction`實例並相應地配置它們的目的地。

#### Q：指定目標頁面有什麼限制嗎？

答：指定目標頁面僅限於控制 PDF 開啟時的初始視圖。顯示 PDF 後，它不會影響使用者互動或導航。

#### Q：我可以使用此功能在 PDF 文件中建立簡報嗎？

答：是的，您可以使用此功能在 PDF 文件中建立類似簡報的體驗，引導使用者瀏覽不同的部分或主題。

#### Q：我可以自訂初始視圖的其他方面，例如頁面佈局嗎？

答：是的，Aspose.PDF for .NET 提供了自訂初始視圖其他方面的屬性，包括頁面佈局、頁面模式等。

#### Q：如何測試指定的目標頁面和縮放係數是否如預期般運作？

答：套用提供的程式碼指定目標頁面和縮放係數後，開啟修改後的 PDF 檔案並驗證它是否以正確的頁面和縮放等級開啟。