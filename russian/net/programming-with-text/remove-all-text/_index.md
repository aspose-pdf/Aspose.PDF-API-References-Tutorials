---
title: Удалить весь текст
linktitle: Удалить весь текст
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить весь текст из документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 280
url: /ru/net/programming-with-text/remove-all-text/
---

В этом руководстве мы объясним, как удалить весь текст из документа PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс открытия PDF-файла, выбора и удаления текста на каждой странице и сохранения измененного PDF-файла с использованием предоставленного исходного кода C#.

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

## Шаг 3. Удалите текст с каждой страницы

 Мы перебираем все страницы документа PDF и используем`OperatorSelector` чтобы выделить весь текст на каждой странице. Затем мы удаляем выделенный текст.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Шаг 4: Сохраните измененный PDF-файл

Наконец, мы сохраняем измененный PDF-документ в указанный выходной файл.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Пример исходного кода для удаления всего текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Перебрать все страницы PDF-документа
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Выделить весь текст на странице
	page.Contents.Accept(operatorSelector);
	// Удалить весь текст
	page.Contents.Delete(operatorSelector.Selected);
}
// Сохраните документ
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Заключение

В этом руководстве вы узнали, как удалить весь текст из документа PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете открыть PDF-файл, выбрать и удалить текст на каждой странице и сохранить измененный PDF-файл.