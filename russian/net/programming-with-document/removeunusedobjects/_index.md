---
title: Удалить неиспользуемые объекты
linktitle: Удалить неиспользуемые объекты
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET для удаления неиспользуемых объектов из PDF-документов с помощью этого пошагового руководства.
type: docs
weight: 260
url: /ru/net/programming-with-document/removeunusedobjects/
---
Если вы ищете способ удалить неиспользуемые объекты в ваших документах PDF с помощью Aspose.PDF для .NET, вы попали по адресу. Это пошаговое руководство покажет вам, как использовать предоставленный исходный код C# для выполнения этой задачи.

## Шаг 1. Установите путь к каталогу

Во-первых, вам нужно указать путь к каталогу документов, заменив «ВАШ КАТАЛОГ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

Затем вам нужно открыть PDF-документ, который вы хотите оптимизировать, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 3: Установите параметр RemoveUnusedObjects

Чтобы удалить неиспользуемые объекты в документе PDF, вам необходимо установить для параметра RemoveUnusedObjects значение «true» следующим образом:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Шаг 4. Оптимизируйте PDF-документ с помощью OptimizationOptions

Теперь вы можете оптимизировать свой PDF-документ, используя метод OptimizeResources с параметрами оптимизации, которые вы только что установили:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Шаг 5: Сохраните обновленный документ

Наконец, вы можете сохранить обновленный документ с помощью следующего кода:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

Вот и все! Вы успешно удалили неиспользуемые объекты из документа PDF с помощью Aspose.PDF для .NET.

### Пример исходного кода для удаления неиспользуемых объектов с помощью Aspose.PDF для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Открыть документ
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Установите параметр RemoveUsedObject
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// Оптимизируйте документ PDF с помощью OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Сохранить обновленный документ
	pdfDocument.Save(dataDir);

```
