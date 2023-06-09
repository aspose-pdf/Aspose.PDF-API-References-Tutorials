---
title: PDF-операторы
linktitle: PDF-операторы
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по использованию операторов PDF с Aspose.PDF для .NET. Добавьте изображение на страницу PDF и укажите его положение.
type: docs
weight: 20
url: /ru/net/programming-with-operators/pdf-operators/
---
В этом руководстве мы предоставим вам пошаговое руководство по использованию операторов PDF с помощью Aspose.PDF для .NET. Операторы PDF позволяют точно и контролируемо манипулировать и добавлять содержимое в документы PDF. Используя операторы, предоставляемые Aspose.PDF, вы можете добавить изображение на страницу PDF и точно указать его положение.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена с .NET framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF для .NET. Вы можете загрузить библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2. Импортируйте необходимые пространства имен

В файле кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Шаг 3: Загрузка PDF-документа

Используйте следующий код для загрузки PDF-документа:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document pdfDocument = new Document(dataDir + "PDFOperators.pdf");
```

Обязательно укажите фактический путь к файлу PDF на вашем компьютере.

## Шаг 4: Загрузка изображения и добавление его на страницу

Используйте следующий код, чтобы загрузить изображение из файла и добавить его на страницу PDF:

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;

Page page = pdfDocument.Pages[1];

FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream);

page. Contents. Add(new GSave());

Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });

page.Contents.Add(new ConcatenateMatrix(matrix));

XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Do(ximage.Name));

page. Contents. Add(new GRestore());
```

 Обязательно укажите фактические пути к файлам PDF и изображений на вашем компьютере. Вы также можете настроить`lowerLeftX`, `lowerLeftY`, `upperRightX` и`upperRightY` координаты для позиционирования изображения по мере необходимости.

### Пример исходного кода для операторов PDF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir+ "PDFOperators.pdf");
// Установить координаты
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Получить страницу, на которую нужно добавить изображение
Page page = pdfDocument.Pages[1];
// Загрузить изображение в поток
FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
// Добавить изображение в коллекцию изображений ресурсов страницы
page.Resources.Images.Add(imageStream);
// Использование оператора GSave: этот оператор сохраняет текущее состояние графики.
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Создание объектов «Прямоугольник» и «Матрица»
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//Использование оператора ConcatenateMatrix (сцепление матрицы): определяет, как должно быть размещено изображение.
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Использование оператора Do: этот оператор рисует изображение
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Использование оператора GRestore: этот оператор восстанавливает состояние графики
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "PDFOperators_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
```

## Заключение

В этом руководстве вы узнали, как использовать операторы PDF с помощью Aspose.PDF для .NET. Следуя описанным шагам, вы сможете добавить изображение на страницу PDF и точно указать его положение. Операторы PDF обеспечивают детальный контроль над манипулированием PDF-документами, позволяя настраивать содержимое.
