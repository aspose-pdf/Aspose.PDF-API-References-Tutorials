---
title: Удалить изображения
linktitle: Удалить изображения
second_title: Aspose.PDF для справочника API .NET
description: Легко удаляйте изображения из файла PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-images/delete-images/
---

Это руководство поможет вам шаг за шагом удалить изображения из файла PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Шаг 3. Удалите конкретное изображение

 На этом этапе мы собираемся удалить определенное изображение с определенной страницы. Использовать`Delete` метод ресурса страницы`Images` объект для удаления изображения. В приведенном ниже примере мы удаляем изображение с индексом 1 с первой страницы.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Шаг 4. Сохраните обновленный PDF-файл.

 Сохраните обновленный файл PDF с помощью`Save` метод`pdfDocument` объект. Укажите выходной путь для файла PDF.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для удаления изображений с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Удалить конкретное изображение
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Сохранить обновленный файл PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Заключение

Поздравляем! Вы успешно удалили изображения из файла PDF с помощью Aspose.PDF для .NET. Обновленный файл PDF сохраняется в указанном каталоге. Теперь вы можете использовать этот файл PDF без удаленных изображений.