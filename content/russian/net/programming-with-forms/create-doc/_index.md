---
title: Создать документ
linktitle: Создать документ
second_title: Справочник по API Aspose.PDF для .NET
description: Легко создавайте документы с переключателями с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-forms/create-doc/
---
В этом уроке мы покажем вам, как создать документ с радиокнопками, используя Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы провести вас через этот процесс.

##Шаг 1: Подготовка

Сначала убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте новый документ

Создайте новый объект Document для хранения PDF-документа:

```csharp
Document doc = new Document();
```

## Шаг 3: Добавьте страницу

Добавить новую страницу в документ:

```csharp
Page page = doc.Pages.Add();
```

## Шаг 4: Добавьте поле переключателя

Создайте поле переключателя и задайте его положение и размер:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Шаг 5: Добавьте параметры переключателя

Добавьте нужные параметры в поле радиокнопки. Вы можете задать координаты и размер каждого параметра по мере необходимости:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Шаг 6: Добавьте поле переключателя в форму.

Добавьте поле переключателя в коллекцию полей формы документа:

```csharp
doc.Form.Add(field);
```

## Шаг 7: Сохраните документ.

Сохраните PDF-документ:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для создания документа с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Создать новый документ
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Добавить поле переключателя
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Добавьте параметры переключателя. Обратите внимание, что эти параметры расположены
	// Ни по горизонтали, ни по вертикали.
	// Вы можете попробовать задать для них любые координаты (и даже размер).
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Сохраните PDF-документ
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом уроке мы узнали, как создать документ с радиокнопками с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко добавлять радиокнопки в свои PDF-документы с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### В: Можно ли настроить внешний вид переключателей в документе с помощью Aspose.PDF для .NET?

A: Да, вы можете настроить внешний вид радиокнопок в документе с помощью Aspose.PDF для .NET. Вы можете задать такие свойства, как размер, цвет, стиль границы и многое другое, чтобы настроить внешний вид радиокнопок.

#### В: Как добавить группы переключателей с взаимоисключающими опциями?

A: Чтобы создать взаимоисключающие опции, вы можете добавить несколько полей радиокнопок с одинаковым именем. Это гарантирует, что при выборе одной опции другие опции с тем же именем будут автоматически отменены.

#### В: Можно ли установить для переключателей параметр, выбранный по умолчанию?

A: Да, вы можете установить выбранный по умолчанию вариант для радиокнопок с помощью Aspose.PDF для .NET. Вы можете использовать`Selected` собственность`RadioButtonOptionField` объект, чтобы отметить параметр как выбранный по умолчанию.

#### В: Могу ли я добавить обработчики событий к переключателям?

 A: Да, вы можете добавить обработчики событий к радиокнопкам с помощью Aspose.PDF для .NET. Вы можете связать действия JavaScript, такие как`OnValueChanged`, к переключателям для выполнения определенных действий, когда пользователь выбирает опцию.

#### В: Как извлечь выбранный параметр из группы переключателей после того, как пользователь сделал выбор?

 A: Вы можете получить выбранный параметр из группы радиокнопок с помощью Aspose.PDF для .NET. После того, как пользователь сделает выбор, вы можете получить доступ к`Selected` собственность`RadioButtonOptionField` объект для проверки выбранного варианта.