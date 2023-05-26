---
title: 设置标注属性
linktitle: 设置标注属性
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 设置标注属性。使用标注线、文本颜色和结束样式自定义注释。
type: docs
weight: 130
url: /zh/net/annotations/setcalloutproperty/
---
Aspose.PDF for .NET 是一个强大的库，用于在 C# 中创建、操作和转换 PDF 文档。该库提供的功能之一是能够为 PDF 文档中的自由文本注释设置标注属性。这可以使用`FreeTextAnnotation`类，它允许您创建带有标注的注释。

在本教程中，我们将指导您使用 C# 中的 Aspose.PDF for .NET 为自由文本注释设置标注属性。请按照以下步骤开始。

## 安装适用于 .NET 的 Aspose.PDF

如果您还没有这样做，您将需要[下载](https://releases.aspose.com/pdf/net/)并从 Aspose Releases 或通过 NuGet 包管理器安装 Aspose.PDF for .NET。

## 创建一个新的 PDF 文档

使用创建一个新的 PDF 文档`Document`Aspose.PDF for .NET 提供的类。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 向文档添加新页面

使用`Pages`的集合`Document`班级。

```csharp
Page page = doc.Pages.Add();
```

## 设置默认外观

通过创建一个新的来设置自由文本注释的默认外观`DefaultAppearance`对象并设置其属性，例如`TextColor`和`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## 创建带有标注的自由文本注释

使用标注创建一个新的自由文本注释`FreeTextAnnotation`班级。设置`Intent`财产给`FreeTextIntent.FreeTextCallout`指定这是标注注释。设置`EndingStyle`财产给`LineEnding.OpenArrow`指定标注末尾箭头的样式。设置`Callout`属性数组`Point`表示页面上应绘制标注线的点的对象。

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## 将自由文本注释添加到页面

使用`Annotations`的集合`Page`班级。

```csharp
page.Annotations.Add(fta);
```

## 向注释添加文本

通过设置`RichText`属性为格式化的 XML 字符串。在本教程中，我们将文本颜色设置为红色，将字体大小设置为 9。

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## 8.保存文档

现在使用以下代码保存文档：

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### 使用 Aspose.PDF for .NET 设置标注属性的示例源代码

```csharp

            
            //文档目录的路径。
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            Document doc = new Document();
            Page page = doc.Pages.Add();
            DefaultAppearance da = new DefaultAppearance();
            da.TextColor = System.Drawing.Color.Red;
            da.FontSize = 10;
            FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
            fta.Intent = FreeTextIntent.FreeTextCallout;
            fta.EndingStyle = LineEnding.OpenArrow;
            fta.Callout = new Point[]
            {
                new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
            };
            page.Annotations.Add(fta);
            fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">这是一个示例</span></p></body>";
            doc.Save(dataDir + "SetCalloutProperty.pdf");

            
        
```
