---
title: Вычеркнуть слова
linktitle: Вычеркнуть слова
second_title: Справочник по Aspose.PDF для .NET API
description: В этой статье представлено пошаговое руководство по использованию Aspose.PDF для функции «Зачеркнуть слова» в .NET, включая пошаговое руководство и пояснения.
type: docs
weight: 150
url: /ru/net/annotations/strikeoutwords/
---
Aspose.PDF для .NET — это библиотека манипулирования и обработки PDF-документов, которая предоставляет различные функции для создания, изменения и преобразования PDF-файлов. Одной из полезных функций, предоставляемых Aspose.PDF, является возможность вычеркивать слова или фразы в PDF-документе с использованием исходного кода C#. В этой статье мы предоставим пошаговое руководство о том, как вычеркивать слова с помощью Aspose.PDF для .NET.

## Шаг 1. Загрузка PDF-документа
Первый шаг — загрузить PDF-документ, который вы хотите изменить. В этом уроке мы загрузим PDF-документ с именем «input.pdf» из папки «ВАШ ДОКУМЕНТНЫЙ КАТАЛОГ». 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Шаг 2: Поиск фрагментов текста
Чтобы вычеркнуть определенные слова или фразы в документе PDF, сначала необходимо выполнить их поиск. Aspose.PDF предоставляет класс TextFragmentAbsorber, который можно использовать для поиска определенного фрагмента текста в PDF-документе.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

В приведенном выше коде мы ищем текстовый фрагмент «Estoque» в PDF-документе. Вы можете изменить это, чтобы искать любое другое слово или фразу, которую вы хотите вычеркнуть.

## Шаг 3. Вычеркивание фрагментов текста
После обнаружения фрагментов текста следующим шагом будет их вычеркивание. Aspose.PDF предоставляет класс StrikeOutAnnotation, который можно использовать для создания зачеркнутой аннотации для текстового фрагмента. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

В приведенном выше коде мы создаем зачеркнутую аннотацию для каждого найденного фрагмента текста. Мы также устанавливаем непрозрачность, границу и цвет зачеркнутой аннотации.

## Шаг 4. Сохранение измененного PDF-документа.
После вычеркивания фрагментов текста сохраните измененный документ.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Пример исходного кода для вычеркивания слов с использованием Aspose.PDF для .NET


```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document document = new Document(dataDir + "input.pdf");

// Создайте экземпляр TextFragment Absorber для поиска определенного фрагмента текста.
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Перебирать страницы PDF-документа
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Получить первую страницу PDF-документа
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Создайте коллекцию поглощенного текста.
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Перебрать вышеуказанную коллекцию
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
	// Установить непрозрачность аннотации
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

## Заключение

В этом уроке мы узнали, как использовать Aspose.PDF для .NET для вычеркивания определенных слов в PDF-документе. Следуя пошаговому руководству и используя предоставленный исходный код C#, вы можете легко загрузить PDF-документ, искать определенные фрагменты текста и создавать зачеркивающие аннотации, чтобы визуально отмечать и зачеркивать эти слова. Aspose.PDF для .NET предоставляет простой и эффективный способ программного управления PDF-документами, что делает его ценным инструментом для разработчиков, работающих с PDF-файлами в приложениях .NET.

### Часто задаваемые вопросы

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам программно создавать, редактировать и манипулировать PDF-документами в приложениях .NET. Он предоставляет широкий спектр функций для работы с PDF-файлами, включая извлечение текста, обработку аннотаций, заполнение форм и многое другое.

#### Вопрос: Могу ли я использовать Aspose.PDF для .NET, чтобы вычеркивать определенные слова в PDF-документе?

О: Да, Aspose.PDF для .NET предоставляет функциональные возможности для поиска определенных фрагментов текста в PDF-документе, а затем создания зачеркивающих аннотаций для визуального выделения и зачеркивания этих слов.

#### Вопрос: Как указать текст, который я хочу зачеркнуть в PDF-документе?

 О: Чтобы указать текст, который вы хотите зачеркнуть, вы можете использовать`TextFragmentAbsorber` класс, предоставленный Aspose.PDF для .NET. Он позволяет вам искать определенный фрагмент текста в PDF-документе по желаемым критериям.

#### Вопрос: Могу ли я настроить внешний вид зачеркнутой аннотации?

О: Да, вы можете настроить различные свойства зачеркнутой аннотации, такие как непрозрачность, стиль границы и цвет. Это позволяет адаптировать внешний вид зачеркнутой аннотации к вашим конкретным требованиям.