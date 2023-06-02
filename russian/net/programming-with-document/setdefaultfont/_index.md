---
title: Установить шрифт по умолчанию
linktitle: Установить шрифт по умолчанию
second_title: Aspose.PDF для справочника API .NET
description: Из этого пошагового руководства вы узнаете, как установить шрифт по умолчанию для документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 280
url: /ru/net/programming-with-document/setdefaultfont/
---
Если вы работаете с PDF-документами в .NET, вы можете столкнуться с проблемами, когда шрифт, используемый в PDF-файле, недоступен в системе, в которой он просматривается или печатается. Это может привести к неправильному отображению текста или его отсутствию. Aspose.PDF для .NET предлагает решение этой проблемы, позволяя вам установить шрифт по умолчанию для документа. В этом примере показано, как установить шрифт по умолчанию с помощью Aspose.PDF для .NET.

## Шаг 1: Установите путь к каталогу документов

нам нужно указать путь к каталогу, в котором находится наш PDF-документ. Мы будем хранить этот путь в переменной с именем «dataDir».

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите PDF-документ

 Мы начнем с загрузки существующего документа PDF, в котором отсутствуют шрифты. В этом примере мы предполагаем, что документ PDF находится в каталоге, указанном параметром`dataDir` переменная.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // код идет сюда
}
```

## Шаг 3: Установите шрифт по умолчанию

 Далее мы установим шрифт по умолчанию для документа PDF, используя`PdfSaveOptions` сорт. В этом примере мы установим шрифт по умолчанию «Arial».

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Шаг 4: Сохраните обновленный документ

Наконец, мы сохраним обновленный документ в новый файл. В этом примере мы сохраним обновленный документ в файл с именем «output_out.pdf» в том же каталоге, что и входной файл.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Пример исходного кода для установки шрифта по умолчанию с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузите существующий документ PDF с отсутствующим шрифтом
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Укажите имя шрифта по умолчанию
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```
