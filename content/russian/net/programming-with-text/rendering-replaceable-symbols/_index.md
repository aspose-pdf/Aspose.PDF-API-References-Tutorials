---
title: Отображение заменяемых символов в файле PDF
linktitle: Отображение заменяемых символов в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как визуализировать заменяемые символы в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 310
url: /ru/net/programming-with-text/rendering-replaceable-symbols/
---
В этом уроке мы объясним, как визуализировать заменяемые символы в PDF-файле с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс создания PDF-файла, добавления текстового фрагмента с маркерами новой строки, настройки свойств текста, позиционирования текста и сохранения PDF-файла с помощью предоставленного исходного кода C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовые знания программирования на C#.

## Шаг 1: Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменить`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменную с путем к нужному вам каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте PDF-документ и страницу

 Далее мы создаем новый PDF-документ и добавляем в него страницу с помощью`Document` класс и`Page` класс из библиотеки Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Шаг 3: Добавьте фрагмент текста с маркерами новой строки

 Мы создаем`TextFragment` объект и включите в его текст маркеры новой строки (`Environment.NewLine`) для представления нескольких строк текста.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Шаг 4: Задайте свойства текстового фрагмента

При желании мы можем задать различные свойства для текстового фрагмента, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Шаг 5: Создание текстового абзаца и его положения

 Мы создаем`TextParagraph` объект, добавьте фрагмент текста к абзацу и задайте положение абзаца на странице.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Шаг 6: Добавьте текстовый абзац на страницу

 Мы создаем`TextBuilder` объект со страницей и добавьте текстовый абзац в текстовый конструктор.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Шаг 7: Сохраните PDF-документ.

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
// Инициализируйте новый TextFragment с текстом, содержащим требуемые маркеры новой строки.
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// При необходимости задайте свойства фрагмента текста.
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Создать объект TextParagraph
TextParagraph par = new TextParagraph();
// Добавить новый TextFragment в абзац
par.AppendLine(textFragment);
// Установить позицию абзаца
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

В этом уроке вы узнали, как визуализировать заменяемые символы в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете создать PDF, добавить текст с маркерами новой строки, задать свойства текста, разместить текст на странице и сохранить PDF.

### Часто задаваемые вопросы

#### В: Какова цель руководства «Отображение заменяемых символов в файле PDF»?

A: Учебник "Rendering Replaceable Symbols In PDF File" демонстрирует, как использовать библиотеку Aspose.PDF для .NET для создания PDF-документа, включающего заменяемые символы. Эти символы представлены в виде текстовых фрагментов с маркерами новой строки для создания многострочного содержимого.

#### В: Зачем мне отображать заменяемые символы в PDF-документе?

A: Отображение заменяемых символов полезно, когда вам нужно динамически генерировать содержимое PDF, которое включает переменную или пользовательскую информацию. Эти символы действуют как заполнители, которые могут быть заменены фактическими данными во время выполнения, такими как значения полей формы или персонализированные данные.

#### В: Как настроить каталог документов?

A: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором вы хотите сохранить сгенерированный PDF-файл.

#### В: Как отобразить заменяемые символы в PDF-документе с помощью библиотеки Aspose.PDF?

A: Учебное пособие проведет вас через весь процесс шаг за шагом:

1.  Создайте новый PDF-документ с помощью`Document` сорт.
2.  Добавьте страницу в документ с помощью`Page` сорт.
3.  Создать`TextFragment` объект с маркерами новой строки (`Environment.NewLine`) для представления многострочного содержимого.
4. Настройте свойства текстового фрагмента, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана.
5.  Создать`TextParagraph` объект, добавьте к нему фрагмент текста и задайте положение абзаца на странице.
6.  Создать`TextBuilder` объект со страницей и добавьте к нему текстовый абзац.
7. Сохраните PDF-документ.

#### В: Какова цель использования маркеров новой строки (`Environment.NewLine`) in the text fragment?

 A: Маркеры новой строки используются для создания многострочного содержимого в пределах одного текстового фрагмента. С помощью`Environment.NewLine`вы можете указать, где в тексте должны располагаться переносы строк.

#### В: Могу ли я настроить внешний вид заменяемых символов?

A: Да, вы можете настроить различные свойства текстового фрагмента, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана. Эти свойства определяют визуальный вид заменяемых символов в документе PDF.

#### В: Как указать положение текста на странице?

 A: Вы можете задать положение текста, создав`TextParagraph` объект и использование`Position` свойство для указания координат X и Y на странице, где должен располагаться абзац.

#### В: Каков ожидаемый результат выполнения предоставленного кода?

A: Следуя руководству и запустив предоставленный код C#, вы создадите документ PDF, включающий заменяемые символы. Заменяемые символы будут представлены в виде текстовых фрагментов с маркерами новой строки и настраиваемыми свойствами.

#### В: Могу ли я использовать этот подход для динамического создания персонализированных PDF-документов?

A: Да, этот подход подходит для динамического создания PDF-документов с персонализированной информацией. Заменяя заменяемые символы реальными данными, вы можете создавать персонализированный PDF-контент для каждого пользователя или сценария.