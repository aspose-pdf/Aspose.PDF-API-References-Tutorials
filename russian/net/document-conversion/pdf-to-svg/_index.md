---
title: PDF в SVG
linktitle: PDF в SVG
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию PDF в SVG с помощью Aspose.PDF для .NET.
type: docs
weight: 180
url: /ru/net/document-conversion/pdf-to-svg/
---

В этом руководстве мы познакомим вас с процессом преобразования PDF в формат SVG с помощью Aspose.PDF для .NET. SVG (Scalable Vector Graphics) — это формат векторного изображения, который помогает поддерживать качество и масштабирование графики. Следуя приведенным ниже инструкциям, вы сможете преобразовать файл PDF в формат SVG.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка PDF-документа
На этом этапе мы загрузим исходный PDF-файл, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите PDF-документ
Document doc = new Document(dataDir + "input.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2: Создание параметров сохранения SVG
После загрузки файла PDF мы создадим экземпляр параметров сохранения SVG. Используйте следующий код:

```csharp
// Создание экземпляра объекта SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Не сжимайте изображение SVG в Zip-архиве.
saveOptions.CompressOutputToZipArchive = false;
```

## Шаг 3: Сохранение полученного файла SVG
Теперь мы собираемся сохранить преобразованный файл PDF в формате SVG. Используйте следующий код:

```csharp
// Сохранить вывод в файлы SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Приведенный выше код сохраняет преобразованный PDF в формат SVG с именем файла`"PDFToSVG_out.svg"`.

### Пример исходного кода для преобразования PDF в SVG с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузить PDF-документ
Document doc = new Document(dataDir + "input.pdf");
// Создать экземпляр объекта SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Не сжимайте изображение SVG в Zip-архив
saveOptions.CompressOutputToZipArchive = false;
// Сохраните результат в файлах SVG.
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла PDF в формат SVG с использованием Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете преобразовать файл PDF в формат SVG. Эта функция полезна, когда вы хотите сохранить качество графики и масштабирование при преобразовании в векторные изображения.