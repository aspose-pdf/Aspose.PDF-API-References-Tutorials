---
title: Z-порядок прямоугольника управления
linktitle: Z-порядок прямоугольника управления
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как управлять Z-порядком прямоугольников в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-graphs/control-rectangle-z-order/
---

В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы управлять Z-порядком прямоугольников с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

## Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором вы хотите сохранить полученный PDF-файл. Измените переменную «dataDir» на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание экземпляра объекта документа и добавление страницы

Мы создаем экземпляр класса Document и добавляем в этот документ страницу.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Шаг 3: Настройка размера страницы

Мы устанавливаем размер страницы PDF с помощью метода SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Шаг 4: Настройка полей страницы

Мы можем настроить поля страницы, используя свойства объекта PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Шаг 5: Добавьте прямоугольники с указанным порядком Z

Мы создаем и добавляем на страницу прямоугольники с разными цветами и указанными порядками Z.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Шаг 6: Сохранение полученного PDF-файла

Наконец, мы сохраняем полученный файл PDF с именем «ControlRectangleZOrder_out.pdf» в указанном каталоге.

```csharp
doc1.Save(dataDir);
```
### Пример исходного кода для управления порядком Z прямоугольника с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создание экземпляра объекта класса Document
Document doc1 = new Document();
/// Добавить страницу в коллекцию страниц файла PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Установить размер страницы PDF
page1.SetPageSize(375, 300);
//Установите левое поле для объекта страницы как 0
page1.PageInfo.Margin.Left = 0;
// Установите верхнее поле объекта страницы как 0
page1.PageInfo.Margin.Top = 0;
// Создайте новый прямоугольник с красным цветом, Z-порядком 0 и определенными размерами.
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Создайте новый прямоугольник с синим цветом, Z-порядком как 0 и определенными размерами.
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Создайте новый прямоугольник с зеленым цветом, Z-порядком как 0 и определенными размерами.
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Сохраните полученный файл PDF
doc1.Save(dataDir);

```

## Заключение

В этом руководстве мы объяснили, как управлять Z-порядком прямоугольников с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для точного размещения и наложения прямоугольников в PDF-файлах.
