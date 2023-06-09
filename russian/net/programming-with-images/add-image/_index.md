---
title: Добавить изображение
linktitle: Добавить изображение
second_title: Aspose.PDF для справочника API .NET
description: Легко добавляйте изображение в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-images/add-image/
---

Это руководство шаг за шагом расскажет вам, как добавить изображение в документ PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Шаг 3: Установите координаты изображения

 Установите координаты изображения, которое вы хотите добавить. Переменные`lowerLeftX`, `lowerLeftY`, `upperRightX` и`upperRightY` представляют координаты левого нижнего и правого верхнего углов изображения соответственно.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Шаг 4: Получите страницу, на которую нужно добавить изображение

Чтобы добавить изображение на определенную страницу документа PDF, нам сначала нужно получить эту страницу. В этом примере мы добавляем изображение на вторую страницу (индекс 1) документа.

```csharp
Page page = pdfDocument.Pages[1];
```

## Шаг 5: Загрузите изображение из потока

Теперь мы загрузим изображение, которое хотим добавить в документ PDF. В этом примере предполагается, что у вас есть файл изображения с именем`aspose-logo.jpg` в том же каталоге, что и ваш документ. При необходимости замените имя файла.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Шаг 6: Добавьте изображение в ресурсы страницы

Чтобы использовать изображение в документе PDF, нам нужно добавить его в коллекцию изображений ресурса страницы.

```csharp
page.Resources.Images.Add(imageStream);
```

## Шаг 7: Сохраните текущее состояние графики

 Перед рисованием изображения нам нужно сохранить текущее состояние графики с помощью`GSave` оператор. Это гарантирует, что изменения состояния графики можно будет отменить позже.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Шаг 8: Создайте объекты Rectangle и Matrix

 Сейчас мы создадим`Rectangle` объект и`Matrix` объект. Прямоугольник представляет положение и размер изображения, а матрица определяет, как изображение должно быть размещено.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Шаг 9: Объедините матрицу для размещения изображения

 Чтобы указать, как изображение должно быть размещено в прямоугольнике, мы используем`ConcatenateMatrix`оператор. Этот оператор определяет матрицу преобразования, которая отображает координатное пространство изображения в координатное пространство страницы.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Шаг 10: Нарисуйте изображение

 На этом шаге мы нарисуем изображение на странице с помощью`Do` оператор.`Do` Оператор берет имя изображения из ресурсов и рисует его на странице.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Шаг 11: Восстановите состояние графики

 После отрисовки изображения нам нужно восстановить предыдущее состояние графики с помощью команды`GRestore` оператор.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Шаг 12: Сохраните обновленный документ

 Наконец, мы сохраним обновленный документ в новый файл. Обновите`dataDir` переменная с желаемым выходным каталогом и именем файла.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для добавления изображения с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Установить координаты
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Получить страницу, на которую нужно добавить изображение
Page page = pdfDocument.Pages[1];
// Загрузить изображение в поток
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
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
dataDir = dataDir + "AddImage_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Заключение

В этом руководстве мы узнали, как добавить изображение в документ PDF с помощью Aspose.PDF для .NET. Мы подробно рассмотрели каждый шаг, от открытия документа до сохранения обновленной версии. Следуя этому руководству, вы теперь сможете программно встраивать изображения в файлы PDF с помощью C# и Aspose.PDF.