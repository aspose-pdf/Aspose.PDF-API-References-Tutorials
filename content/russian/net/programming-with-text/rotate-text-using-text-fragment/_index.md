---
title: Поворот текста с использованием фрагмента текста в PDF-файле
linktitle: Поворот текста с использованием фрагмента текста в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как вращать текст, используя текстовые фрагменты в PDF-файле, с помощью Aspose.PDF для .NET.
type: docs
weight: 390
url: /ru/net/programming-with-text/rotate-text-using-text-fragment/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поворота текста с использованием текстовых фрагментов в файле PDF. Приведенный исходный код C# демонстрирует процесс шаг за шагом.

## Предварительные условия

Прежде чем продолжить обучение, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для установки в свой проект.

## Шаг 1. Настройте проект

Начните с создания нового проекта C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.

Добавьте следующие директивы using в начало файла C#, чтобы импортировать необходимые пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Шаг 3. Создайте PDF-документ.

 Инициализируйте`Document` объект для создания нового PDF-документа:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

## Шаг 4. Добавьте страницу

 Получите конкретную страницу из документа, используя`Pages.Add()` метод:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Шаг 5: Создайте фрагменты текста

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

Настройте текст, положение и другие свойства по своему усмотрению.

## Шаг 6. Создайте TextBuilder и добавьте фрагменты текста.

 Создать`TextBuilder` объект с помощью`pdfPage` и добавьте фрагменты текста на страницу PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Шаг 7. Сохраните PDF-документ.

 Сохраните измененный PDF-документ в файл с помощью`Save` метод:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Обязательно замените`"TextFragmentTests_Rotated1_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для поворота текста с использованием фрагмента текста с использованием Aspose.PDF для .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Инициализировать объект документа
Document pdfDocument = new Document();
// Получить конкретную страницу
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

Поздравляем! Вы успешно научились вращать текст с помощью текстовых фрагментов в PDF-документе с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство: от создания документа до сохранения измененной версии. Теперь вы можете включить этот код в свои собственные проекты C#, чтобы управлять поворотом текста в файлах PDF.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Поворот текста с помощью фрагмента текста»?

О: Учебное пособие «Поворот текста с использованием фрагмента текста» призвано провести вас через процесс использования библиотеки Aspose.PDF для .NET для поворота текста с использованием текстовых фрагментов в PDF-документе. В руководстве представлены пошаговые инструкции и пример кода для реализации этой функции.

#### Вопрос: Что подразумевается под «поворотом текста с использованием текстовых фрагментов»?

О: Поворот текста с использованием текстовых фрагментов означает возможность применять поворот к отдельным фрагментам текста в PDF-документе с помощью библиотеки Aspose.PDF. Этот метод позволяет вам управлять ориентацией текста под разными углами или положениями внутри содержимого PDF.

#### Вопрос: Зачем мне поворачивать фрагменты текста в PDF-документе?

О: Поворот фрагментов текста в PDF-документе может быть полезен для различных целей, например для выделения определенного содержания, создания художественного оформления или улучшения макета и читаемости.

#### Вопрос: Как мне настроить проект для обучения?

О: Чтобы настроить проект:

1. Создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE).
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.
3. Добавьте необходимые директивы using в файл C#.

#### Вопрос: Как создать новый PDF-документ?

 О: Чтобы создать новый PDF-документ, инициализируйте`Document`объект из библиотеки Aspose.PDF. Вы можете использовать этот объект для добавления страниц и содержимого в PDF-файл.

#### Вопрос: Как повернуть фрагменты текста с помощью текстовых фрагментов?

О: Чтобы повернуть текстовые фрагменты с помощью текстовых фрагментов:

1.  Создавать`TextFragment` объекты.
2. Задайте текст и свойства текстовых фрагментов.
3. Укажите положение фрагментов текста на странице.
4.  Установите угол поворота с помощью`TextState.Rotation` свойство текстовых фрагментов.
5.  Создать`TextBuilder`объект и добавьте фрагменты текста на страницу PDF.

#### Вопрос: Могу ли я применять разные углы поворота к разным фрагментам текста?

 О: Да, вы можете применять разные углы поворота к разным`TextFragment` объекты. Каждый текстовый фрагмент может иметь свой угол поворота, заданный с помощью параметра`TextState.Rotation` свойство.

#### Вопрос: Как сохранить PDF-документ с повернутыми фрагментами текста?

 О: Чтобы сохранить PDF-документ с повернутыми фрагментами текста, используйте команду`Save` метод`Document` объект и укажите желаемый путь и имя выходного файла.