---
title: Сохраняйте права
linktitle: Сохраняйте права
second_title: Справочник по API Aspose.PDF для .NET
description: Сохраняйте права на формы в ваших PDF-документах с помощью Aspose.PDF для .NET.
type: docs
weight: 210
url: /ru/net/programming-with-forms/preserve-rights/
---
В этом уроке мы покажем вам, как сохранить права формы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы провести вас через этот процесс.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Откройте документ.

 Откройте исходный PDF-документ с помощью`FileStream` с разрешением на чтение и запись:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Шаг 3: Редактирование полей формы

Пройдитесь по всем полям формы в документе и внесите необходимые изменения. В этом примере мы меняем значение поля формы, в названии которого есть «A1»:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Шаг 4: Сохраните обновленный документ.

Сохраните измененный PDF-документ:

```csharp
pdfDocument.Save();
```

##  Шаг 5: Закройте`FileStream`

 Не забудьте закрыть`FileStream` объект, когда вы закончите:

```csharp
fs. Close();
```

### Пример исходного кода для сохранения прав с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Прочитайте исходную PDF-форму с помощью FileAccess, имеющего права на чтение и запись.
// Нам необходимо разрешение ReadWrite, поскольку после внесения изменений
// Нам необходимо сохранить обновленное содержимое в том же документе/файле.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Создать экземпляр документа
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Получить значения из всех полей
foreach (Field formField in pdfDocument.Form)
{
	// Если полное имя поля содержит A1, выполнить операцию
	if (formField.FullName.Contains("A1"))
	{
		// Преобразовать поле формы в TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Изменить значение поля
		textBoxField.Value = "Testing";
	}
}
// Сохраните обновленный документ в FileStream.
pdfDocument.Save();
// Закройте объект File Stream.
fs.Close();
```

## Заключение

В этом уроке мы узнали, как сохранить права формы в документе PDF с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко получить доступ к полям формы и внести определенные изменения, сохраняя при этом права доступа и записи.


### Часто задаваемые вопросы

#### В: Могу ли я сохранить права определенных полей формы, не затрагивая другие поля в документе PDF?

 A: Да, с помощью`FullName` Свойство полей формы позволяет сохранить определенные поля формы, оставив остальные нетронутыми.

#### В: Могу ли я сохранить права формы в защищенном паролем PDF-документе?

A: Да, Aspose.PDF для .NET позволяет сохранять права формы даже в защищенных паролем PDF-документах, если вы предоставите правильный пароль для доступа к файлу и его изменения.

#### В: Что произойдет, если я попытаюсь изменить поля формы без соответствующих прав доступа?

A: Если вы попытаетесь изменить поля формы без соответствующих прав доступа, изменения не будут сохранены в документе PDF, и вы можете получить исключение или сообщение об ошибке.

#### В: Совместим ли Aspose.PDF для .NET со всеми версиями .NET Framework?

A: Да, Aspose.PDF для .NET совместим со всеми версиями .NET Framework, включая .NET Core и .NET Standard.

#### В: Можно ли программно сохранить права формы в документе PDF на других языках программирования, помимо C#?

A: Да, Aspose.PDF для .NET поддерживает различные языки программирования, такие как VB.NET и ASP.NET, в дополнение к C#.