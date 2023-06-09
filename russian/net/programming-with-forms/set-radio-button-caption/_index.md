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

 Первый шаг — настроить каталог документов, в котором находится PDF-форма, с которой вы хотите работать. Вы можете использовать`dataDir`переменная для указания пути к каталогу.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 2. Загрузка исходной PDF-формы

 На этом шаге мы загрузим исходную форму PDF, используя`Aspose.Pdf.Facades.Form`класс Aspose.PDF.

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