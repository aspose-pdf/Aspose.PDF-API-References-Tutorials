---
title: Изображение и номер страницы в верхнем колонтитуле, встроенный в раздел нижнего колонтитула
linktitle: Изображение и номер страницы в верхнем колонтитуле, встроенный в раздел нижнего колонтитула
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить изображение и номер страницы в верхний и нижний колонтитул, используя встроенные абзацы, с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
В этом уроке мы шаг за шагом покажем вам, как добавить изображение и номер страницы в раздел верхнего и нижнего колонтитула PDF-документа с помощью Aspose.PDF для .NET. Мы будем использовать предоставленный исходный код C# для создания страницы, установки верхнего и нижнего колонтитула, добавления изображения и текста, используя встроенные абзацы в заголовке PDF-документа.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и используется в вашем проекте.

## Шаг 2. Создание PDF-документа и страницы

Первым шагом является создание нового объекта Document и страницы в документе PDF. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте новый объект документа.
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Создать страницу в документе
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Приведенный выше код создает новый объект Document и пустую страницу в документе PDF.

## Шаг 3. Добавление заголовка с изображением и встроенным текстом.

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

// Создайте объект Image для изображения.
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Установить путь к изображению
image1.File = dataDir + "aspose-logo.jpg";

// Определите размеры изображения
image1.FixWidth = 50;
image1.FixHeight = 20;

// Укажите, что первый встроенный текст — это изображение.
image1.IsInLineParagraph = true;

// Создайте второй встроенный текст
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Добавляйте элементы в шапку
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Приведенный выше код создает раздел заголовка, устанавливает заголовок страницы с этим разделом, добавляет TextFragment со встроенным текстом и встроенным объектом изображения.

## Шаг 4. Сохранение измененного PDF-документа.

После добавления заголовка с изображением и встроенным текстом мы можем сохранить измененный PDF-документ. Вот как:

```csharp
// Сохраните измененный PDF-документ.
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для изображения и номера страницы в верхнем колонтитуле, нижнем колонтитуле, встроенный с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создайте экземпляр объекта Document, вызвав его пустой конструктор.
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Создайте страницу в объекте PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Создать раздел заголовка документа
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Установите заголовок для PDF-файла
page.Header = header;

// Создать текстовый объект
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Укажите цвет
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Создайте объект изображения в разделе
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Установите путь к файлу изображения
image1.File = dataDir + "aspose-logo.jpg";

// Установка ширины изображения Информация
image1.FixWidth = 50;
image1.FixHeight = 20;

// Укажите, что InlineParagraph сегмента 1 является изображением.
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

Поздравляем! Вы узнали, как добавить изображение и номер страницы в раздел верхнего и нижнего колонтитула PDF-документа, используя встроенные абзацы, с помощью Aspose.PDF для .NET. Теперь вы можете гибко настраивать верхний и нижний колонтитулы PDF-документов.

### Часто задаваемые вопросы

#### Вопрос: В чем преимущество использования встроенных абзацев для добавления изображения и текста в заголовок PDF-документа?

О: Использование встроенных абзацев позволяет легко интегрировать изображения и текст в одном абзаце, обеспечивая точный контроль над их размещением и форматированием. Этот метод особенно полезен для создания индивидуальных заголовков с визуальными элементами.

#### Вопрос: Как предоставленный исходный код C# обеспечивает встроенные абзацы для заголовка в PDF-документе?

О: Приведенный код демонстрирует, как создать PDF-документ, добавить страницу и настроить заголовок с помощью встроенных абзацев. Он добавляет TextFragment со встроенным текстом, встроенным изображением и еще одним встроенным TextFragment.

#### Вопрос: Как указать цвет встроенного текста в заголовке?

 О: Цвет встроенного текста задается с помощью`ForegroundColor` собственность`TextState` принадлежащий`TextFragment` объект.

#### Вопрос: Могу ли я настроить размеры встроенного изображения в шапке?

 О: Да, вы можете настроить размеры встроенного изображения с помощью`FixWidth` и`FixHeight` свойства`Image` объект. Это позволяет вам контролировать ширину и высоту изображения в заголовке.

#### Вопрос: Могу ли я включить в заголовок дополнительные встроенные элементы, такие как гиперссылки или другие стили шрифта?

 О: Да, вы можете включить в заголовок дополнительные встроенные элементы, создав больше`TextFragment` или`Image` объекты с желаемыми свойствами. Это позволяет дополнительно настроить заголовок, включая гиперссылки, различные стили шрифта или другие визуальные элементы.

#### Вопрос: Как я могу гарантировать, что встроенное изображение и текст будут правильно выровнены и отформатированы на разных устройствах и в различных программах просмотра?

О: Aspose.PDF для .NET гарантирует, что встроенные изображения и текст правильно выровнены и отформатированы, что приводит к единообразному виду на разных устройствах и в программах просмотра PDF.

#### Вопрос: Могу ли я применить встроенные абзацы и к нижнему колонтитулу?

 О: Да, вы можете применить ту же технику использования встроенных абзацев к нижнему колонтитулу, создав`Footer` объект и добавление к нему встроенных элементов, таких как текст и изображения.

#### Вопрос: Можно ли комбинировать встроенные абзацы с другими методами настройки верхнего или нижнего колонтитула?

О: Да, вы можете комбинировать встроенные абзацы с другими методами настройки верхнего или нижнего колонтитула, предоставляемыми Aspose.PDF для .NET, для создания более сложных и адаптированных дизайнов верхнего или нижнего колонтитула.

#### Вопрос: Могу ли я удалить или очистить встроенные элементы из заголовка, если это необходимо?

 О: Да, вы можете удалить или очистить встроенные элементы, изменив содержимое файла.`HeaderFooter` объект и удаление соответствующих встроенных абзацев.

#### Вопрос: Как применить встроенные абзацы к определенным страницам PDF-документа?

 О: Чтобы применить встроенные абзацы к конкретным страницам, вы можете создать отдельные`HeaderFooter` объекты для каждой страницы и назначайте их с помощью`Header` собственность соответствующего`Aspose.Pdf.Page` объекты.