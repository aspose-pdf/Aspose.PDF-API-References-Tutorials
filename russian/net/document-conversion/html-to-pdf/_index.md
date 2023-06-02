---
title: HTML в PDF
linktitle: HTML в PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию HTML в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/document-conversion/html-to-pdf/
---

В этом руководстве мы познакомим вас с процессом преобразования HTML-файла в PDF с помощью Aspose.PDF для .NET. HTML (HyperText Markup Language) — это язык разметки, используемый для структурирования и представления веб-контента. Следуя приведенным ниже инструкциям, вы сможете конвертировать файлы HTML в формат PDF.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка HTML-файла
На этом этапе мы загрузим файл HTML, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл HTML.

## Шаг 2: параметры загрузки HTML
Теперь, когда мы загрузили файл HTML, мы можем указать определенные параметры загрузки. Используйте следующий код:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

Приведенный выше код указывает Aspose.PDF использовать собственную стратегию загрузки для внешних ресурсов, таких как изображения. Вы можете настроить эту политику в соответствии с вашими потребностями.

## Шаг 3: Преобразование HTML в PDF
После загрузки файла HTML и указания параметров загрузки мы можем приступить к преобразованию в PDF. Используйте следующий код:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### Пример исходного кода для преобразования HTML в PDF с использованием Aspose.Words для .NET

```csharp
try
{
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение
В этом уроке мы рассмотрели процесс шаг за шагом. шаг преобразования HTML-файла в PDF с помощью Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете конвертировать файлы HTML в формат PDF. Эта функция может быть полезна, когда вам нужно создать документы PDF из содержимого HTML.

