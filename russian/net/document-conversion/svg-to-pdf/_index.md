---
title: SVG в PDF
linktitle: SVG в PDF
second_title: Aspose.PDF для справочника API .NET
description: Простое и быстрое преобразование SVG в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 280
url: /ru/net/document-conversion/svg-to-pdf/
---

В этом руководстве вы узнаете, как преобразовать файл SVG в файл PDF с помощью Aspose.PDF для .NET. Aspose.PDF предлагает простое и эффективное решение для преобразования файлов SVG в PDF с сохранением качества содержимого и макета. Выполните следующие шаги, чтобы выполнить это преобразование.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка файла SVG
 Первый шаг — загрузить файл SVG в`Document`объект с помощью опции загрузки SVG (`SvgLoadOptions`). Используйте следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание экземпляра объекта LoadOption с использованием параметра загрузки SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Создать объект документа
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл SVG.

## Шаг 2. Конвертируйте в PDF
 Второй шаг — преобразовать документ SVG в документ PDF с помощью`Save` метод`Document` объект. Используйте следующий код:

```csharp
// Сохраните полученный PDF-документ
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Обязательно укажите желаемый путь и имя файла для полученного PDF-файла.

### Пример исходного кода для SVG в PDF с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создание экземпляра объекта LoadOption с использованием параметра загрузки SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Создать объект документа
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Сохраните полученный PDF-документ
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Заключение
В этом руководстве мы узнали, как преобразовать файл SVG в файл PDF с помощью Aspose.PDF для .NET. Следуя приведенным выше шагам, вы можете легко выполнить это преобразование. Используйте этот метод для преобразования файлов SVG в PDF и наслаждайтесь гибкостью и качеством Aspose.PDF.