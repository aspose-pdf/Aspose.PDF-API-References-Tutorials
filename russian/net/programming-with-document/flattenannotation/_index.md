---
title: Свести аннотацию
linktitle: Свести аннотацию
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как свести аннотации в документе PDF с помощью Aspose.PDF для .NET. Сохраняйте аннотации и предотвращайте случайное изменение.
type: docs
weight: 150
url: /ru/net/programming-with-document/flattenannotation/
---

Aspose.PDF для .NET — это мощная библиотека, позволяющая разработчикам программно работать с PDF-документами. Одной из функций, которые он предоставляет, является возможность сглаживания аннотаций в документах PDF. Сведение аннотаций в документе PDF означает, что аннотации становятся частью содержимого документа и больше не могут быть отредактированы или удалены. Это полезно, когда вы хотите убедиться, что аннотации сохранены и не могут быть случайно изменены.

В этом руководстве мы обсудим, как использовать Aspose.PDF для .NET для выравнивания аннотаций в документе PDF. Мы предоставим пошаговое руководство о том, как это сделать, а также пример исходного кода.

## Шаг 1. Создайте новое консольное приложение C#
Для начала создайте новое консольное приложение C# в Visual Studio. Вы можете назвать это как угодно. После создания проекта необходимо добавить ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте пространство имен Aspose.PDF
Добавьте следующую строку кода вверху файла C#, чтобы импортировать пространство имен Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Шаг 3: Откройте PDF-документ
Откройте документ PDF, который вы хотите свести:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 4: сгладьте аннотации
Выровняйте аннотации в документе PDF:

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## Шаг 5: Сохраните обновленный документ
Сохраните обновленный документ:

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для Flatten Annotation с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Свести аннотации
foreach (var page in pdfDocument.Pages)
{
	foreach (var annotation in page.Annotations)
	{
		annotation.Flatten();
	}

}
// Сохранить обновленный документ
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом руководстве мы обсудили, как сгладить аннотации в документе PDF с помощью Aspose.PDF для .NET. Сведение аннотаций в PDF-документе — это полезная функция, которая гарантирует, что аннотации будут сохранены и их нельзя будет случайно изменить. Aspose.PDF для .NET предоставляет простой и удобный API для работы с PDF-документами, включая сглаживание аннотаций. 

