---
title: Пользовательские позиции табуляции в PDF-файле
linktitle: Пользовательские позиции табуляции в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как создавать собственные позиции табуляции в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-text/custom-tab-stops/
---

Это руководство проведет вас через процесс создания пользовательских позиций табуляции в PDF-файле с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файле кода, в котором вы хотите создать собственные позиции табуляции, добавьте следующие директивы с помощью в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте новый экземпляр документа.
 Создать экземпляр нового`Document` объект, добавив следующую строку кода:

```csharp
Document _pdfdocument = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages`коллекция. В предоставленном коде новая страница присваивается переменной`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Шаг 6. Создайте собственные позиции табуляции
 Создать`TabStops` объект и добавьте к нему собственные позиции табуляции. Установите тип выравнивания и тип выноски для каждой позиции табуляции.

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

## Шаг 7. Создайте фрагменты текста с позициями табуляции.
 Создавать`TextFragment` объекты и передавать им пользовательские позиции табуляции. Используйте специальные символы`#$TAB` для обозначения позиции табуляции в тексте.

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

## Шаг 8. Сохраните PDF-документ.
 Сохраните PDF-документ, используя`Save` метод`Document` объект.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для пользовательских позиций табуляции с использованием Aspose.PDF для .NET 
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
Вы успешно создали PDF-документ с настраиваемыми позициями табуляции, используя Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути к выходному файлу.

### Часто задаваемые вопросы

#### Вопрос: Чему посвящено это руководство?

О: Это руководство посвящено процессу создания пользовательских позиций табуляции в файле PDF с использованием библиотеки Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги для достижения этой цели.

#### Вопрос: Какие пространства имен мне следует импортировать для этого руководства?

О: В файле кода, в котором вы хотите создать собственные позиции табуляции, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как создать новый экземпляр документа?

 О: На шаге 4 вы создадите новый экземпляр`Document` объект, используя предоставленный код.

#### Вопрос: Как добавить страницу в документ?

 О: На шаге 5 вы добавите в документ новую страницу, используя`Add` метод`Pages` коллекция.

#### Вопрос: Как создать собственные позиции табуляции?

 О: На шаге 6 вы создадите`TabStops` объект и добавьте к нему собственные позиции табуляции. Вы также зададите типы выравнивания и выноски для каждой позиции табуляции.

#### Вопрос: Как создать фрагменты текста с позициями табуляции?

 О: На шаге 7 вы создадите`TextFragment` объекты и передавать им пользовательские позиции табуляции. Вы будете использовать специальные символы`#$TAB` для обозначения позиции табуляции в тексте.

#### Вопрос: Как сохранить PDF-документ?

 О: На шаге 8 вы сохраните PDF-документ, используя`Save` метод`Document` объект.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы узнали, как создать PDF-документ с настраиваемыми позициями табуляции с помощью Aspose.PDF для .NET. Это может быть полезно для организации и выравнивания текста в структурированном виде.