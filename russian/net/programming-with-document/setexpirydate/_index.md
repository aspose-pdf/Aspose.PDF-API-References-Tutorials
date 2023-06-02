---
title: Установить дату истечения срока действия
linktitle: Установить дату истечения срока действия
second_title: Aspose.PDF для справочника API .NET
description: Из этого пошагового руководства вы узнаете, как установить дату истечения срока действия в документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 300
url: /ru/net/programming-with-document/setexpirydate/
---
Aspose.PDF для .NET — это мощная библиотека, предоставляющая различные функции для работы с PDF-файлами. Одной из таких функций является возможность установить дату истечения срока действия для документа PDF. В этом руководстве мы познакомим вас с процессом установки даты истечения срока действия для документа PDF с помощью Aspose.PDF для .NET. 

## Шаг 1: Установите путь к каталогу документов

Прежде чем мы начнем, нам нужно указать путь к каталогу, в котором находится наш PDF-документ. Мы будем хранить этот путь в переменной с именем «dataDir».

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создание нового PDF-документа

Чтобы создать новый PDF-документ, нам нужно создать новый экземпляр`Aspose.Pdf.Document` объект. Мы можем сделать это, используя следующий код:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Шаг 3. Добавление новой страницы в документ PDF

После того, как мы создали документ PDF, мы можем добавить к нему новую страницу. Мы можем сделать это, используя следующий код:

```csharp
doc.Pages.Add();
```

## Шаг 4: Добавление текста в документ PDF

 После добавления страницы в документ PDF мы можем добавить к ней текст с помощью кнопки`Paragraphs` коллекция. Мы можем сделать это, используя следующий код:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Шаг 5: Установка даты истечения срока действия PDF с помощью JavaScript

Чтобы установить дату истечения срока действия PDF, нам нужно создать объект JavaScript. Мы можем сделать это, используя следующий код:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Установить JavaScript как действие открытия PDF
doc.OpenAction = javaScript;
```

В этом коде мы устанавливаем дату истечения срока действия до мая 2017 года.

## Шаг 6: Сохраните файл PDF

 После того, как вы установили дату истечения срока действия, вам нужно сохранить файл PDF. Для этого можно использовать`Save` метод`Document` объект и укажите путь к тому месту, где вы хотите сохранить обновленный файл PDF.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);
```

### Пример исходного кода для установки даты истечения срока действия с использованием Aspose.PDF для .NET

Вот полный пример исходного кода для установки даты истечения срока действия с помощью Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать объект документа
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Добавить страницу в коллекцию страниц файла PDF
doc.Pages.Add();
// Добавить текстовый фрагмент в коллекцию абзацев объекта страницы
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Создайте объект JavaScript, чтобы установить дату истечения срока действия PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Установить JavaScript как действие открытия PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);
```
