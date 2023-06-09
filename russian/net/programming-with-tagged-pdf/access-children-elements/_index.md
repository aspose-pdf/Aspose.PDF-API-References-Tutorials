---
title: Доступ к дочерним элементам
linktitle: Доступ к дочерним элементам
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по доступу и редактированию дочерних элементов документа PDF с помощью Aspose.PDF для .NET. Персонализируйте содержимое PDF.
type: docs
weight: 10
url: /ru/net/programming-with-tagged-pdf/access-children-elements/
---
В этом руководстве мы предоставим вам пошаговое руководство по доступу к дочерним элементам документа PDF с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, обрабатывать и конвертировать PDF-документы. Используя отмеченные функции структуры содержимого Aspose.PDF, вы можете получить доступ и изменить свойства структурированных элементов в документе PDF.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена с .NET framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF для .NET. Вы можете загрузить библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2. Импортируйте необходимые пространства имен

В файле кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Шаг 3: Загрузка документа PDF и доступ к дочерним элементам

Используйте следующий код для загрузки документа PDF и доступа к дочерним элементам:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document(dataDir + "StructureElementsTree.pdf");
ITaggedContent taggedContent = document.TaggedContent;
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// Доступ к свойствам элемента
string title = structureElement.Title;
string language = structureElement.Language;
string actualText = structureElement.ActualText;
string expansionText = structureElement.ExpansionText;
string alternativeText = structureElement.AlternativeText;
}
}
```

Этот код позволяет получить доступ к дочерним элементам корня структуры документа PDF и получить свойства каждого элемента.

## Шаг 4: Доступ к дочерним элементам корневого элемента и изменение свойств

Используйте следующий код для доступа к дочерним элементам корневого элемента и изменения свойств:

```csharp
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// Изменить свойства элемента
structureElement.Title = "title";
structureElement.Language = "fr-FR";
structureElement.ActualText = "actual text";
structureElement.ExpansionText = "exp";
structureElement.AlternativeText = "alt";
}
}
```

Этот код позволяет получить доступ к дочерним элементам первого элемента корневого элемента и изменить свойства каждого элемента.


### Пример исходного кода для доступа к дочерним элементам с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть PDF-документ
Document document = new Document(dataDir + "StructureElementsTree.pdf");
// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Доступ к корневому элементу(ам)
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// Получить свойства
		string title = structureElement.Title;
		string language = structureElement.Language;
		string actualText = structureElement.ActualText;
		string expansionText = structureElement.ExpansionText;
		string alternativeText = structureElement.AlternativeText;
	}
}
// Доступ к дочерним элементам первого элемента в корневом элементе
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// Установить свойства
		structureElement.Title = "title";
		structureElement.Language = "fr-FR";
		structureElement.ActualText = "actual text";
		structureElement.ExpansionText = "exp";
		structureElement.AlternativeText = "alt";
	}
}
// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "AccessChildrenElements.pdf");
```

## Заключение

В этом руководстве вы узнали, как получить доступ к дочерним элементам документа PDF и как изменить свойства элемента с помощью Aspose.PDF для .NET. Это позволяет вам настраивать и управлять структурированными элементами в документе PDF в соответствии с вашими потребностями.