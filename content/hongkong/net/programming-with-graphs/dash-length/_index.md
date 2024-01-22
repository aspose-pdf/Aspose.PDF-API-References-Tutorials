---
title: 短劃線長度
linktitle: 短劃線長度
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 設定破折號的長度。自訂破折號圖案的逐步指南。
type: docs
weight: 70
url: /zh-hant/net/programming-with-graphs/dash-length/
---
在本教學中，我們將引導您逐步完成以下 C# 原始碼，以使用 Aspose.PDF for .NET 設定破折號的長度。

在開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也具備 C# 程式設計的基礎知識。

## 第 1 步：文檔目錄設置

在提供的原始程式碼中，您需要指定要儲存產生的 PDF 檔案的目錄。將“dataDir”變數變更為所需的目錄。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：實例化文檔物件並新增頁面

我們建立 Document 類別的一個實例並為該文件新增一個頁面。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 3 步：建立圖形物件並將其新增至頁面

我們建立一個具有指定尺寸的 Graph 物件並將其新增至頁面的段落集合中。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## 第 4 步：建立線路物件並配置

我們使用指定的座標建立一個 Line 對象，並配置虛線的顏色和長度。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 第 5 步：將線條新增至圖形對象

我們將線條加入 Graph 物件的形狀集合。

```csharp
canvas.Shapes.Add(line);
```

## 第 6 步：儲存生成的 PDF 文件

最後，我們將產生的 PDF 檔案以名稱「DashLength_out.pdf」保存在指定目錄中。

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### 使用 Aspose.PDF for .NET 的 Dash Length 範例原始碼 

```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文件實例
Document doc = new Document();
//將頁面新增到 Document 物件的頁面集合中
Page page = doc.Pages.Add();
//建立具有特定尺寸的繪圖對象
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//將繪圖物件加入到頁面實例的段落集合中
page.Paragraphs.Add(canvas);
//建立線對象
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//設定線條物件的顏色
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
//為線物件指定虛線數組
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
//設定 Line 實例的破折號相位
line.GraphInfo.DashPhase = 1;
//將線條新增至繪圖物件的形狀集合中
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## 結論

在本教學中，我們說明如何使用 Aspose.PDF for .NET 設定破折號的長度。現在，您可以利用這些知識在 PDF 檔案中建立具有自訂虛線圖案的線條。

## 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學的目的是引導您完成使用 Aspose.PDF for .NET 設定線條破折號長度的過程。您將學習如何在 PDF 文件中使用自訂虛線圖案建立線條。

#### Q：開始之前需要什麼先決條件？

答：開始之前，請確保您已經安裝了 Aspose.PDF 庫並設定了開發環境。也建議您對 C# 程式設計有基本的了解。

#### Q：如何指定PDF檔案的保存目錄？

答：修改提供的原始程式碼中的“dataDir”變數以指示要儲存產生的 PDF 檔案的目錄。

#### Q：如何建立具有自訂虛線圖案的線條？

答：本教學示範了建立 Line 物件並使用以下命令配置其顏色、破折號陣列和破折號相位：`GraphInfo`目的。修改這些設定以獲得所需的虛線圖案。

#### Q：我可以自訂線條的顏色嗎？

答：是的，您可以透過設定來自訂線條的顏色`Color`的財產`GraphInfo`與線關聯的物件。

#### Q：設定了破折號長度後如何儲存PDF文件？

答：使用所需的虛線圖案配置 Line 物件後，您可以使用以下命令儲存產生的 PDF 文件：`doc.Save(dataDir + "DashLength_out.pdf");`提供的源代碼中的行。