---
title: Удалить неиспользуемые потоки
linktitle: Удалить неиспользуемые потоки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить неиспользуемые потоки из файлов PDF с помощью Aspose.PDF для .NET. Наше пошаговое руководство.
type: docs
weight: 270
url: /ru/net/programming-with-document/removeunusedstreams/
---
В этом примере мы обсудим, как удалить неиспользуемые потоки из документов PDF с помощью Aspose.PDF для .NET. Мы предоставим пошаговое руководство о том, как это сделать, включая полный исходный код с пояснениями.

## Шаг 1: Путь к каталогу документов

Первая строка кода задает путь к каталогу, в котором находится ваш PDF-документ. Обязательно замените «ВАШ КАТАЛОГ ДОКУМЕНТОВ» фактическим путем к каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

Следующая строка кода открывает документ PDF с помощью библиотеки Aspose.PDF для .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 3: Установите параметр RemoveUnusedStreams

Следующим шагом является установка для параметра RemoveUnusedStreams значения true. Это удалит все неиспользуемые потоки из документа PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Шаг 4. Оптимизируйте PDF-документ с помощью OptimizationOptions

Теперь, когда мы установили параметры оптимизации, мы можем оптимизировать PDF-документ, используя следующую строку кода.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Шаг 5: Сохраните обновленный документ

Наконец, мы можем сохранить обновленный документ, используя метод Save класса Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для удаления неиспользуемых потоков с использованием Aspose.PDF для .NET

Ниже приведен пример исходного кода для удаления неиспользуемых потоков с помощью Aspose.PDF для .NET.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Установите параметр RemoveUsedStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
// Оптимизируйте документ PDF с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
```
