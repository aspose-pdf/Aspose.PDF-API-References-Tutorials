---
title: Выберите переключатель
linktitle: Выберите переключатель
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как выбрать переключатель в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 250
url: /ru/net/programming-with-forms/select-radio-button/
---

Вот подробное руководство о том, как выбрать переключатель с помощью Aspose.PDF для .NET. Следуй этим шагам:

##  Шаг 1: Начните с определения каталога ваших документов, указав путь в`dataDir` variable.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Шаг 2: Откройте документ PDF с помощью`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Шаг 3: Получите поле переключателя из формы документа.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Шаг 4: Укажите индекс переключателя для выбора из группы.

```csharp
radioField. Selected = 2;
```

## Шаг 5: Установите выходной путь для редактируемого PDF-файла.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Шаг 6: Сохраните измененный файл PDF.

```csharp
pdfDocument.Save(dataDir);
```

## Шаг 7: Отобразите сообщение с подтверждением и местоположение сохраненного файла.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Пример исходного кода для выбора радиокнопки с использованием Aspose.Words для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Открыть документ
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Получить поле
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Укажите индекс переключателя из группы
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Сохраните PDF-файл
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом руководстве мы узнали, как выбрать переключатель с помощью Aspose.PDF для .NET. Выполняя шаги, описанные выше, вы можете манипулировать и изменять переключатели в своих PDF-документах, используя Aspose.PDF для .NET.