---
title: Определить разрыв строки в PDF-файле
linktitle: Определить разрыв строки в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как определить разрывы строк в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 130
url: /ru/net/programming-with-text/determine-line-break/
---
Это руководство проведет вас через процесс определения разрывов строк в PDF-файле с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файле кода, в котором вы хотите определить разрывы строк, добавьте следующие директивы в верхней части файла:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте новый экземпляр документа.
 Создать экземпляр нового`Document` объект, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages`коллекция. В предоставленном коде новая страница присваивается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 6. Добавьте фрагменты текста с разрывами строк.
Создайте цикл для добавления на страницу нескольких фрагментов текста, каждый из которых содержит абзац с разрывами строк.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Шаг 7. Сохраните PDF-документ и извлеките информацию о разрыве строки.
 Сохраните PDF-документ, используя`Save` метод`Document` объект. Затем извлеките информацию о разрыве строки, используя`GetNotifications` метод нужной страницы.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Пример исходного кода для определения разрыва строки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Заключение
Вы успешно определили разрывы строк в PDF-документе с помощью Aspose.PDF для .NET. Информация о разрыве строки была извлечена и сохранена в текстовый файл.

### Часто задаваемые вопросы

#### Вопрос: Какова основная цель этого урока?

О: Это руководство направлено на то, чтобы помочь вам определить разрывы строк в PDF-файле с помощью библиотеки Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги для достижения этой цели.

#### Вопрос: Какие пространства имен мне следует импортировать для этого руководства?

О: В файле кода, в котором вы хотите определить разрывы строк, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как создать новый экземпляр документа?

 О: На шаге 4 вы создадите новый экземпляр`Document` объект, используя предоставленный код.

#### Вопрос: Как добавить страницу в документ?

 О: На шаге 5 вы добавите в документ новую страницу, используя`Add` метод`Pages` коллекция.

#### Вопрос: Как добавить фрагменты текста с разрывами строк?

О: На шаге 6 вы создадите цикл для добавления на страницу нескольких фрагментов текста, каждый из которых содержит абзац с разрывами строк.

#### Вопрос: Как сохранить PDF-документ и извлечь информацию о разрыве строки?

 О: На шаге 7 вы сохраните PDF-документ, используя`Save` метод`Document` объект. Затем вы извлечете информацию о разрыве строки, используя`GetNotifications` метод нужной страницы и сохраните его в текстовый файл.

#### Вопрос: Какова цель извлеченной информации о разрыве строки?

Ответ: Извлеченная информация о разрыве строки содержит подробную информацию о разрывах строк и уведомлениях, присутствующих в PDF-документе. Это может быть полезно для анализа и понимания структуры текста и абзацев в документе.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы научились определять разрывы строк в PDF-документе с помощью Aspose.PDF для .NET. Вы можете использовать эти знания для программного извлечения и анализа информации о разрыве строк из файлов PDF.