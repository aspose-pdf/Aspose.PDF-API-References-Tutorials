---
title: Удалить все вложения
linktitle: Удалить все вложения
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить все вложения из файла PDF с помощью Aspose.PDF для .NET. Пошаговое руководство для простого управления.
type: docs
weight: 20
url: /ru/net/programming-with-attachments/delete-all-attachments/
---
В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы удалить все вложения из файла PDF с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

### Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором находится файл PDF, из которого вы хотите удалить вложения. Измените переменную «dataDir» на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Шаг 2: Откройте существующий PDF-документ

Открываем существующий PDF-документ по указанному пути.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Шаг 3. Удалите все вложения

Удаляем все вложения из документа.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Шаг 4: Сохраните обновленный файл

Наконец, мы сохраняем обновленный файл PDF с именем «DeleteAllAttachments_out.pdf» в указанном каталоге.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Пример исходного кода для удаления всех вложений с использованием Aspose.PDF для .NET 

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Удалить все вложения
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Сохранить обновленный файл
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Заключение

В этом руководстве мы объяснили, как удалить все вложения из файла PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для очистки ваших PDF-документов, удалив все ненужные вложения.
