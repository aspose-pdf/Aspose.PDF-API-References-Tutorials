---
title: Получить значения из всех полей в PDF-документе
linktitle: Получить значения из всех полей в PDF-документе
second_title: Справочник по Aspose.PDF для .NET API
description: Легко получайте значения всех полей формы в PDF-документе с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/programming-with-forms/get-values-from-all-fields/
---
В этом уроке мы покажем вам, как получить значения всех полей формы в PDF-документе с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код C#, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу с вашими документами:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Откройте документ.

Откройте PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Шаг 3. Получите значения для всех полей

Прокрутите все поля формы в документе и получите их имена и значения:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Пример исходного кода для получения значений из всех полей с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Получить значения из всех полей
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Заключение

В этом уроке мы узнали, как получить значения всех полей формы в PDF-документе с помощью Aspose.PDF для .NET. Выполнив эти шаги, вы сможете легко извлечь значения всех полей формы из ваших PDF-документов с помощью Aspose.PDF.

### Часто задаваемые вопросы

#### Вопрос: Могу ли я изменить значения полей формы при их получении с помощью Aspose.PDF для .NET?

 О: Да, вы можете изменять значения полей формы при их получении с помощью Aspose.PDF для .NET. Как только у вас появится`Field` объект, представляющий поле формы, вы можете обновить его`Value`недвижимость желаемой стоимости. После внесения необходимых изменений вы можете сохранить обновленный PDF-документ, чтобы отразить изменения.

#### Вопрос: Как я могу фильтровать и получать определенные поля формы на основе их типов (например, текстовые поля, флажки)?

 О: Чтобы получить определенные поля формы на основе их типов, вы можете использовать условные операторы или запросы LINQ для фильтрации интересующих полей. Вы можете проверить тип каждого поля формы, используя поле`FieldType` свойство, а затем получить соответствующие значения.

#### Вопрос: Что произойдет, если в PDF-документе нет полей формы?

 О: Если документ PDF не содержит полей формы,`pdfDocument.Form` свойство вернет пустую коллекцию. В таких случаях цикл получения значений не будет выполнен, и значения не будут отображаться.

#### Вопрос: Могу ли я извлечь значения полей формы в определенном порядке или отсортировать их по алфавиту?

О: Порядок извлечения полей формы зависит от базовой структуры PDF-документа. Aspose.PDF для .NET возвращает поля формы в том порядке, в котором они были добавлены в документ. Если вы хотите отображать или обрабатывать поля формы в определенном порядке, вы можете реализовать собственную логику сортировки в соответствии с вашими требованиями.

#### Вопрос: Как обрабатывать зашифрованные PDF-документы с полями формы, защищенными паролем?

 О: Aspose.PDF для .NET предоставляет функции для работы с зашифрованными PDF-документами и полями форм, защищенными паролем. Перед загрузкой документа вы можете установить пароль с помощью`pdfDocument.Password` свойство для доступа к защищенному PDF-документу и полям его формы.