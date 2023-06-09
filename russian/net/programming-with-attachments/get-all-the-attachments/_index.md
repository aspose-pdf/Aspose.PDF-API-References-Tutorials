---
title: Получить все вложения
linktitle: Получить все вложения
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как получить все вложения из файла PDF с помощью Aspose.PDF для .NET. Пошаговое руководство для простого управления.
type: docs
weight: 40
url: /ru/net/programming-with-attachments/get-all-the-attachments/
---
В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы получить все вложения из файла PDF с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

### Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором находится файл PDF, из которого вы хотите получить вложения. Измените переменную «dataDir» на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Шаг 2: Откройте существующий PDF-документ

Открываем существующий PDF-документ по указанному пути.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Шаг 3: Получение коллекции вложений

Получаем коллекцию вложений из документа.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Шаг 4. Получение вложений

Проходим по коллекции, чтобы получить все вложения и отобразить их информацию. Мы также сохраняем вложения в отдельных файлах.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Проверить, содержат ли параметры объекта дополнительную информацию
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Получить вложение и сохранить в файл
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Пример исходного кода для получения всех вложений с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Получить коллекцию встроенных файлов
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Получить количество встроенных файлов
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Прокрутите коллекцию, чтобы получить все вложения
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	// Проверьте, содержит ли объект параметров параметры
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// Получить вложение и записать в файл или поток
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Заключение

В этом руководстве мы объяснили, как получить все вложения из файла PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для извлечения вложений из файлов PDF и управления ими.