---
title: Изображение и номер страницы в верхнем колонтитуле в строке
linktitle: Изображение и номер страницы в верхнем колонтитуле в строке
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить изображение и номер страницы в верхний и нижний колонтитулы, используя встроенные абзацы с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
В этом руководстве мы шаг за шагом расскажем вам, как добавить изображение и номер страницы в верхний и нижний колонтитулы документа PDF с помощью Aspose.PDF для .NET. Мы будем использовать предоставленный исходный код C# для создания страницы, установки верхнего и нижнего колонтитула, добавления изображения и текста с использованием встроенных абзацев в заголовке документа PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 2: Создание PDF-документа и страницы

Первым шагом является создание нового объекта документа и страницы в документе PDF. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте новый объект документа
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Создать страницу в документе
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Приведенный выше код создает новый объект Document и пустую страницу в документе PDF.

## Шаг 3: Добавление заголовка с изображением и встроенным текстом

Теперь, когда страница создана, мы можем добавить раздел заголовка с изображением и текстом, используя встроенные абзацы. Вот как:

```csharp
// Создайте раздел заголовка
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Установить заголовок страницы
page. Header = header;

// Создайте объект TextFragment для первого встроенного текста.
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Укажите цвет текста
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//Создайте объект изображения для изображения
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Установить путь к изображению
image1.File = dataDir + "aspose-logo.jpg";

// Определите размеры изображения
image1.FixWidth = 50;
image1.FixHeight = 20;

// Укажите, что первый встроенный текст является изображением
image1.IsInLineParagraph = true;

// Создайте второй встроенный текст
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Добавить элементы в заголовок
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Приведенный выше код создает раздел заголовка, устанавливает заголовок страницы с этим разделом, добавляет TextFragment со встроенным текстом и встроенным объектом Image.

## Шаг 4: Сохранение измененного PDF-документа

После добавления заголовка с изображением и встроенным текстом мы можем сохранить измененный PDF-документ. Вот как:

```csharp
// Сохраните измененный PDF-документ
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для изображения и номера страницы в нижнем колонтитуле заголовка, встроенный с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создайте экземпляр объекта Document, вызвав его пустой конструктор
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Создать страницу в объекте Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Создать раздел заголовка документа
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Установите заголовок для файла PDF
page.Header = header;

// Создайте текстовый объект
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Укажите цвет
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Создайте объект изображения в разделе
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Установить путь к файлу изображения
image1.File = dataDir + "aspose-logo.jpg";

// Установите ширину изображения Информация
image1.FixWidth = 50;
image1.FixHeight = 20;

// Укажите, что InlineParagraph seg1 является изображением.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Сохраните PDF-файл
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Заключение

Поздравляем! Вы узнали, как добавить изображение и номер страницы в верхний и нижний колонтитулы PDF-документа, используя встроенные абзацы с помощью Aspose.PDF для .NET. Теперь вы можете гибко настраивать верхний и нижний колонтитулы ваших PDF-документов.
