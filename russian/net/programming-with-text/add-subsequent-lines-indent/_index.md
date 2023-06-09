---
title: Добавить отступ для последующих строк
linktitle: Добавить отступ для последующих строк
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить отступ последующих строк к тексту с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-text/add-subsequent-lines-indent/
---

Этот учебник проведет вас через процесс добавления отступа последующих строк к тексту с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файле кода, где вы хотите добавить отступ последующих строк, добавьте следующую директиву using вверху файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Создайте новый объект документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью кнопки`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Шаг 6: Создайте TextFragment с последующим отступом строк
 Создать экземпляр`TextFragment` объект и предоставить желаемый текст. В предоставленном коде текст присваивается переменной`text` . Затем инициализируйте`TextFormattingOptions` для`TextFragment` и указать`SubsequentLinesIndent` ценить.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Шаг 7: Добавьте TextFragment на страницу
 Добавить`TextFragment` возражать против коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(text);
```

## Шаг 8: Повторите шаги 6 и 7 для дополнительных строк.
Чтобы добавить последующие строки с таким же отступом, повторите шаги 6 и 7 для каждой строки. Обновите текстовое содержимое по мере необходимости.

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

## Шаг 9: Сохраните PDF-документ
 Сохраните документ PDF с помощью`Save` метод`Document` объект. Укажите путь к выходному файлу.

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
//Инициализируйте TextFormattingOptions для текстового фрагмента и укажите значение SubsequentLinesIndent.
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
Вы успешно добавили отступ последующих строк к тексту, используя Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.