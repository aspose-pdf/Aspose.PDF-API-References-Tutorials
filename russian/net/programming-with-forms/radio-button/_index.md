---
title: Переключатель
linktitle: Переключатель
second_title: Aspose.PDF для справочника API .NET
description: Легко добавляйте переключатели в свои документы PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 220
url: /ru/net/programming-with-forms/radio-button/
---

В этом руководстве мы покажем вам, как добавить переключатель в документ PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте экземпляр объекта документа

Создайте экземпляр объекта Document для создания нового PDF-документа:

```csharp
Document pdfDocument = new Document();
```

## Шаг 3. Добавьте страницу

Добавьте страницу в документ PDF:

```csharp
pdfDocument.Pages.Add();
```

## Шаг 4: Создайте экземпляр объекта RadioButtonField

Создайте экземпляр объекта RadioButtonField, указав номер страницы в качестве аргумента:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Шаг 5: Добавьте параметры переключателя

Добавьте параметры переключателя в объект RadioButtonField, указав координаты каждого параметра с помощью объекта Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Шаг 6: Добавьте переключатель в форму

Добавьте переключатель в объект формы документа:

```csharp
pdfDocument.Form.Add(radio);
```

## Шаг 7: Сохраните PDF-документ

Сохраните созданный PDF-документ:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для радиокнопки с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Создать объект документа
	Document pdfDocument = new Document();
	// Добавить страницу в файл PDF
	pdfDocument.Pages.Add();
	// Создайте объект RadioButtonField с номером страницы в качестве аргумента.
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Добавьте первый параметр переключателя, а также укажите его происхождение с помощью объекта Rectangle.
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Добавить второй вариант переключателя
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Добавить переключатель, чтобы сформировать объект объекта документа
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Сохраните PDF-файл
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом руководстве мы узнали, как добавить переключатель в документ PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко создать переключатель и поместить его на определенную страницу в документе PDF.