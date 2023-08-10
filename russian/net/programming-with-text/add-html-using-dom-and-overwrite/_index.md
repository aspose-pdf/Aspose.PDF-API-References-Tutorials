---
title: Добавить HTML с помощью DOM и перезаписать
linktitle: Добавить HTML с помощью DOM и перезаписать
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить HTML-контент с помощью DOM в Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-text/add-html-using-dom-and-overwrite/
---

Этот учебник проведет вас через процесс добавления содержимого HTML с использованием DOM (объектная модель документа) в Aspose.PDF для .NET. Кроме того, вы узнаете, как перезаписывать стили для содержимого HTML. Предоставленный исходный код C# демонстрирует необходимые шаги.

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
using Aspose.Pdf.Text;
```

## Шаг 3: Установите каталог документа и путь к выходному файлу
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

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
Создать экземпляр`HtmlFragment` объект и предоставить желаемый HTML-контент. В предоставленном коде содержимое HTML присваивается переменной`title`. При необходимости вы можете изменить HTML-контент.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Шаг 7. Перезапишите стили для содержимого HTML
 Чтобы перезаписать стили содержимого HTML, вы можете изменить`TextState` свойства`HtmlFragment` объект. В предоставленном коде семейство шрифтов изменено на «Arial», а размер шрифта установлен на 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Шаг 8: Установите информацию о марже
При необходимости отрегулируйте нижнее и верхнее поля HTML-фрагмента. В предоставленном коде нижнее поле установлено на 10, а верхнее поле установлено на 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Шаг 9: Добавьте HtmlFragment на страницу
 Добавить`HtmlFragment` возражать против коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(title);
```

## Шаг 10: Сохраните PDF-документ
 Сохраните документ PDF с помощью`Save` метод`Document` объект. Укажите путь к выходному файлу, заданный на шаге 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для добавления HTML с помощью DOM и перезаписи с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать объект документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц файла PDF
Page page = doc.Pages.Add();
// Создание экземпляра HtmlFragment с контекстами HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Семейство шрифтов Verdana будет сброшено на Arial.
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Установить информацию о нижнем поле
title.Margin.Bottom = 10;
// Установить информацию о верхнем поле
title.Margin.Top = 400;
// Добавить HTML-фрагмент в коллекцию абзацев страницы
page.Paragraphs.Add(title);
// Сохранить PDF-файл
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Сохранить PDF-файл
doc.Save(dataDir);
```

## Заключение
Вы успешно добавили HTML-контент с помощью DOM в Aspose.PDF для .NET и перезаписали стили для HTML-контента. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.