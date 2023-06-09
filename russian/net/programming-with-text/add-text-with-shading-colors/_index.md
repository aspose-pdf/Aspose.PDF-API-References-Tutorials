---
title: Добавить текст с затенением цветов
linktitle: Добавить текст с затенением цветов
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить текст с затеняющими цветами в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-text/add-text-with-shading-colors/
---

Этот учебник проведет вас через процесс добавления текста с использованием цветов заливки с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файле кода, куда вы хотите добавить текст с цветами затенения, добавьте следующую директиву using вверху файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Загрузите PDF-документ
 Загрузите существующий документ PDF с помощью`Document` конструктор и указать путь к файлу документа.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Код идет сюда...
}
```

## Шаг 5: Найдите текст, который нужно изменить
 Использовать`TextFragmentAbsorber` чтобы найти нужный текст в документе. В предоставленном коде он ищет текст «Lorem ipsum».

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Шаг 6: Установите цвет заливки для текста
 Создать новый`Color` объект с цветовым пространством шаблона и укажите цвета градиентного затенения. Назначьте этот цвет`ForegroundColor` собственность`TextState` принадлежащий`TextFragment` объект.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Шаг 7. Примените дополнительное форматирование текста (необязательно)
 К текстовому фрагменту можно применить дополнительное форматирование, например, подчеркивание, изменив свойства`TextState` объект.

```csharp
textFragment.TextState.Underline = true;
```

## Шаг 8: Сохраните измененный PDF-документ
 Сохраните измененный PDF-документ с помощью кнопки`Save` метод`Document` объект.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Пример исходного кода для добавления текста с цветами заливки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Создайте новый цвет с цветовым пространством узора
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Заключение
Вы успешно добавили текст с цветами заливки в документ PDF с помощью Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.