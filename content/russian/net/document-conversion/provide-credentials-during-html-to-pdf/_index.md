---
title: Предоставление учетных данных при преобразовании HTML в PDF
linktitle: Предоставление учетных данных при преобразовании HTML в PDF
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по преобразованию HTML в PDF путем предоставления учетных данных с помощью Aspose.PDF для .NET.
type: docs
weight: 240
url: /ru/net/document-conversion/provide-credentials-during-html-to-pdf/
---
В этом руководстве мы покажем вам процесс преобразования HTML-файла в PDF, предоставив учетные данные при доступе к защищенному URL-адресу с помощью Aspose.PDF для .NET. Выполнив следующие шаги, вы сможете конвертировать HTML-контент в PDF, используя соответствующие учетные данные.

## Предварительные условия
Прежде чем начать, убедитесь, что вы соответствуете следующим предварительным условиям:

- Базовые знания языка программирования C#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Получите безопасный HTML-контент
На этом этапе мы получим защищенный HTML-контент по URL-адресу, используя соответствующие учетные данные. Используйте следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте запрос URL-адреса.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Если необходимо для сервера, установите учетные данные.
request.Credentials = CredentialCache.DefaultCredentials;
// Получите ответ.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Получите поток, содержащий содержимое, возвращенное сервером.
Stream dataStream = response. GetResponseStream();
// Откройте поток с помощью StreamReader для быстрого доступа.
StreamReader reader = new StreamReader(dataStream);
// Прочтите содержание.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором вы хотите сохранить полученный PDF-файл.

## Шаг 2. Конвертируйте HTML в PDF, предоставив учетные данные.
Теперь мы загрузим полученное содержимое HTML и преобразуем его в формат PDF, предоставив соответствующие учетные данные. Используйте следующий код:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Загрузите HTML-файл
Document pdfDocument = new Document(stream, options);
```

## Шаг 3. Сохранение полученного PDF-файла.
Наконец, мы сохраним полученный PDF-файл. Используйте следующий код:

```csharp
// Сохраните полученный PDF-файл.
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Приведенный выше код сохраняет полученный PDF-файл с именем файла.`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Пример исходного кода для предоставления учетных данных при преобразовании HTML в PDF с использованием Aspose.PDF для .NET

```csharp
try
{
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Создайте запрос URL-адреса.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Если этого требует сервер, задайте учетные данные.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Получите ответ.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Получите поток, содержащий контент, возвращенный сервером.
	Stream dataStream = response.GetResponseStream();
	// Откройте поток с помощью StreamReader для быстрого доступа.
	StreamReader reader = new StreamReader(dataStream);
	// Прочтите содержание.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Загрузить HTML-файл
	Document pdfDocument = new Document(stream, options);
	// Сохранить полученный файл
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования HTML-файла в PDF с предоставлением учетных данных при доступе к защищенному URL-адресу с использованием Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, вы сможете успешно преобразовать содержимое HTML в PDF, предоставив правильные учетные данные.

### Часто задаваемые вопросы

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это надежная библиотека, которая позволяет разработчикам работать с PDF-документами в приложениях C#. Он предлагает широкий спектр функций, включая преобразование HTML в PDF.

#### Вопрос: Как получить защищенный HTML-контент по URL-адресу?

 О: Чтобы получить защищенный HTML-контент с URL-адреса, вы можете использовать команду`WebRequest` класс на C#. Обязательно установите соответствующие учетные данные, используя`Credentials` свойство.

#### Вопрос: Каковы предварительные условия для этого урока?

О: Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания языка программирования C#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

#### Вопрос: Как Aspose.PDF for .NET обрабатывает внешние ресурсы при преобразовании HTML в PDF?

 О: Aspose.PDF для .NET предоставляет`HtmlLoadOptions`класс для обработки внешних ресурсов во время преобразования HTML в PDF. Вы можете установить учетные данные внешнего ресурса, используя`ExternalResourcesCredentials` свойство.

#### Вопрос: Могу ли я настроить имя полученного PDF-файла?

 О: Да, вы можете настроить имя полученного PDF-файла, изменив код, сохраняющий PDF-документ. Просто измените желаемое имя файла в`pdfDocument.Save()` метод.