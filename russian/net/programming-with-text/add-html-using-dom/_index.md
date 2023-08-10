---
title: Добавить HTML с помощью DOM
linktitle: Добавить HTML с помощью DOM
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить HTML-контент с помощью DOM в Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-text/add-html-using-dom/
---

Этот учебник проведет вас через процесс добавления содержимого HTML с использованием DOM (объектная модель документа) в Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файл кода, в который вы хотите добавить содержимое HTML, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
```

## Шаг 3: Установите каталог документа и путь к выходному файлу
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Создайте новый объект документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью кнопки`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 6: Создайте HtmlFragment с содержимым HTML
Создать экземпляр`HtmlFragment` объект и предоставить желаемый HTML-контент. В предоставленном коде содержимое HTML присваивается переменной`titel`. При необходимости вы можете изменить HTML-контент.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Шаг 7. Установите информацию о марже
При необходимости отрегулируйте нижнее и верхнее поле фрагмента HTML. В предоставленном коде для нижнего поля установлено значение 10, а для верхнего поля — 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Шаг 8: Добавьте HtmlFragment на страницу
 Добавить`HtmlFragment` возражать против коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Шаг 9: Сохраните PDF-документ
 Сохраните документ PDF с помощью`Save` метод`Document` объект. Укажите путь к выходному файлу, заданный на шаге 3.

```csharp
doc.Save(dataDir);
```

## Шаг 10: Отобразите сообщение об успешном завершении
Отобразите сообщение об успешном завершении вместе с путем сохранения файла PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для добавления HTML с использованием DOM с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать объект документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц файла PDF
Page page = doc.Pages.Add();
// Создание экземпляра HtmlFragment с контекстами HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Установить информацию о нижнем поле
titel.Margin.Bottom = 10;
// Установить информацию о верхнем поле
titel.Margin.Top = 200;
// Добавить HTML-фрагмент в коллекцию абзацев страницы
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Сохранить PDF-файл
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно добавили HTML-контент с помощью DOM в Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.