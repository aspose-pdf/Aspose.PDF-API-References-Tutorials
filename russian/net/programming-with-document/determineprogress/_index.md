---
title: Определить прогресс
linktitle: Определить прогресс
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как определить ход процесса преобразования PDF-документа с помощью Aspose.PDF для .NET с помощью этого пошагового руководства и примера кода.
type: docs
weight: 110
url: /ru/net/programming-with-document/determineprogress/
---

Aspose.PDF для .NET предоставляет функцию, которая позволяет вам определять ход процесса преобразования PDF-документа. В этом руководстве мы предоставим пошаговое руководство по реализации этой функции с помощью C# и Aspose.PDF для .NET.

## Шаг 1: Загрузка PDF-документа

Первый шаг — загрузить документ PDF, который вы хотите преобразовать. Для этого урока мы будем использовать файл «AddTOC.pdf». Замените путь к этому файлу на путь к вашему собственному PDF-документу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## Шаг 2. Настройка пользовательского обработчика прогресса

 Далее нам нужно настроить пользовательский обработчик прогресса, который будет вызываться в процессе преобразования. В этом уроке мы будем использовать`ConversionProgressEventHandler` делегат, предоставленный Aspose.PDF для .NET.

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## Шаг 3: Сохранение PDF-документа

 Наконец, нам нужно сохранить документ PDF, используя`Save()` метод`Document`объект. Мы передадим пользовательский обработчик прогресса, который мы настроили на предыдущем шаге, в качестве параметра.

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## Шаг 4: Реализация обработчика прогресса

 Чтобы реализовать обработчик прогресса, нам нужно определить метод, который принимает один параметр типа`ConversionProgressEventArgs`. Этот метод будет вызываться во время процесса преобразования, чтобы сообщать о ходе преобразования.

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### Пример исходного кода для определения прогресса с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## Заключение

В этом руководстве мы предоставили пошаговое руководство о том, как определить ход процесса преобразования PDF-документа с помощью Aspose.PDF для .NET. Мы также предоставили пример кода, который вы можете использовать в качестве справочного материала при реализации этой функции в своем собственном приложении.