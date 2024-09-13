---
title: Добавить HTML с помощью DOM и перезаписать PDF
linktitle: Добавить HTML с помощью DOM и перезаписать
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как добавлять HTML-контент с помощью DOM и перезаписи PDF в Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Это руководство проведет вас через процесс добавления HTML-контента с использованием DOM (Document Object Model) в Aspose.PDF для .NET. Кроме того, вы узнаете, как перезаписывать стили для HTML-контента. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, куда вы хотите добавить HTML-контент, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите каталог документа и путь к выходному файлу
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 4: Создайте новый объект «Документ»
 Создать новый экземпляр`Document` объект, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5: Добавьте страницу в документ
 Добавьте новую страницу в документ, используя`Add` Метод`Pages` Коллекция. В представленном коде новая страница присваивается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 6: Создайте HtmlFragment с HTML-содержимым
 Создайте экземпляр`HtmlFragment` объект и предоставить желаемый HTML-контент. В предоставленном коде HTML-контент назначается переменной`title`. Вы можете изменить HTML-контент по мере необходимости.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Шаг 7: Перезапишите стили для HTML-контента.
 Чтобы перезаписать стили HTML-контента, вы можете изменить`TextState` свойства`HtmlFragment` объект. В предоставленном коде семейство шрифтов изменено на «Arial», а размер шрифта установлен на 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Шаг 8: Установите информацию о марже
При необходимости отрегулируйте нижнее и верхнее поля фрагмента HTML. В предоставленном коде нижнее поле установлено на 10, а верхнее поле установлено на 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Шаг 9: Добавьте HtmlFragment на страницу
 Добавьте`HtmlFragment` возражать против коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(title);
```

## Шаг 10: Сохраните PDF-документ.
 Сохраните PDF-документ с помощью`Save` Метод`Document` объект. Укажите путь к выходному файлу, который вы задали в Шаге 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для добавления HTML с использованием DOM и перезаписи с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр объекта Document
Document doc = new Document();
// Добавить страницу в коллекцию страниц PDF-файла
Page page = doc.Pages.Add();
// Создание HtmlFragment с HTML-контентом
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Семейство шрифтов «Verdana» будет сброшено на «Arial»
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Установить информацию о нижнем поле
title.Margin.Bottom = 10;
// Установить информацию о верхнем поле
title.Margin.Top = 400;
// Добавить фрагмент HTML в коллекцию абзацев страницы
page.Paragraphs.Add(title);
// Сохранить PDF-файл
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Сохранить PDF-файл
doc.Save(dataDir);
```

## Заключение
Вы успешно добавили HTML-контент с помощью DOM в Aspose.PDF для .NET и перезаписали стили для HTML-контента. Полученный PDF-файл теперь можно найти по указанному пути выходного файла.

### Часто задаваемые вопросы

#### В: На чем сосредоточено внимание в этом уроке?

A: Этот учебник разработан, чтобы провести вас через процесс добавления HTML-контента в PDF-документ с использованием Document Object Model (DOM) в Aspose.PDF для .NET. Кроме того, вы узнаете, как перезаписывать стили для HTML-контента, что позволит вам настраивать его внешний вид. Учебник предоставляет фрагменты исходного кода C# для демонстрации необходимых шагов.

#### В: Какие пространства имен мне необходимо импортировать для этого руководства?

A: В файле кода, куда вы собираетесь добавить HTML-контент, импортируйте следующие пространства имен в начале файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### В: Как указать каталог документа и путь к выходному файлу?

 A: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как создать объект «Документ»?

 A: На шаге 4 вы создадите новый экземпляр`Document` объект, используя следующую строку кода:

```csharp
Document doc = new Document();
```

#### В: Как добавить страницу в документ?

 A: На шаге 5 вы добавите новую страницу в документ с помощью`Add` Метод`Pages` коллекция:

```csharp
Page page = doc.Pages.Add();
```

#### В: Как настроить HTML-контент с помощью DOM?

 A: На шаге 6 вы создадите`HtmlFragment` объект и присвойте ему желаемое содержимое HTML. Содержимое HTML присваивается переменной`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### В: Как перезаписать стили HTML-контента?

 A: На шаге 7 вы перезапишете стили HTML-контента, изменив`TextState` свойства`HtmlFragment`объект. Например, вы можете изменить семейство шрифтов на «Arial» и установить размер шрифта на 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### В: Могу ли я настроить поля HTML-контента?

A: Да, на шаге 8 вы можете настроить нижнее и верхнее поля фрагмента HTML по мере необходимости:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### В: Как добавить HtmlFragment в PDF-документ?

 A: На шаге 9 вы добавите`HtmlFragment` объект (`title`) к коллекции абзацев страницы:

```csharp
page.Paragraphs.Add(title);
```

#### В: Как сохранить полученный PDF-документ?

 A: После добавления HTML-контента и настройки его стилей используйте`Save` Метод`Document` объект для сохранения PDF-документа:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы успешно научились включать HTML-контент с помощью Document Object Model (DOM) в Aspose.PDF для .NET. Кроме того, вы получили возможность перезаписывать стили, чтобы адаптировать внешний вид HTML-контента в результирующем PDF-документе.