---
title: Добавить дочерние закладки в PDF-файлы
linktitle: Добавить дочерние закладки в PDF-файлы
second_title: Aspose.PDF Java API обработки PDF
description: Узнайте, как улучшить PDF-документы с помощью дочерних закладок с помощью Aspose.PDF для Java. Пошаговое руководство с примерами кода для улучшения навигации и организации.
type: docs
weight: 11
url: /ru/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Введение в добавление дочерних закладок в PDF-файлы

В этой статье мы рассмотрим, как добавлять дочерние закладки в PDF-документы с помощью Aspose.PDF для Java. Дочерние закладки — это удобный способ упорядочить содержимое PDF-документа и перемещаться по нему, упрощая пользователям поиск определенных разделов или тем в документе.

## Предварительные условия

Прежде чем мы углубимся в реализацию, убедитесь, что у вас есть следующие предварительные условия:

- В вашей системе установлена среда разработки Java.
-  Aspose.PDF для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/pdf/java/).

## Настройка среды

1. Загрузите библиотеку Aspose.PDF для Java по предоставленной ссылке.
2. Добавьте библиотеку в свой Java-проект.

Теперь давайте начнем с создания нового PDF-документа и пошагового добавления к нему дочерних закладок.

## Создание нового PDF-документа

Для начала нам нужно инициализировать PDF-документ и добавить в него страницы. Вот фрагмент кода для начала:

```java
// Инициализировать PDF-документ
Document pdfDocument = new Document();

// Добавьте страницы в PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

В этом примере мы создали новый PDF-документ и добавили к нему две страницы.

## Добавление родительских закладок

Родительские закладки служат основными разделами или категориями PDF-документа. Давайте создадим несколько родительских закладок:

```java
// Создание родительских закладок
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Мы добавили две родительские закладки: «Родительская закладка 1» и «Родительская закладка 2».

## Добавление дочерних закладок

Теперь пришло время добавить дочерние закладки к родительским закладкам, которые мы создали ранее. Дочерние закладки представляют собой определенные темы или подразделы в каждой родительской закладке. Вот как вы можете это сделать:

```java
// Добавить дочерние закладки в родительскую закладку 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Добавить дочерние закладки в родительскую закладку 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Мы добавили дочерние закладки как в «Родительскую закладку 1», так и в «Родительскую закладку 2».

## Настройка внешнего вида закладки

Вы можете настроить внешний вид закладок, изменив их текст и стиль. Кроме того, вы можете добавлять значки в закладки для лучшего визуального представления. Вот пример того, как это сделать:

```java
// Настроить внешний вид закладки
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

В этом примере мы выделили родительскую закладку курсивом, изменили цвет текста дочерней закладки на зеленый и добавили к дочерней закладке значок курсива.

## Обработка событий

С закладками также могут быть связаны действия. Например, вы можете добавить действия, которые срабатывают, когда пользователь нажимает на закладку. Вот как вы можете обрабатывать события щелчка по закладке:

```java
// Добавить действие в закладку
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

В этом коде мы добавили действие «Перейти» к дочерней закладке, которое при нажатии приведет пользователя на вторую страницу PDF-файла.

## Сохранение PDF-файла

После того, как вы добавили все необходимые закладки и настроили их внешний вид и действия, вы можете сохранить измененный PDF-документ:

```java
// Сохраните PDF-документ
pdfDocument.save("output.pdf");
```

Ваш PDF-документ с дочерними закладками готов.

## Полный исходный код

Вот полный исходный код для добавления дочерних закладок в PDF-документ с помощью Aspose.PDF для Java:

```java
// Инициализировать PDF-документ
Document pdfDocument = new Document();

// Добавьте страницы в PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Создание родительских закладок
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Добавить дочерние закладки в родительскую закладку 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Добавить дочерние закладки в родительскую закладку 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Настроить внешний вид закладки
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Добавить действие в закладку
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Сохраните PDF-документ
pdfDocument.save("output.pdf");
```

## Заключение

Добавление дочерних закладок в PDF-файлы с помощью Aspose.PDF для Java — это мощная функция, улучшающая навигацию и организацию ваших документов. Следуя инструкциям, описанным в этой статье, вы сможете создавать хорошо структурированные PDF-файлы с родительскими и дочерними закладками, настраивать их внешний вид и даже добавлять действия для улучшения пользовательского опыта.

## Часто задаваемые вопросы

### Как я могу скачать Aspose.PDF для Java?

 Вы можете скачать Aspose.PDF для Java с сайта.[здесь](https://releases.aspose.com/pdf/java/).

### Поддерживаются ли дочерние закладки во всех программах просмотра PDF?

Да, дочерние закладки поддерживаются большинством современных программ просмотра PDF-файлов и обеспечивают расширенные возможности навигации по PDF-документам.

### Могу ли я дополнительно настроить внешний вид закладок?

Да, вы можете настроить внешний вид закладок, настроив стили текста, цвета и значки в соответствии с дизайном вашего документа.

### Какие еще действия можно добавить в закладки?

Помимо действий «GoTo», вы можете добавить такие действия, как действия «URI» для открытия веб-ссылок или действия «JavaScript» для выполнения пользовательских сценариев при щелчке по закладке.

### Подходит ли Aspose.PDF для Java для коммерческих проектов?

Да, Aspose.PDF для Java подходит как для личных, так и для коммерческих проектов и предлагает широкий спектр функций для обработки и создания PDF-файлов.