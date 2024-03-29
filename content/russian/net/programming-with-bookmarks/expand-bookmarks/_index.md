---
title: Развернуть закладки в PDF-файле
linktitle: Развернуть закладки в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Легко расширяйте закладки в PDF-файле для улучшения навигации с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-bookmarks/expand-bookmarks/
---
При раскрытии закладок в PDF-файле по умолчанию отображаются все открытые закладки. С помощью Aspose.PDF для .NET вы можете легко расширить закладки, выполнив следующий исходный код:

## Шаг 1. Импортируйте необходимые библиотеки.

Прежде чем начать, вам необходимо импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
```

## Шаг 2. Установите путь к папке с документами.

 На этом шаге вам необходимо указать путь к папке, содержащей PDF-файл, закладки которого вы хотите расширить. Заменять`"YOUR DOCUMENT DIRECTORY"`в следующем коде с фактическим путем к папке ваших документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3. Откройте PDF-документ.

Теперь мы откроем PDF-документ, закладки которого хотим расширить, используя следующий код:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 4. Установите режим отображения страницы

На этом этапе мы установим режим отображения страницы для отображения закладок по умолчанию. Мы используем`PageMode` собственность`doc` объект для установки желаемого режима страницы. Вот соответствующий код:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Шаг 5. Просмотрите закладки и разверните их

 Теперь мы пройдемся по каждому элементу закладки в коллекции закладок документа и установим для каждого элемента открытое состояние.`true` чтобы развернуть их по умолчанию. Вот соответствующий код:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Шаг 6. Сохраните обновленный файл.

 Наконец, мы сохраняем обновленный PDF-файл, используя`Save` метод`doc` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для расширения закладок с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document doc = new Document(dataDir + "input.pdf");
// Установить режим просмотра страницы, т.е. показывать миниатюры, полноэкранный режим, показывать панель вложений.
doc.PageMode = PageMode.UseOutlines;
// Просмотрите каждый элемент Ouline в коллекции контуров PDF-файла.
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Установить открытый статус для элемента структуры
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Сохранить вывод
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по разработке закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код, чтобы показать все закладки по умолчанию в ваших PDF-документах.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.

### Часто задаваемые вопросы по расширению закладок в PDF-файле

#### Вопрос: Что такое закладки в PDF-файле?

О: Закладки в PDF-файле — это средства навигации, которые позволяют пользователям быстро переходить к определенным разделам или страницам документа. Они обеспечивают удобный способ доступа к различным частям документа.

#### Вопрос: Зачем мне расширять закладки в PDF-файле?

О: Раскрытие закладок может улучшить взаимодействие с пользователем, поскольку по умолчанию все закладки отображаются в развернутом состоянии. Это дает пользователям четкое представление о структуре документа и позволяет им легко переходить к различным разделам.

#### Вопрос: Как мне импортировать необходимые библиотеки для моего проекта C#?

О: Чтобы импортировать необходимую библиотеку для вашего проекта C#, используйте следующую директиву импорта:

```csharp
using Aspose.Pdf;
```

Эта директива позволяет вам использовать классы и методы, предоставляемые Aspose.PDF для .NET.

#### Вопрос: Как указать путь к папке с документами?

 О: В предоставленном исходном коде замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к папке, содержащей PDF-файл, с которым вы хотите работать. Это гарантирует, что код сможет найти целевой PDF-файл.

#### Вопрос: Как открыть PDF-документ, чтобы развернуть его закладки?

О: Чтобы открыть PDF-документ для расширения закладок, используйте следующий код:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Заменять`"input.pdf"` с фактическим именем файла.

#### Вопрос: Как настроить режим отображения страницы, чтобы по умолчанию отображались закладки?

О: Чтобы настроить режим отображения страницы на отображение закладок по умолчанию, используйте команду`PageMode` собственность`doc` объект:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Вопрос: Как развернуть все закладки в PDF-документе?

 О: Чтобы развернуть все закладки, просмотрите каждый элемент закладки в коллекции структур документа и установите`Open` собственность`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Вопрос: Что произойдет, если закладка имеет вложенные дочерние закладки?

О: Если закладка имеет вложенные дочерние закладки, раскрытие родительской закладки также приведет к расширению ее дочерних закладок, предоставляя полное представление о структуре документа.

#### Вопрос: Как сохранить обновленный PDF-файл после расширения закладок?

О: Чтобы сохранить обновленный PDF-файл после расширения закладок, используйте следующий код:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Вопрос: Могу ли я настроить внешний вид развернутых закладок?

О: Хотя в этом руководстве основное внимание уделяется расширению закладок по умолчанию, вы можете настроить внешний вид закладок, используя другие функции и свойства Aspose.PDF.