---
title: Скрыть номера страниц в оглавлении
linktitle: Скрыть номера страниц в оглавлении
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как скрыть номера страниц в оглавлении с помощью Aspose.PDF для .NET, с помощью этого пошагового руководства.
type: docs
weight: 220
url: /ru/net/programming-with-document/hidepagenumbersintoc/
---
В этой статье мы обсудим реализацию функции Hide Page Numbers In TOC в Aspose.PDF for .NET с использованием C#. Мы начнем с краткого введения в Aspose.PDF for .NET, а затем перейдем к пошаговому руководству по реализации этой функции. 

## Введение в Aspose.PDF для .NET

Aspose.PDF для .NET — это мощный компонент для работы с PDF, позволяющий разработчикам создавать, редактировать и обрабатывать файлы PDF программным способом. Он предоставляет широкий спектр функций и возможностей, упрощающих работу с документами PDF. Aspose.PDF для .NET поддерживает как 32-разрядные, так и 64-разрядные операционные системы и может использоваться с платформами .NET Framework, .NET Core и Xamarin. 

## Что такое функция «Скрыть номера страниц в оглавлении»?

Оглавление (TOC) — это важная часть документа PDF, которая предоставляет пользователям быстрый обзор содержимого. Иногда пользователи могут захотеть скрыть номера страниц в TOC, чтобы сделать его более удобным для пользователя. Aspose.PDF для .NET предоставляет встроенную функцию скрытия номеров страниц в TOC. Эту функцию можно использовать для создания более удобных для пользователя документов PDF. 

## Предпосылки

Для прохождения этого урока вам понадобится следующее:

- Visual Studio 2010 или более поздняя версия
- Aspose.PDF для .NET установлен в вашей системе
- Базовые знания языка программирования C#

## Пошаговое руководство по реализации функции «Скрыть номера страниц в оглавлении»

Чтобы реализовать функцию скрытия номеров страниц в оглавлении с помощью Aspose.PDF для .NET, выполните следующие действия:

## Шаг 1: Создайте новое консольное приложение C# в Visual Studio

Откройте Visual Studio и создайте новое консольное приложение C#.

## Шаг 2: Добавьте ссылку на Aspose.PDF для .NET

Щелкните правой кнопкой мыши папку References в вашем проекте и выберите Add Reference. Перейдите к месту, где установлен Aspose.PDF for .NET в вашей системе, и добавьте ссылку на него.

## Шаг 1: Создайте новый PDF-документ

Создайте новый PDF-документ, используя следующий код:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Шаг 2: Создайте страницу оглавления

Создайте новую страницу для оглавления и добавьте ее в PDF-документ, используя следующий код:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Шаг 3: Добавьте раздел списка в коллекцию разделов документа PDF.

Добавьте раздел списка в коллекцию разделов PDF-документа, используя следующий код:

```csharp
tocPage.TocInfo = tocInfo;
```

## Шаг 4: Определите формат четырехуровневого списка.

Определите формат списка из четырех уровней, задав левые поля и параметры формата текста каждого уровня, используя следующий код:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Шаг 5: Добавьте четыре заголовка в раздел

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Пример исходного кода для скрытия номеров страниц в оглавлении с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Добавить раздел списка в коллекцию разделов документа PDF.
tocPage.TocInfo = tocInfo;
//Определите формат списка из четырех уровней, установив левые поля и
//настройки текстового формата каждого уровня

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Добавить четыре заголовка в раздел
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Заключение

В этом уроке мы изучили, как работать с метаданными XMP в документе PDF с помощью Aspose.PDF для .NET. Метаданные XMP предоставляют ценную информацию о документе PDF, включая его название, автора, дату создания и многое другое. Aspose.PDF для .NET позволяет разработчикам получать доступ к этим метаданным и управлять ими, предоставляя гибкий и мощный API для работы с документами PDF.

### Часто задаваемые вопросы

#### В: Что такое метаданные XMP в документе PDF?

A: Метаданные XMP (Extensible Metadata Platform) в документе PDF — это стандартный формат для хранения метаданных о документе. Он включает такие данные, как название документа, автора, дату создания, ключевые слова и многое другое. Метаданные XMP предоставляют структурированный и стандартизированный способ хранения и распространения информации о документе PDF.

#### В: Могу ли я изменить метаданные XMP документа PDF с помощью Aspose.PDF для .NET?

 A: Да, вы можете программно изменять метаданные XMP документа PDF с помощью Aspose.PDF для .NET. Вы можете получить доступ к`Info` собственность`Document` объект, который дает вам доступ к свойствам метаданных XMP. Затем вы можете обновить значения этих свойств, чтобы изменить метаданные XMP документа PDF.

#### В: Можно ли извлечь пользовательские свойства метаданных XMP из документа PDF с помощью Aspose.PDF для .NET?

 A: Да, вы можете извлечь пользовательские свойства метаданных XMP из документа PDF с помощью Aspose.PDF для .NET. Вы можете использовать`Metadata` собственность`Document`объект, который обеспечивает доступ ко всем свойствам метаданных XMP документа PDF. Затем вы можете извлечь пользовательские свойства и использовать их значения по мере необходимости.