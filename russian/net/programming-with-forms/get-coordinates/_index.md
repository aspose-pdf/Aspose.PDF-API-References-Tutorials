---
title: Получить координаты
linktitle: Получить координаты
second_title: Aspose.PDF для справочника API .NET
description: Легко получайте координаты полей формы в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-forms/get-coordinates/
---

В этом руководстве мы покажем вам, как получить координаты поля формы с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите выходной документ

Загрузите выходной PDF-документ:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Шаг 3. Найдите добавленные поля.

Найдите добавленные поля формы (в этом примере мы используем поля «Элемент1», «Элемент2» и «Элемент3»):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Шаг 4. Отображение позиций подэлементов для каждого поля

Просмотрите параметры для каждого поля и просмотрите координаты для каждого подэлемента:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Пример исходного кода для получения координат с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите выходной документ
	Document doc1 = new Document( dataDir + "input.pdf");
	// Найти добавленные поля
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// И показать позиции подэлементов для каждого из них.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом руководстве мы узнали, как получить координаты поля формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко получить координаты подэлементов полей формы в ваших документах PDF с помощью Aspose.PDF.