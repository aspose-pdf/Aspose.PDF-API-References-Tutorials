---
title: Создать дерево элементов конструкции
linktitle: Создать дерево элементов конструкции
second_title: Aspose.PDF для справочника API .NET
description: Создайте структуру элементов дерева, используя Aspose.PDF для .NET. Пошаговое руководство по созданию структурированного PDF-документа.
type: docs
weight: 70
url: /ru/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
В этом пошаговом руководстве мы объясним исходный код на C# для создания структуры элементов дерева с использованием Aspose.PDF для .NET. Мы покажем вам, как создать PDF-документ со структурированными элементами и как организовать их иерархически. Использование библиотеки Aspose.PDF значительно упрощает работу с элементами PDF и предоставляет расширенные возможности для работы со структурированными документами.

## Шаг 1. Настройка среды
Прежде чем начать, убедитесь, что вы настроили среду разработки с помощью Aspose.PDF для .NET. Также убедитесь, что у вас есть путь к каталогу ваших документов, установленный в`dataDir` переменная.

## Шаг 2: Создание PDF-документа
 Для начала мы создадим новый PDF-документ, используя`Document` класс, предоставленный Aspose.PDF. Вот код для этого шага:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создать PDF-документ
Document document = new Document();
```

## Шаг 3. Настройка контента для работы с TaggedPdf
 Библиотека Aspose.PDF позволяет работать со структурированными PDF-документами, используя концепцию Tagged PDF. Для этого нам нужно получить ссылку на помеченный элемент содержимого, используя атрибут документа.`TaggedContent` свойство. Вот код для этого шага:

```csharp
// Получите содержимое для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 4: Установите название документа и язык
 Прежде чем мы начнем создавать структуру элементов, нам нужно определить заголовок и язык документа. Это можно сделать с помощью`SetTitle` и`SetLanguage` методы`taggedContent` объект. Вот код для этого шага:

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5: Создание элементов логической структуры
Теперь, когда мы настроили наш документ и установили заголовок и язык, мы можем приступить к созданию элементов логической структуры. Эти элементы будут организованы иерархически для формирования дерева структуры. Вот код для этого шага:

```csharp
// Получить элемент корневой структуры (Документ)
StructureElement rootElement = taggedContent.RootElement;

// Создайте логическую структуру
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## Шаг 6: Сохранение документа PDF с тегами
 Создав структуру элементов, мы можем сохранить PDF-документ. Использовать`Save` метод`document` объект, чтобы указать путь и имя файла PDF для сохранения. Вот код для этого шага:

```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "StructureElementsTree.pdf");
```

### Пример исходного кода для создания дерева элементов структуры с использованием Aspose.PDF для .NET 
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
// Получить элемент корневой структуры (Документ)
StructureElement rootElement = taggedContent.RootElement;
// Создайте логическую структуру
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "StructureElementsTree.pdf");

```

## Заключение
Вы узнали, как создать структуру элементов дерева, используя Aspose.PDF для .NET. В этом руководстве показаны шаги, необходимые для настройки документа PDF, создания элементов логической структуры и сохранения конечного документа. Используя Aspose.PDF, вы можете легко манипулировать элементами PDF и создавать структурированные документы.
