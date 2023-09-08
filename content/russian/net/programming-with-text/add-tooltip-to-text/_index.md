---
title: Добавить подсказку к тексту в PDF-файле
linktitle: Добавить подсказку к тексту в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавлять всплывающие подсказки к тексту в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-text/add-tooltip-to-text/
---
Это руководство проведет вас через процесс добавления всплывающих подсказок к тексту в PDF-файле с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файле кода, в котором вы хотите добавить всплывающие подсказки к тексту, добавьте следующие директивы в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте образец документа с текстом
 Создать новый`Document` объект и добавлять страницы с фрагментами текста. В предоставленном коде в документ добавляются два текстовых фрагмента с соответствующим текстом подсказки.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Шаг 5: Откройте документ и найдите фрагменты текста.
 Загрузите созданный документ с помощью`Document` конструктор и найдите фрагменты текста, которым нужны всплывающие подсказки, с помощью`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Шаг 6: Добавьте всплывающие подсказки к текстовым фрагментам
 Прокрутите извлеченные фрагменты текста и создайте невидимые кнопки на их местах. Назначьте нужный текст всплывающей подсказки`AlternateName` собственность`ButtonField`. Добавьте поля кнопок в форму документа.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Шаг 7. Повторите эти действия для дополнительных фрагментов текста с длинными подсказками.
Повторите шаги 5 и 6 для фрагментов текста с длинными подсказками. Измените критерии поиска и текст всплывающей подсказки соответствующим образом.

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

## Шаг 8. Сохраните измененный документ.
 Сохраните измененный PDF-документ, используя`Save` метод`Document` объект.

```csharp
document. Save(outputFile);
```

### Пример исходного кода для добавления всплывающей подсказки в текст с использованием Aspose.PDF для .NET 
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
// Создайте объект TextAbsorber, чтобы найти все фразы, соответствующие регулярному выражению.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Примите поглотитель для страниц документа
document.Pages.Accept(absorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragments = absorber.TextFragments;
// Перебирать фрагменты
foreach (TextFragment fragment in textFragments)
{
	// Создать невидимую кнопку в позиции фрагмента текста
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Значение AlternateName будет отображаться во всплывающей подсказке приложением просмотра.
	field.AlternateName = "Tooltip for text.";
	// Добавить поле кнопки в документ
	document.Form.Add(field);
}
// Далее будет образец очень длинной всплывающей подсказки.
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
Вы успешно добавили всплывающие подсказки в текст PDF-документа с помощью Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути к выходному файлу.

## Часто задаваемые вопросы

#### Вопрос: Чему посвящено это руководство?

О: В этом руководстве основное внимание уделяется добавлению всплывающих подсказок к тексту в файле PDF с использованием библиотеки Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует шаги, необходимые для достижения этой цели.

#### Вопрос: Какие пространства имен необходимо импортировать для этого руководства?

О: В файле кода, в котором вы хотите добавить всплывающие подсказки к тексту, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как создать образец документа с текстом?

 О: На шаге 4 вы создадите новый`Document` объект и добавлять страницы с фрагментами текста. Предоставленный код добавляет два текстовых фрагмента с соответствующим текстом всплывающей подсказки.

#### Вопрос: Как открыть документ и найти фрагменты текста?

 О: На шаге 5 вы загрузите созданный документ, используя`Document` конструктор и найдите фрагменты текста, требующие всплывающих подсказок, с помощью`TextFragmentAbsorber`.

#### Вопрос: Как добавить подсказки к фрагментам текста?

 О: На шаге 6 вы пройдете по извлеченным фрагментам текста и создадите невидимые кнопки на их позициях. Текст всплывающей подсказки присваивается`AlternateName` собственность`ButtonField`который добавляется в форму документа.

#### Вопрос: Как повторить процедуру для дополнительных фрагментов текста с длинными подсказками?

О: Для фрагментов текста с длинными подсказками повторите шаги 5 и 6. Измените критерии поиска и текст подсказки соответствующим образом.

#### Вопрос: Как сохранить измененный документ?

 О: На шаге 8 вы сохраните измененный PDF-документ, используя`Save` метод`Document` объект.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы узнали, как улучшить свой PDF-документ, добавив всплывающие подсказки к тексту с помощью Aspose.PDF для .NET. Это может предоставить читателям ценную дополнительную информацию при взаимодействии с содержимым PDF.