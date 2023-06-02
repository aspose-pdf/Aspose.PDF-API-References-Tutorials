---
title: Получить размеры SVG
linktitle: Получить размеры SVG
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по получению размеров SVG с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/document-conversion/get-svg-dimensions/
---

## Введение
В этом руководстве мы познакомим вас с процессом получения размеров файла SVG с помощью Aspose.PDF для .NET. SVG (Scalable Vector Graphics) — это формат изображения на основе XML, используемый для представления векторной графики. Используя приведенные ниже шаги, вы сможете получить размеры файла SVG и сохранить их в формате PDF.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка файла SVG
На этом этапе мы загрузим файл SVG, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл SVG.

## Шаг 2: Настройка размера страницы
Теперь, когда мы загрузили файл SVG, мы можем настроить размер страницы для размещения содержимого SVG. Используйте следующий код:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Приведенный выше код устанавливает поля страницы равными нулю, позволяя регулировать размер страницы в зависимости от содержимого SVG.

## Шаг 3: Сохранение полученного PDF-файла
После настройки размера страницы мы можем сохранить полученный PDF-документ. Вот последний шаг:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с желаемым каталогом, где вы хотите сохранить выходной файл PDF.
  
### Пример исходного кода для получения размеров SVG с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс получения размеров файла SVG с помощью Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете получить размеры файла SVG и сохранить их в формате PDF. Эта функция может быть полезна, когда вам нужно измерить размеры векторной графики.

