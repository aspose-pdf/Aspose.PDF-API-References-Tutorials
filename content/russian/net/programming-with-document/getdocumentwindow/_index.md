---
title: Окно «Получить документ»
linktitle: Окно «Получить документ»
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как использовать функцию GetDocumentWindow в Aspose.PDF для .NET для получения информации о свойствах окна PDF-документа.
type: docs
weight: 170
url: /ru/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET — это мощная библиотека для работы с PDF-файлами, которая позволяет разработчикам создавать, редактировать и конвертировать PDF-файлы в своих .NET-приложениях. Одной из функций, предлагаемых этой библиотекой, является возможность получения информации о свойствах окна документа. Это руководство проведет вас через этапы использования`GetDocumentWindow` функция Aspose.PDF для .NET для получения информации о свойствах окна PDF-документа.

## Шаг 1. Установите Aspose.PDF для .NET.

 Чтобы использовать Aspose.PDF для .NET в своих приложениях .NET, вам необходимо сначала установить библиотеку. Вы можете скачать последнюю версию библиотеки с сайта[Страница загрузки Aspose.PDF для .NET](https://releases.aspose.com/pdf/net).

Загрузив библиотеку, извлеките содержимое ZIP-файла в папку на своем компьютере. Затем вам нужно будет добавить ссылку на Aspose.PDF for .NET DLL в ваш проект .NET.

## Шаг 2. Загрузите PDF-документ

После того как вы установили Aspose.PDF для .NET и добавили ссылку на DLL в свой проект .NET, вы можете начать использовать`GetDocumentWindow` функция для получения информации о свойствах окна PDF-документа.

Первым шагом в использовании этой функции является загрузка PDF-документа, информацию о котором вы хотите получить. Для этого вы можете использовать следующий код:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 В приведенном выше коде замените`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором находится ваш PDF-документ. Этот код загрузит PDF-документ в`Document` объект, который затем можно использовать для получения информации о свойствах окна документа.

## Шаг 3. Получите свойства окна документа

Чтобы получить информацию о свойствах окна PDF-документа, вы можете использовать следующий код:

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

В приведенном выше коде каждая строка извлекает другое свойство окна PDF-документа и выводит его на консоль. Вы можете настроить этот код так, чтобы он получал только те свойства, которые вас интересуют.

### Пример исходного кода для получения окна документа PDF-файла с использованием Aspose.PDF для .NET 

 Вот полный исходный код для получения свойств окна PDF-документа с помощью`GetDocumentWindow` особенность Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Получить различные свойства документа
// Положение окна документа. По умолчанию: false.
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Преобладающий порядок чтения; определяет положение страницы
// При отображении рядом — по умолчанию: L2R.
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Должна ли строка заголовка окна отображать заголовок документа
// Если значение false, в строке заголовка отображается имя файла PDF. По умолчанию: false.
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Следует ли изменить размер окна документа в соответствии с размером
// Первая отображаемая страница. По умолчанию: false.
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Скрывать ли строку меню приложения просмотра. По умолчанию: false.
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Скрывать ли панель инструментов приложения просмотра. По умолчанию: false.
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Скрывать ли элементы пользовательского интерфейса, такие как полосы прокрутки
// И оставлять отображаемым только содержимое страницы. По умолчанию: false.
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Режим страницы документа. Как отобразить документ при выходе из полноэкранного режима.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Макет страницы, т.е. одна страница, один столбец.
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Как должен отображаться документ при открытии
// Т.е. показывать миниатюры, полноэкранный режим, показывать панель вложений
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Заключение

В этом руководстве мы узнали, как использовать Aspose.PDF для .NET для получения информации о свойствах окна PDF-документа. Загрузив документ PDF и получив доступ к свойствам его окна, вы можете собрать информацию о том, как документ должен отображаться при открытии в приложении просмотра. Aspose.PDF для .NET предоставляет мощный набор функций для программной работы с PDF-файлами, что делает его ценным инструментом для манипулирования PDF-файлами в приложениях .NET.

### Часто задаваемые вопросы

#### Вопрос: Какова цель получения свойств окна PDF-документа?

О: Получение свойств окна PDF-документа позволяет вам собрать информацию о том, как PDF-документ должен отображаться при открытии в приложении просмотра. Эти свойства управляют различными аспектами, такими как положение окна, режим отображения и видимость элементов пользовательского интерфейса.

#### Вопрос: Как мне установить Aspose.PDF для .NET в мой проект .NET?

 О: Чтобы установить Aspose.PDF для .NET, вам необходимо скачать библиотеку с сайта[Страница загрузки Aspose.PDF для .NET](https://releases.aspose.com/pdf/net). После загрузки извлеките содержимое ZIP-файла и добавьте ссылку на Aspose.PDF for .NET DLL в свой проект .NET.

#### Вопрос: Могу ли я настроить код для получения только определенных свойств окна?

О: Да, вы можете настроить код для получения определенных свойств окна, закомментировав ненужные строки. Каждая строка кода соответствует определенному свойству окна, поэтому вы можете включать или исключать свойства в зависимости от ваших требований.

#### Вопрос: Какие типы свойств окна я могу получить с помощью Aspose.PDF для .NET?

О: Используя Aspose.PDF для .NET, вы можете получить различные свойства окна PDF-документа, включая центрирование окна, настройку макета страницы, управление отображением панелей инструментов и строк меню и многое другое.