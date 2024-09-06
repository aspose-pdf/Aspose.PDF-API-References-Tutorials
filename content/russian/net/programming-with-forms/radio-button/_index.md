---
title: Радиокнопка
linktitle: Радиокнопка
second_title: Справочник по API Aspose.PDF для .NET
description: Легко добавляйте переключатели в свои PDF-документы с помощью Aspose.PDF для .NET.
type: docs
weight: 220
url: /ru/net/programming-with-forms/radio-button/
---
В этом уроке мы покажем вам, как добавить радиокнопку в документ PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы провести вас через этот процесс.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание объекта документа

Создайте экземпляр объекта Document для создания нового PDF-документа:

```csharp
Document pdfDocument = new Document();
```

## Шаг 3: Добавьте страницу

Добавить страницу в PDF-документ:

```csharp
pdfDocument.Pages.Add();
```

## Шаг 4: Создание объекта RadioButtonField

Создайте объект RadioButtonField, указав номер страницы в качестве аргумента:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Шаг 5: Добавьте параметры переключателя

Добавьте параметры переключателя к объекту RadioButtonField, указав координаты каждого параметра с помощью объекта Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Шаг 6: Добавьте переключатель в форму.

Добавьте переключатель к объекту формы документа:

```csharp
pdfDocument.Form.Add(radio);
```

## Шаг 7: Сохраните PDF-документ.

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
	// Создать экземпляр объекта Document
	Document pdfDocument = new Document();
	// Добавить страницу в PDF-файл
	pdfDocument.Pages.Add();
	// Создать объект RadioButtonField с номером страницы в качестве аргумента
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Добавьте первый вариант переключателя, а также укажите его начало с помощью объекта Rectangle.
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Добавить вторую опцию переключателя
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Добавить переключатель в объект формы объекта документа
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

В этом уроке мы узнали, как добавить радиокнопку в документ PDF с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко создать радиокнопку и разместить ее на определенной странице вашего документа PDF.


### Часто задаваемые вопросы

#### В: Могу ли я настроить внешний вид переключателя, например его размер и цвет?

 A: Да, вы можете настроить внешний вид переключателя с помощью`Rectangle` координаты объекта для определения его размера и положения. Aspose.PDF для .NET позволяет вам настроить внешний вид переключателя в соответствии с вашими потребностями.

#### В: Можно ли добавить несколько переключателей с разными группами на одну страницу?

A: Да, вы можете добавить несколько радиокнопок с разными группами на одной странице. Каждая группа радиокнопок может иметь уникальное имя, и только один вариант в каждой группе может быть выбран за раз.

#### В: Как добавить метку или текстовое описание к параметрам переключателя?

 A: Чтобы добавить метку или текстовое описание к параметрам переключателя, вы можете использовать`TextStamp`класс из Aspose.PDF для .NET для наложения текста на PDF-документ в определенных координатах.

#### В: Совместим ли Aspose.PDF для .NET со всеми версиями .NET Framework?

A: Да, Aspose.PDF для .NET совместим со всеми версиями .NET Framework, включая .NET Core и .NET Standard.

#### В: Могу ли я программно управлять выбором параметра переключателя в документе PDF?

 A: Да, вы можете программно управлять выбором опции радиокнопки с помощью`IsSelected` собственность`RadioButtonOption` класс. Это свойство позволяет вам установить определенную опцию как выбранную.