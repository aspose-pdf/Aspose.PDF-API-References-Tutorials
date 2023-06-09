---
title: Добавить упорядоченный список HTML в документы
linktitle: Добавить упорядоченный список HTML в документы
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить упорядоченный список HTML в документ с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-text/add-html-ordered-list-into-documents/
---

В этом руководстве вы узнаете, как использовать библиотеку Aspose.PDF для .NET для добавления упорядоченного списка HTML в документ. Предоставленный код демонстрирует необходимые шаги для выполнения этой задачи.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файл кода, в который вы хотите добавить упорядоченный список HTML, добавьте следующие директивы using вверху файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Установите каталог документа и путь к выходному файлу
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

 Затем найдите строку, которая говорит`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` и заменить`"AddHTMLOrderedListIntoDocuments_out.pdf"` с желаемым именем для выходного PDF-файла.

## Шаг 4: Создайте новый объект документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Создайте объект HtmlFragment с содержимым HTML.
 Создать экземпляр`HtmlFragment` объект с содержимым HTML, которое вы хотите добавить в документ. В предоставленном коде содержимое HTML присваивается переменной`t`. При необходимости вы можете изменить HTML-контент.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Шаг 6: Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью кнопки`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 7: Добавьте HtmlFragment на страницу
 Добавить`HtmlFragment` объект на страницу с помощью`Add` метод`Paragraphs` коллекция.

```csharp
page.Paragraphs.Add(t);
```

## Шаг 8: Сохраните PDF-документ
 Сохраните полученный файл PDF с помощью`Save` метод`Document` объект. Укажите путь к выходному файлу, заданный на шаге 3.

```csharp
doc.Save(outFile);
```

### Пример исходного кода для добавления упорядоченного списка HTML в документы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Путь к выходному документу.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Создать объект документа
Document doc = new Document();
// Создать экземпляр объекта HtmlFragment с соответствующим фрагментом HTML
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Добавить страницу в коллекцию страниц
Page page = doc.Pages.Add();
// Добавить HtmlFragment внутри страницы
page.Paragraphs.Add(t);
// Сохраните полученный файл PDF
doc.Save(outFile);
```

## Заключение
Вы успешно добавили упорядоченный список HTML в документ, используя Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.

Не забудьте настроить содержимое HTML и настроить код в соответствии с вашими конкретными требованиями.