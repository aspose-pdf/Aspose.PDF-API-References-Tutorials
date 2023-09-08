---
title: Извлекайте шрифты и оптимизируйте PDF-файлы
linktitle: Извлекайте шрифты и оптимизируйте PDF-файлы
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как использовать Aspose.PDF для .NET для извлечения шрифтов из системы и оптимизации PDF-файлов. Пошаговое руководство.
type: docs
weight: 370
url: /ru/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET — это мощная библиотека, предоставляющая широкий спектр функций для работы с PDF-документами. Одна из его функций — извлечение шрифтов из PDF-документа. Это может быть полезно, если вам нужно извлечь шрифты из PDF-документа и использовать их в других приложениях.

мы предоставим пошаговое руководство, объясняющее следующий исходный код C# функции извлечения шрифтов из Aspose.PDF для .NET.

## Шаг 1. Установите путь к каталогу документов.

Прежде чем начать, нам нужно указать путь к каталогу, в котором находится наш PDF-документ. Мы сохраним этот путь в переменной с именем «dataDir».

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Замените «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» фактическим путем к каталогу, в котором находится ваш PDF-документ.

## Шаг 2. Откройте PDF-документ.

 Первый шаг — загрузить PDF-документ, который вы хотите сделать, используйте команду`Document` класс Aspose.PDF для .NET. В следующем фрагменте кода показано, как загрузить PDF-документ:

```csharp
// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 3. Установите параметр UnembedFonts.

 Чтобы извлечь шрифты из PDF-документа, вам необходимо установить`UnembedFonts` возможность`true` . Эта опция доступна в`OptimizationOptions` сорт. В следующем фрагменте кода показано, как установить`UnembedFonts` вариант:

```csharp
// Установите параметр UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Шаг 4. Оптимизируйте PDF-документ

 После установки`UnembedFonts` вариант, вы можете оптимизировать PDF-документ, используя`OptimizeResources` метод`Document` сорт. В следующем фрагменте кода показано, как оптимизировать PDF-документ:

```csharp
// Оптимизация PDF-документа с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Шаг 5. Сохраните обновленный документ

 После оптимизации PDF-документа вы можете сохранить обновленный документ, используя`Save` метод`Document`сорт. В следующем фрагменте кода показано, как сохранить обновленный документ:

```csharp
// Сохранить обновленный документ
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Шаг 6. Получите исходный и уменьшенный размер файла

 Наконец, вы можете получить исходный и уменьшенный размер файла PDF-документа, используя команду`FileInfo` класс System.IO. В следующем фрагменте кода показано, как получить исходный и уменьшенный размер файла:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Пример исходного кода для получения извлеченных шрифтов с использованием Aspose.PDF для .NET

Вот полный пример исходного кода для извлечения шрифтов из PDF-документа с помощью Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Установите параметр UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Оптимизация PDF-документа с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Сохранить обновленный документ
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Заключение

В этом уроке мы продемонстрировали, как использовать Aspose.PDF для .NET для извлечения шрифтов из PDF-документа. Следуя пошаговому руководству, вы сможете легко реализовать эту функцию в своих приложениях C#. Удаление шрифтов может оказаться полезным, если вам нужно работать с извлеченными шрифтами отдельно или обеспечить единообразное использование шрифтов на различных платформах.

## Часто задаваемые вопросы

#### Вопрос: Какова цель извлечения шрифтов из PDF-документа?

О: Извлечение шрифтов из PDF-документа позволяет вам извлечь встроенные шрифты и использовать их в других приложениях. Это может быть полезно для обеспечения единообразного отображения шрифтов и сохранения внешнего вида документа.

#### Вопрос: Как указать путь к каталогу документов в коде C#?

 О: Чтобы указать путь к каталогу документов, замените`"YOUR DOCUMENT DIRECTORY"` в коде с указанием фактического пути к каталогу, в котором находится ваш PDF-документ.

####  Вопрос: Что означает`UnembedFonts` option do, and where is it set?

 А:`UnembedFonts` вариант, доступный в`OptimizationOptions` class, включает или отключает извлечение шрифтов из PDF-документа. Чтобы установить эту опцию`true`, используйте следующий код:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Вопрос: Могу ли я отменить изменения, внесенные в процессе оптимизации?

О: Aspose.PDF для .NET не вносит необратимых изменений в исходный PDF-документ во время оптимизации. Процесс оптимизации выполняется на копии документа, оставляя оригинал нетронутым.

#### Вопрос: Как я могу проверить исходный и уменьшенный размер файла после оптимизации?

О: Вы можете использовать`FileInfo` класс`System.IO` чтобы получить исходный и уменьшенный размер файла. Вот пример фрагмента кода для достижения этой цели:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```