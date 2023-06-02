---
title: Поле со списком
linktitle: Поле со списком
second_title: Aspose.PDF для справочника API .NET
description: Легко создавайте список полей со списком в ваших документах PDF, используя Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-forms/combo-box/
---

В этом руководстве мы покажем вам, как создать список полей со списком, используя Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте объект документа

Создайте объект Document для хранения формы PDF:

```csharp
Document doc = new Document();
```

## Шаг 3. Добавьте страницу

Добавьте страницу в документ:

```csharp
doc.Pages.Add();
```

## Шаг 4: Создайте экземпляр объекта ComboBoxField

Создайте экземпляр объекта ComboBoxField с нужными размерами:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Шаг 5: Добавьте параметры в раскрывающийся список

Добавьте нужные опции в выпадающий список:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Шаг 6. Добавьте список полей со списком в форму.

Добавьте объект ComboBoxField в коллекцию полей формы документа:

```csharp
doc.Form.Add(combo);
```

## Шаг 7: Сохраните документ

Сохраните PDF-документ:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для поля со списком с использованием Aspose.Words для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Создать объект документа
	Document doc = new Document();
	// Добавить страницу в объект документа
	doc.Pages.Add();
	// Создание экземпляра объекта поля ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Добавить опцию в ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Добавить объект поля со списком для формирования коллекции полей объекта документа
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Сохраните PDF-документ
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом руководстве мы узнали, как создать список полей со списком, используя Aspose.PDF для .NET. Следуя этим шагам, вы можете легко добавить список полей со списком в свои PDF-документы с помощью Aspose.PDF.