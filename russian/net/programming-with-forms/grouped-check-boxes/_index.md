---
title: Сгруппированные флажки в документе PDF
linktitle: Сгруппированные флажки в документе PDF
second_title: Aspose.PDF для справочника API .NET
description: Легко создавайте сгруппированные флажки в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 170
url: /ru/net/programming-with-forms/grouped-check-boxes/
---
В этом руководстве мы покажем вам, как создавать сгруппированные флажки в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте экземпляр объекта документа

Создайте экземпляр объекта Document:

```csharp
Document pdfDocument = new Document();
```

## Шаг 3: Добавьте страницу в документ PDF

Добавьте страницу в документ PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Шаг 4: Создайте экземпляр объекта RadioButtonField

Создайте объект RadioButtonField с номером страницы в качестве аргумента:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Шаг 5: Добавьте параметры переключателя

Добавьте параметры переключателя с помощью объекта RadioButtonOptionField и укажите их положение с помощью объекта Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Шаг 6. Настройте параметры переключателя

Настройте параметры переключателя, задав их стиль, границу и внешний вид:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Шаг 7: Добавьте переключатели в форму

Добавьте переключатели в объект формы документа:

```csharp
pdfDocument.Form.Add(radio);
```

## Шаг 8: Сохраните документ

Сохраните PDF-документ:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для сгруппированных флажков с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Создать объект документа
	Document pdfDocument = new Document();
	// Добавить страницу в файл PDF
	Page page = pdfDocument.Pages.Add();
	// Создайте объект RadioButtonField с номером страницы в качестве аргумента.
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Добавьте первый параметр переключателя, а также укажите его происхождение с помощью объекта Rectangle.
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Добавить переключатель, чтобы сформировать объект объекта документа
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Сохраните PDF-документ
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом руководстве мы узнали, как создавать сгруппированные флажки в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко добавить пользовательские параметры переключателя и объединить их в свои PDF-документы с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### В: Что такое сгруппированные флажки в документе PDF?

О. Сгруппированные флажки в документе PDF относятся к набору переключателей, сгруппированных вместе. Радиокнопки позволяют пользователям выбирать только один вариант из группы взаимоисключающих вариантов. Когда выбран один переключатель, другие в той же группе автоматически отменяются. Это групповое поведение полезно, когда вы хотите предоставить пользователям несколько вариантов, но ограничиваете их выбор только одним вариантом.

#### В: Могу ли я настроить внешний вид сгруппированных флажков в Aspose.PDF для .NET?

О: Да, вы можете настроить внешний вид сгруппированных флажков в Aspose.PDF для .NET. API предоставляет различные параметры для установки стиля, границы и внешнего вида переключателей. Вы можете определить положение каждого параметра, выбрать один из стилей блока (например, квадрат, круг, крест) и настроить свойства границы для достижения желаемого визуального представления.

#### В: Как добавить сгруппированные флажки на определенную страницу документа PDF?

О. Чтобы добавить сгруппированные флажки на определенную страницу документа PDF, необходимо создать экземпляр`RadioButtonField` объект с желаемым номером страницы в качестве аргумента. Затем создайте`RadioButtonOptionField` объекты, представляющие каждую опцию переключателя, и укажите их положение, используя`Rectangle` объект. Наконец, добавьте эти параметры в`RadioButtonField` и настроить их внешний вид по мере необходимости перед добавлением`RadioButtonField` к форме документа.

#### В: Могу ли я добавить несколько групп флажков в один PDF-документ?

 О: Да, вы можете добавить несколько групп флажков в один документ PDF. Каждая группа должна иметь уникальный`RadioButtonField` объект, и`RadioButtonOptionField` объекты в каждой группе должны иметь одну и ту же страницу и уникальные имена для своих опций. Это гарантирует, что переключатели в каждой группе работают правильно, а выбор является взаимоисключающим.

#### В: Поддерживаются ли сгруппированные флажки во всех программах и программах для просмотра PDF?

О: Да, сгруппированные флажки поддерживаются во всех стандартных программах и программах для просмотра PDF. Спецификация PDF определяет переключатели и их поведение при группировании, что делает их общепризнанными в формате PDF. Тем не менее, важно протестировать функциональность в разных средствах просмотра PDF, чтобы обеспечить согласованное поведение на разных платформах.