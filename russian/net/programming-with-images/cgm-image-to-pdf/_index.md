---
title: Изображение CGM в PDF
linktitle: Изображение CGM в PDF
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте изображение CGM в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-images/cgm-image-to-pdf/
---

В этом пошаговом руководстве объясняется, как преобразовать изображение CGM в PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с путем к каталогу, где находится ваш файл CGM.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Определите входной и выходной файл

 Установите имя входного файла CGM и имя выходного файла PDF. Заменять`"corvette.cgm"` с именем вашего файла CGM и обновите`dataDir`с желаемым выходным каталогом и именем файла PDF.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Шаг 3: Преобразуйте изображение CGM в PDF

 Использовать`Produce` метод`PdfProducer` чтобы преобразовать файл CGM в формат PDF, используя`ImportFormat.Cgm`. Укажите входной файл CGM и выходной файл PDF.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Пример исходного кода для CGMImage в PDF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Сохранить CGM в формате PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Заключение

Поздравляем! Вы успешно преобразовали файл CGM в PDF, используя Aspose.PDF для .NET. Теперь вы можете использовать сгенерированный файл PDF в своих проектах или приложениях.