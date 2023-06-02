---
title: Вычеркнуть слова
linktitle: Вычеркнуть слова
second_title: Aspose.PDF для справочника API .NET
description: В этой статье представлено пошаговое руководство по использованию Aspose.PDF для функции .NET Strike Out Words, включая пошаговое руководство и пояснения.
type: docs
weight: 150
url: /ru/net/annotations/strikeoutwords/
---
Aspose.PDF для .NET — это библиотека для обработки и обработки PDF-документов, которая предоставляет различные функции для создания, изменения и преобразования PDF-файлов. Одной из полезных функций, предоставляемых Aspose.PDF, является возможность зачеркивать слова или фразы в документе PDF с использованием исходного кода C#. В этой статье мы предоставим пошаговое руководство о том, как зачеркивать слова с помощью Aspose.PDF для .NET.

## Загрузка PDF-документа
Первый шаг — загрузить документ PDF, который вы хотите изменить. В этом руководстве мы загрузим PDF-документ с именем «input.pdf» из папки «ВАШ КАТАЛОГ ДОКУМЕНТОВ». 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Поиск текстовых фрагментов
Чтобы вычеркнуть определенные слова или фразы в документе PDF, сначала необходимо выполнить их поиск. Aspose.PDF предоставляет класс TextFragmentAbsorber, который можно использовать для поиска определенного текстового фрагмента в документе PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

В приведенном выше коде мы ищем фрагмент текста «Estoque» в документе PDF. Вы можете изменить это для поиска любого другого слова или фразы, которые вы хотите вычеркнуть.

## Вычеркивание фрагментов текста
После нахождения текстовых фрагментов следующим шагом будет их вычеркивание. Aspose.PDF предоставляет класс StrikeOutAnnotation, который можно использовать для создания зачеркивающей аннотации к текстовому фрагменту. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

В приведенном выше коде мы создаем зачеркнутую аннотацию для каждого найденного фрагмента текста. Мы также устанавливаем непрозрачность, границу и цвет зачеркнутой аннотации.

## Сохранение измененного документа PDF
Вычеркнув фрагменты текста, сохраните измененный документ.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Пример исходного кода для Strike Out Words с использованием Aspose.PDF для .NET


```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document document = new Document(dataDir + "input.pdf");

// Создайте экземпляр TextFragment Absorber для поиска определенного текстового фрагмента
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Итерация по страницам PDF-документа
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Получить первую страницу документа PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Создайте коллекцию поглощенного текста
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Повторить вышеприведенную коллекцию
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Получить прямоугольные размеры объекта TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Создание экземпляра аннотации StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Установить непрозрачность для аннотации
	strikeOut.Opacity = .80f;
	// Установите границу для экземпляра аннотации
	strikeOut.Border = new Border(strikeOut);
	// Установить цвет аннотации
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Добавить аннотацию в коллекцию аннотаций TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```
