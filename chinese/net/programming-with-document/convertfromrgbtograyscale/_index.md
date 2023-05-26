---
title: 从 RGB 转换为灰度
linktitle: 从 RGB 转换为灰度
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将 PDF 从 RGB 转换为灰度。提高打印质量并减小文件大小。
type: docs
weight: 60
url: /zh/net/programming-with-document/convertfromrgbtograyscale/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 将 PDF 文档从 RGB 色彩空间转换为灰度。这种转换可用于各种目的，例如减小文件大小或准备文档以供打印。请按照以下分步指南操作：

## 第 1 步：加载源 PDF 文件

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    //你的代码在这里...
}
```

## 第二步：设置转化策略

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## 第 3 步：将每个页面转换为灰度

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## 第 4 步：保存生成的文件

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

恭喜！您已经使用 Aspose.PDF for .NET 成功地将 PDF 文档从 RGB 转换为灰度。

### 使用 Aspose.PDF for .NET 从 RGB 转换为灰度的示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载源 PDF 文件
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

现在您可以使用 Aspose.PDF for .NET 轻松地将您的 PDF 文档从 RGB 转换为灰度。

