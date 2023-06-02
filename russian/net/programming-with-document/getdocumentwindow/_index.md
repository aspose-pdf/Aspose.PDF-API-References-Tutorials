---
title: Получить окно документа
linktitle: Получить окно документа
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать функцию GetDocumentWindow в Aspose.PDF для .NET для получения информации о свойствах окна PDF-документа.
type: docs
weight: 170
url: /ru/net/programming-with-document/getdocumentwindow/
---

 Aspose.PDF для .NET — это мощная библиотека для работы с PDF, которая позволяет разработчикам создавать, редактировать и преобразовывать PDF-файлы в своих приложениях .NET. Одной из функций, предлагаемых этой библиотекой, является возможность получения информации о свойствах окна документа. Этот учебник проведет вас через этапы использования`GetDocumentWindow` функция Aspose.PDF для .NET для получения информации о свойствах окна документа PDF.

## Шаг 1: Установите Aspose.PDF для .NET

 Чтобы использовать Aspose.PDF для .NET в ваших .NET-приложениях, вы должны сначала установить библиотеку. Вы можете скачать последнюю версию библиотеки с сайта[Страница загрузки Aspose.PDF для .NET](https://releases.aspose.com/pdf/net).

После загрузки библиотеки извлеките содержимое ZIP-файла в папку на своем компьютере. Затем вам нужно будет добавить ссылку на Aspose.PDF для .NET DLL в ваш проект .NET.

## Шаг 2: Загрузите PDF-документ

 После того, как вы установили Aspose.PDF для .NET и добавили ссылку на DLL в свой проект .NET, вы можете начать использовать`GetDocumentWindow` функция для получения информации о свойствах окна документа PDF.

Первым шагом в использовании этой функции является загрузка документа PDF, информацию о котором вы хотите получить. Для этого можно использовать следующий код:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 В приведенном выше коде замените`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором находится ваш PDF-документ. Этот код загрузит документ PDF в`Document` объект, который затем можно использовать для получения информации о свойствах окна документа.

## Шаг 3: Получите свойства окна документа

Чтобы получить информацию о свойствах окна документа PDF, вы можете использовать следующий код:

```csharp
// Получить свойства окна документа
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

В приведенном выше коде каждая строка извлекает разные свойства окна документа PDF и выводит их на консоль. Вы можете настроить этот код для получения только тех свойств, которые вас интересуют.

### Пример исходного кода для получения окна документа из файла PDF с использованием Aspose.PDF для .NET 

 Вот полный исходный код для получения свойств окна PDF-документа с помощью`GetDocumentWindow` особенность Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Получить различные свойства документа
// Положение окна документа - По умолчанию: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// преобладающий порядок чтения; определяет позицию страницы
// При отображении рядом — по умолчанию: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Должна ли строка заголовка окна отображать название документа
// Если false, в строке заголовка отображается имя файла PDF. По умолчанию: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Нужно ли изменять размер окна документа, чтобы он соответствовал размеру
// Первая отображаемая страница — по умолчанию: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Скрывать ли строку меню приложения просмотра — по умолчанию: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Скрывать ли панель инструментов приложения просмотра — по умолчанию: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Следует ли скрывать элементы пользовательского интерфейса, такие как полосы прокрутки
// И оставить только отображаемое содержимое страницы — по умолчанию: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Страничный режим документа. Как отображать документ при выходе из полноэкранного режима.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Макет страницы, т.е. одна страница, один столбец
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Как документ должен отображаться при открытии
// Т.е. показывать эскизы, полноэкранный режим, показывать панель вложений
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```
