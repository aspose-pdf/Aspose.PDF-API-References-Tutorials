---
title: Встроить шрифт Standard Type 1
linktitle: Встроить шрифт Standard Type 1
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как встроить стандартные шрифты Type 1 в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 140
url: /ru/net/programming-with-text/embed-standard-type-1fonts/
---

Это руководство проведет вас через процесс встраивания стандартных шрифтов Type 1 в документ PDF с использованием Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файл кода, в который вы хотите внедрить стандартные шрифты Type 1, добавьте следующую директиву using в верхней части файла:

```csharp
using Aspose.Pdf;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Загрузите существующий документ PDF
 Загрузите существующий PDF-документ с помощью`Document` конструктор и передать путь к входному файлу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Шаг 5. Задайте свойство EmbedStandardFonts
 Установить`EmbedStandardFonts` свойство документа`true` чтобы включить встраивание стандартных шрифтов Type 1.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Шаг 6. Вставьте шрифты на каждую страницу
 Просмотрите каждую страницу документа PDF и проверьте, встроены ли уже шрифты. Если нет, установите`IsEmbedded` собственность на`true` для встраивания шрифта.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Шаг 7: Сохраните обновленный PDF-документ
 Сохраните обновленный PDF-документ, используя`Save` метод`Document` объект, указав путь к выходному файлу.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Пример исходного кода для Embed Standard Type 1Fonts с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузите существующий PDF-документ
Document pdfDocument = new Document(dataDir + "input.pdf");
// Установить свойство EmbedStandardFonts документа
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Проверьте, встроен ли уже шрифт
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Заключение
Вы успешно внедрили стандартные шрифты Type 1 в документ PDF, используя Aspose.PDF для .NET. Обновленный PDF-файл со встроенными шрифтами сохранен по указанному пути к выходному файлу.