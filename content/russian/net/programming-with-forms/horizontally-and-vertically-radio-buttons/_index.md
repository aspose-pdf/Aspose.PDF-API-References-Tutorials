---
title: Горизонтальные и вертикальные переключатели
linktitle: Горизонтальные и вертикальные переключатели
second_title: Справочник по Aspose.PDF для .NET API
description: Легко создавайте горизонтальные и вертикальные переключатели в ваших PDF-документах с помощью Aspose.PDF для .NET.
type: docs
weight: 180
url: /ru/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
В этом уроке мы покажем вам, как создавать горизонтально и вертикально расположенные переключатели в PDF-документе с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код C#, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу с вашими документами:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ

Загрузите существующий PDF-документ:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Шаг 3. Настройте параметры переключателя

Настройте параметры переключателя, установив следующие свойства:

```csharp
formEditor. RadioGap = 4; // Расстояние между двумя опциями переключателя
formEditor. RadioHoriz = true; //Горизонтальное расположение переключателей
formEditor.RadioButtonItemSize = 20; // Размер переключателей
formEditor.Facade.BorderWidth = 1; // Ширина границы переключателя
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Цвет рамки переключателя
```

## Шаг 4. Добавьте горизонтальные переключатели

Добавьте переключатели, расположенные горизонтально, указав параметры и положение поля:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Шаг 5. Добавьте вертикальные переключатели

Добавьте переключатели, расположенные вертикально, указав параметры и положение поля:

```csharp
formEditor. RadioHoriz = false; // Вертикальное расположение переключателей
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Шаг 6: Сохраните документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Пример исходного кода для горизонтально и вертикально переключателей с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите ранее сохраненный документ
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap — это расстояние между двумя опциями переключателя.
	formEditor.RadioGap = 4;
	// Добавить горизонтальный переключатель
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize — размер элемента переключателя.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Добавить другой переключатель, расположенный вертикально.
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

В этом уроке мы узнали, как создавать горизонтально и вертикально расположенные переключатели в PDF-документе с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко настроить расположение переключателей и добавить их в свои PDF-документы с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### Вопрос: Что такое горизонтально и вертикально расположенные переключатели в PDF-документе?

О: Горизонтально и вертикально расположенные переключатели в PDF-документе относятся к ориентации макета параметров переключателей. Горизонтальная компоновка размещает параметры переключателей рядом, позволяя пользователям делать выбор слева направо. С другой стороны, в вертикальной компоновке параметры переключателей располагаются друг над другом, что позволяет пользователям делать выбор сверху вниз.

#### Вопрос: Как настроить внешний вид переключателей в Aspose.PDF для .NET?

О: Вы можете настроить внешний вид переключателей в Aspose.PDF для .NET, настроив несколько свойств. API предоставляет параметры для установки расстояния между двумя параметрами переключателя (`RadioGap`), ориентация макета (`RadioHoriz`), размер элементов переключателя (`RadioButtonItemSize`), ширину границы и цвет переключателей и многое другое.

#### Вопрос: Могу ли я добавить в один и тот же PDF-документ как горизонтальные, так и вертикальные переключатели?

О: Да, вы можете добавить как горизонтальные, так и вертикальные переключатели в один и тот же PDF-документ, используя Aspose.PDF для .NET. Пример исходного кода, представленный в руководстве, демонстрирует, как сначала добавить переключатели, расположенные горизонтально, а затем добавить еще один набор переключателей, расположенных вертикально, в тот же PDF-документ.

#### Вопрос: Могу ли я установить разные параметры переключателей для каждой группы переключателей?

 О: Да, вы можете установить разные параметры переключателей для каждой группы переключателей. Каждая группа должна иметь уникальный`RadioButtonField` объект, и`RadioButtonOptionField` объекты внутри каждой группы должны иметь одну и ту же страницу и уникальные имена для своих параметров. Это гарантирует, что переключатели внутри каждой группы будут работать правильно, а выбор будет взаимоисключающим.

#### Вопрос: Поддерживаются ли настройки макета и внешнего вида переключателей во всех программах просмотра PDF-файлов и приложениях?

О: Да, настройки макета и внешнего вида переключателей поддерживаются во всех стандартных программах просмотра PDF-файлов и приложениях. Спецификация PDF определяет переключатели и их различные атрибуты, что делает их общепризнанными в формате PDF. Однако важно протестировать внешний вид и поведение переключателей в различных программах просмотра PDF-файлов, чтобы обеспечить единообразный рендеринг на различных платформах.