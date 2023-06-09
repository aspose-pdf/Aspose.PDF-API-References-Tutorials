---
title: Корневая структура
linktitle: Корневая структура
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по использованию элементов корневой структуры с Aspose.PDF для .NET для доступа к корню и объекту StructTreeRoot документа PDF.
type: docs
weight: 130
url: /ru/net/programming-with-tagged-pdf/root-structure/
---
В этом пошаговом руководстве мы покажем вам, как использовать элементы корневой структуры с Aspose.PDF для .NET. Aspose.PDF — мощная библиотека, позволяющая программно создавать PDF-документы и управлять ими. Элементы корневой структуры позволяют получить доступ к объекту StructTreeRoot документа PDF и элементу корневой структуры.

Давайте углубимся в код и узнаем, как использовать элементы корневой структуры с Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1. Настройка среды

Для начала откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили в свой проект ссылку на библиотеку Aspose.PDF для .NET.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа

 Первым шагом является создание нового документа PDF с помощью`Document` сорт.

```csharp
// Создайте PDF-документ
Document document = new Document();
```

## Шаг 3. Работа с размеченным контентом

Затем мы получаем тегированное содержимое документа для работы.

```csharp
// Получить тегированное содержимое документа
ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 4: Установите название документа и язык

Теперь мы можем установить название документа и язык.

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5: Доступ к элементу корневой структуры

Теперь мы можем получить доступ к объекту StructTreeRoot документа и корневому элементу структуры.

```csharp
// Доступ к элементу корневой структуры
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;
```

### Пример исходного кода для корневой структуры с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать PDF-документ
Document document = new Document();

// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Установить заголовок и язык для Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Свойства StructTreeRootElement и RootElement используются для доступа к
// StructTreeRoot объект pdf-документа и корневой элемент структуры (элемент структуры документа).
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;

```

## Заключение

Поздравляем! Вы узнали, как использовать элементы корневой структуры с Aspose.PDF для .NET. Теперь вы можете получить доступ к объекту StructTreeRoot документа PDF и корневому элементу структуры для выполнения расширенных операций со структурой документа.
