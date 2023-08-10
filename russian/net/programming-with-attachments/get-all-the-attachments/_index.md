---
title: Получить все вложения в файле PDF
linktitle: Получить все вложения в файле PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как получить все вложения в файле PDF с помощью Aspose.PDF для .NET. Пошаговое руководство для простого управления.
type: docs
weight: 40
url: /ru/net/programming-with-attachments/get-all-the-attachments/
---
В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы получить все вложения в файле PDF с помощью Aspose.PDF для .NET.

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
	//Проверьте, содержит ли объект параметров параметры
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

## Часто задаваемые вопросы для получения всех вложений в файл PDF

#### В: Зачем мне нужно извлекать все вложения из PDF-документа?

О: Получение вложений позволяет вам получать доступ к дополнительным файлам, встроенным в PDF, и управлять ими, что может быть полезно для архивирования, совместного использования или дальнейшей обработки.

#### В: Какие типы файлов можно прикрепить к документу PDF?

О: Документы PDF могут содержать широкий спектр вложенных файлов, включая изображения, документы, электронные таблицы, аудиофайлы и многое другое.

#### В: Как это руководство поможет мне извлечь вложения из PDF-файла с помощью Aspose.PDF для .NET?

О: В этом руководстве представлены пошаговые инструкции и исходный код C# для доступа и извлечения всех вложений в документе PDF.

#### В: Могу ли я получить определенные вложения вместо всех вложений с помощью этого руководства?

О: Да, вы можете изменить предоставленный код, чтобы выборочно извлекать вложения в соответствии с вашими требованиями.

#### В: Какую информацию о каждом вложении я могу получить с помощью этого руководства?

О: В этом руководстве показано, как получить и отобразить такие сведения, как имя вложения, описание, тип MIME, дату создания, дату изменения и размер.

#### В: Как сохраняются извлеченные вложения с помощью этого руководства?

О: Учебное пособие поможет вам сохранить каждое полученное вложение в виде отдельного файла в указанном каталоге.

#### В: Могу ли я использовать эти знания для извлечения вложений из файлов PDF, защищенных паролем?

О: Да, вы можете применять аналогичные принципы для извлечения вложений из защищенных паролем PDF-файлов с помощью Aspose.PDF для .NET.

#### В: Как Aspose.PDF для .NET упрощает извлечение вложений?

О: Aspose.PDF для .NET предоставляет интуитивно понятный API, который позволяет легко получать доступ к вложениям в документах PDF и управлять ими.

#### Вопрос: Существуют ли конкретные сценарии, в которых рекомендуется получать вложения?

О: Получение вложений полезно, когда вам нужно получить доступ к файлам, встроенным в PDF, например, для извлечения изображений, аудиофайлов или дополнительных документов.