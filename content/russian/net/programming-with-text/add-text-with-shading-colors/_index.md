---
title: Добавить текст с цветами заливки в файл PDF
linktitle: Добавить текст с цветами заливки в файл PDF
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить текст с цветами заливки в файл PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-text/add-text-with-shading-colors/
---
Это руководство проведет вас через процесс добавления текста с цветами заливки в PDF-файл с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файл кода, куда вы хотите добавить текст с цветами заливки, добавьте следующую директиву using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Загрузите PDF-документ.
 Загрузите существующий PDF-документ, используя`Document` конструктор и укажите путь к файлу документа.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Код идет сюда...
}
```

## Шаг 5. Найдите текст, который нужно изменить.
 Использовать`TextFragmentAbsorber` чтобы найти нужный текст в документе. В предоставленном коде он ищет текст «Lorem ipsum».

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Шаг 6: Установите цвет заливки для текста
 Создать новый`Color` объект с цветовым пространством узора и укажите цвета градиентной заливки. Назначьте этот цвет`ForegroundColor` собственность`TextState` принадлежащий`TextFragment` объект.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Шаг 7. Примените дополнительное форматирование текста (необязательно).
 К фрагменту текста можно применить дополнительное форматирование, например подчеркивание, изменив свойства элемента`TextState` объект.

```csharp
textFragment.TextState.Underline = true;
```

## Шаг 8. Сохраните измененный PDF-документ.
 Сохраните измененный PDF-документ, используя`Save` метод`Document` объект.

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
	// Создайте новый цвет с помощью цветового пространства шаблона
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Заключение
Вы успешно добавили текст с цветами заливки в свой PDF-документ с помощью Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути к выходному файлу.

### Часто задаваемые вопросы

#### Вопрос: Какова основная цель этого урока?

О: Это руководство проведет вас через процесс добавления текста с цветами заливки в файл PDF с использованием библиотеки Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги для достижения этой цели.

#### Вопрос: Какие пространства имен мне нужно импортировать для работы с этим руководством?

О: В файле кода, в который вы хотите добавить текст с цветами заливки, импортируйте следующие пространства имен в начале файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как загрузить существующий PDF-документ?

 О: На шаге 4 вы загрузите существующий PDF-документ, используя`Document` конструктор и указав путь к файлу документа:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Код идет сюда...
}
```

#### Вопрос: Как найти и изменить определенный текст в PDF-документе?

 О: На шаге 5 вы будете использовать`TextFragmentAbsorber`чтобы найти нужный текст в документе. Затем вы можете изменить его свойства:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### Вопрос: Как задать цвета заливки текста?

 О: На шаге 6 вы создадите новый`Color` объект с цветовым пространством узора и укажите цвета градиентной заливки. Назначьте этот цвет`ForegroundColor` собственность`TextState` принадлежащий`TextFragment` объект:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### Вопрос: Могу ли я применить к измененному тексту дополнительное форматирование?

 О: Да, на шаге 7 вы можете применить дополнительное форматирование текста, например подчеркивание, изменив свойства`TextState` объект:

```csharp
textFragment.TextState.Underline = true;
```

#### Вопрос: Как сохранить измененный PDF-документ?

 О: На шаге 8 вы сохраните измененный PDF-документ, используя`Save` метод`Document` объект:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы успешно научились улучшать свой PDF-документ, добавляя текст с цветами заливки с помощью Aspose.PDF для .NET. Это может быть особенно полезно для выделения и выделения определенного текстового содержимого в файлах PDF.