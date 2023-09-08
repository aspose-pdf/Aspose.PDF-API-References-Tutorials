---
title: Добавить отступ последующих строк в PDF-файле
linktitle: Добавить отступ последующих строк в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить отступ к последующим строкам текста в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-text/add-subsequent-lines-indent/
---
Это руководство проведет вас через процесс добавления отступов последующих строк к тексту в PDF-файле с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файле кода, в котором вы хотите добавить отступы для последующих строк, добавьте следующую директиву using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте новый объект документа.
 Создать экземпляр нового`Document` объект, добавив следующую строку кода:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages`коллекция. В предоставленном коде новая страница присваивается переменной`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Шаг 6. Создайте TextFragment с отступом последующих строк.
 Создать экземпляр`TextFragment` объект и укажите желаемый текст. В предоставленном коде текст присваивается переменной`text` . Затем инициализируйте`TextFormattingOptions` для`TextFragment`и укажите`SubsequentLinesIndent` ценить.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Шаг 7. Добавьте TextFragment на страницу.
 Добавить`TextFragment` объект коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(text);
```

## Шаг 8. Повторите шаги 6 и 7 для дополнительных строк.
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

## Шаг 9. Сохраните PDF-документ.
 Сохраните PDF-документ, используя`Save` метод`Document` объект. Укажите путь к выходному файлу.

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
// Инициализируйте TextFormattingOptions для фрагмента текста и укажите значение FollowLinesIndent.
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
Вы успешно добавили отступ последующих строк к тексту, используя Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути к выходному файлу.

### Часто задаваемые вопросы

#### Вопрос: Чему посвящено это руководство?

О: В этом руководстве представлено подробное руководство о том, как добавить отступы к последующим строкам текста в PDF-файле с помощью библиотеки Aspose.PDF для .NET. Он включает примеры исходного кода C#, иллюстрирующие шаги, необходимые для достижения этой цели.

#### Вопрос: Какие пространства имен мне нужно импортировать для работы с этим руководством?

О: В файле кода, в котором вы собираетесь добавить отступы для последующих строк, импортируйте в начало файла следующие пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как создать объект «Документ»?

 О: На шаге 4 вы создадите новый экземпляр`Document` объект, используя следующую строку кода:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Вопрос: Как добавить страницу в документ?

 О: На шаге 5 вы добавите в документ новую страницу, используя`Add` метод`Pages` коллекция:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Вопрос: Как добавить отступы к последующим строкам текста?

 О: На шаге 6 вы создадите`TextFragment` объект и присвойте ему нужный текст. Затем вы инициализируете`TextFormattingOptions` для`TextFragment`и укажите`SubsequentLinesIndent` ценить:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Вопрос: Как добавить TextFragment в документ PDF?

 О: На шаге 7 вы добавите`TextFragment` объект (`text`) в коллекцию абзацев страницы:

```csharp
page.Paragraphs.Add(text);
```

#### Вопрос: Могу ли я повторить процесс для дополнительных строк?

 О: Да, на шаге 8 вы можете повторить процесс для дополнительных строк с тем же отступом, создав новые.`TextFragment` объекты и добавление их в коллекцию абзацев на странице.

#### Вопрос: Как сохранить полученный PDF-документ?

 О: После добавления текста с отступом последующих строк используйте команду`Save` метод`Document` объект для сохранения PDF-документа:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы успешно научились улучшать читаемость текста в PDF-документе, добавляя отступы к последующим строкам с помощью Aspose.PDF для .NET. Этот метод может быть полезен для различных типов документов и отчетов.