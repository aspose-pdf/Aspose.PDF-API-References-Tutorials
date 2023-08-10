---
title: Добавить Удалить Javascript в документ PDF
linktitle: Добавить Удалить Javascript в документ
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять и удалять JavaScript в документе PDF с помощью Aspose.PDF для .NET. Пошаговое руководство с учебными пособиями по коду для написания сценариев на уровне документа.
type: docs
weight: 30
url: /ru/net/programming-with-document/addremovejavascripttodoc/
---
Чтобы добавить и удалить JavaScript в документе PDF, мы будем использовать библиотеку Aspose.PDF для .NET. Эта мощная библиотека позволяет нам манипулировать файлами PDF в приложениях .NET. Следуйте приведенным ниже пошаговым инструкциям, чтобы добавить и удалить JavaScript с помощью Aspose.PDF для .NET.

## Шаг 1: Создайте новый PDF-документ

 Начните с создания нового экземпляра`Document` класс, предоставляемый Aspose.PDF для .NET. Это будет PDF-документ, в который мы добавим JavaScript.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Шаг 2. Добавьте JavaScript на уровне документа

 Чтобы добавить JavaScript на уровне документа, используйте`JavaScript` собственность`Document` сорт. Назначьте функции JavaScript ключам в словаре JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 В этом руководстве мы добавили две функции JavaScript,`func1` и`func2`, в документ PDF.

## Шаг 3. Удалите JavaScript уровня документа

Чтобы удалить JavaScript на уровне документа, загрузите документ PDF и откройте`JavaScript` словарь. Переберите ключи и удалите нужную функцию JavaScript.

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

 В этом уроке мы удаляем`func1` Функция JavaScript из документа PDF.

## Шаг 4: Сохраните и проверьте изменения

Сохраните измененный документ PDF и проверьте изменения.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Этот код сохранит измененный PDF-документ и отобразит сообщение об успешном завершении.

### Пример исходного кода для добавления и удаления Javascript из документов PDF с использованием Aspose.PDF для .NET

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

В этой статье мы предоставили пошаговое руководство по добавлению и удалению JavaScript из документов PDF с помощью Aspose.PDF для .NET. Следуя инструкциям и используя предоставленные руководства по коду, вы можете легко включить JavaScript в свои PDF-документы и удалить его при необходимости. JavaScript обеспечивает динамическую функциональность и интерактивность в ваших файлах PDF, повышая удобство работы пользователей.


### Часто задаваемые вопросы по добавлению удаления javascript в документ PDF

#### В: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам эффективно манипулировать файлами PDF в приложениях .NET. Он предоставляет широкие возможности для работы с PDF-документами программными средствами.

#### В: Как я могу добавить JavaScript в документ PDF, используя Aspose.PDF для .NET?

 О: Вы можете добавить JavaScript на уровне документа, используя`JavaScript` собственность`Document` сорт. Просто назначьте функции JavaScript ключам в словаре JavaScript.

#### В: Могу ли я удалить JavaScript из документа PDF с помощью Aspose.PDF для .NET?

 О: Да, вы можете удалить JavaScript из документа PDF, открыв`JavaScript` словарь и удаление нужной функции JavaScript.

#### В: Подходит ли Aspose.PDF для .NET для профессиональных проектов?

О: Безусловно, Aspose.PDF для .NET широко используется в профессиональных проектах для задач обработки и создания PDF-файлов. Он предлагает высокую производительность и надежную функциональность.

#### Вопрос. Какие преимущества дает добавление JavaScript в документ PDF?

О: Добавление JavaScript в PDF-документ позволяет создавать интерактивные и динамические PDF-файлы. Вы можете реализовать проверку формы, выполнять вычисления и добавлять различные интерактивные функции для улучшения взаимодействия с пользователем.