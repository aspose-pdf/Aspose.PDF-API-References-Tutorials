---
title: Извлечение шрифтов и оптимизация PDF-файлов
linktitle: Извлечение шрифтов и оптимизация PDF-файлов
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как использовать Aspose.PDF для .NET, чтобы получить Unembed Fonts и оптимизировать PDF-файлы. Пошаговое руководство.
type: docs
weight: 370
url: /ru/net/programming-with-document/unembedfonts/
---
Aspose.PDF для .NET — мощная библиотека, которая предоставляет широкий спектр функций для работы с PDF-документами. Одна из ее функций — извлечение невстроенных шрифтов из PDF-документа. Это может быть полезно, если вам нужно извлечь шрифты из PDF-документа и использовать их в других приложениях.

мы предоставим пошаговое руководство, объясняющее следующий исходный код C# функции получения невстроенных шрифтов Aspose.PDF для .NET.

## Шаг 1: Укажите путь к каталогу документов.

Прежде чем начать, нам нужно задать путь к каталогу, где находится наш PDF-документ. Мы сохраним этот путь в переменной с именем "dataDir".

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу, в котором находится ваш PDF-документ.

## Шаг 2: Откройте PDF-документ.

 Первый шаг — загрузить PDF-документ, который вы хотите сделать, используйте`Document` класс Aspose.PDF для .NET. Следующий фрагмент кода показывает, как загрузить PDF-документ:

```csharp
// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 3: Установите параметр UnembedFonts

 Чтобы получить невстроенные шрифты из документа PDF, вам необходимо установить`UnembedFonts` возможность`true` . Эта опция доступна в`OptimizationOptions` класс. Следующий фрагмент кода показывает, как задать`UnembedFonts` вариант:

```csharp
// Установить опцию UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Шаг 4: Оптимизируйте PDF-документ

 После установки`UnembedFonts` вариант, вы можете оптимизировать PDF-документ с помощью`OptimizeResources` Метод`Document` класс. Следующий фрагмент кода показывает, как оптимизировать PDF-документ:

```csharp
// Оптимизируйте PDF-документ с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Шаг 5: Сохраните обновленный документ.

 После оптимизации PDF-документа вы можете сохранить обновленный документ с помощью`Save` Метод`Document`класс. Следующий фрагмент кода показывает, как сохранить обновленный документ:

```csharp
// Сохранить обновленный документ
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Шаг 6: Получите исходный и уменьшенный размер файла

 Наконец, вы можете получить исходный и уменьшенный размер файла PDF-документа с помощью`FileInfo` класс System.IO. Следующий фрагмент кода показывает, как получить исходный и уменьшенный размер файла:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Пример исходного кода для получения невстроенных шрифтов с помощью Aspose.PDF для .NET

Вот полный пример исходного кода для получения невстроенных шрифтов из PDF-документа с помощью Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Установить опцию UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Оптимизируйте PDF-документ с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Сохранить обновленный документ
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Заключение

В этом уроке мы продемонстрировали, как использовать Aspose.PDF для .NET для получения невстроенных шрифтов из документа PDF. Следуя пошаговому руководству, вы сможете легко реализовать эту функцию в своих приложениях C#. Невстроенные шрифты могут быть полезны, когда вам нужно работать с извлеченными шрифтами по отдельности или обеспечить единообразное использование шрифтов на различных платформах.

## Часто задаваемые вопросы

#### В: Какова цель извлечения шрифтов из PDF-документа?

A: Извлечение шрифтов из документа PDF позволяет извлекать встроенные шрифты и использовать их в других приложениях. Это может быть полезно для обеспечения согласованного отображения шрифтов и сохранения визуального вида документа.

#### В: Как указать путь к каталогу документов в коде C#?

 A: Чтобы указать путь к каталогу документов, замените`"YOUR DOCUMENT DIRECTORY"` в коде фактический путь к каталогу, где находится ваш PDF-документ.

####  В: Что означает`UnembedFonts` option do, and where is it set?

 А:`UnembedFonts` опция, доступная в`OptimizationOptions` класс, включает или отключает извлечение шрифтов из документа PDF. Чтобы установить этот параметр в`true`, используйте следующий код:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### В: Могу ли я отменить изменения, внесенные в процессе оптимизации?

A: Aspose.PDF for .NET не вносит постоянных изменений в исходный PDF-документ во время оптимизации. Процесс оптимизации выполняется на копии документа, оставляя оригинал нетронутым.

#### В: Как проверить исходный и уменьшенный размер файла после оптимизации?

 О: Вы можете использовать`FileInfo` класс`System.IO` чтобы получить исходный и уменьшенный размер файла. Вот пример фрагмента кода для достижения этого:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```