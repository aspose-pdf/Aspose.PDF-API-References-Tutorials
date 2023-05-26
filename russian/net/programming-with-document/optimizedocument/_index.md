---
title: Оптимизировать документ
linktitle: Оптимизировать документ
second_title: Aspose.PDF для справочника API .NET
description: Оптимизация документа для Интернета необходима для удобства пользователей. Узнайте, как это сделать с помощью Aspose.PDF для .NET, из этого пошагового руководства.
type: docs
weight: 240
url: /ru/net/programming-with-document/optimizedocument/
---
Оптимизация PDF-документов для Интернета — важный шаг в обеспечении быстрого и эффективного взаимодействия с пользователем. Это пошаговое руководство научит вас использовать Aspose.PDF для .NET для оптимизации ваших PDF-документов для Интернета.

## Шаг 1. Установка пути к каталогу документов

Во-первых, вам нужно указать путь к каталогу, содержащему PDF-документ, который вы хотите оптимизировать. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Открытие документа

Затем откройте документ PDF с помощью класса Document.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Шаг 3: Оптимизация документа

 Чтобы оптимизировать документ PDF для Интернета, просто вызовите`Optimize` метод.

```csharp
pdfDocument.Optimize();
```

## Шаг 4: Сохранение документа

 Наконец, сохраните оптимизированный документ, используя`Save` метод.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

Следуя этому пошаговому руководству, вы теперь можете легко оптимизировать свои PDF-документы для Интернета, используя Aspose.PDF для .NET.

### Пример исходного кода для оптимизации PDF-документов с использованием Aspose.PDF для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Открыть документ
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

	// Оптимизировать для Интернета
	pdfDocument.Optimize();

	dataDir = dataDir + "OptimizeDocument_out.pdf";

	// Сохранить выходной документ
	pdfDocument.Save(dataDir);

```
