---
title: Добавить подсказку к тексту в PDF-файле
linktitle: Добавить подсказку к тексту в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как добавлять всплывающие подсказки к тексту в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-text/add-tooltip-to-text/
---
Этот урок проведет вас через процесс добавления подсказок к тексту в PDF-файле с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, где вы хотите добавить всплывающие подсказки к тексту, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Создайте образец документа с текстом
 Создать новый`Document` объект и добавить страницы с текстовыми фрагментами. В предоставленном коде два текстовых фрагмента добавляются в документ с соответствующим текстом подсказки.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Шаг 5: Откройте документ и найдите фрагменты текста.
 Загрузите созданный документ с помощью`Document` конструктор и найдите фрагменты текста, которым нужны подсказки, используя`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Шаг 6: Добавьте подсказки к текстовым фрагментам
 Пройдитесь по извлеченным фрагментам текста и создайте невидимые кнопки на их позициях. Назначьте нужный текст подсказки`AlternateName` собственность`ButtonField`. Добавьте поля кнопок в форму документа.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Шаг 7: Повторите для дополнительных фрагментов текста с длинными подсказками.
Повторите шаги 5 и 6 для фрагментов текста с длинными подсказками. Измените критерии поиска и текст подсказки соответствующим образом.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Шаг 8: Сохраните измененный документ.
 Сохраните измененный PDF-документ с помощью`Save` Метод`Document` объект.

```csharp
document. Save(outputFile);
```

### Пример исходного кода для добавления подсказки к тексту с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Создать образец документа с текстом
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Открыть документ с текстом
Document document = new Document(outputFile);
// Создайте объект TextAbsorber для поиска всех фраз, соответствующих регулярному выражению.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Принять поглотитель для страниц документа
document.Pages.Accept(absorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragments = absorber.TextFragments;
// Просмотрите фрагменты
foreach (TextFragment fragment in textFragments)
{
	// Создать невидимую кнопку в позиции текстового фрагмента
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Значение AlternateName будет отображаться в виде подсказки в приложении-просмотрщике
	field.AlternateName = "Tooltip for text.";
	// Добавить поле кнопки в документ
	document.Form.Add(field);
}
// Далее будет пример очень длинной подсказки
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Установить очень длинный текст
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Сохранить документ
document.Save(outputFile);
```

## Заключение
Вы успешно добавили подсказки к тексту в документе PDF с помощью Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути выходного файла.

## Часто задаваемые вопросы

#### В: На чем сосредоточено внимание в этом уроке?

A: В этом руководстве основное внимание уделяется добавлению всплывающих подсказок к тексту в файле PDF с использованием библиотеки Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует шаги, необходимые для достижения этого.

#### В: Какие пространства имен необходимо импортировать для этого руководства?

A: В файле кода, где вы хотите добавить подсказки к тексту, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### В: Как указать каталог документа?

 A: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как создать образец документа с текстом?

 A: На шаге 4 вы создадите новый`Document` объект и добавить страницы с текстовыми фрагментами. Приведенный код добавляет два текстовых фрагмента с соответствующим текстом подсказки.

#### В: Как открыть документ и найти фрагменты текста?

 A: На шаге 5 вы загрузите созданный документ с помощью`Document` конструктор и найдите фрагменты текста, требующие подсказок, используя`TextFragmentAbsorber`.

#### В: Как добавить подсказки к текстовым фрагментам?

 A: На шаге 6 вы будете проходить по извлеченным фрагментам текста и создавать невидимые кнопки на их позициях. Текст подсказки назначается`AlternateName` собственность`ButtonField`который добавляется в форму документа.

#### В: Как повторить процесс для дополнительных фрагментов текста с длинными подсказками?

A: Для текстовых фрагментов с длинными подсказками повторите шаги 5 и 6. Измените критерии поиска и текст подсказки соответствующим образом.

#### В: Как сохранить измененный документ?

 A: На шаге 8 вы сохраните измененный PDF-документ с помощью`Save` Метод`Document` объект.

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы узнали, как улучшить свой PDF-документ, добавив подсказки к тексту с помощью Aspose.PDF для .NET. Это может предоставить читателям ценную дополнительную информацию при их взаимодействии с содержимым PDF.