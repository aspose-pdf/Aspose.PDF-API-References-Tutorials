---
title: Добавить приложение
linktitle: Добавить приложение
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять вложения в файлы PDF с помощью Aspose.PDF для .NET. Пошаговое руководство для простого управления.
type: docs
weight: 10
url: /ru/net/programming-with-attachments/add-attachment/
---

В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы добавить вложение в файл PDF с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

### Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором находится PDF-файл, к которому вы хотите добавить вложение. Измените переменную «dataDir» на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Шаг 2: Откройте существующий PDF-документ

Открываем существующий PDF-документ по указанному пути.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Шаг 3. Настройка нового файла для добавления в качестве вложения

Мы настраиваем новый файл, который мы хотим добавить в качестве вложения. В этом примере мы добавляем текстовый файл с именем «test.txt» и описанием «Пример текстового файла».

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Шаг 4. Добавление вложения в коллекцию вложений документа

Мы добавляем вложение в коллекцию вложений документа.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Шаг 5: Сохранение нового выходного файла

Наконец, мы сохраняем полученный новый PDF-файл с именем «AddAttachment_out.pdf» в указанном каталоге.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Пример исходного кода для добавления вложения с использованием Aspose.PDF для .NET
 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Настройте новый файл, который будет добавлен в качестве вложения
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Добавить вложение в коллекцию вложений документа
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Сохранить новый вывод
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Заключение

В этом руководстве мы объяснили, как добавить вложение в файл PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для добавления дополнительных файлов в качестве вложений в ваши PDF-документы.
