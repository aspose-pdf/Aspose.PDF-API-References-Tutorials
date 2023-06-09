---
title: Горизонтальные и вертикальные радиокнопки
linktitle: Горизонтальные и вертикальные радиокнопки
second_title: Aspose.PDF для справочника API .NET
description: С легкостью создавайте горизонтальные и вертикальные переключатели в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 180
url: /ru/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

В этом уроке мы покажем вам, как создавать горизонтально и вертикально расположенные переключатели в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ

Загрузите существующий PDF-документ:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Шаг 3. Настройте параметры переключателя

Настройте параметры переключателя, установив следующие свойства:

```csharp
formEditor. RadioGap = 4; // Расстояние между двумя вариантами переключателя
formEditor. RadioHoriz = true; // Горизонтальное расположение радиокнопок
formEditor.RadioButtonItemSize = 20; // Размер радиокнопок
formEditor.Facade.BorderWidth = 1; // Ширина границы переключателя
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Цвет границы радиокнопки
```

## Шаг 4: Добавьте горизонтальные переключатели

Добавьте радиокнопки, расположенные горизонтально, указав параметры и положение поля:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Шаг 5: Добавьте вертикальные переключатели

Добавьте радиокнопки, расположенные вертикально, указав параметры и положение поля:

```csharp
formEditor. RadioHoriz = false; // Вертикальное расположение радиокнопок
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Шаг 6: Сохраните документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Пример исходного кода для переключателей по горизонтали и вертикали с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите ранее сохраненный документ
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap — это расстояние между двумя переключателями.
	formEditor.RadioGap = 4;
	// Добавить горизонтальный переключатель
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize, если размер элемента переключателя.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Добавить другой переключатель, расположенный вертикально
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Сохраните PDF-документ
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом уроке мы узнали, как создавать горизонтально и вертикально расположенные переключатели в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко настроить расположение переключателей и добавить их в свои PDF-документы с помощью Aspose.PDF.