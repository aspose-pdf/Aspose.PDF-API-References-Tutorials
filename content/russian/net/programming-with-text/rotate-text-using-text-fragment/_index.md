---
title: Поворот текста с использованием фрагмента текста в файле PDF
linktitle: Поворот текста с использованием фрагмента текста в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как повернуть текст, используя текстовые фрагменты в PDF-файле, используя Aspose.PDF для .NET.
type: docs
weight: 390
url: /ru/net/programming-with-text/rotate-text-using-text-fragment/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поворота текста с использованием фрагментов текста в файле PDF. Предоставленный исходный код C# демонстрирует процесс шаг за шагом.

## Предпосылки

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете получить ее с сайта Aspose или использовать NuGet для установки в свой проект.

## Шаг 1: Настройте проект

Начните с создания нового проекта C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен

Добавьте следующие директивы using в начало файла C#, чтобы импортировать необходимые пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Шаг 3: Создайте PDF-документ

 Инициализируйте`Document` объект для создания нового PDF-документа:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 4: Добавьте страницу

 Получить определенную страницу из документа с помощью`Pages.Add()` метод:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Шаг 5: Создание текстовых фрагментов

 Создать несколько`TextFragment` объекты, задайте их текст и свойства, а также укажите их положение на странице:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

При необходимости отрегулируйте текст, положение и другие свойства.

## Шаг 6: Создайте TextBuilder и добавьте фрагменты текста.

 Создать`TextBuilder` объект с использованием`pdfPage` и добавьте фрагменты текста на страницу PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Шаг 7: Сохраните PDF-документ.

 Сохраните измененный PDF-документ в файл с помощью`Save` метод:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Обязательно замените`"TextFragmentTests_Rotated1_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для поворота текста с использованием текстового фрагмента с использованием Aspose.PDF для .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Инициализировать объект документа
Document pdfDocument = new Document();
// Получить определенную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Создать фрагмент текста
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Установить свойства текста
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Создать повернутый фрагмент текста
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Установить свойства текста
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Создать повернутый фрагмент текста
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Установить свойства текста
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// создать объект TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Добавить фрагмент текста на страницу PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Сохранить документ
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Заключение

Поздравляем! Вы успешно научились поворачивать текст с использованием фрагментов текста в документе PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от создания документа до сохранения измененной версии. Теперь вы можете включить этот код в свои собственные проекты C# для управления поворотом текста в файлах PDF.

### Часто задаваемые вопросы

#### В: Какова цель урока «Поворот текста с использованием фрагмента текста»?

A: Учебник "Поворот текста с использованием фрагмента текста" призван провести вас через процесс использования библиотеки Aspose.PDF для .NET для поворота текста с использованием фрагментов текста в документе PDF. Учебник содержит пошаговые инструкции и пример кода для достижения этой функциональности.

#### В: Что подразумевается под «поворотом текста с использованием текстовых фрагментов»?

A: Поворот текста с использованием фрагментов текста относится к возможности применять поворот к отдельным фрагментам текста в документе PDF с использованием библиотеки Aspose.PDF. Эта техника позволяет контролировать ориентацию текста под разными углами или в разных положениях в содержимом PDF.

#### В: Зачем мне может понадобиться поворачивать фрагменты текста в PDF-документе?

A: Поворот фрагментов текста в PDF-документе может быть полезен для различных целей, например, для выделения определенного контента, создания художественного дизайна или улучшения макета и читабельности.

#### В: Как настроить проект для обучения?

A: Чтобы настроить проект:

1. Создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE).
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.
3. Добавьте необходимые директивы using в ваш файл C#.

#### В: Как создать новый PDF-документ?

 A: Чтобы создать новый PDF-документ, инициализируйте`Document`объект из библиотеки Aspose.PDF. Вы можете использовать этот объект для добавления страниц и контента в PDF.

#### В: Как повернуть фрагменты текста с помощью фрагментов текста?

A: Чтобы повернуть фрагменты текста с помощью фрагментов текста:

1.  Создавать`TextFragment` объекты.
2. Задайте текст и свойства текстовых фрагментов.
3. Укажите расположение фрагментов текста на странице.
4.  Установите угол поворота с помощью`TextState.Rotation` свойство фрагментов текста.
5.  Создать`TextBuilder`объект и добавьте фрагменты текста на страницу PDF.

#### В: Можно ли применять разные углы поворота к разным фрагментам текста?

 A: Да, вы можете применять разные углы поворота к разным`TextFragment` объекты. Каждый фрагмент текста может иметь свой собственный угол поворота, заданный с помощью`TextState.Rotation` свойство.

#### В: Как сохранить PDF-документ с повернутыми фрагментами текста?

 A: Чтобы сохранить PDF-документ с повернутыми фрагментами текста, используйте`Save` Метод`Document` объект и укажите желаемый путь и имя выходного файла.