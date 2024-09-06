---
title: Добавить отступ последующих строк в файле PDF
linktitle: Добавить отступ последующих строк в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как добавить отступ последующих строк к тексту в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-text/add-subsequent-lines-indent/
---
Этот урок проведет вас через процесс добавления отступа последующих строк в текст в файле PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, где вы хотите добавить отступ для последующих строк, добавьте следующую директиву using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Создайте новый объект «Документ»
 Создать новый экземпляр`Document` объект, добавив следующую строку кода:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Шаг 5: Добавьте страницу в документ
 Добавьте новую страницу в документ, используя`Add` Метод`Pages`Коллекция. В представленном коде новая страница присваивается переменной`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Шаг 6: Создайте TextFragment с отступом последующих строк
 Создать экземпляр`TextFragment` объект и предоставить желаемый текст. В предоставленном коде текст присваивается переменной`text` . Затем инициализируйте`TextFormattingOptions` для`TextFragment`и укажите`SubsequentLinesIndent` ценить.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Шаг 7: Добавьте TextFragment на страницу
 Добавьте`TextFragment` возражать против коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(text);
```

## Шаг 8: Повторите шаги 6 и 7 для дополнительных строк.
Чтобы добавить последующие строки с тем же отступом, повторите шаги 6 и 7 для каждой строки. При необходимости обновите текстовое содержимое.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Шаг 9: Сохраните PDF-документ.
 Сохраните PDF-документ с помощью`Save` Метод`Document` объект. Укажите путь к выходному файлу.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Пример исходного кода для добавления отступа последующих строк с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать новый объект документа
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Инициализируйте TextFormattingOptions для текстового фрагмента и укажите значение FollowingLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Заключение
Вы успешно добавили отступ последующих строк в текст с помощью Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути выходного файла.

### Часто задаваемые вопросы

#### В: На чем сосредоточено внимание в этом уроке?

A: Этот учебник предоставляет полное руководство о том, как добавить отступ последующих строк к тексту в файле PDF с помощью библиотеки Aspose.PDF для .NET. Он включает примеры исходного кода C# для иллюстрации шагов, необходимых для достижения этого.

#### В: Какие пространства имен мне необходимо импортировать для этого руководства?

A: В файле кода, где вы собираетесь добавить отступ для последующих строк, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### В: Как указать каталог документа?

 A: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как создать объект «Документ»?

 A: На шаге 4 вы создадите новый экземпляр`Document` объект, используя следующую строку кода:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### В: Как добавить страницу в документ?

 A: На шаге 5 вы добавите новую страницу в документ с помощью`Add` Метод`Pages` коллекция:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### В: Как добавить отступ к последующим строкам текста?

 A: На шаге 6 вы создадите`TextFragment` объект и присвоить ему нужный текст. Затем вы инициализируете`TextFormattingOptions` для`TextFragment`и укажите`SubsequentLinesIndent` ценить:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### В: Как добавить TextFragment в PDF-документ?

 A: На шаге 7 вы добавите`TextFragment` объект (`text`) к коллекции абзацев страницы:

```csharp
page.Paragraphs.Add(text);
```

#### В: Могу ли я повторить процесс для дополнительных строк?

 A: Да, на шаге 8 вы можете повторить процесс для дополнительных строк с тем же отступом, создав новые`TextFragment` объектов и добавление их в коллекцию абзацев страницы.

#### В: Как сохранить полученный PDF-документ?

 A: После добавления текста с отступом последующих строк используйте`Save` Метод`Document` объект для сохранения PDF-документа:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы успешно узнали, как улучшить читаемость текста в документе PDF, добавляя отступы последующих строк с помощью Aspose.PDF для .NET. Этот метод может быть полезен для различных типов документов и отчетов.