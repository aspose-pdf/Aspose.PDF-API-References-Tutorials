---
title: Получить координаты поля формы PDF
linktitle: Получить координаты поля формы PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Легко получайте координаты полей формы PDF в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-forms/get-coordinates/
---
В этом уроке мы покажем вам, как получить координаты полей формы PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы провести вас через этот процесс.

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

## Шаг 3: Найдите добавленные поля

Найдите добавленные поля формы (в этом примере мы используем поля «Item1», «Item2» и «Item3»):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Шаг 4: Отобразите позиции подэлементов для каждого поля

Просмотрите параметры каждого поля и координаты каждого подэлемента:

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
	// И показать позиции подпунктов для каждого из них.
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

В этом уроке мы узнали, как получить координаты полей формы с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко получить координаты подэлементов полей формы в ваших документах PDF с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### В: Можно ли использовать этот метод для получения координат для любого типа поля формы в Aspose.PDF для .NET?

A: Да, вы можете использовать этот метод для получения координат для различных типов полей формы в Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует, как получить координаты для полей RadioButton, но вы можете адаптировать тот же подход для других типов полей формы, таких как TextBox, CheckBox, ListBox и т. д.

#### В: Как изменить или настроить координаты поля формы?

A: Координаты поля формы основаны на системе координат документа PDF, где начало координат (0,0) находится в нижнем левом углу страницы. Чтобы изменить или настроить координаты поля формы, вы можете обновить`Rect` свойство соответствующего поля формы или его подэлементов, например RadioButtonOptionField.

#### В: Можно ли программно добавить координаты полей формы в PDF-документ?

A: Да, вы можете получить координаты полей формы, которые были добавлены программно в документ PDF. Aspose.PDF для .NET позволяет вам добавлять поля формы динамически, и после добавления вы можете получить их координаты, используя подход, продемонстрированный в этом руководстве.

#### В: Какова цель получения координат полей формы?

A: Получение координат полей формы может быть полезным, когда вам нужно выполнить определенные операции, связанные с макетом, или проверки полей формы в документе PDF. Это позволяет вам точно позиционировать и выравнивать поля формы на основе их координат, гарантируя, что они правильно отображаются в документе и обеспечивают бесперебойный пользовательский опыт.

#### В: Координаты поля формы выражены в точках или других единицах?

A: Координаты поля формы в Aspose.PDF для .NET выражаются в точках. Одна точка эквивалентна 1/72 дюйма, что делает ее стандартной единицей измерения в формате PDF.