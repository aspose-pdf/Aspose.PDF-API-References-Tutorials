---
title: Предоставление учетных данных во время преобразования HTML в PDF
linktitle: Предоставление учетных данных во время преобразования HTML в PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию HTML в PDF путем предоставления учетных данных с помощью Aspose.PDF для .NET.
type: docs
weight: 240
url: /ru/net/document-conversion/provide-credentials-during-html-to-pdf/
---

В этом руководстве мы познакомим вас с процессом преобразования HTML-файла в PDF, предоставив учетные данные при доступе к безопасному URL-адресу с помощью Aspose.PDF для .NET. Следуя приведенным ниже инструкциям, вы сможете конвертировать содержимое HTML в PDF, используя соответствующие учетные данные.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Получите безопасный HTML-контент
На этом шаге мы получим защищенный HTML-контент из URL-адреса, используя соответствующие учетные данные. Используйте следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте запрос для URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Если необходимо для сервера, установите учетные данные.
request.Credentials = CredentialCache.DefaultCredentials;
// Получите ответ.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Получите поток, содержащий содержимое, возвращенное сервером.
Stream dataStream = response. GetResponseStream();
// Откройте поток с помощью StreamReader для быстрого доступа.
StreamReader reader = new StreamReader(dataStream);
// Прочтите содержимое.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором вы хотите сохранить полученный PDF-файл.

## Шаг 2. Преобразуйте HTML в PDF, предоставив учетные данные
Теперь мы загрузим полученный HTML-контент и преобразуем его в формат PDF, предоставив соответствующие учетные данные. Используйте следующий код:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://Мой.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Загрузите HTML-файл
Document pdfDocument = new Document(stream, options);
```

## Шаг 3: Сохранение полученного PDF-файла
Наконец, мы сохраним полученный файл PDF. Используйте следующий код:

```csharp
// Сохраните полученный PDF-файл
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Приведенный выше код сохраняет полученный PDF-файл с именем файла`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Пример исходного кода для предоставления учетных данных во время преобразования HTML в PDF с использованием Aspose.Words для .NET

```csharp
try
{
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Создайте запрос для URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Если требуется сервером, установите учетные данные.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Получите ответ.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Получите поток, содержащий содержимое, возвращенное сервером.
	Stream dataStream = response.GetResponseStream();
	// Откройте поток с помощью StreamReader для быстрого доступа.
	StreamReader reader = new StreamReader(dataStream);
	// Прочтите содержимое.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// Мой.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Загрузить HTML-файл
	Document pdfDocument = new Document(stream, options);
	// Сохранить результирующий файл
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла HTML в PDF с предоставлением учетных данных при доступе к защищенному URL-адресу с помощью Aspose.PDF для .NET. Следуя приведенным выше инструкциям, вы сможете успешно конвертировать содержимое HTML в PDF, предоставив правильные учетные данные.