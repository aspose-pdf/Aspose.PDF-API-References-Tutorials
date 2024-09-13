---
title: Пользовательские позиции табуляции в PDF-файле
linktitle: Пользовательские позиции табуляции в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как создавать пользовательские позиции табуляции в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-text/custom-tab-stops/
---

Этот урок проведет вас через процесс создания пользовательских табуляторов в PDF-файле с использованием Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, где вы хотите создать пользовательские позиции табуляции, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Создайте новый экземпляр документа
 Создать новый экземпляр`Document` объект, добавив следующую строку кода:

```csharp
Document _pdfdocument = new Document();
```

## Шаг 5: Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` Метод`Pages` Коллекция. В представленном коде новая страница присваивается переменной`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Шаг 6: Создайте пользовательские позиции табуляции
 Создать`TabStops` объект и добавьте к нему пользовательские табуляции. Установите тип выравнивания и тип лидера для каждой табуляции.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Шаг 7: Создание текстовых фрагментов с табуляциями
 Создавать`TextFragment` объекты и передайте им пользовательские табуляции. Используйте специальные символы`#$TAB` для обозначения позиций табуляции в тексте.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Шаг 8: Сохраните PDF-документ.
 Сохраните PDF-документ с помощью`Save` Метод`Document` объект.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для пользовательских табуляторов с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно создали PDF-документ с пользовательскими позициями табуляции с помощью Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути выходного файла.

### Часто задаваемые вопросы

#### В: На чем сосредоточено внимание в этом уроке?

A: Этот урок посвящен тому, как провести вас через процесс создания пользовательских позиций табуляции в файле PDF с использованием библиотеки Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги для достижения этого.

#### В: Какие пространства имен мне следует импортировать для этого руководства?

A: В файле кода, где вы хотите создать пользовательские позиции табуляции, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### В: Как указать каталог документа?

 A: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как создать новый экземпляр документа?

 A: На шаге 4 вы создадите новый экземпляр`Document` объект, используя предоставленный код.

#### В: Как добавить страницу в документ?

 A: На шаге 5 вы добавите новую страницу в документ с помощью`Add` Метод`Pages` коллекция.

#### В: Как создать пользовательские позиции табуляции?

 A: На шаге 6 вы создадите`TabStops` объект и добавьте к нему пользовательские табуляции. Вы также зададите типы выравнивания и лидера для каждой табуляции.

#### В: Как создать текстовые фрагменты с табуляциями?

 A: На шаге 7 вы создадите`TextFragment` объекты и передать им пользовательские табуляции. Вы будете использовать специальные символы`#$TAB` для обозначения позиций табуляции в тексте.

#### В: Как сохранить PDF-документ?

 A: На шаге 8 вы сохраните PDF-документ с помощью`Save` Метод`Document` объект.

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы узнали, как создать PDF-документ с пользовательскими табуляциями с помощью Aspose.PDF для .NET. Это может быть полезно для организации и выравнивания текста в структурированном виде.