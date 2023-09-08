---
title: Отрисовка заменяемых символов в PDF-файле
linktitle: Отрисовка заменяемых символов в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как отображать заменяемые символы в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 310
url: /ru/net/programming-with-text/rendering-replaceable-symbols/
---
В этом уроке мы объясним, как отображать заменяемые символы в файле PDF с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс создания PDF-файла, добавления фрагмента текста с маркерами новой строки, установки свойств текста, позиционирования текста и сохранения PDF-файла, используя предоставленный исходный код C#.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir`переменная с путем к желаемому каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте PDF-документ и страницу.

 Далее мы создаем новый PDF-документ и добавляем к нему страницу с помощью`Document` класс и`Page` класс из библиотеки Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Шаг 3. Добавьте фрагмент текста с маркерами новой строки

 Мы создаем`TextFragment`объект и установите в его тексте маркеры новой строки (`Environment.NewLine`) для представления нескольких строк текста.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Шаг 4. Установите свойства фрагмента текста

При желании мы можем установить различные свойства для фрагмента текста, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Шаг 5. Создайте текстовый абзац и позицию

 Мы создаем`TextParagraph` объект, добавьте фрагмент текста в абзац и задайте положение абзаца на странице.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Шаг 6. Добавьте текстовый абзац на страницу

 Мы создаем`TextBuilder` объект со страницей и добавьте текстовый абзац в построитель текста.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Шаг 7. Сохраните PDF-документ.

Наконец, мы сохраняем PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Пример исходного кода для рендеринга заменяемых символов с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Инициализировать новый TextFragment текстом, содержащим необходимые маркеры новой строки.
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// При необходимости задайте свойства фрагмента текста
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Создать объект TextParagraph
TextParagraph par = new TextParagraph();
// Добавить новый TextFragment в абзац
par.AppendLine(textFragment);
// Установить положение абзаца
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Создать объект TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Добавьте TextParagraph с помощью TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Заключение

В этом уроке вы узнали, как отображать заменяемые символы в PDF-документе с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы можете создать PDF-файл, добавить текст с маркерами новой строки, установить свойства текста, расположить текст на странице и сохранить PDF-файл.

### Часто задаваемые вопросы

#### Вопрос: Какова цель руководства «Отображение заменяемых символов в PDF-файле»?

О: Учебное пособие «Рендеринг заменяемых символов в PDF-файле» демонстрирует, как использовать библиотеку Aspose.PDF для .NET для создания PDF-документа, содержащего заменяемые символы. Эти символы представлены в виде текстовых фрагментов с маркерами новой строки для создания многострочного содержимого.

#### Вопрос: Зачем мне отображать заменяемые символы в PDF-документе?

О: Отображение заменяемых символов полезно, когда вам нужно динамически генерировать содержимое PDF, включающее переменную или специфичную для пользователя информацию. Эти символы действуют как заполнители, которые можно заменить фактическими данными во время выполнения, такими как значения полей формы или персонализированные данные.

#### Вопрос: Как настроить каталог документов?

О: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором вы хотите сохранить созданный PDF-файл.

#### Вопрос: Как визуализировать заменяемые символы в PDF-документе с помощью библиотеки Aspose.PDF?

Ответ: Учебное пособие шаг за шагом проведет вас через весь процесс:

1.  Создайте новый PDF-документ, используя`Document` сорт.
2.  Добавьте страницу в документ с помощью`Page` сорт.
3.  Создать`TextFragment` объект с маркерами новой строки (`Environment.NewLine`) для представления многострочного содержимого.
4. Настройте свойства фрагмента текста, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана.
5.  Создать`TextParagraph` объект, добавьте к нему фрагмент текста и задайте положение абзаца на странице.
6.  Создать`TextBuilder` объект со страницей и добавьте к нему текстовый абзац.
7. Сохраните PDF-документ.

#### Вопрос: Какова цель использования маркеров новой строки (`Environment.NewLine`) in the text fragment?

 О: Маркеры новой строки используются для создания многострочного содержимого внутри одного фрагмента текста. Используя`Environment.NewLine`, вы можете указать, где в тексте должны быть разрывы строк.

#### Вопрос: Могу ли я настроить внешний вид заменяемых символов?

О: Да, вы можете настроить различные свойства текстового фрагмента, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана. Эти свойства определяют внешний вид заменяемых символов в документе PDF.

#### Вопрос: Как указать положение текста на странице?

 О: Вы можете установить положение текста, создав`TextParagraph` объект и используя`Position` свойство, позволяющее указать координаты X и Y на странице, где должен располагаться абзац.

#### Вопрос: Каков ожидаемый результат выполнения предоставленного кода?

О: Следуя инструкциям и запустив предоставленный код C#, вы создадите PDF-документ, содержащий заменяемые символы. Заменяемые символы будут представлены в виде текстовых фрагментов с маркерами новой строки и настраиваемыми свойствами.

#### Вопрос: Могу ли я использовать этот подход для динамического создания персонализированных PDF-документов?

О: Да, этот подход подходит для динамического создания PDF-документов с персонализированной информацией. Заменяя заменяемые символы фактическими данными, вы можете создавать индивидуальный PDF-контент для каждого пользователя или сценария.