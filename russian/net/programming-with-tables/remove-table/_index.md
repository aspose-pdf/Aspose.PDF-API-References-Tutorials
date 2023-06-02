---
title: Удалить таблицу
linktitle: Удалить таблицу
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить таблицу из документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-tables/remove-table/
---

В этом руководстве мы шаг за шагом проведем вас по удалению таблицы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и покажем, как его реализовать.

## Шаг 1: Загрузка существующего документа PDF
Во-первых, вам нужно загрузить существующий PDF-документ, используя следующий код:

```csharp
// Путь к каталогу документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите существующий PDF-документ
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
```

## Шаг 2: Создание объекта TableAbsorber для поиска таблиц
Далее мы создадим объект TableAbsorber для поиска таблиц в документе PDF:

```csharp
// Создайте объект TableAbsorber, чтобы найти таблицы
TableAbsorber absorber = new TableAbsorber();
```

## Шаг 3: Посетите первую страницу с поглотителем
Теперь мы посетим первую страницу PDF-документа с помощью поглотителя:

```csharp
//Посетите первую страницу с поглотителем
absorb.Visit(pdfDocument.Pages[1]);
```

## Шаг 4: Получение первой таблицы на странице
Чтобы иметь возможность удалить таблицу, мы получим первую таблицу страницы:

```csharp
// Получить первую таблицу на странице
AbsorbedTable table = absorb.TableList[0];
```

## Шаг 5: Удаление таблицы
Теперь с помощью абсорбера снимаем стол:

```csharp
// удалить стол
absorb.Remove(table);
```

## Шаг 6: Сохраните PDF
Наконец, мы сохраняем измененный PDF-документ:

```csharp
// Сохранить PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Пример исходного кода для удаления таблицы с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузить существующий PDF-документ
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Создайте объект TableAbsorber для поиска таблиц
TableAbsorber absorber = new TableAbsorber();

// Посетите первую страницу с поглотителем
absorber.Visit(pdfDocument.Pages[1]);

// Получить первую таблицу на странице
AbsorbedTable table = absorber.TableList[0];

// Удалить таблицу
absorber.Remove(table);

// Сохранить PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Заключение
Поздравляем! Теперь вы узнали, как удалить таблицу в документе PDF с помощью Aspose.PDF для .NET. В этом пошаговом руководстве показано, как загрузить документ, найти таблицу и удалить ее. Теперь вы можете применить эти знания в своих проектах.