---
title: Настройка номеров страниц при добавлении оглавления
linktitle: Настройка номеров страниц при добавлении оглавления
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как настроить номера страниц при добавлении оглавления (TOC) с помощью Aspose.PDF для .NET с помощью этого пошагового руководства и примера кода.
type: docs
weight: 100
url: /ru/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---

В этом руководстве мы рассмотрим, как настраивать номера страниц при добавлении оглавления (TOC) с помощью Aspose.PDF для .NET. Мы предоставим пошаговое руководство вместе с примером кода, чтобы помочь вам в этом.

## Шаг 1. Загрузка существующего файла PDF

Во-первых, нам нужно загрузить существующий файл PDF. В этом уроке мы будем использовать файл «42824.pdf», расположенный в каталоге «ВАШ ДОКУМЕНТАРИЙ». Замените этот путь к каталогу фактическим путем к каталогу вашего документа.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Шаг 2: Добавление страницы оглавления

 Далее нам нужно добавить новую страницу в начало документа, которая будет служить страницей оглавления. Мы можем добиться этого с помощью`Insert()` метод`Pages` коллекция`Document` объект.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Шаг 3: Создание объекта TOC

 Чтобы создать объект TOC, нам сначала нужно создать`TocInfo`объекта и установить его свойства. В этом уроке мы установим заголовок TOC на «Table Of Contents» и префикс номера страницы на «P».

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Шаг 4: Создание записей оглавления

Чтобы создать записи TOC, нам нужно пройтись по всем страницам документа, кроме страницы TOC, и создать объект заголовка для каждой страницы. Затем мы можем добавить объект заголовка на страницу оглавления и указать его целевую страницу.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Создать объект заголовка
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Укажите целевую страницу для объекта заголовка
    heading2.DestinationPage = doc.Pages[i + 1];
    // Целевая страница
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Координата пункта назначения
    segment2.Text = "Page " + i.ToString();
    // Добавить заголовок на страницу, содержащую оглавление
    tocPage.Paragraphs.Add(heading2);
}
```

## Шаг 5: Сохранение обновленного документа

 Наконец, нам нужно сохранить обновленный документ в новый файл. Мы можем добиться этого с помощью`Save()` метод`Document` объект.

```csharp
doc.Save(outFile);
```

### Пример исходного кода для настройки номеров страниц при добавлении оглавления с использованием Aspose.PDF для .NET

```csharp

            
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inFile = dataDir + "42824.pdf";
            string outFile = dataDir + "42824_out.pdf";
            // Загрузите существующие файлы PDF
            Document doc = new Document(inFile);
            // Получить доступ к первой странице файла PDF
            Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
            // Создайте объект для представления информации TOC
            TocInfo tocInfo = new TocInfo();
            TextFragment title = new TextFragment("Table Of Contents");
            title.TextState.FontSize = 20;
            title.TextState.FontStyle = FontStyles.Bold;
            // Установите заголовок для оглавления
            tocInfo.Title = title;
            tocInfo.PageNumbersPrefix = "P";
            tocPage.TocInfo = tocInfo;
            for (int i = 1; i<doc.Pages.Count; i++)
            {
                // Создать объект заголовка
                Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
                TextSegment segment2 = new TextSegment();
                heading2.TocPage = tocPage;
                heading2.Segments.Add(segment2);
                // Укажите целевую страницу для объекта заголовка
                heading2.DestinationPage = doc.Pages[i + 1];
                // Целевая страница
                heading2.Top = doc.Pages[i + 1].Rect.Height;
                // Координата пункта назначения
                segment2.Text = "Page " + i.ToString();
                // Добавить заголовок на страницу, содержащую оглавление
                tocPage.Paragraphs.Add(heading2);
            }

            //Сохраните обновленный документ
            doc.Save(outFile);
            
        
```

## Заключение

В этом руководстве мы предоставили пошаговое руководство по настройке номеров страниц при добавлении оглавления с помощью Aspose.PDF для .NET. Мы также предоставили пример кода, который вы можете использовать в качестве справочного материала при реализации этой функции в своем

