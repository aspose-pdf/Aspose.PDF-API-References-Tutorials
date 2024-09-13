---
title: Добавление и поиск скрытого текста в PDF-файле
linktitle: Добавление и поиск скрытого текста в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Пошаговое руководство по добавлению и поиску скрытого текста в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-text/add-and-search-hidden-text/
---
В этом уроке мы покажем вам, как добавлять и искать скрытый текст в PDF-файле с помощью Aspose.PDF для .NET. Выполните следующие шаги, чтобы легко выполнить эту операцию.

## 1. Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любая другая установленная и настроенная среда разработки.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Скачать ее можно с официального сайта Aspose.

## 2. Создание PDF-документа со скрытым текстом

Для начала используйте следующий код для создания нового PDF-документа, содержащего скрытый текст:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Создать документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Установить свойство текста - невидимый
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Обязательно укажите желаемый путь и имя файла для PDF-документа.

## 3. Поиск текста в документе

Далее мы будем искать скрытый текст в документе PDF. Используйте следующий код:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Сделайте что-нибудь с фрагментами.
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Будет выполнен поиск скрытого текста на второй странице PDF-документа и отображена соответствующая информация.

### Пример исходного кода для добавления и поиска скрытого текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Создать документ со скрытым текстом
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Установить свойство текста - невидимый
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Поиск текста в документе
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Сделайте что-нибудь с фрагментами
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Заключение

Поздравляем! Вы успешно добавили и нашли скрытый текст в PDF-документе с помощью Aspose.PDF для .NET. Теперь вы можете применять этот метод к своим собственным проектам для управления и поиска скрытого текста в PDF-файлах.

### Часто задаваемые вопросы

#### В: Что такое Aspose.PDF для .NET?

A: Aspose.PDF для .NET — это надежная библиотека, которая позволяет разработчикам создавать, обрабатывать и преобразовывать PDF-документы в приложениях .NET.

#### В: Можно ли использовать скрытый текст для создания водяных знаков?

A: Конечно! Скрытый текст может служить эффективным средством маркировки PDF-документов водяными знаками, добавляя дополнительный уровень безопасности.

#### В: Можно ли раскрыть скрытый текст в PDF-документе?

A: Да, процесс поиска и обнаружения скрытого текста в документе PDF может быть реализован с использованием методов, описанных в этом руководстве.

#### В: Какие еще функции предлагает Aspose.PDF для .NET?

A: Помимо манипуляций со скрытым текстом, Aspose.PDF для .NET предоставляет широкий спектр функций, включая создание PDF-файлов, преобразование, шифрование и многое другое.