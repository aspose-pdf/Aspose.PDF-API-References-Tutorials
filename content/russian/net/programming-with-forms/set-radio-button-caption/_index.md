---
title: Установить заголовок радиокнопки
linktitle: Установить заголовок радиокнопки
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как использовать Aspose.PDF для .NET, чтобы задать заголовок переключателя в форме PDF.
type: docs
weight: 280
url: /ru/net/programming-with-forms/set-radio-button-caption/
---
В этом руководстве мы шаг за шагом объясним, как использовать библиотеку Aspose.PDF для .NET для определения заголовка переключателя в форме PDF. Мы покажем вам, как получить доступ к полю переключателя, создать новый параметр переключателя и настроить заголовок кнопки.

## Шаг 1: Настройка каталога документов

 Первый шаг — настроить каталог документов, в котором находится PDF-форма, с которой вы хотите работать. Вы можете использовать`dataDir` переменная для указания пути к каталогу.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 2: Загрузка исходной PDF-формы

 На этом этапе мы загрузим исходную PDF-форму с помощью`Aspose.Pdf.Facades.Form` класс Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Убедитесь, что PDF-файл, содержащий форму, присутствует в указанном каталоге документов.

## Шаг 3: Редактирование заголовка переключателя

Мы пройдемся по именам полей формы и найдем поля радиокнопок. Если будет найдено соответствующее поле, мы создадим новый вариант радиокнопки с пользовательским заголовком и добавим его в существующее поле.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Создать объект TextParagraph
TextParagraph par = new TextParagraph();
// Установить позицию абзаца
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Укажите режим переноса слов
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Добавьте новый TextFragment в абзац
par.AppendLine(updatedFragment);
// Добавьте TextParagraph с помощью TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

При необходимости настройте переключатель «Подпись» и другие параметры.

## Шаг 4: Сохранение полученного PDF-файла

 Теперь, когда мы закончили изменять заголовок переключателя, мы можем сохранить полученный PDF-файл с помощью команды`Save` Метод`Document` сорт.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Обязательно укажите полный путь и имя файла для полученного PDF-файла.

### Пример исходного кода для установки заголовка радиокнопки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить исходную форму PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Создать объект TextParagraph
		TextParagraph par = new TextParagraph();
		// Установить позицию абзаца
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Укажите режим переноса слов
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Добавить новый TextFragment в абзац
		par.AppendLine(updatedFragment);
		// Добавьте TextParagraph с помощью TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Заключение

В этом руководстве мы узнали, как использовать библиотеку Aspose.PDF для .NET для установки заголовка для переключателя в форме PDF. Выполнив описанные шаги, вы сможете настроить параметры переключателя и изменить заголовок по мере необходимости. Не стесняйтесь и дальше изучать функции Aspose.PDF для .NET, чтобы расширить возможности манипулирования файлами PDF.

### Часто задаваемые вопросы

#### В: Могу ли я использовать Aspose.PDF для .NET для установки подписей к переключателям в форме PDF?

A: Да, вы можете использовать Aspose.PDF для .NET для установки подписей для радиокнопок в форме PDF. Предоставленный пример исходного кода демонстрирует, как получить доступ к полю радиокнопки, создать новый параметр радиокнопки с пользовательским заголовком и обновить существующее поле.

#### В: Как настроить внешний вид заголовка переключателя, например размер шрифта и цвет?

 A: Вы можете настроить внешний вид заголовка переключателя, изменив свойства`TextFragment` используется для подписи. Например, вы можете задать шрифт, размер шрифта, цвет, межстрочный интервал и другие параметры форматирования текста.

#### В: Можно ли добавить несколько вариантов переключателей с разными подписями в одну группу переключателей?

A: Да, вы можете добавить несколько вариантов радиокнопок с разными подписями в одну группу радиокнопок. Каждый вариант будет представлять другой выбор, и пользователи могут выбрать только один вариант из группы.

#### В: Могу ли я использовать Aspose.PDF для .NET для изменения других полей формы в PDF-документе?

A: Да, Aspose.PDF для .NET предоставляет полный набор функций для управления различными полями форм в документе PDF, такими как текстовые поля, флажки, раскрывающиеся списки и т. д. Вы можете использовать библиотеку для установки значений, изменения внешнего вида и добавления интерактивности в поля форм.

#### В: Поддерживает ли Aspose.PDF для .NET работу с PDF-файлами, созданными из других источников, например, отсканированными документами?

A: Да, Aspose.PDF for .NET поддерживает работу с PDF-файлами, созданными из различных источников, включая отсканированные документы. Библиотека предоставляет возможности OCR (оптического распознавания символов) для извлечения текста из отсканированных PDF-файлов и программной обработки содержимого.