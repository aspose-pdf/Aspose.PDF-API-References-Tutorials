---
title: Сгруппированные флажки в PDF-документе
linktitle: Сгруппированные флажки в PDF-документе
second_title: Справочник по Aspose.PDF для .NET API
description: Легко создавайте сгруппированные флажки в PDF-документе с помощью Aspose.PDF для .NET.
type: docs
weight: 170
url: /ru/net/programming-with-forms/grouped-check-boxes/
---
В этом уроке мы покажем вам, как создавать сгруппированные флажки в PDF-документе с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код C#, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу с вашими документами:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создайте экземпляр объекта документа

Создайте экземпляр объекта Document:

```csharp
Document pdfDocument = new Document();
```

## Шаг 3. Добавьте страницу в PDF-документ.

Добавьте страницу в PDF-документ:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Шаг 4. Создайте экземпляр объекта RadioButtonField

Создайте экземпляр объекта RadioButtonField с номером страницы в качестве аргумента:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Шаг 5. Добавьте параметры переключателя

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

Настройте параметры переключателей, задав их стиль, рамку и внешний вид:

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

## Шаг 7. Добавьте переключатели в форму.

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
	// Создать экземпляр объекта документа
	Document pdfDocument = new Document();
	// Добавить страницу в PDF-файл
	Page page = pdfDocument.Pages.Add();
	// Создать объект RadioButtonField с номером страницы в качестве аргумента.
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Добавьте первый параметр переключателя, а также укажите его начало с помощью объекта Rectangle.
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
	// Добавить переключатель для формирования объекта объекта документа.
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

В этом уроке мы узнали, как создавать сгруппированные флажки в PDF-документе с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко добавить пользовательские параметры переключателей и объединить их в свои PDF-документы с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### Вопрос: Что такое сгруппированные флажки в PDF-документе?

О: Сгруппированные флажки в PDF-документе относятся к набору параметров переключателей, сгруппированных вместе. Радиокнопки позволяют пользователям выбирать только один вариант из группы взаимоисключающих вариантов. Когда выбран один переключатель, выбор остальных в той же группе автоматически отменяется. Такое группирование полезно, когда вы хотите предоставить пользователям несколько вариантов, но ограничить их выбор только одним вариантом.

#### Вопрос: Могу ли я настроить внешний вид сгруппированных флажков в Aspose.PDF для .NET?

О: Да, вы можете настроить внешний вид сгруппированных флажков в Aspose.PDF для .NET. API предоставляет различные параметры для установки стиля, границы и внешнего вида переключателей. Вы можете определить положение каждого параметра, выбирать между различными стилями рамки (например, квадрат, круг, крест) и настраивать свойства границы для достижения желаемого визуального представления.

#### Вопрос: Как добавить сгруппированные флажки на определенную страницу PDF-документа?

О: Чтобы добавить сгруппированные флажки на определенную страницу PDF-документа, вам необходимо создать экземпляр`RadioButtonField` объект с нужным номером страницы в качестве аргумента. Затем создайте`RadioButtonOptionField` объекты, представляющие каждую опцию переключателя, и укажите их положение с помощью`Rectangle` объект. Наконец, добавьте эти параметры в`RadioButtonField` и настройте их внешний вид по мере необходимости, прежде чем добавлять`RadioButtonField` в форму документа.

#### Вопрос: Могу ли я добавить несколько групп флажков в один PDF-документ?

 О: Да, вы можете добавить несколько групп флажков в один PDF-документ. Каждая группа должна иметь уникальный`RadioButtonField` объект, и`RadioButtonOptionField` объекты внутри каждой группы должны иметь одну и ту же страницу и уникальные имена для своих параметров. Это гарантирует, что переключатели внутри каждой группы будут работать правильно, а выбор будет взаимоисключающим.

#### Вопрос: Поддерживаются ли сгруппированные флажки во всех программах просмотра PDF-файлов и приложениях?

О: Да, сгруппированные флажки поддерживаются во всех стандартных программах просмотра PDF-файлов и приложениях. Спецификация PDF определяет переключатели и их группировку, что делает их общепризнанными в формате PDF. Однако важно протестировать функциональность в разных программах просмотра PDF-файлов, чтобы обеспечить единообразное поведение на разных платформах.