---
title: Добавить оглавление
linktitle: Добавить оглавление
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить оглавление в документы PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с примером исходного кода. Ускорьте навигацию по документу!
type: docs
weight: 40
url: /ru/net/programming-with-document/addtoc/
---

В этом руководстве мы рассмотрим, как использовать функцию добавления оглавления (оглавление) Aspose.PDF для .NET для добавления оглавления в документы PDF. Мы предоставим пошаговое руководство и объясним исходный код C#, необходимый для достижения этой цели. К концу этого руководства вы сможете создать PDF-документ с оглавлением, используя Aspose.PDF для .NET.


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

// Создайте строковые объекты, которые будут использоваться в качестве элементов TOC.
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

	//Добавить заголовок на страницу, содержащую оглавление
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Сохраните обновленный документ
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```
