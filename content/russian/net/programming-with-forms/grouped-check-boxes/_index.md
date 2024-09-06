---
title: Сгруппированные флажки в документе PDF
linktitle: Сгруппированные флажки в документе PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Легко создавайте сгруппированные флажки в PDF-документе с помощью Aspose.PDF для .NET.
type: docs
weight: 170
url: /ru/net/programming-with-forms/grouped-check-boxes/
---
В этом уроке мы покажем вам, как создавать сгруппированные флажки в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы провести вас через этот процесс.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание объекта документа

Создайте экземпляр объекта Document:

```csharp
Document pdfDocument = new Document();
```

## Шаг 3: Добавьте страницу в PDF-документ

Добавить страницу в PDF-документ:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Шаг 4: Создание объекта RadioButtonField

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

## Шаг 6: Настройте параметры переключателя

Настройте параметры переключателя, задав его стиль, границу и внешний вид:

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

## Шаг 7: Добавьте переключатели в форму.

Добавьте переключатели к объекту формы документа:

```csharp
pdfDocument.Form.Add(radio);
```

## Шаг 8: Сохраните документ.

Сохраните PDF-документ:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для групповых флажков с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Создать экземпляр объекта Document
	Document pdfDocument = new Document();
	// Добавить страницу в PDF-файл
	Page page = pdfDocument.Pages.Add();
	// Создать объект RadioButtonField с номером страницы в качестве аргумента
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Добавьте первый вариант переключателя, а также укажите его начало с помощью объекта Rectangle.
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
	// Добавить переключатель в объект формы объекта документа
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

В этом уроке мы узнали, как создавать сгруппированные флажки в документе PDF с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко добавлять пользовательские параметры переключателей и объединять их в своих документах PDF с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### В: Что такое сгруппированные флажки в PDF-документе?

A: Сгруппированные флажки в документе PDF относятся к набору вариантов переключателей, которые сгруппированы вместе. Переключатели позволяют пользователям выбирать только один вариант из группы взаимоисключающих вариантов. Когда выбран один переключатель, другие в той же группе автоматически снимаются с выбора. Такое поведение группировки полезно, когда вы хотите предоставить пользователям несколько вариантов, но ограничить их выбор только одним вариантом.

#### В: Можно ли настроить внешний вид сгруппированных флажков в Aspose.PDF для .NET?

A: Да, вы можете настроить внешний вид сгруппированных флажков в Aspose.PDF для .NET. API предоставляет различные параметры для установки стиля, границ и внешнего вида параметров переключателей. Вы можете определить положение каждого параметра, выбрать между различными стилями полей (например, квадрат, круг, крест) и настроить свойства границ для достижения желаемого визуального представления.

#### В: Как добавить сгруппированные флажки на определенную страницу PDF-документа?

A: Чтобы добавить сгруппированные флажки на определенную страницу PDF-документа, вам необходимо создать экземпляр`RadioButtonField` объект с желаемым номером страницы в качестве аргумента. Затем создайте`RadioButtonOptionField` объекты, представляющие каждую опцию переключателя, и укажите их положение с помощью`Rectangle` объект. Наконец, добавьте эти параметры в`RadioButtonField` и настройте их внешний вид по мере необходимости перед добавлением`RadioButtonField` к форме документа.

#### В: Можно ли добавить несколько групп флажков в один PDF-документ?

 A: Да, вы можете добавить несколько групп флажков в один PDF-документ. Каждая группа должна иметь уникальный`RadioButtonField` объект, и`RadioButtonOptionField` Объекты в каждой группе должны иметь одну и ту же страницу и уникальные имена для своих опций. Это гарантирует, что радиокнопки в каждой группе будут работать правильно, а выборы будут взаимоисключающими.

#### В: Поддерживаются ли групповые флажки во всех программах и приложениях для просмотра PDF-файлов?

A: Да, сгруппированные флажки поддерживаются во всех стандартных просмотрщиках PDF и приложениях. Спецификация PDF определяет переключатели и их поведение при группировке, что делает их универсально распознаваемыми в формате PDF. Однако важно протестировать функциональность в разных просмотрщиках PDF, чтобы обеспечить единообразное поведение на разных платформах.