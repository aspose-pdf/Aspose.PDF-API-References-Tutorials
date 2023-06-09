---
title: 自定义制表位
linktitle: 自定义制表位
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中创建自定义制表位。
type: docs
weight: 120
url: /zh/net/programming-with-text/custom-tab-stops/
---

本教程将指导您使用 Aspose.PDF for .NET 在 PDF 文档中创建自定义制表位。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具有以下内容：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- .NET 库的 Aspose.PDF。您可以从 Aspose 官方网站下载它，或者使用像 NuGet 这样的包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入所需的命名空间
在要创建自定义制表位的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：设置文档目录
在代码中，找到显示的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并更换`"YOUR DOCUMENT DIRECTORY"`与存储文档的目录的路径。

## 第 4 步：创建一个新的 Document 实例
实例化一个新的`Document`通过添加以下代码行对象：

```csharp
Document _pdfdocument = new Document();
```

## 第 5 步：向文档添加页面
使用`Add`的方法`Pages`收藏。在提供的代码中，新页面被分配给变量`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## 第 6 步：创建自定义制表位
创建一个`TabStops`对象并向其添加自定义制表位。为每个制表位设置对齐类型和引导符类型。

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## 第 7 步：创建带有制表位的文本片段
创造`TextFragment`对象并将自定义制表位传递给它们。使用特殊字符`#$TAB`指示文本中的制表位。

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## 步骤 8：保存 PDF 文档
使用保存 PDF 文档`Save`的方法`Document`目的。

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 的自定义制表位示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## 结论
您已经使用 Aspose.PDF for .NET 成功创建了带有自定义制表位的 PDF 文档。现在可以在指定的输出文件路径中找到生成的 PDF 文件。