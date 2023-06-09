---
title: Конвертировать поток изображений в PDF
linktitle: Конвертировать поток изображений в PDF
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте поток изображений в файл PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-images/convert-image-stream-to-pdf/
---

В этом руководстве вы шаг за шагом узнаете, как преобразовать поток изображений в файл PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваше изображение.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте экземпляр объекта Document

 На этом шаге мы создадим экземпляр`Document` объект с помощью пустого конструктора`Aspose.Pdf.Document` сорт.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Шаг 3. Добавьте страницу в документ PDF

 Добавьте страницу в документ PDF, используя кнопку`Add` метод`Pages` объект`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Шаг 4: Чтение потока изображений

 На этом шаге мы создадим`FileStream` объект для чтения файла изображения из потока.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Шаг 5: Считайте изображение в массив байтов

 Прочитайте изображение из потока и сохраните его в массиве байтов, используя`Read` метод`fs` объект.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Шаг 6: Создайте объект MemoryStream из массива байтов

 Создать`MemoryStream` объект из массива байтов, содержащего изображение.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Шаг 7: Создайте объект изображения

 На этом шаге мы создадим`Image` объект с помощью`Aspose.Pdf.Image` сорт. Укажите поток изображения с помощью`ImageStream` имущество и передать`ms` объект, который мы создали ранее.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Шаг 8. Добавьте объект Image в коллекцию Paragraphs.

 Добавить`imageht` возражать против`Paragraphs` коллекция`sec` раздел.

```csharp
sec.Paragraphs.Add(imageht);
```

## Шаг 9: Сохраните PDF-документ

 Сохраните документ PDF с помощью`Save` метод`pdf1` объект. Укажите выходной путь файла PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Шаг 10: Закройте объект MemoryStream

 Закрой`ms` объект с помощью`Close` метод освобождения ресурсов.

```csharp
ms. Close();
```

### Пример исходного кода для преобразования потока изображений в PDF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Создайте экземпляр документа, вызвав его пустой конструктор
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Добавить страницу в документ PDF
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Создайте объект FileStream для чтения файла изображения.
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Считайте изображение в массив байтов
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Создайте объект MemoryStream из массива байтов изображения
MemoryStream ms = new MemoryStream(data);
// Создайте объект изображения
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Укажите источник изображения как MemoryStream
imageht.ImageStream = ms;
// Добавить объект изображения в коллекцию Paragraphs раздела
sec.Paragraphs.Add(imageht);
// Сохраните PDF-файл
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Закройте объект MemoryStream
ms.Close();
```

## Заключение

Поздравляем! Вы успешно преобразовали поток изображений в файл PDF с помощью Aspose.PDF для .NET. Сгенерированный файл PDF сохраняется в указанном каталоге. Теперь вы можете использовать этот PDF-файл в своих проектах или приложениях.