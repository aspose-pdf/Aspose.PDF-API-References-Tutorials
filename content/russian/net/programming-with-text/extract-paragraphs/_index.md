---
title: Извлечь абзацы из файла PDF
linktitle: Извлечь абзацы из файла PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как извлекать абзацы из PDF-файла с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-text/extract-paragraphs/
---
Этот урок проведет вас через процесс извлечения абзацев в PDF-файле с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, из которого вы хотите извлечь абзацы, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Откройте PDF-документ.
 Откройте существующий PDF-документ с помощью`Document` конструктор и передача пути к входному PDF-файлу.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 5: Извлечение абзацев
 Создайте экземпляр`ParagraphAbsorber` класс и использовать его`Visit` метод извлечения абзацев из документа.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Шаг 6: Повторите абзацы
Пройдитесь по извлеченным абзацам, чтобы получить доступ к текстовому содержимому. Используйте вложенные циклы для прохода по разделам и строкам внутри каждого абзаца.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Пример исходного кода для извлечения абзацев с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть существующий PDF-файл
Document doc = new Document(dataDir + "input.pdf");
// Создать экземпляр ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Заключение
Вы успешно извлекли абзацы из документа PDF с помощью Aspose.PDF для .NET. Извлеченные абзацы были отображены в окне консоли.

### Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: Цель этого руководства — провести вас через процесс извлечения абзацев из файла PDF с помощью Aspose.PDF для .NET. Сопутствующий исходный код C# предоставляет практические шаги для выполнения этой задачи.

#### В: Какие пространства имен мне следует импортировать?

A: В файле кода, из которого вы собираетесь извлекать абзацы, включите следующие директивы using в начале файла:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### В: Как указать каталог документа?

 A: Найдите линию`string dataDir = "YOUR DOCUMENT DIRECTORY";` в коде и замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как открыть существующий PDF-документ?

 A: На шаге 4 вы откроете существующий PDF-документ с помощью`Document` конструктор и указание пути к входному PDF-файлу.

#### В: Как извлечь абзацы из документа?

 A: Шаг 5 включает создание экземпляра`ParagraphAbsorber` класс и использование его`Visit` метод извлечения абзацев из PDF-документа.

#### В: Как перебрать извлеченные абзацы?

A: Шаг 6 проведет вас через цикл по извлеченным абзацам. Вложенные циклы используются для обхода разделов и строк внутри каждого абзаца, в конечном итоге получая доступ к текстовому содержимому и отображая его.

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы узнали, как извлекать абзацы из документа PDF с помощью Aspose.PDF для .NET. Извлеченные абзацы отображаются в окне консоли, предоставляя вам ценную информацию о структуре содержимого документа.