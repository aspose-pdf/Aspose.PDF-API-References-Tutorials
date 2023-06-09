---
title: Определить разрыв строки
linktitle: Определить разрыв строки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как определить разрывы строк в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 130
url: /ru/net/programming-with-text/determine-line-break/
---

Это руководство проведет вас через процесс определения разрывов строк в документе PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файл кода, где вы хотите определить разрывы строк, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Создайте новый экземпляр документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 6: Добавьте текстовые фрагменты с разрывами строк
Создайте цикл, чтобы добавить на страницу несколько текстовых фрагментов, каждый из которых содержит абзац с разрывами строк.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Шаг 7. Сохраните документ PDF и извлеките информацию о разрыве строки.
 Сохраните документ PDF с помощью`Save` метод`Document` объект. Затем извлеките информацию о разрыве строки с помощью`GetNotifications` метод нужной страницы.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Пример исходного кода для определения разрыва строки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Заключение
Вы успешно определили разрывы строк в документе PDF с помощью Aspose.PDF для .NET. Информация о разрыве строки извлечена и сохранена в текстовом файле.