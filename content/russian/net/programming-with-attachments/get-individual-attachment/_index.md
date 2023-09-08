---
title: Получить индивидуальное вложение в PDF-файле
linktitle: Получить индивидуальное вложение в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как получить отдельное вложение в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-attachments/get-individual-attachment/
---
В этом руководстве мы шаг за шагом познакомим вас со следующим исходным кодом C#, чтобы получить отдельное вложение PDF-файла с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

### Шаг 1. Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором находится PDF-файл, из которого вы хотите получить отдельное вложение. Измените переменную dataDir на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Шаг 2. Откройте существующий PDF-документ.

Открываем существующий PDF-документ по указанному пути.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Шаг 3: Получение конкретного вложения

Мы извлекаем конкретное вложение из коллекции вложений документа. В этом примере мы получаем первое вложение с индексом 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Шаг 4. Получите свойства файла

Мы отображаем свойства вложения, такие как имя, описание, тип MIME, контрольный хеш, дата создания, дата изменения и размер.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Проверьте, содержат ли параметры объекта дополнительную информацию
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Шаг 5. Получите вложение и сохраните его в файл.

Мы извлекаем содержимое вложения и сохраняем его в текстовый файл. В этом примере файл сохраняется с именем «test_out.txt».

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Пример исходного кода для получения индивидуального вложения с помощью Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Получить конкретный встроенный файл
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Получить свойства файла
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
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
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Заключение

В этом уроке мы объяснили, как получить отдельное вложение из файла PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для извлечения и сохранения вложений из ваших PDF-файлов.

### Часто задаваемые вопросы о получении отдельного вложения в PDF-файле

#### Вопрос: Какова цель получения отдельного вложения из PDF-документа?

О: Получение отдельного вложения позволяет вам извлечь и сохранить определенный встроенный файл в PDF-файл, который может быть полезен для дальнейшего анализа или манипулирования.

#### Вопрос: Какую пользу я могу получить от этого руководства при выполнении задач, связанных с PDF?

О: В этом руководстве представлены пошаговые инструкции и исходный код C# для извлечения и сохранения определенного вложения из PDF-документа с помощью Aspose.PDF для .NET.

#### Вопрос: К каким свойствам вложений я могу получить доступ с помощью этого руководства?

О: Вы можете получить доступ к свойствам вложения, таким как имя, описание, тип MIME, контрольный хеш, дата создания, дата изменения и размер конкретного вложения.

#### Вопрос: Могу ли я изменить код, чтобы получать вложения, отличные от первого вложения?

 О: Конечно, вы можете настроить индекс (например,`pdfDocument.EmbeddedFiles[1]`) для извлечения вложений по разным индексам в PDF-файле.

#### Вопрос: Как сохранить полученное вложение в файл?

О: В этом руководстве представлен код для получения содержимого вложения и сохранения его в текстовый файл с указанным именем.

#### Вопрос: Каково значение свойства «Проверить хеш» в информации о вложении?

О: Свойство «Проверить хэш» представляет собой контрольное хэш-значение вложения, которое можно использовать для проверки целостности вложения.

#### Вопрос: Могу ли я расширить эти знания, чтобы извлекать вложения по определенным критериям, например по типу файла?

О: Да, вы можете улучшить код для фильтрации вложений на основе определенных критериев, таких как тип файла или другие свойства.

#### Вопрос: Как Aspose.PDF для .NET упрощает процесс извлечения отдельных вложений?

О: Aspose.PDF для .NET предоставляет удобный API, который облегчает извлечение и манипулирование вложениями в PDF-документах.

#### Вопрос. Подходит ли это руководство и для PDF-файлов, защищенных паролем?

О: Да, вы можете адаптировать аналогичные методы для извлечения отдельных вложений из PDF-файлов, защищенных паролем, с помощью Aspose.PDF для .NET.
