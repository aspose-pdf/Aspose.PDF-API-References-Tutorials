---
title: Установить заголовок радиокнопки
linktitle: Установить заголовок радиокнопки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET, чтобы установить заголовок для переключателя в форме PDF.
type: docs
weight: 280
url: /ru/net/programming-with-forms/set-radio-button-caption/
---
В этом руководстве мы шаг за шагом объясним, как использовать библиотеку Aspose.PDF для .NET, чтобы определить заголовок переключателя в форме PDF. Мы покажем вам, как получить доступ к полю переключателя, создать новый параметр переключателя и настроить заголовок кнопки.

## Шаг 1. Настройка каталога документов

 Первый шаг — настроить каталог документов, в котором находится PDF-форма, с которой вы хотите работать. Вы можете использовать`dataDir` переменная для указания пути к каталогу.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 2. Загрузка исходной PDF-формы

 На этом шаге мы загрузим исходную форму PDF, используя`Aspose.Pdf.Facades.Form` класс Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Убедитесь, что файл PDF, содержащий форму, находится в указанной папке документов.

## Шаг 3. Редактирование заголовка радиокнопки

Мы пройдемся по именам полей формы и найдем поля переключателей. Если соответствующее поле будет найдено, мы создадим новый переключатель с настраиваемой подписью и добавим его в существующее поле.

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
// Создайте объект TextParagraph
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

При необходимости настройте переключатель заголовка и другие параметры.

## Шаг 4: Сохранение полученного PDF-файла

 Теперь, когда мы закончили изменять заголовок переключателя, мы можем сохранить полученный PDF-файл, используя`Save` метод`Document` сорт.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Обязательно укажите полный путь и имя файла для полученного PDF-файла.

### Пример исходного кода для установки заголовка радиокнопки с использованием Aspose.PDF для .NET 
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

В этом руководстве мы узнали, как использовать библиотеку Aspose.PDF для .NET, чтобы установить заголовок для переключателя в форме PDF. Следуя описанным шагам, вы можете настроить параметры переключателя и изменить заголовок по мере необходимости. Изучите возможности Aspose.PDF для .NET, чтобы расширить возможности работы с PDF-файлами.

### Часто задаваемые вопросы

#### В: Могу ли я использовать Aspose.PDF для .NET, чтобы установить подписи для радиокнопок в PDF-форме?

О: Да, вы можете использовать Aspose.PDF для .NET, чтобы установить подписи для переключателей в форме PDF. В предоставленном образце исходного кода показано, как получить доступ к полю переключателя, создать новый параметр переключателя с пользовательским заголовком и обновить существующее поле.

#### Вопрос. Как настроить внешний вид подписи переключателя, например размер и цвет шрифта?

 О: Вы можете настроить внешний вид заголовка радиокнопки, изменив свойства`TextFragment` используется для заголовка. Например, вы можете установить шрифт, размер шрифта, цвет, межстрочный интервал и другие параметры форматирования текста.

#### Вопрос. Можно ли добавить несколько вариантов переключателей с разными заголовками в одну группу переключателей?

О: Да, вы можете добавить несколько вариантов переключателей с разными заголовками в одну группу переключателей. Каждый вариант будет представлять другой вариант, и пользователи могут выбрать только один вариант из группы.

#### В: Могу ли я использовать Aspose.PDF для .NET для изменения других полей формы в документе PDF?

О: Да, Aspose.PDF для .NET предоставляет полный набор функций для управления различными полями формы в документе PDF, такими как текстовые поля, флажки, раскрывающиеся списки и многое другое. Вы можете использовать библиотеку для установки значений, изменения внешнего вида и добавления интерактивности в поля формы.

#### В: Поддерживает ли Aspose.PDF для .NET работу с PDF-файлами, созданными из других источников, например, с отсканированными документами?

О: Да, Aspose.PDF для .NET поддерживает работу с PDF-файлами, созданными из различных источников, включая отсканированные документы. Библиотека предоставляет возможности OCR (оптическое распознавание символов) для извлечения текста из отсканированных PDF-файлов и программного управления содержимым.