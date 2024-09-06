---
title: Добавить упорядоченный список HTML в документы
linktitle: Добавить HTML-упорядоченный список в документы
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как добавить упорядоченный список HTML в документ с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-text/add-html-ordered-list-into-documents/
---
В этом уроке вы узнаете, как использовать библиотеку Aspose.PDF для .NET для добавления упорядоченного списка HTML в документ. Приведенный код демонстрирует необходимые шаги для выполнения этой задачи.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, куда вы хотите добавить упорядоченный список HTML, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите каталог документа и путь к выходному файлу
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

 Далее найдите строку, в которой говорится:`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` и заменить`"AddHTMLOrderedListIntoDocuments_out.pdf"` с желаемым именем для вашего выходного PDF-файла.

## Шаг 4: Создайте новый объект «Документ»
 Создать новый экземпляр`Document` объект, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5: Создайте объект HtmlFragment с HTML-содержимым
 Создайте экземпляр`HtmlFragment` объект с содержимым HTML, которое вы хотите добавить в документ. В предоставленном коде содержимое HTML назначается переменной`t`. Вы можете изменить HTML-контент по мере необходимости.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Шаг 6: Добавьте страницу в документ
 Добавьте новую страницу в документ, используя`Add` Метод`Pages`Коллекция. В представленном коде новая страница присваивается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 7: Добавьте HtmlFragment на страницу
 Добавьте`HtmlFragment` объект на страницу с помощью`Add` Метод`Paragraphs` коллекция.

```csharp
page.Paragraphs.Add(t);
```

## Шаг 8: Сохраните PDF-документ.
 Сохраните полученный PDF-файл с помощью`Save` Метод`Document` объект. Укажите путь к выходному файлу, который вы задали в Шаге 3.

```csharp
doc.Save(outFile);
```

### Пример исходного кода для добавления HTMLOrdered List в документы с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Путь к выходному документу.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Создать экземпляр объекта Document
Document doc = new Document();
// Создать экземпляр объекта HtmlFragment с соответствующим фрагментом HTML
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Добавить страницу в коллекцию страниц
Page page = doc.Pages.Add();
// Добавить HtmlFragment внутрь страницы
page.Paragraphs.Add(t);
// Сохранить полученный PDF-файл
doc.Save(outFile);
```

## Заключение
Вы успешно добавили упорядоченный список HTML в документ с помощью Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути выходного файла.

Не забудьте настроить HTML-контент и скорректировать код в соответствии с вашими конкретными требованиями.

### Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: Цель этого руководства — провести вас через процесс добавления упорядоченного списка HTML в документ с использованием библиотеки Aspose.PDF для .NET. Оно предоставляет пошаговые инструкции и фрагменты кода, которые помогут вам выполнить эту задачу.

#### В: Какие пространства имен мне необходимо импортировать для этого руководства?

A: Вам необходимо импортировать следующие пространства имен в верхнюю часть файла кода:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### В: Как указать каталог документа и путь к выходному файлу?

 A: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов. Также найдите строку`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` и заменить`"AddHTMLOrderedListIntoDocuments_out.pdf"` с желаемым именем выходного PDF-файла.

#### В: Могу ли я настроить HTML-контент, добавляемый в документ?

 A: Конечно! На шаге 5 вы создадите`HtmlFragment` объект назван`t` который содержит HTML-контент. Вы можете изменить HTML-контент в обратных кавычках в соответствии с вашими требованиями.

#### В: Как добавить упорядоченный список HTML на страницу документа?

 A: На шаге 7 вы добавите`HtmlFragment` объект (`t` ) на страницу с помощью`Add` Метод`Paragraphs`Коллекция. Это позволит легко интегрировать упорядоченный список HTML в документ.

#### В: Как сохранить полученный PDF-документ?

 A: После добавления HTML-контента и размещения его на странице вы можете сохранить PDF-документ с помощью`Save` Метод`Document` объект. Обязательно укажите правильный путь к выходному файлу, который вы установили ранее.

#### В: Можете ли вы предоставить краткое изложение исходного кода примера для справки?

A: Конечно! Вот обобщенная версия исходного кода примера, представленного в этом руководстве:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы успешно узнали, как использовать библиотеку Aspose.PDF для .NET для включения упорядоченного списка HTML в документ. Эти новые знания можно применить для улучшения процессов создания и обработки документов.