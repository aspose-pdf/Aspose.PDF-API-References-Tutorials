---
title: Добавить оглавление в PDF-файл
linktitle: Добавить оглавление в PDF-файл
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить оглавление в файл PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с примером исходного кода. Улучшите навигацию по документам!
type: docs
weight: 40
url: /ru/net/programming-with-document/addtoc/
---
В этом уроке мы рассмотрим, как использовать функцию «Добавить оглавление» (оглавление) в файл PDF в Aspose.PDF для .NET, чтобы добавить оглавление в PDF-документы. Мы предоставим пошаговое руководство и объясним исходный код C#, необходимый для достижения этой цели. К концу этого руководства вы сможете создать PDF-документ с оглавлением, используя Aspose.PDF для .NET.


## Шаг 1. Загрузите существующий PDF-файл.

 Для начала нам нужно загрузить существующий PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде, указав фактический путь к вашему PDF-файлу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Шаг 2. Создайте новую страницу для оглавления.

Мы создадим новую страницу для содержания оглавления. Следующий код вставляет новую страницу с индексом 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Шаг 3. Определите информацию о содержании.

Далее нам нужно определить информацию о содержании. Мы установим заголовок и другие свойства оглавления. Добавьте следующий код:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Шаг 4. Создайте элементы содержания.

Теперь мы создадим элементы оглавления. В этом уроке мы создадим четыре элемента TOC, соответствующие разным страницам. Измените следующий код в соответствии с вашими требованиями:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Шаг 5. Сохраните обновленный документ.

 Наконец, нам нужно сохранить измененный документ с оглавлением. Заменять`"YOUR DOCUMENT DIRECTORY"` в приведенном ниже коде с желаемым путем к выходному файлу:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Пример исходного кода для добавления содержания в PDF-документы с использованием Aspose.PDF для .NET

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузить существующие PDF-файлы
Document doc = new Document(dataDir + "AddTOC.pdf");

// Получите доступ к первой странице PDF-файла
Page tocPage = doc.Pages.Insert(1);

// Создайте объект для представления информации TOC.
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Установите заголовок для оглавления
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Создайте строковые объекты, которые будут использоваться в качестве элементов TOC.
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Создать объект заголовка
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Укажите целевую страницу для объекта заголовка
	heading2.DestinationPage = doc.Pages[i + 2];

	// Страница назначения
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Координата назначения
	segment2.Text = titles[i];

	// Добавить заголовок на страницу, содержащую оглавление
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Сохраните обновленный документ
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Заключение

В этом уроке мы рассмотрели, как добавить оглавление (TOC) в PDF-документы с помощью Aspose.PDF для .NET. Следуя пошаговому руководству и используя предоставленный исходный код C#, вы можете легко создать PDF-документ с оглавлением. Содержание повышает удобство использования документа, позволяя пользователям более эффективно переходить к определенным разделам или страницам. Aspose.PDF для .NET предоставляет надежное и удобное решение для работы с PDF-файлами в приложениях .NET, позволяющее с легкостью создавать динамические и интерактивные PDF-документы.

### Часто задаваемые вопросы по добавлению содержания в файл PDF

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF for .NET — это мощная библиотека, которая позволяет разработчикам эффективно работать с PDF-файлами в .NET-приложениях. Он предоставляет широкий спектр функций для программного создания, манипулирования и управления PDF-документами.

#### Вопрос: Какова цель добавления оглавления (TOC) в документ PDF?

О: Оглавление (TOC) предоставляет пользователям помощь в навигации, позволяя им быстро переходить к определенным разделам или страницам PDF-документа. Это повышает удобство использования документа и удобство для пользователя.

#### Вопрос: Как добавить оглавление в документ PDF с помощью Aspose.PDF для .NET?

О: Чтобы добавить оглавление в PDF-документ с помощью Aspose.PDF для .NET, вам необходимо создать новую страницу для хранения оглавления, определить информацию оглавления, а затем создать элементы оглавления, соответствующие конкретным страницам или разделы в документе.

#### Вопрос: Могу ли я настроить внешний вид оглавления?

О: Да, вы можете настроить внешний вид оглавления, задав различные свойства элементов оглавления, такие как размер шрифта, стиль шрифта и выравнивание. Aspose.PDF для .NET обеспечивает гибкость при разработке оглавления в соответствии с желаемым внешним видом.

#### Вопрос: Подходит ли Aspose.PDF для .NET для добавления дополнительных функций в PDF-документы?

О: Конечно, Aspose.PDF для .NET — это многофункциональная библиотека, которая позволяет добавлять в PDF-документы расширенные функции, включая интерактивные элементы, поля форм, цифровые подписи и многое другое.