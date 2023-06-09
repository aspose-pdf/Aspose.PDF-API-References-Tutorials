---
title: Удалить весь текст из PDF
linktitle: Удалить весь текст из PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить весь текст из документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 290
url: /ru/net/programming-with-text/remove-all-text-from-pdf/
---

 В этом руководстве мы объясним, как удалить весь текст из документа PDF с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс открытия PDF-файла, используя`TextFragmentAbsorber` для удаления всего текста и сохранения измененного PDF-файла с использованием предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором находятся ваши PDF-файлы. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к вашим файлам PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

 Затем мы открываем документ PDF с помощью`Document` класс из библиотеки Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Шаг 3: Удалить весь текст

 Мы инициализируем`TextFragmentAbsorber` объект и используйте его, чтобы удалить весь поглощенный текст из документа PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Шаг 4: Сохраните измененный PDF-файл

Наконец, мы сохраняем измененный PDF-документ в указанный выходной файл.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Пример исходного кода для удаления всего текста из PDF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Инициировать TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Удалить весь поглощенный текст
absorber.RemoveAllText(pdfDocument);
// Сохраните документ
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Заключение

В этом руководстве вы узнали, как удалить весь текст из документа PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы можете открыть PDF-файл, удалить весь текст с помощью`TextFragmentAbsorber`и сохраните измененный PDF.