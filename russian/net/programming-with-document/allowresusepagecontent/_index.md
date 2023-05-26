---
title: Разрешить повторное использование содержимого страницы
linktitle: Разрешить повторное использование содержимого страницы
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как оптимизировать PDF-файлы, включив функцию «Разрешить повторное использование содержимого страницы» с помощью Aspose.PDF для .NET. Уменьшите размер файла и улучшите производительность.
type: docs
weight: 50
url: /ru/net/programming-with-document/allowresusepagecontent/
---

В этом руководстве мы объясним, как включить функцию «Разрешить повторное использование содержимого страницы» с помощью Aspose.PDF для .NET. Эта функция оптимизирует документ PDF за счет повторного использования содержимого страницы, уменьшения размера файла и повышения производительности. Следуйте пошаговой инструкции ниже:

## Шаг 1. Загрузите PDF-документ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 2. Установите параметр AllowReusePageContent.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Шаг 3. Оптимизируйте PDF-документ

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Шаг 4: Сохраните обновленный документ

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Шаг 5: Проверьте уменьшение размера файла

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Поздравляем! Вы успешно разрешили повторное использование содержимого страницы в документе PDF.

### Пример исходного кода для разрешения повторного использования содержимого страницы с помощью Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Установите параметр AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Оптимизируйте документ PDF с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Сохранить обновленный документ
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Теперь вы можете эффективно оптимизировать свои PDF-документы, разрешив повторное использование содержимого страницы.
