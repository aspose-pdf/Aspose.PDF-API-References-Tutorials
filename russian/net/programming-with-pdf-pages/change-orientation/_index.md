---
title: Изменить ориентацию
linktitle: Изменить ориентацию
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по изменению ориентации страницы PDF с помощью Aspose.PDF для .NET. Легко следовать и внедрять в свои проекты.
type: docs
weight: 10
url: /ru/net/programming-with-pdf-pages/change-orientation/
---
В этом руководстве мы пошагово проведем вас через процесс изменения ориентации страницы документа PDF с помощью Aspose.PDF для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как изменить ориентацию страницы ваших PDF-документов с помощью Aspose.PDF для .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#
- Aspose.PDF для .NET, установленный в вашей среде разработки

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где находится ваш входной PDF-файл, и где вы хотите сохранить измененный выходной PDF-файл. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите PDF-документ
 Затем вы можете загрузить документ PDF из входного файла, используя`Document` класс Aspose.PDF. Обязательно укажите правильный путь к файлу PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 3. Измените ориентацию страницы
Теперь мы пройдемся по каждой странице документа и изменим ее ориентацию. Для каждой страницы мы изменяем размеры медиабокса (`MediaBox`), поменяв местами ширину и высоту, затем мы настроим координаты медиабокса, чтобы сохранить положение страницы. Наконец, мы устанавливаем поворот страницы на 90 градусов.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Шаг 4: Сохраните измененный PDF-документ
 Наконец, вы можете сохранить измененный PDF-документ в выходной файл, используя`Save()` метод`Document`сорт. Обязательно укажите правильный путь и имя файла.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для изменения ориентации с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Мы должны переместить страницу вверх, чтобы компенсировать изменение размера страницы
	// (нижний край страницы равен 0,0 и информация обычно размещается с
	// Верхняя часть страницы. Вот почему мы перемещаем нижний край вверх по разнице между
	// Старая и новая высота.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Иногда нам также нужно установить CropBox (если он был установлен в исходном файле)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Настройка угла поворота страницы
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Сохранить выходной файл
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Заключение
В этом руководстве мы узнали, как изменить ориентацию страницы документа PDF с помощью Aspose.PDF для .NET. Выполняя шаги, описанные выше, вы можете легко реализовать эту функциональность в своих собственных проектах. Не стесняйтесь дополнительно изучать документацию Aspose.PDF, чтобы узнать о других полезных функциях для работы с файлами PDF.