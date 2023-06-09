---
title: Объединить файлы PDF
linktitle: Объединить файлы PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по объединению файлов PDF с помощью Aspose.PDF для .NET. Легко следовать и внедрять в свои проекты.
type: docs
weight: 20
url: /ru/net/programming-with-pdf-pages/concatenate-pdf-files/
---
В этом руководстве мы пошагово проведем вас через процесс объединения PDF-файлов с помощью Aspose.PDF для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как объединять PDF-файлы с помощью Aspose.PDF для .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#
- Aspose.PDF для .NET, установленный в вашей среде разработки

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Здесь находятся ваши PDF-файлы для объединения. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Откройте PDF-файлы
 Затем вы можете открыть файлы PDF для объединения с помощью`Document` класс Aspose.PDF. Обязательно укажите правильный путь к каждому файлу PDF.

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## Шаг 3. Объедините страницы
 Теперь вы можете добавить страницы из второго документа в первый документ, используя`Add()` способ получения документа`Pages` коллекция. Это объединит страницы обоих документов в один документ.

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## Шаг 4. Сохраните объединенный PDF-файл.
 Наконец, вы можете сохранить объединенный PDF-документ в выходной файл, используя`Save()` метод. Обязательно укажите правильный путь и имя файла.

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### Пример исходного кода для объединения файлов Pdf с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Откройте первый документ
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
// Откройте второй документ
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
// Добавить страницы второго документа к первому
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
// Сохранить объединенный выходной файл
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## Заключение
В этом руководстве мы узнали, как объединять PDF-файлы с помощью Aspose.PDF для .NET. Выполняя шаги, описанные выше, вы можете легко реализовать эту функциональность в своих собственных проектах. Не стесняйтесь дополнительно изучать документацию Aspose.PDF, чтобы узнать о других полезных функциях для работы с файлами PDF.
