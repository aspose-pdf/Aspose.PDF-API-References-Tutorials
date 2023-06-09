---
title: Отключить сжатие файлов
linktitle: Отключить сжатие файлов
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как отключить сжатие файла в файле PDF с помощью Aspose.PDF для .NET. Пошаговое руководство для простого управления.
type: docs
weight: 30
url: /ru/net/programming-with-attachments/disable-files-compression/
---
В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы отключить сжатие файлов в PDF с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

### Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором находится файл PDF, для которого вы хотите отключить сжатие файла. Измените переменную «dataDir» на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Шаг 2: Откройте существующий PDF-документ

Открываем существующий PDF-документ по указанному пути.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Шаг 3. Настройка нового файла для добавления в качестве вложения

Мы настраиваем новый файл, который мы хотим добавить в качестве вложения. В этом примере мы добавляем текстовый файл с именем «test_out.txt» и описанием «Пример текстового файла».

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Шаг 4. Отключите сжатие файлов

Мы отключаем сжатие файлов, присваивая свойству Encoding объекта FileSpecification значение FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Шаг 5. Добавление вложения в коллекцию вложений документа

Мы добавляем вложение в коллекцию вложений документа.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Шаг 6: Сохраните новый выходной файл

Наконец, мы сохраняем полученный новый PDF-файл с именем «DisableFilesCompression_out.pdf» в указанном каталоге.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Пример исходного кода для отключения сжатия файлов с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Настройте новый файл, который будет добавлен в качестве вложения
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Укажите пропатент кодирования, установив для него значение FileEncoding.None.
fileSpecification.Encoding = FileEncoding.None;
// Добавить вложение в коллекцию вложений документа
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Сохранить новый вывод
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Заключение

В этом руководстве мы объяснили, как отключить сжатие файлов в PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для сохранения целостности вложенных файлов без сжатия.