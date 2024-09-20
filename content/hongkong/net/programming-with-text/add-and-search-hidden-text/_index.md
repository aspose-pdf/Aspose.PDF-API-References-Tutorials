---
title: 新增並蒐索 PDF 文件中的隱藏文本
linktitle: 新增並蒐索 PDF 文件中的隱藏文本
second_title: Aspose.PDF for .NET API 參考
description: 了解使用 Aspose.PDF for .NET 在 PDF 文件中新增和搜尋隱藏文字。包含程式碼範例的分步指南。
type: docs
weight: 20
url: /zh-hant/net/programming-with-text/add-and-search-hidden-text/
---
## 介紹

在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增和搜尋隱藏文字。無論您是經驗豐富的開發人員還是希望提高程式設計技能的新手，本文都將為您提供將隱藏文字功能合併到應用程式所需的見解。

## 先決條件

在深入編碼部分之前，您需要注意一些先決條件：

### 要求清單
- Visual Studio：確保您已安裝 Visual Studio。本教學假設您使用的是 .NET Framework。
-  Aspose.PDF for .NET：您需要擁有 Aspose.PDF for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/pdf/net/).
- C#基礎知識：熟悉C#程式設計將有助於您更好地理解程式碼片段。

## 導入包

在開始使用程式碼之前，您需要確保匯入必要的 Aspose.PDF 命名空間。操作方法如下：

### 設定您的項目
1. 開啟 Visual Studio 並建立一個新的 C# 專案或使用現有專案。
2. 透過新增 NuGet 套件來安裝 Aspose.PDF。您可以透過導航到 NuGet 套件管理器並蒐索`Aspose.PDF`. 
3. 或者，您可以直接從以下位置下載該程式庫[這裡](https://releases.aspose.com/pdf/net/)並將其添加為項目中的參考。

### 導入所需的命名空間
在 C# 檔案的頂部，匯入以下命名空間：

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

此步驟至關重要，因為這些命名空間包含操作 PDF 文件所需的類別和方法。

## 建立帶有隱藏文字的 PDF 文檔

現在您已完成設置，讓我們逐步完成建立包含可見文字和不可見文字的 PDF 文件的步驟。

### 第 1 步：定義文檔目錄
首先，您需要設定 PDF 的儲存路徑。這就是魔法開始的地方！

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //將其變更為您的目錄
```

此行定義產生的 PDF 的儲存位置。別忘了更換`YOUR DOCUMENT DIRECTORY`與你的實際路徑。

### 第 2 步：建立 PDF 文檔
接下來，讓我們建立一個新的 PDF 文件並在其中新增頁面。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

在這裡，我們正在初始化一個新文件並添加一個頁面，我們將在其中放置文字片段。

### 第 3 步：新增可見和隱藏文本
現在我們將向 PDF 添加可見和不可見文字。

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

在這個片段中，`frag1`將是可見的，而`frag2`接下來將被設定為不可見。

### 步驟 4：將文字設定為不可見
使文字`frag2`不可見，你只需修改它`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

透過設定此屬性，與關聯的任何文本`frag2`查看 PDF 時不會呈現。

### 第 5 步：將文字片段新增至頁面
最後，我們將這些文字片段新增至頁面並儲存 PDF。

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

這部分程式碼將我們的文字片段加入到頁面中。之後，我們妥善保存並處理該文件。

## 搜尋 PDF 中的隱藏文本

現在我們已經建立了包含可見文字和隱藏文字的 PDF，那麼我們該如何搜尋隱藏文字呢？讓我們來分解一下。

### 第 1 步：載入 PDF 文檔
要在 PDF 中搜尋文本，我們首先需要載入剛剛建立的文件。

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### 第 2 步：建立文字片段吸收器
我們將使用`TextFragmentAbsorber`擷取 PDF 中的所有文字片段。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

在這裡，我們指定要吸收第一頁中的所有文字片段。

### 第 3 步：迭代片段
現在，我們可以迭代收集的文字片段，找出哪些是可見的，哪些是隱藏的。

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

此循環檢查每個文字片段並列印出其內容及其位置和可見性狀態。如果`fragment.TextState.Invisible`設定為true，表示文字被隱藏！

### 第 4 步：處置文件
最後，請記住在完成後再次處理該文件。

```csharp
doc.Dispose();
```

## 結論

在本教學中，我們示範了使用 Aspose.PDF for .NET 在 PDF 檔案中新增和搜尋隱藏文字的令人興奮的過程。我們學習如何建立包含可見文字和隱藏文字的 PDF 文檔，以及如何以程式設計方式搜尋隱藏文字。無論您需要儲存機密資訊還是在文件中提供獨特的使用者體驗，此功能在各種應用程式中都非常有用。

隨著您越來越熟悉 ASPose.PDF，可能性將變得無窮無盡。不斷嘗試並突破 PDF 文件所能實現的極限！

## 常見問題解答

### Aspose.PDF可以處理加密的PDF檔案嗎？  
是的，Aspose.PDF支援PDF文件的加密和解密。您可以使用密碼輕鬆保護您的 PDF。

### Aspose.PDF 有試用版嗎？  
絕對地！您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).

### Aspose.PDF 支援哪些程式語言？  
Aspose.PDF 提供多種語言的支持，包括 C#、Java 和 Python。

### 在哪裡可以找到 Aspose.PDF 的文件？  
您可以存取文檔[這裡](https://reference.aspose.com/pdf/net/).

### 如果遇到問題，我該如何獲得支援？  
如需支持，您可以造訪 Aspose 論壇[這裡](https://forum.aspose.com/c/pdf/10).