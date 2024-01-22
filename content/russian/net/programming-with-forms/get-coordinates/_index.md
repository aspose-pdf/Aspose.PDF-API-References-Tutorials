---
title: Получить координаты полей формы PDF
linktitle: Получить координаты полей формы PDF
second_title: Справочник по Aspose.PDF для .NET API
description: Легко получайте координаты полей PDF-формы в ваших PDF-документах с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-forms/get-coordinates/
---
В этом уроке мы покажем вам, как получить координаты полей формы PDF с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код C#, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и задали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите выходной документ

Загрузите выходной PDF-документ:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Шаг 3. Найдите добавленные поля

Найдите добавленные поля формы (в этом примере мы используем поля «Элемент1», «Элемент2» и «Элемент3»):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Шаг 4. Отобразите позиции подпунктов для каждого поля.

Перебирайте параметры для каждого поля и просматривайте координаты каждого подпункта:

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

### Пример исходного кода для получения координат с помощью Aspose.PDF для .NET 
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
	// И покажите позиции подпунктов для каждого из них.
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

В этом уроке мы узнали, как получить координаты полей формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко получить координаты подэлементов полей формы в ваших PDF-документах с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### Вопрос: Могу ли я использовать этот метод для получения координат любого типа поля формы в Aspose.PDF для .NET?

О: Да, вы можете использовать этот метод для получения координат различных типов полей формы в Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует, как получить координаты для полей RadioButton, но вы можете адаптировать тот же подход для других типов полей формы, таких как TextBox, CheckBox, ListBox и других.

#### Вопрос: Как я могу изменить или настроить координаты полей формы?

О: Координаты полей формы основаны на системе координат PDF-документа, где начало координат (0,0) находится в левом нижнем углу страницы. Чтобы изменить или настроить координаты поля формы, вы можете обновить`Rect` свойство соответствующего поля формы или его подэлементов, например RadioButtonOptionField.

#### Вопрос: Могу ли я получить координаты полей формы, программно добавленных в PDF-документ?

О: Да, вы можете получить координаты полей формы, которые были программно добавлены в PDF-документ. Aspose.PDF для .NET позволяет динамически добавлять поля формы, и после добавления вы можете получить их координаты, используя подход, продемонстрированный в этом руководстве.

#### Вопрос: Какова цель получения координат полей формы?

О: Получение координат полей формы может оказаться полезным, когда вам необходимо выполнить определенные операции, связанные с макетом, или проверить поля формы в PDF-документе. Он позволяет точно размещать и выравнивать поля формы на основе их координат, обеспечивая их правильное отображение в документе и обеспечивая удобство работы с пользователем.

#### Вопрос: Координаты полей формы выражаются в пунктах или других единицах измерения?

О: Координаты полей формы в Aspose.PDF для .NET выражаются в точках. Одна точка эквивалентна 1/72 дюйма, что делает ее стандартной единицей измерения в формате PDF.