---
title: Добавить удаление Javascript в PDF-документ
linktitle: Добавить удаление Javascript в документ
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавлять и удалять JavaScript в документ PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с уроками по коду для написания сценариев на уровне документа.
type: docs
weight: 30
url: /ru/net/programming-with-document/addremovejavascripttodoc/
---
Чтобы добавить и удалить JavaScript в PDF-документ, мы будем использовать библиотеку Aspose.PDF для .NET. Эта мощная библиотека позволяет нам манипулировать PDF-файлами в приложениях .NET. Следуйте пошаговым инструкциям ниже, чтобы добавить и удалить JavaScript с помощью Aspose.PDF для .NET.

## Шаг 1. Создайте новый PDF-документ

 Начните с создания нового экземпляра`Document` класс, предоставленный Aspose.PDF для .NET. Это будет PDF-документ, в который мы добавим JavaScript.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Шаг 2. Добавьте JavaScript на уровне документа

 Чтобы добавить JavaScript на уровне документа, используйте команду`JavaScript` собственность`Document` сорт. Назначьте функции JavaScript клавишам в словаре JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 В этом уроке мы добавили две функции JavaScript:`func1` и`func2`, в документ PDF.

## Шаг 3. Удалите JavaScript на уровне документа.

 Чтобы удалить JavaScript на уровне документа, загрузите PDF-документ и откройте`JavaScript`словарь. Переберите клавиши и удалите нужную функцию JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 В этом уроке мы удалим`func1` Функция JavaScript из PDF-документа.

## Шаг 4. Сохраните и проверьте изменения.

Сохраните измененный PDF-документ и проверьте изменения.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Этот код сохранит измененный PDF-документ и отобразит сообщение об успехе.

### Пример исходного кода для добавления и удаления Javascript из PDF-документов с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Удалить JavaScript уровня документа
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Заключение

В этой статье мы предоставили пошаговое руководство по добавлению и удалению JavaScript из PDF-документов с помощью Aspose.PDF для .NET. Следуя инструкциям и используя предоставленные руководства по кодированию, вы можете легко включить JavaScript в свои PDF-документы и удалить его при необходимости. JavaScript обеспечивает динамическую функциональность и интерактивность ваших PDF-файлов, повышая удобство использования.


### Часто задаваемые вопросы по добавлению и удалению JavaScript в документ PDF

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF for .NET — это мощная библиотека, которая позволяет разработчикам эффективно манипулировать PDF-файлами в приложениях .NET. Он предоставляет обширные возможности для программной работы с PDF-документами.

#### Вопрос: Как добавить JavaScript в документ PDF с помощью Aspose.PDF для .NET?

 О: Вы можете добавить JavaScript на уровне документа, используя`JavaScript` собственность`Document` сорт. Просто назначьте функции JavaScript клавишам в словаре JavaScript.

#### Вопрос: Могу ли я удалить JavaScript из PDF-документа с помощью Aspose.PDF для .NET?

 О: Да, вы можете удалить JavaScript из PDF-документа, открыв`JavaScript` словарь и удаление нужной функции JavaScript.

#### Вопрос: Подходит ли Aspose.PDF для .NET для профессиональных проектов?

О: Конечно, Aspose.PDF для .NET широко используется в профессиональных проектах для обработки и создания PDF-файлов. Он предлагает высокую производительность и надежную функциональность.

#### Вопрос: Какие преимущества дает добавление JavaScript в PDF-документ?

О: Добавление JavaScript в PDF-документ позволяет создавать интерактивные и динамические PDF-файлы. Вы можете реализовать проверку формы, выполнять вычисления и добавлять различные интерактивные функции для улучшения пользовательского опыта.