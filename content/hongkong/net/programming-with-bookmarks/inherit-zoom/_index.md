---
title: 繼承放大 PDF 文件
linktitle: 繼承放大 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆繼承 PDF 檔案中的書籤縮放。
type: docs
weight: 90
url: /zh-hant/net/programming-with-bookmarks/inherit-zoom/
---
PDF 檔案中的縮放繼承可讓您指定書籤的預設縮放等級。使用Aspose.PDF for .NET，您可以透過以下原始程式碼輕鬆繼承縮放：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。這是必要的導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要繼承縮放的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 3：開啟 PDF 文檔

現在我們將使用以下程式碼開啟要繼承縮放的 PDF 文件：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：取得書籤集合

在此步驟中，我們將使用以下方法來取得文件的書籤或地標的集合`Outlines`的財產`doc`目的。這是對應的程式碼：

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## 第 5 步：設定縮放級別

現在我們將透過建立一個來設定縮放級別`XYZExplicitDestination`具有指定 x、y 和 z 座標的物件。這裡我們使用座標(100, 100, 0)，縮放為2。以下是對應的程式碼：

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## 第 6 步：將縮放等級加入書籤

在此步驟中，我們新增`XYZExplicitDestination`物件作為對書籤的操作`item`收藏。這是對應的程式碼：

```csharp
item. Action = new GoToAction(dest);
```

## 步驟 7：將更新後的書籤加入文件中

最後，我們使用以下命令將更新後的書籤新增至文件的書籤集合中：`Add`的方法`doc.Outlines`目的。這是對應的程式碼：

```csharp
doc. Outlines. Add(item);
```

## 第 8 步：儲存更新的文件

現在讓我們使用以下命令儲存更新後的 PDF 文件`Save`的方法`doc`目的。這是對應的程式碼：

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 繼承縮放的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document doc = new Document(dataDir + "input.pdf");
//取得PDF文件的大綱/書籤集合
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
//將縮放等級設為 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
//新增 XYZExplicitDestination 作為操作來概述 PDF 集合
item.Action = new GoToAction(dest);
//將項目新增至 PDF 檔案的大綱集合
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
//保存輸出
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## 結論

恭喜！現在您有了使用 Aspose.PDF for .NET 繼承 Zoom 的逐步指南。您可以使用此程式碼指定 PDF 文件中書籤的預設縮放等級。

請務必查看官方 Aspose.PDF 文檔，以獲取有關高級書籤操作功能的更多資訊。

### PDF 檔案繼承縮放的常見問題解答

#### Q：什麼是 PDF 檔案中的縮放繼承？

答：縮放繼承是指為 PDF 文件中的書籤指定預設縮放等級的功能。當用戶與書籤互動時，這可以實現一致且用戶友好的導航。

#### Q：為什麼我要繼承書籤的縮放等級？

答：繼承縮放等級可確保使用者在瀏覽 PDF 文件中的書籤時獲得一致的檢視體驗。當您想要為文件的不同部分提供特定視圖時，它會特別有用。

#### Q：如何導入 C# 專案所需的庫？

答：要匯入 C# 專案所需的函式庫，請包含以下導入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

這些指令使您能夠存取處理 PDF 文件和書籤所需的類別和方法。

#### Q：如何指定文件資料夾的路徑？

 A：在提供的源代碼中，替換`"YOUR DOCUMENT DIRECTORY"`包含要繼承縮放等級的 PDF 檔案的資料夾的實際路徑。

#### Q：如何開啟 PDF 文件以繼承縮放等級？

答：要開啟 PDF 文件以繼承縮放級別，請使用以下程式碼：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

代替`"input.pdf"`與實際的檔案名稱。

#### Q：如何設定書籤的縮放等級？

 A：若要設定縮放級別，請建立一個`XYZExplicitDestination`具有所需座標和縮放係數的物件。這是一個例子：

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

這會將座標 (100, 100) 處的縮放等級設為 2。

#### Q：如何將縮放等級加到書籤？

答：新增`XYZExplicitDestination`物件作為書籤集合的操作：

```csharp
item.Action = new GoToAction(dest);
```

在哪裡`item`是一個`OutlineItemCollection`代表一個書籤。

#### Q：如何儲存更新後的 PDF 檔案？

答：使用以下命令儲存更新的 PDF 文件`Save`的方法`doc`目的：

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Q：我可以為不同的書籤自訂縮放等級嗎？

答：是的，您可以透過建立多個書籤來自訂不同書籤的縮放級別`XYZExplicitDestination`具有不同座標和縮放係數的物件。

#### Q：我可以套用縮放繼承的書籤數量有限制嗎？

答：通常，您可以應用縮放繼承的書籤數量沒有嚴格限制。然而，具有過多書籤的非常大的文件可能需要高效的記憶體管理。

#### Q：如何確認縮放繼承已套用？

答：開啟產生的 PDF 檔案以驗證書籤是否繼承了指定的縮放等級。