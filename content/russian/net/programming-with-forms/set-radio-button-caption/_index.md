---
title: Установить заголовок переключателя
linktitle: Установить заголовок переключателя
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как использовать Aspose.PDF для .NET, чтобы установить заголовок для переключателя в форме PDF.
type: docs
weight: 280
url: /ru/net/programming-with-forms/set-radio-button-caption/
---
В этом руководстве мы шаг за шагом объясним, как использовать библиотеку Aspose.PDF для .NET для определения заголовка переключателя в форме PDF. Мы покажем вам, как получить доступ к полю переключателя, создать новый параметр переключателя и настроить заголовок кнопки.

## Шаг 1. Настройка каталога документов

 Первым шагом является настройка каталога документов, в котором находится PDF-форма, над которой вы хотите работать. Вы можете использовать`dataDir` переменная для указания пути к каталогу.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 2. Загрузка исходной PDF-формы

 На этом этапе мы загрузим исходную PDF-форму, используя`Aspose.Pdf.Facades.Form` класс Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Убедитесь, что PDF-файл, содержащий форму, присутствует в указанном каталоге документов.

## Шаг 3. Редактирование заголовка переключателя

Мы пройдемся по именам полей формы и найдем поля переключателей. Если подходящее поле найдено, мы создадим новый переключатель с настраиваемым заголовком и добавим его в существующее поле.

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
// Создайте объект TextParagraph.
TextParagraph par = new TextParagraph();
// Установить положение абзаца
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Укажите режим переноса слов
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Добавьте новый TextFragment в абзац.
par.AppendLine(updatedFragment);
// Добавьте TextParagraph с помощью TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Настройте переключатель заголовка и другие параметры по мере необходимости.

## Шаг 4. Сохранение полученного PDF-файла

 Теперь, когда мы закончили изменять заголовок переключателя, мы можем сохранить полученный PDF-файл, используя команду`Save` метод`Document` сорт.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Обязательно укажите полный путь и имя файла полученного PDF-файла.

### Пример исходного кода для установки заголовка переключателя с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить исходную PDF-форму
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
		// Установить положение абзаца
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

В этом руководстве мы узнали, как использовать библиотеку Aspose.PDF для .NET, чтобы установить заголовок для переключателя в форме PDF. Выполнив описанные шаги, вы можете настроить параметры переключателя и при необходимости изменить заголовок. Не стесняйтесь продолжить изучение возможностей Aspose.PDF для .NET, чтобы расширить возможности управления PDF-файлами.

### Часто задаваемые вопросы

#### Вопрос: Могу ли я использовать Aspose.PDF для .NET для установки заголовков переключателей в форме PDF?

О: Да, вы можете использовать Aspose.PDF для .NET, чтобы установить подписи для переключателей в форме PDF. Предоставленный пример исходного кода демонстрирует, как получить доступ к полю переключателя, создать новый параметр переключателя с настраиваемым заголовком и обновить существующее поле.

#### Вопрос: Как настроить внешний вид заголовка переключателя, например размер и цвет шрифта?

 О: Вы можете настроить внешний вид заголовка переключателя, настроив свойства переключателя.`TextFragment` используется для подписи. Например, вы можете установить шрифт, размер шрифта, цвет, межстрочный интервал и другие параметры форматирования текста.

#### Вопрос: Можно ли добавить несколько переключателей с разными заголовками в одну группу переключателей?

О: Да, вы можете добавить несколько вариантов переключателей с разными заголовками в одну группу переключателей. Каждый вариант представляет собой отдельный вариант, и пользователи могут выбрать только один вариант из группы.

#### Вопрос: Могу ли я использовать Aspose.PDF для .NET для изменения других полей формы в PDF-документе?

О: Да, Aspose.PDF для .NET предоставляет полный набор функций для управления различными полями форм в PDF-документе, такими как текстовые поля, флажки, раскрывающиеся списки и многое другое. Вы можете использовать библиотеку для установки значений, изменения внешнего вида и добавления интерактивности в поля форм.

#### Вопрос: Поддерживает ли Aspose.PDF for .NET работу с PDF-файлами, созданными из других источников, например, отсканированных документов?

О: Да, Aspose.PDF для .NET поддерживает работу с PDF-файлами, созданными из различных источников, включая отсканированные документы. Библиотека предоставляет возможности OCR (оптического распознавания символов) для извлечения текста из отсканированных PDF-файлов и программного управления содержимым.