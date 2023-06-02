---
title: Добавить аннотацию
linktitle: Добавить аннотацию
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять текстовые аннотации с помощью Aspose.PDF для .NET, используя этот исходный код C#. Настройте свои аннотации с конкретными деталями и значками.
type: docs
weight: 10
url: /ru/net/annotations/addannotation/
---

Добавление аннотаций к документам PDF — это мощная функция, которая может улучшить процессы совместной работы и рецензирования. Aspose.PDF для .NET упрощает программное добавление аннотаций в PDF-документы с помощью C#. В этом руководстве мы шаг за шагом объясним, как использовать Aspose.PDF для .NET для добавления аннотаций в документ PDF.

## Шаг 1: Создайте новый проект и установите Aspose.PDF для .NET

Прежде чем мы начнем писать код для добавления аннотаций, нам нужно создать новый проект и установить Aspose.PDF для .NET. Чтобы установить Aspose.PDF для .NET, выполните следующие действия:

1. Откройте Visual Studio и создайте новый проект C#.
2. Щелкните правой кнопкой мыши проект в обозревателе решений и выберите «Управление пакетами NuGet».
3. Найдите «Aspose.PDF» и выберите «Установить».

После завершения установки мы можем приступить к написанию кода.

## Шаг 2: Откройте PDF-документ

Первым шагом в добавлении аннотаций является открытие документа PDF. Мы можем использовать следующий код, чтобы открыть документ:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

В этом коде мы указываем путь к документу PDF, который хотим открыть. Обязательно замените «ВАШ КАТАЛОГ ДАННЫХ» фактическим путем к вашему каталогу данных.

## Шаг 3: Создайте аннотацию

 Чтобы добавить аннотацию, нам нужно создать новый экземпляр`TextAnnotation` сорт. Мы можем использовать следующий код для создания новой текстовой аннотации:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

В этом коде мы создаем новую текстовую аннотацию на второй странице документа PDF. Мы также устанавливаем свойства заголовка, темы, состояния, содержимого, открытия и значка аннотации.

## Шаг 4: Настройте аннотацию

 Мы можем настроить внешний вид аннотации с помощью`Border` сорт. Мы можем использовать следующий код для настройки границы аннотации:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 В этом коде мы создаем новый`Border` объекта и задайте его ширину и свойства тире. Затем мы устанавливаем`Border` свойство аннотации к новому`Border`объект. Наконец, мы устанавливаем`Rect` свойство аннотации, чтобы указать ее положение и размер.

## Шаг 5: добавьте аннотацию в документ PDF

После того, как мы создали и настроили аннотацию, нам нужно добавить ее в документ PDF. Мы можем использовать следующий код, чтобы добавить аннотацию в документ PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

В этом коде мы добавляем аннотацию в коллекцию аннотаций второй страницы PDF-документа.

## Шаг 6: Сохраните выходной файл

Наконец, нам нужно сохранить документ PDF с добавленной аннотацией. Мы можем использовать следующий код для сохранения выходного файла:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Пример исходного кода для добавления аннотаций с использованием Aspose.PDF для .NET


```csharp   
 // Путь к каталогу документов.
string dataDir = "YOUR DATA DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Создать аннотацию
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Добавить аннотацию в коллекцию аннотаций страницы
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Сохранить выходной файл
pdfDocument.Save(dataDir);
```
Этот код демонстрирует, как добавить текстовую аннотацию с определенным заголовком, темой, состоянием, содержимым и значком на страницу PDF с помощью Aspose.PDF для .NET. Вы можете изменить этот код в соответствии с вашими требованиями для добавления аннотаций к документам PDF. Просто не забудьте заменить YOUR DATA DIRECTORY фактическим путем к каталогу, в котором находится ваш файл PDF и где вы хотите сохранить выходной файл.