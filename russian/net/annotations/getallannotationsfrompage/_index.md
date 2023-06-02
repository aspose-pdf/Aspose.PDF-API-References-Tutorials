---
title: Получить все аннотации со страницы
linktitle: Получить все аннотации со страницы
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET для извлечения всех аннотаций со страницы PDF с помощью этого пошагового руководства.
type: docs
weight: 70
url: /ru/net/annotations/getallannotationsfrompage/
---
Эта статья проведет вас через процесс извлечения всех аннотаций со страницы PDF с помощью Aspose.PDF для .NET. Aspose.PDF для .NET — это библиотека, которая позволяет разработчикам создавать, редактировать и преобразовывать PDF-документы. С помощью этого руководства вы сможете получить все аннотации с определенной страницы PDF, используя предоставленный исходный код C#.

Выполните следующие шаги, чтобы получить все аннотации для страницы PDF с помощью Aspose.PDF для .NET:

## Шаг 1: Путь к каталогу документов

Первым шагом в получении всех аннотаций со страницы PDF с помощью Aspose.PDF для .NET является установка пути к каталогу документов, в котором хранятся ваши файлы PDF. Вы можете сделать это, изменив следующую строку кода:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Шаг 2: Ваши PDF-файлы сохранены

Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на путь к папке, в которой хранятся ваши PDF-файлы. Например:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Шаг 3: Откройте документ

Следующим шагом является открытие документа PDF, содержащего аннотации, которые вы хотите извлечь. Вы можете сделать это, добавив следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Эта строка кода инициализирует новый экземпляр класса Document и загружает PDF-документ «GetAllAnnotationsFromPage.pdf». Замените это имя файла на имя вашего файла PDF.

## Шаг 4: просмотр всех аннотаций

Открыв документ PDF, вы можете просмотреть все аннотации на определенной странице. Например, чтобы просмотреть все аннотации на первой странице документа PDF, добавьте следующий код:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Код идет здесь
}
```

Этот код перебирает все аннотации на первой странице документа PDF и назначает каждую аннотацию переменной «аннотация».

## Шаг 5: Получите свойства аннотации

Чтобы извлечь свойства каждой аннотации, вы можете добавить следующий код в цикл foreach:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Этот код записывает заголовок, тему и содержимое каждой аннотации в консоль.

### Пример исходного кода для получения всех аннотаций со страницы с использованием Aspose.PDF для .NET

Вот полный исходный код для получения всех аннотаций со страницы PDF с использованием Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Перебрать все аннотации
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Получить свойства аннотации
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```
