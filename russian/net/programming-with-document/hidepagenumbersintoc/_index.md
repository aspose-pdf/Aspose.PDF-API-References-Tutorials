---
title: Скрыть номера страниц в оглавлении
linktitle: Скрыть номера страниц в оглавлении
second_title: Aspose.PDF для справочника API .NET
description: Из этого пошагового руководства вы узнаете, как скрыть номера страниц в оглавлении с помощью Aspose.PDF для .NET.
type: docs
weight: 220
url: /ru/net/programming-with-document/hidepagenumbersintoc/
---
В этой статье мы обсудим реализацию функции «Скрыть номера страниц в оглавлении» Aspose.PDF для .NET с использованием C#. Мы начнем с краткого введения в Aspose.PDF для .NET, а затем перейдем к пошаговому руководству по реализации этой функции. 

### Оглавление

- Введение в Aspose.PDF для .NET
- Что такое функция «Скрыть номера страниц в оглавлении»?
- Предпосылки
- Пошаговое руководство по реализации функции «Скрыть номера страниц в оглавлении»
- Пример исходного кода для скрытия номеров страниц в оглавлении с использованием Aspose.PDF для .NET
- Заключение

### Введение в Aspose.PDF для .NET

Aspose.PDF для .NET — это мощный компонент для работы с PDF-файлами, который позволяет разработчикам программно создавать, редактировать и манипулировать PDF-файлами. Он предоставляет широкий спектр функций и функций, упрощающих работу с PDF-документами. Aspose.PDF для .NET поддерживает как 32-разрядные, так и 64-разрядные операционные системы и может использоваться с платформами .NET Framework, .NET Core и Xamarin. 

### Что такое функция «Скрыть номера страниц в оглавлении»?

Оглавление (TOC) — это неотъемлемая часть PDF-документа, которая предоставляет пользователям краткий обзор содержимого. Иногда пользователи могут захотеть скрыть номера страниц в оглавлении, чтобы сделать его более удобным для пользователя. Aspose.PDF для .NET предоставляет встроенную функцию для скрытия номеров страниц в оглавлении. Эту функцию можно использовать для создания более удобных PDF-документов. 

### Предпосылки

Чтобы следовать этому руководству, вам понадобится следующее:

- Visual Studio 2010 или более поздняя версия
- Aspose.PDF для .NET, установленный в вашей системе
- Базовые знания языка программирования С#

### Пошаговое руководство по реализации функции «Скрыть номера страниц в оглавлении»

Выполните следующие шаги, чтобы реализовать функцию «Скрыть номера страниц в оглавлении» с помощью Aspose.PDF для .NET:

#### Шаг 1. Создайте новое консольное приложение C# в Visual Studio.

Откройте Visual Studio и создайте новое консольное приложение C#.

#### Шаг 2: Добавьте ссылку на Aspose.PDF для .NET

Щелкните правой кнопкой мыши папку «Ссылки» в вашем проекте и выберите «Добавить ссылку». Перейдите к месту, где в вашей системе установлен Aspose.PDF для .NET, и добавьте ссылку на него.

## Шаг 1. Создайте новый PDF-документ

Создайте новый PDF-документ, используя следующий код:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Шаг 2: Создайте страницу оглавления

Создайте новую страницу для оглавления и добавьте ее в документ PDF, используя следующий код:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Шаг 3: Добавьте раздел списка в коллекцию разделов документа PDF.

Добавьте раздел списка в коллекцию разделов документа PDF, используя следующий код:

```csharp
tocPage.TocInfo = tocInfo;
```

## Шаг 4: Определите формат списка четырех уровней

Определите формат списка четырех уровней, установив левые поля и настройки формата текста каждого уровня, используя следующий код:

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

### Пример исходного кода для сокрытия номеров страниц в оглавлении с использованием Aspose.PDF для .NET

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
	//Добавьте раздел списка в коллекцию разделов документа Pdf.
	tocPage.TocInfo = tocInfo;
	//Определите формат списка четырех уровней, установив левые поля и
	//настройки формата текста каждого уровня

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
	//Добавьте четыре заголовка в раздел
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
