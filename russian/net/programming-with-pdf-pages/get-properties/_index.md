---
title: Получить свойства PDF
linktitle: Получить свойства PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по получению свойств PDF, таких как размеры коробки и поворот, с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-pdf-pages/get-properties/
---
В этом руководстве мы пошагово проведем вас через процесс получения свойств PDF с помощью Aspose.PDF для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого урока вы узнаете, как получить доступ к различным свойствам страницы PDF, таким как художественная рамка, рамка обрезки, рамка обрезки и т. д., используя Aspose.PDF для .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#
- Aspose.PDF для .NET, установленный в вашей среде разработки

## Шаг 1: Установите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это расположение файла PDF, свойства которого вы хотите получить. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Откройте PDF-документ
 Далее вам нужно открыть документ PDF с помощью`Document` класс Aspose.PDF. Обязательно укажите правильный путь к файлу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Шаг 3. Получите доступ к коллекции страниц
 Теперь вы можете получить доступ к коллекции страниц документа с помощью`Pages` собственность`pdfDocument` объект.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Шаг 4. Перейдите на определенную страницу
Затем вы можете перейти на определенную страницу, используя индекс страницы в коллекции. В приведенном ниже примере мы обращаемся ко второй странице (индекс 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Шаг 5: Получите свойства страницы
 Теперь вы можете получить различные свойства страницы PDF, такие как художественная рамка, рамка обрезки, рамка обрезки и т. д., используя соответствующие свойства страницы.`pdfPage` объект.

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

### Пример исходного кода для получения свойств с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Получить коллекцию страниц
PageCollection pageCollection = pdfDocument.Pages;
// Получить конкретную страницу
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
Поздравляем! Вы успешно получили свойства PDF, используя Aspose.PDF для .NET. Вы узнали, как открыть документ PDF, перейти к определенной странице и получить различные свойства страницы, такие как поля размеров и поворот. Теперь вы можете использовать эту информацию для настройки обработки файлов PDF в зависимости от их свойств.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для .NET для получения дополнительной информации о расширенных функциях и возможностях настройки.

### Часто задаваемые вопросы

#### В: Как я могу получить свойства PDF-файла, используя Aspose.PDF для .NET?

О: Чтобы получить свойства PDF-файла с помощью Aspose.PDF для .NET, выполните следующие действия:

1. Задайте каталог документа, указав путь к файлу PDF, свойства которого вы хотите получить.
2.  Откройте документ PDF с помощью`Document` класс Aspose.PDF, указав правильный путь к файлу PDF.
3.  Доступ к коллекции страниц документа с помощью`Pages` собственность`pdfDocument` объект.
4. Перейти на определенную страницу, используя индекс страницы в коллекции (индексация начинается с 1).
5.  Получите различные свойства страницы PDF, такие как ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number и Rotation, используя соответствующие свойства`pdfPage` объект.

#### В: Какие различные свойства страницы PDF я могу получить с помощью Aspose.PDF для .NET?

О: С помощью Aspose.PDF для .NET можно получить различные свойства страницы PDF, например:

- ArtBox: представляет размеры обложки страницы.
- BleedBox: представляет размеры выхода за обрез страницы.
- CropBox: представляет размеры видимого содержимого страницы после обрезки.
- MediaBox: представляет размеры физического носителя страницы.
- TrimBox: представляет размеры обрезанного содержимого страницы.
- Rect: представляет размеры ограничивающей рамки страницы.
- Номер страницы: представляет номер страницы в документе.
- Поворот: представляет угол поворота страницы.

#### Вопрос. Как получить доступ к определенной странице документа PDF, чтобы получить ее свойства?

 О: Чтобы получить доступ к определенной странице в документе PDF и получить ее свойства, вы можете использовать`Pages` собственность`pdfDocument` объект для доступа к коллекции страниц документа. Затем вы можете использовать индекс страницы в коллекции, чтобы перейти на нужную страницу. Например, чтобы получить доступ ко второй странице, вы можете использовать`pdfDocument.Pages[1]` (индексация начинается с 1).

#### Вопрос: Могу ли я выполнять операции с извлеченными свойствами, например изменять или изменять размер полей страницы?

О: Да, как только вы получите свойства страницы PDF с помощью Aspose.PDF для .NET, вы сможете выполнять с ними различные операции. Например, вы можете изменить размеры полей страницы, повернуть страницу или использовать полученную информацию для пользовательской обработки и обработки документа PDF.

#### В: Поддерживает ли Aspose.PDF для .NET извлечение свойств из зашифрованных или защищенных паролем PDF-файлов?

О: Да, Aspose.PDF для .NET поддерживает извлечение свойств из зашифрованных или защищенных паролем PDF-файлов. Если вы укажете правильный пароль для открытия документа PDF, вы сможете получить доступ к его свойствам и получить их, используя тот же подход, который продемонстрирован в руководстве.