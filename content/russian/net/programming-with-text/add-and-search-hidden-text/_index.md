---
title: Добавление и поиск скрытого текста в PDF-файле
linktitle: Добавление и поиск скрытого текста в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по добавлению и поиску скрытого текста в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-text/add-and-search-hidden-text/
---
В этом уроке мы расскажем вам, как добавлять и искать скрытый текст в PDF-файле с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

## 1. Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любая другая среда разработки установлена и настроена.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## 2. Создание PDF-документа со скрытым текстом

Чтобы начать, используйте следующий код, чтобы создать новый PDF-документ, содержащий скрытый текст:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Создать документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Установить свойство текста - невидимо
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Обязательно укажите желаемый путь и имя файла PDF-документа.

## 3. Поиск текста в документе

Далее мы найдем скрытый текст в PDF-документе. Используйте следующий код:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Сделайте что-нибудь с фрагментами
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Это позволит выполнить поиск скрытого текста на второй странице PDF-документа и отобразить соответствующую информацию.

### Пример исходного кода для добавления и поиска скрытого текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Создать документ со скрытым текстом
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Установить свойство текста - невидимо
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

Поздравляем! Вы успешно добавили и нашли скрытый текст в PDF-документе, используя Aspose.PDF для .NET. Теперь вы можете применить этот метод к своим собственным проектам для управления и поиска скрытого текста в файлах PDF.

### Часто задаваемые вопросы

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это надежная библиотека, которая позволяет разработчикам создавать, манипулировать и преобразовывать PDF-документы в приложениях .NET.

#### Вопрос: Можно ли использовать скрытый текст для создания водяных знаков?

А: Абсолютно! Скрытый текст может служить эффективным средством нанесения водяных знаков на PDF-документы, добавляя дополнительный уровень безопасности.

#### Вопрос: Можно ли показать скрытый текст в PDF-документе?

О: Да, процесс поиска и обнаружения скрытого текста в PDF-документе можно выполнить, используя методы, описанные в этом руководстве.

#### Вопрос: Какие еще функции предлагает Aspose.PDF для .NET?

О: Помимо манипулирования скрытым текстом, Aspose.PDF для .NET предоставляет широкий спектр функций, включая создание PDF-файлов, преобразование, шифрование и многое другое.