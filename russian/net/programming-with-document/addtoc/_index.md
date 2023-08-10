---
title: Добавить оглавление в файл PDF
linktitle: Добавить оглавление в файл PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить оглавление в файл PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с примером исходного кода. Ускорьте навигацию по документу!
type: docs
weight: 40
url: /ru/net/programming-with-document/addtoc/
---
В этом руководстве мы рассмотрим, как использовать функцию «Добавить оглавление» в PDF-файл Aspose.PDF для .NET, чтобы добавить оглавление в PDF-документы. Мы предоставим пошаговое руководство и объясним исходный код C#, необходимый для достижения этой цели. К концу этого руководства вы сможете создать PDF-документ с оглавлением, используя Aspose.PDF для .NET.


## Шаг 1: Загрузите существующий файл PDF

 Для начала нам нужно загрузить существующий файл PDF. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашему файлу PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Шаг 2: Создайте новую страницу для оглавления

Мы создадим новую страницу для хранения оглавления. Следующий код вставляет новую страницу в индекс 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Шаг 3: Определите информацию о содержании

Далее нам нужно определить информацию о содержании. Мы установим заголовок и другие свойства оглавления. Добавьте следующий код:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Шаг 4: Создайте элементы TOC

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

## Шаг 5: Сохраните обновленный документ

 Наконец, нам нужно сохранить измененный документ с оглавлением. Заменять`"YOUR DOCUMENT DIRECTORY"` в приведенном ниже коде с желаемым путем к выходному файлу:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Пример исходного кода для добавления оглавления в документы PDF с использованием Aspose.PDF для .NET

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите существующие файлы PDF
Document doc = new Document(dataDir + "AddTOC.pdf");

// Получить доступ к первой странице файла PDF
Page tocPage = doc.Pages.Insert(1);

// Создайте объект для представления информации TOC
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

	// Целевая страница
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Координата пункта назначения
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

В этом руководстве мы рассмотрели, как добавить оглавление (TOC) в документы PDF с помощью Aspose.PDF для .NET. Следуя пошаговому руководству и используя предоставленный исходный код C#, вы можете легко создать PDF-документ с оглавлением. Оглавление повышает удобство использования документа, позволяя пользователям более эффективно переходить к определенным разделам или страницам. Aspose.PDF для .NET представляет собой надежное и удобное решение для работы с файлами PDF в приложениях .NET, позволяющее с легкостью создавать динамические и интерактивные документы PDF.

### Часто задаваемые вопросы по добавлению оглавления в файл PDF

#### В: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам эффективно работать с файлами PDF в приложениях .NET. Он предоставляет широкий спектр функций для создания, обработки и управления PDF-документами программными средствами.

#### В: Какова цель добавления оглавления (TOC) в документ PDF?

О: Оглавление (TOC) предоставляет пользователям помощь в навигации, позволяя им быстро переходить к определенным разделам или страницам в документе PDF. Это повышает удобство использования документа и взаимодействие с пользователем.

#### В: Как добавить оглавление в документ PDF с помощью Aspose.PDF для .NET?

О: Чтобы добавить оглавление в документ PDF с помощью Aspose.PDF для .NET, вам необходимо создать новую страницу для хранения оглавления, определить информацию о оглавлении, а затем создать элементы оглавления, соответствующие определенным страницам или разделы в документе.

#### В: Могу ли я настроить внешний вид оглавления?

О: Да, вы можете настроить внешний вид оглавления, задав различные свойства элементов оглавления, такие как размер шрифта, стиль шрифта и выравнивание. Aspose.PDF для .NET обеспечивает гибкость при разработке оглавления в соответствии с желаемым внешним видом.

#### В: Подходит ли Aspose.PDF для .NET для добавления расширенных функций в документы PDF?

О: Безусловно, Aspose.PDF для .NET — это многофункциональная библиотека, которая позволяет добавлять в PDF-документы расширенные функции, включая интерактивные элементы, поля форм, цифровые подписи и многое другое.