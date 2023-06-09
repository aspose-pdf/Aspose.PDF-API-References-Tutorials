---
title: Добавить слои
linktitle: Добавить слои
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять слои в файлы PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с учебными пособиями по коду для создания и сохранения многоуровневых PDF-файлов.
type: docs
weight: 20
url: /ru/net/programming-with-document/addlayers/
---

Чтобы добавить слои в файл PDF, мы будем использовать Aspose.PDF для .NET. Эта библиотека позволяет нам эффективно работать с файлами PDF в приложениях .NET. Следуйте приведенным ниже пошаговым инструкциям, чтобы добавить слои с помощью Aspose.PDF для .NET.

## Шаг 1: Создайте новый PDF-документ

 Начните с создания нового экземпляра`Document` класс, предоставляемый Aspose.PDF для .NET. Это будет документ PDF, в который мы добавим слои.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Шаг 2: добавьте страницу в документ

Затем добавьте страницу в документ, используя`Add` метод`Pages` коллекция в`Document` сорт.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 3: Создайте и добавьте слои на страницу

 Создание экземпляров`Layer` class для каждого слоя, который вы хотите добавить в файл PDF. Укажите уникальный идентификатор и имя для каждого слоя.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

В этом уроке мы добавили на страницу три слоя с разными цветами и именами.

## Шаг 4: Сохраните файл PDF

 Сохраните измененный файл PDF с помощью`Save` метод`Document` сорт.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Этот код сохранит измененный файл PDF в указанный каталог.

### Пример исходного кода для добавления слоев на страницы PDF с использованием Aspose.PDF для .NET

```csharp            
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Заключение

В этой статье мы предоставили пошаговое руководство по добавлению слоев в файлы PDF с помощью Aspose.PDF для .NET. Следуя инструкциям и используя предоставленные учебные пособия по коду, вы можете легко включать слои в свои документы PDF. Слои позволяют вам организовывать и контролировать видимость контента, обеспечивая более интерактивный и настраиваемый опыт для ваших пользователей.