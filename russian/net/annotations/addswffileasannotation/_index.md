---
title: Добавить SWF-файл как аннотацию
linktitle: Добавить SWF-файл как аннотацию
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять SWF-файлы в качестве аннотаций в Aspose.PDF для .NET, с помощью этого пошагового руководства.
type: docs
weight: 30
url: /ru/net/annotations/addswffileasannotation/
---
Если вы являетесь разработчиком .NET и хотите добавить мультимедийный файл SWF в качестве аннотации к документу PDF с помощью Aspose.PDF для .NET, это пошаговое руководство для вас. В этой статье мы объясним, как добавлять SWF-файлы в качестве аннотаций в документы PDF с помощью языка программирования C#. 

Выполните следующие шаги, чтобы добавить SWF-файл в качестве аннотации в документ PDF с помощью Aspose.PDF для .NET:

## Шаг 1. Установите путь к каталогу

Во-первых, нам нужно установить путь к каталогу, в котором хранятся файлы PDF и SWF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на путь к вашему каталогу документов.

## Шаг 2. Загрузите PDF-документ

Далее нам нужно загрузить документ PDF, используя следующий код:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

Этот код загрузит файл «AddSwfFileAsAnnotation.pdf» из каталога документов.

## Шаг 3. Получите страницу для добавления аннотации

Теперь нам нужно получить ссылку на страницу, к которой мы хотим добавить аннотацию. В этом уроке мы добавим аннотацию на первую страницу документа.

```csharp
Page page = doc.Pages[1];
```

## Шаг 4: Создайте объект ScreenAnnotation

 Теперь мы можем создать`ScreenAnnotation` объект с файлом SWF в качестве аргумента.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

`ScreenAnnotation` конструктор принимает три аргумента:

- `page`: страница, на которую будет добавлена аннотация.
- `rectangle`: прямоугольник, в котором SWF-файл будет отображаться на странице.
- `dataDir + "input.swf"`: путь к SWF-файлу.

## Шаг 5: Добавьте аннотацию на страницу

Теперь мы можем добавить аннотацию в коллекцию аннотаций страницы.

```csharp
page.Annotations.Add(annotation);
```

## Шаг 6: Сохраните обновленный PDF-документ

Наконец, нам нужно сохранить обновленный PDF-документ с аннотацией, используя следующий код:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

Этот код сохранит обновленный документ PDF с аннотацией как «AddSwfFileAsAnnotation_out.pdf» в каталоге документов.

### Пример исходного кода для добавления SWF-файла в качестве аннотации с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Откройте PDF-документ
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

// Получить ссылку на страницу, на которую нужно добавить аннотацию
Page page = doc.Pages[1];

// Создайте объект ScreenAnnotation с мультимедийным файлом .swf в качестве аргумента
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

// Добавьте аннотацию в коллекцию аннотаций страницы
page.Annotations.Add(annotation);

dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
// Сохраните обновленный PDF-документ с аннотацией.
doc.Save(dataDir);
```        
