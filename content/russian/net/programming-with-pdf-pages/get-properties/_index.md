---
title: Получить свойства PDF
linktitle: Получить свойства PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Пошаговое руководство по получению свойств PDF-файла, таких как размеры и поворот блока, с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-pdf-pages/get-properties/
---
В этом руководстве мы проведем вас через пошаговый процесс получения свойств PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# и предоставим вам полное руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как получить доступ к различным свойствам страницы PDF, таким как art box, crop box, crop box и т. д., с помощью Aspose.PDF для .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#
- Aspose.PDF для .NET установлен в вашей среде разработки

## Шаг 1: Установите каталог документов
Сначала вам нужно задать путь к каталогу ваших документов. Это местоположение файла PDF, свойства которого вы хотите получить. Замените "ВАШ КАТАЛОГ ДОКУМЕНТОВ" на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Откройте PDF-документ.
 Далее вам необходимо открыть PDF-документ с помощью`Document` класс Aspose.PDF. Обязательно укажите правильный путь к PDF-файлу.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Шаг 3: Получите доступ к коллекции страниц
 Теперь вы можете получить доступ к коллекции страниц документа, используя`Pages` собственность`pdfDocument` объект.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Шаг 4: Перейдите на определенную страницу
Затем вы можете перейти на определенную страницу, используя индекс страницы в коллекции. В примере ниже мы получаем доступ ко второй странице (индекс 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Шаг 5: Получите свойства страницы
 Теперь вы можете получить различные свойства страницы PDF, такие как область изображения, область обрезки, область обрезки и т. д., используя соответствующие свойства`pdfPage` объект.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Пример исходного кода для Get Properties с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Получить коллекцию страниц
PageCollection pageCollection = pdfDocument.Pages;
// Получить определенную страницу
Page pdfPage = pageCollection[1];
// Получить свойства страницы
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Заключение
Поздравляем! Вы успешно получили свойства PDF с помощью Aspose.PDF для .NET. Вы узнали, как открыть документ PDF, перейти на определенную страницу и получить различные свойства страницы, такие как размерные поля и поворот. Теперь вы можете использовать эту информацию для настройки обработки ваших файлов PDF на основе их свойств.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для .NET для получения дополнительной информации о расширенных функциях и возможностях настройки.

### Часто задаваемые вопросы

#### В: Как получить свойства PDF-файла с помощью Aspose.PDF для .NET?

A: Чтобы получить свойства PDF-файла с помощью Aspose.PDF для .NET, выполните следующие действия:

1. Задайте каталог документа, указав путь к PDF-файлу, свойства которого вы хотите получить.
2.  Откройте PDF-документ с помощью`Document` класс Aspose.PDF, предоставляющий правильный путь к PDF-файлу.
3.  Доступ к коллекции страниц документа осуществляется с помощью`Pages` собственность`pdfDocument` объект.
4. Перейти к определенной странице, используя индекс страницы в коллекции (индексация начинается с 1).
5.  Получите различные свойства страницы PDF, такие как ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number и Rotation, используя соответствующие свойства`pdfPage` объект.

#### В: Какие свойства страницы PDF я могу получить с помощью Aspose.PDF для .NET?

A: С помощью Aspose.PDF для .NET можно получить различные свойства страницы PDF, например:

- ArtBox: отображает размеры изображения на странице.
- BleedBox: отображает размеры обреза страницы.
- CropBox: представляет размеры видимого содержимого страницы после обрезки.
- MediaBox: представляет размеры физического носителя страницы.
- TrimBox: представляет размеры обрезанного содержимого страницы.
- Rect: представляет размеры ограничивающей рамки страницы.
- Номер страницы: представляет номер страницы в документе.
- Поворот: представляет угол поворота страницы.

#### В: Как получить доступ к определенной странице PDF-документа, чтобы получить ее свойства?

 A: Чтобы получить доступ к определенной странице в документе PDF и получить ее свойства, вы можете использовать`Pages` собственность`pdfDocument` объект для доступа к коллекции страниц документа. Затем вы можете использовать индекс страницы в коллекции для перехода на нужную страницу. Например, для доступа ко второй странице вы можете использовать`pdfDocument.Pages[1]` (индексация начинается с 1).

#### В: Могу ли я выполнять операции с извлеченными свойствами, например, изменять или изменять размеры полей страницы?

A: Да, как только вы извлечете свойства страницы PDF с помощью Aspose.PDF for .NET, вы сможете выполнять различные операции с ними. Например, вы можете изменять размеры полей страницы, поворачивать страницу или использовать извлеченную информацию для пользовательской обработки и манипуляции документом PDF.

#### В: Поддерживает ли Aspose.PDF для .NET извлечение свойств из зашифрованных или защищенных паролем PDF-файлов?

A: Да, Aspose.PDF for .NET поддерживает извлечение свойств из зашифрованных или защищенных паролем файлов PDF. Если вы предоставите правильный пароль для открытия документа PDF, вы сможете получить доступ и извлечь его свойства, используя тот же подход, который продемонстрирован в руководстве.