---
title: Добавить всплывающую подсказку к тексту
linktitle: Добавить всплывающую подсказку к тексту
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять всплывающие подсказки к тексту в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-text/add-tooltip-to-text/
---

Это руководство проведет вас через процесс добавления всплывающих подсказок к тексту в документе PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файле кода, где вы хотите добавить всплывающие подсказки к тексту, добавьте следующие директивы using вверху файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте образец документа с текстом
 Создать новый`Document` объекта и добавить страницы с текстовыми фрагментами. В предоставленном коде в документ добавляются два текстовых фрагмента с соответствующим текстом всплывающей подсказки.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Шаг 5: Откройте документ и найдите фрагменты текста
 Загрузите созданный документ с помощью`Document` конструктор и найти фрагменты текста, которым нужны всплывающие подсказки, используя`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Шаг 6: Добавьте всплывающие подсказки к фрагментам текста
 Прокрутите извлеченные текстовые фрагменты и создайте невидимые кнопки на их позициях. Назначьте желаемый текст всплывающей подсказки`AlternateName` собственность`ButtonField`. Добавьте поля кнопок в форму документа.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Шаг 7: Повторите для дополнительных текстовых фрагментов с длинными всплывающими подсказками.
Повторите шаги 5 и 6 для текстовых фрагментов с длинными всплывающими подсказками. Соответственно измените критерии поиска и текст всплывающей подсказки.

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

## Шаг 8: Сохраните измененный документ
 Сохраните измененный PDF-документ с помощью кнопки`Save` метод`Document` объект.

```csharp
document. Save(outputFile);
```

### Пример исходного кода для добавления всплывающей подсказки к тексту с использованием Aspose.PDF для .NET 
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
// Примите абсорбер для страниц документа
document.Pages.Accept(absorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragments = absorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment fragment in textFragments)
{
	// Создать невидимую кнопку на позиции текстового фрагмента
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Значение AlternateName будет отображаться в виде всплывающей подсказки приложением просмотра
	field.AlternateName = "Tooltip for text.";
	// Добавить поле кнопки в документ
	document.Form.Add(field);
}
// Далее будет образец очень длинной всплывающей подсказки
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
Вы успешно добавили всплывающие подсказки к тексту в документе PDF с помощью Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.