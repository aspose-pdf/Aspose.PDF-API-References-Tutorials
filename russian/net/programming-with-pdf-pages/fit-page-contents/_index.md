---
title: Подогнать содержимое страницы
linktitle: Подогнать содержимое страницы
second_title: Aspose.PDF для справочника API .NET
description: Подробное пошаговое руководство по настройке содержимого страницы PDF с помощью Aspose.PDF для .NET. Простая реализация и полезный вывод.
type: docs
weight: 50
url: /ru/net/programming-with-pdf-pages/fit-page-contents/
---
В этом руководстве мы пошагово проведем вас через процесс настройки содержимого страницы PDF с помощью Aspose.PDF для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как настроить содержимое страниц PDF с помощью Aspose.PDF для .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#
- Aspose.PDF для .NET, установленный в вашей среде разработки

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где находится ваш входной PDF-файл. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите PDF-документ
 Затем вы можете загрузить документ PDF, используя`Document` класс Aspose.PDF. Обязательно укажите правильный путь к исходному файлу PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 3. Настройте содержимое страницы
Теперь вы можете просматривать все страницы документа и настраивать содержимое каждой страницы в соответствии с размером окна мультимедиа. В приведенном примере мы настраиваем ширину страницы, чтобы отображать ее в ландшафтном режиме (альбомная ориентация) с сохранением той же высоты. Новая ширина рассчитывается на основе соотношения сторон медиабокса.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### Пример исходного кода для Fit Page Contents с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// Новая высота такая же
	double newHeight = r.Height;
	// Новая ширина увеличена пропорционально, чтобы сделать ориентацию альбомной.
	// (мы предполагаем, что предыдущая ориентация портретная)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## Заключение
В этом руководстве мы узнали, как настроить содержимое страницы PDF с помощью Aspose.PDF для .NET. Выполняя шаги, описанные выше, вы можете легко реализовать эту функциональность в своих собственных проектах. Не стесняйтесь дополнительно изучать документацию Aspose.PDF, чтобы узнать о других полезных функциях для работы с файлами PDF.
