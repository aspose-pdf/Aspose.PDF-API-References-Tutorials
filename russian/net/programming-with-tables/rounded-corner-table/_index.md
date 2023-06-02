---
title: Скругленный угловой стол
linktitle: Скругленный угловой стол
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как создать таблицу со скругленными углами в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 190
url: /ru/net/programming-with-tables/rounded-corner-table/
---

В этом руководстве мы шаг за шагом проведем вас по созданию таблицы со скругленными углами в документе PDF с использованием Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и покажем, как его реализовать.

## Шаг 1: Создание таблицы
Сначала мы создадим таблицу, используя следующий код:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Шаг 2: Настройка стиля закругленных углов
Далее мы настроим стиль закругленных углов для таблицы:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Шаг 3: Настройка границы таблицы
Чтобы придать таблице границу с закругленными углами, нам нужно создать объект BorderInfo и настроить его с соответствующими параметрами:

```csharp
// Создайте объект GraphInfo, чтобы установить цвет границы
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Создайте пустой объект BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Установите радиус закругленной границы на 15
bInfo.RoundedBorderRadius = 15;

// Применить информацию о границах к таблице
tab1.Border = bInfo;
```

### Пример исходного кода для таблицы со скругленными углами с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Создайте пустой объект BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Установите границу более круглой границы, где радиус скругления равен 15
bInfo.RoundedBorderRadius = 15;
// Установите стиль угла стола как круглый.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Установите информацию о границах таблицы
tab1.Border = bInfo;
```

## Заключение
Поздравляем! Теперь вы узнали, как создать таблицу со скругленными углами в документе PDF с помощью Aspose.PDF для .NET. В этом пошаговом руководстве показано, как настроить стиль закругленных углов и границу таблицы. Теперь вы можете применить эти знания в своих проектах.