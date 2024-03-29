---
title: Сохранить права
linktitle: Сохранить права
second_title: Справочник по Aspose.PDF для .NET API
description: Сохраняйте права форм в ваших PDF-документах с помощью Aspose.PDF для .NET.
type: docs
weight: 210
url: /ru/net/programming-with-forms/preserve-rights/
---
В этом уроке мы покажем вам, как сохранить права формы в PDF-документе с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код C#, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу с вашими документами:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Откройте документ.

 Откройте исходный PDF-документ с помощью`FileStream` с разрешением на чтение и запись:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Шаг 3. Отредактируйте поля формы.

Пройдитесь по всем полям формы в документе и внесите необходимые изменения. В этом примере мы меняем значение поля формы, в имени которого есть «A1»:

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

## Шаг 4. Сохраните обновленный документ.

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
// Прочитайте исходную форму PDF с помощью FileAccess для чтения и записи.
// Нам нужно разрешение ReadWrite, потому что после изменения
// Нам нужно сохранить обновленное содержимое в том же документе/файле.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Создать экземпляр экземпляра документа
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Получить значения из всех полей
foreach (Field formField in pdfDocument.Form)
{
	// Если полное имя поля содержит A1, выполните операцию
	if (formField.FullName.Contains("A1"))
	{
		// Привести поле формы как TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Изменить значение поля
		textBoxField.Value = "Testing";
	}
}
// Сохраните обновленный документ в save FileStream.
pdfDocument.Save();
// Закройте объект файлового потока
fs.Close();
```

## Заключение

В этом уроке мы узнали, как сохранить права формы в PDF-документе с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко получить доступ к полям формы и внести определенные изменения, сохранив при этом разрешения на доступ и запись.


### Часто задаваемые вопросы

#### Вопрос: Могу ли я сохранить права отдельных полей формы, не затрагивая другие поля PDF-документа?

 О: Да, с помощью`FullName` свойства полей формы, вы можете выбрать для сохранения определенные поля формы, оставив другие без изменений.

#### Вопрос: Могу ли я сохранить права формы в PDF-документе, защищенном паролем?

О: Да, Aspose.PDF для .NET позволяет вам сохранять права формы даже в PDF-документах, защищенных паролем, при условии, что вы предоставите правильный пароль для доступа и изменения файла.

#### Вопрос: Что произойдет, если я попытаюсь изменить поля формы без соответствующих прав доступа?

О: Если вы попытаетесь изменить поля формы без соответствующих прав доступа, изменения не будут сохранены в PDF-документе, и вы можете получить исключение или сообщение об ошибке.

#### Вопрос: Совместим ли Aspose.PDF для .NET со всеми версиями .NET Framework?

О: Да, Aspose.PDF для .NET совместим со всеми версиями .NET Framework, включая .NET Core и .NET Standard.

#### Вопрос: Могу ли я программно сохранить права формы в PDF-документе на других языках программирования, кроме C#?

О: Да, Aspose.PDF для .NET поддерживает различные языки программирования, такие как VB.NET и ASP.NET, в дополнение к C#.