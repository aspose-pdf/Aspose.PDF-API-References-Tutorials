---
title: Получить все вложения в PDF-файле
linktitle: Получить все вложения в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как получить все вложения в файл PDF с помощью Aspose.PDF для .NET. Пошаговое руководство для облегчения работы.
type: docs
weight: 40
url: /ru/net/programming-with-attachments/get-all-the-attachments/
---
В этом руководстве мы шаг за шагом проведем вас по следующему исходному коду C#, чтобы получить все вложения в файл PDF с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

### Шаг 1. Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором находится PDF-файл, из которого вы хотите получить вложения. Измените переменную dataDir на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Шаг 2. Откройте существующий PDF-документ.

Открываем существующий PDF-документ по указанному пути.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Шаг 3. Получение коллекции вложений

Получаем коллекцию вложений из документа.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Шаг 4. Получение вложений

Мы просматриваем коллекцию, чтобы получить все вложения и отобразить их информацию. Мы также сохраняем вложения в отдельных файлах.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Проверьте, содержат ли параметры объекта дополнительную информацию
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Получите вложение и сохраните его в файле.
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Пример исходного кода для получения всех вложений с помощью Aspose.PDF для .NET 

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
// Просмотрите коллекцию, чтобы получить все вложения.
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//Проверьте, содержит ли объект параметра параметры
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
	// Получите вложение и запишите в файл или поток.
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

В этом уроке мы объяснили, как получить все вложения из файла PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для извлечения вложений из ваших PDF-файлов и управления ими.

## Часто задаваемые вопросы по получению всех вложений в PDF-файле

#### Вопрос: Зачем мне извлекать все вложения из PDF-документа?

О: Получение вложений позволяет вам получать доступ к дополнительным файлам, встроенным в PDF-файл, и манипулировать ими, что может быть полезно для архивирования, совместного использования или дальнейшей обработки.

#### Вопрос: Какие типы файлов можно прикреплять к PDF-документу?

О: Документы PDF могут содержать широкий спектр вложенных файлов, включая изображения, документы, электронные таблицы, аудиофайлы и многое другое.

#### Вопрос: Как это руководство поможет мне получить вложения из PDF-файла с помощью Aspose.PDF для .NET?

О: В этом руководстве представлены пошаговые инструкции и исходный код C# для доступа и извлечения всех вложений в PDF-документе.

#### Вопрос: Могу ли я получить определенные вложения вместо всех вложений, используя это руководство?

О: Да, вы можете изменить предоставленный код, чтобы выборочно получать вложения в соответствии с вашими требованиями.

#### Вопрос: Какую информацию о каждом вложении я могу получить с помощью этого руководства?

О: В этом руководстве показано, как получить и отобразить такие сведения, как имя вложения, описание, тип MIME, дата создания, дата изменения и размер.

#### Вопрос: Как сохраняются вложения, полученные с помощью этого руководства?

О: В руководстве рассказывается, как сохранить каждое полученное вложение в виде отдельного файла в указанном каталоге.

#### Вопрос: Могу ли я использовать эти знания для извлечения вложений из PDF-файлов, защищенных паролем?

О: Да, вы можете применить аналогичные принципы для извлечения вложений из PDF-файлов, защищенных паролем, с помощью Aspose.PDF для .NET.

#### Вопрос: Как Aspose.PDF for .NET облегчает извлечение вложений?

О: Aspose.PDF для .NET предоставляет интуитивно понятный API, который позволяет легко получать доступ к вложениям в PDF-документах и манипулировать ими.

#### Вопрос. Существуют ли конкретные сценарии, в которых рекомендуется извлекать вложения?

О: Извлечение вложений полезно, когда вам нужно получить доступ к файлам, встроенным в PDF-файл, например для извлечения изображений, аудиофайлов или дополнительных документов.