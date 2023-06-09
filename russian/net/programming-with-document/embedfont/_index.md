---
title: Встроить шрифт
linktitle: Встроить шрифт
second_title: Aspose.PDF для справочника API .NET
description: Из этого пошагового руководства вы узнаете, как встроить шрифты в файл PDF с помощью Aspose.PDF для .NET. Убедитесь, что ваши документы корректно отображаются на любом устройстве.
type: docs
weight: 120
url: /ru/net/programming-with-document/embedfont/
---

В этом руководстве мы обсудим, как встраивать шрифты в файл PDF с помощью Aspose.PDF для .NET. Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам программно создавать, редактировать и управлять PDF-документами. Эта библиотека предоставляет широкий спектр функций для работы с PDF-документами, включая добавление текста, изображений, таблиц и многое другое. Встраивание шрифтов в PDF-файл является общим требованием для разработчиков, которые хотят обеспечить правильное отображение PDF-файла на разных устройствах, независимо от того, установлены ли на этих устройствах требуемые шрифты или нет.

## Шаг 1. Создайте новое консольное приложение C#
Для начала создайте новое консольное приложение C# в Visual Studio. Вы можете назвать это как угодно. После создания проекта необходимо добавить ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте пространство имен Aspose.PDF
Добавьте следующую строку кода вверху файла C#, чтобы импортировать пространство имен Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Шаг 3: Загрузите существующий файл PDF
Чтобы встроить шрифты в существующий файл PDF, вам необходимо загрузить этот файл с помощью класса Document. Следующий код демонстрирует, как загрузить существующий файл PDF:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите существующий файл PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 4: Повторите все страницы
После того, как вы загрузили файл PDF, вам нужно просмотреть все страницы документа. Для каждой страницы вам нужно проверить, используются ли какие-либо шрифты, и если да, то вам нужно встроить эти шрифты. В следующем коде показано, как просмотреть все страницы PDF-файла и внедрить шрифты:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Проверьте, встроен ли уже шрифт
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Проверка объектов формы
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Проверьте, встроен ли шрифт
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Шаг 5: Сохраните PDF-документ
После того, как вы внедрили все шрифты в файл PDF, вам необходимо сохранить документ. Следующий код демонстрирует, как сохранить файл PDF:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Пример исходного кода для Embed Font с использованием Aspose.PDF для .NET

Вот полный исходный код для встраивания шрифта с помощью Aspose.PDF для .NET.


```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите существующие файлы PDF
Document doc = new Document(dataDir + "input.pdf");

// Перебрать все страницы
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Проверьте, встроен ли уже шрифт
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Проверка объектов формы
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Проверьте, встроен ли шрифт
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Заключение
В этой статье мы обсудили, как встраивать шрифты в файл PDF с помощью Aspose.PDF для .NET. Aspose.PDF для .NET предоставляет простой и удобный API для работы с PDF-документами, включая добавление и встраивание шрифтов. Встраивание шрифтов в файл PDF — важный шаг для обеспечения корректного отображения документа на разных устройствах, независимо от того, установлены ли на этих устройствах требуемые шрифты.
