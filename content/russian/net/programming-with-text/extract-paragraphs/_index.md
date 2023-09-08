---
title: Извлечь абзацы из PDF-файла
linktitle: Извлечь абзацы из PDF-файла
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как извлечь абзацы из PDF-файла с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-text/extract-paragraphs/
---
Это руководство проведет вас через процесс извлечения абзацев из PDF-файла с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файл кода, из которого вы хотите извлечь абзацы, добавьте в верхней части файла следующие директивы:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Откройте PDF-документ.
 Откройте существующий PDF-документ с помощью`Document`конструктор и передав путь к входному PDF-файлу.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 5. Извлечение абзацев
 Создайте экземпляр`ParagraphAbsorber` класс и использовать его`Visit` метод извлечения абзацев из документа.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Шаг 6. Перебирайте абзацы
Прокрутите извлеченные абзацы, чтобы получить доступ к текстовому содержимому. Используйте вложенные циклы для перемещения по разделам и строкам внутри каждого абзаца.

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
//Открыть существующий PDF-файл
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
Вы успешно извлекли абзацы из PDF-документа с помощью Aspose.PDF для .NET. Извлеченные абзацы отобразились в окне консоли.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого урока?

О: Это руководство призвано помочь вам извлечь абзацы из файла PDF с помощью Aspose.PDF для .NET. Сопровождающий исходный код C# предоставляет практические шаги для решения этой задачи.

#### Вопрос: Какие пространства имен мне следует импортировать?

О: В файле кода, из которого вы собираетесь извлечь абзацы, включите в начало файла следующие директивы using:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Вопрос: Как указать каталог документа?

 A: Найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` в коде и замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как открыть существующий PDF-документ?

 О: На шаге 4 вы откроете существующий PDF-документ, используя`Document` конструктор и указав путь к входному PDF-файлу.

#### Вопрос: Как извлечь абзацы из документа?

 О: Шаг 5 включает в себя создание экземпляра`ParagraphAbsorber` класс и используя его`Visit` метод извлечения абзацев из PDF-документа.

#### Вопрос: Как перебирать извлеченные абзацы?

О: Шаг 6 поможет вам пройтись по извлеченным абзацам. Вложенные циклы используются для перемещения по разделам и строкам внутри каждого абзаца, обеспечивая в конечном итоге доступ к текстовому содержимому и его отображение.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы научились извлекать абзацы из PDF-документа с помощью Aspose.PDF для .NET. Извлеченные абзацы отображаются в окне консоли, предоставляя вам ценную информацию о структуре содержимого документа.