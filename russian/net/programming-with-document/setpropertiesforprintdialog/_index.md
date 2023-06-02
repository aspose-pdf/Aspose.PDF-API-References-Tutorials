---
title: Установить свойства для диалогового окна печати
linktitle: Установить свойства для диалогового окна печати
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как установить свойства диалогового окна печати в Aspose.PDF для .NET, используя пошаговое руководство.
type: docs
weight: 320
url: /ru/net/programming-with-document/setpropertiesforprintdialog/
---
вот пошаговое руководство по настройке свойств диалогового окна печати с использованием Aspose.PDF для .NET:


## Шаг 1: Определите каталог, в котором находится ваш PDF-документ:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Шаг 2: Создайте новый экземпляр`Document` class:

```csharp
using (Document doc = new Document())
{
  // Код здесь
}
```
   
## Шаг 3: Добавьте новую страницу в документ:

```csharp
doc.Pages.Add();
```
   
##  Шаг 4. Установите для свойства дуплекса значение`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Шаг 5: Сохраните документ с указанным именем файла и форматом:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### Пример исходного кода диалогового окна «Установить свойства для печати» с использованием Aspose.PDF для .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## Заключение

Aspose.PDF for .NET упрощает настройку свойств диалогового окна печати в ваших PDF-файлах. Следуя приведенному выше пошаговому руководству, вы сможете быстро оптимизировать файлы PDF для печати.