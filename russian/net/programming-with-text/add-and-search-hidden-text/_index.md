---
title: Добавить и найти скрытый текст
linktitle: Добавить и найти скрытый текст
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по добавлению и поиску скрытого текста в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-text/add-and-search-hidden-text/
---

В этом руководстве мы расскажем, как добавлять и искать скрытый текст в документе PDF с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

## 1. Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная и настроенная Visual Studio или любая другая среда разработки.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## 2. Создание документа PDF со скрытым текстом

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

Обязательно укажите желаемый путь и имя файла для документа PDF.

## 3. Поиск текста в документе

Далее мы будем искать скрытый текст в документе PDF. Используйте следующий код:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Сделайте что-нибудь с фрагментами
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Это приведет к поиску скрытого текста на второй странице документа PDF и отображению соответствующей информации.

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

Поздравляем! Вы успешно добавили и нашли скрытый текст в документе PDF с помощью Aspose.PDF для .NET. Теперь вы можете применить этот метод к своим собственным проектам для управления и поиска скрытого текста в файлах PDF.