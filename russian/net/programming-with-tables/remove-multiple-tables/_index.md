---
title: Удалить несколько таблиц
linktitle: Удалить несколько таблиц
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить несколько таблиц в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/programming-with-tables/remove-multiple-tables/
---

В этом руководстве мы шаг за шагом проведем вас по удалению нескольких таблиц в документе PDF с помощью Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и покажем, как его реализовать.

## Шаг 1: Загрузка существующего документа PDF
Во-первых, вам нужно загрузить существующий PDF-документ, используя следующий код:

```csharp
// Путь к каталогу документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите существующий PDF-документ
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Шаг 2: Создание объекта TableAbsorber для поиска таблиц
Далее мы создадим объект TableAbsorber для поиска таблиц в документе PDF:

```csharp
// Создайте объект TableAbsorber, чтобы найти таблицы
TableAbsorber absorber = new TableAbsorber();
```

## Шаг 3: Посетите вторую страницу с поглотителем
Теперь мы посетим вторую страницу документа PDF, используя поглотитель:

```csharp
// Посетите вторую страницу с поглотителем
absorb.Visit(pdfDocument.Pages[1]);
```

## Шаг 4: Получение копии коллекции таблиц
Чтобы иметь возможность удалять таблицы, нам нужно получить копию коллекции таблиц:

```csharp
// Получить копию коллекции таблиц
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Шаг 5. Просмотрите копию коллекции и удалите таблицы
Теперь давайте пройдемся по копии набора таблиц и удалим их одну за другой:

```csharp
// Просмотрите копию коллекции и удалите таблицы
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Шаг 6: Сохранение документа
Наконец, мы сохраняем измененный PDF-документ:

```csharp
// Сохраните документ
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Пример исходного кода для удаления нескольких таблиц с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузить существующий PDF-документ
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Создайте объект TableAbsorber для поиска таблиц
TableAbsorber absorber = new TableAbsorber();

// Посетите вторую страницу с поглотителем
absorber.Visit(pdfDocument.Pages[1]);

// Получить копию коллекции таблиц
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Перебрать копию коллекции и удалить таблицы
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Сохранить документ
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Заключение
Поздравляем! Теперь вы узнали, как удалить несколько таблиц в документе PDF с помощью Aspose.PDF для .NET. В этом пошаговом руководстве показано, как загрузить документ, найти таблицы и удалить их. Теперь вы можете применить эти знания в своих проектах.