---
title: Получить координаты поля PDF-формы
linktitle: Получить координаты поля PDF-формы
second_title: Aspose.PDF для справочника API .NET
description: С легкостью получайте координаты полей PDF-формы в своих PDF-документах с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-forms/get-coordinates/
---
В этом руководстве мы покажем вам, как получить координаты поля формы PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

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

В этом руководстве мы узнали, как получить координаты поля формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко получить координаты подэлементов полей формы в ваших PDF-документах с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### В: Могу ли я использовать этот метод для получения координат любого типа поля формы в Aspose.PDF для .NET?

О: Да, вы можете использовать этот метод для получения координат для различных типов полей формы в Aspose.PDF для .NET. В предоставленном исходном коде C# показано, как получить координаты для полей RadioButton, но вы можете адаптировать тот же подход для других типов полей формы, таких как TextBox, CheckBox, ListBox и т. д.

#### Q: Как я могу изменить или настроить координаты поля формы?

О: Координаты поля формы основаны на системе координат документа PDF, где начало координат (0,0) находится в нижнем левом углу страницы. Чтобы изменить или настроить координаты поля формы, вы можете обновить`Rect` свойство соответствующего поля формы или его подэлементов, например RadioButtonOptionField.

#### В: Могу ли я программно добавить координаты полей формы в PDF-документ?

О: Да, вы можете получить координаты полей формы, которые были программно добавлены в PDF-документ. Aspose.PDF для .NET позволяет вам динамически добавлять поля формы, и после добавления вы можете получить их координаты, используя подход, продемонстрированный в этом руководстве.

#### Q: Какова цель получения координат поля формы?

О: Получение координат полей формы может быть полезно, когда вам нужно выполнить определенные операции, связанные с макетом, или проверки полей формы в документе PDF. Это позволяет вам точно размещать и выравнивать поля формы на основе их координат, гарантируя, что они правильно отображаются в документе, и обеспечивает беспрепятственный пользовательский интерфейс.

#### В: Координаты поля формы выражаются в пунктах или других единицах?

О: Координаты поля формы в Aspose.PDF для .NET выражаются в пунктах. Один пункт эквивалентен 1/72 дюйма, что делает его стандартной единицей измерения в формате PDF.