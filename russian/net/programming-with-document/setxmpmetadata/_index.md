---
title: Установить метаданные XMP
linktitle: Установить метаданные XMP
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как установить XMPMetadata в файлах PDF с помощью Aspose.PDF для .NET. Следуйте этому пошаговому руководству.
type: docs
weight: 330
url: /ru/net/programming-with-document/setxmpmetadata/
---
В этой статье мы предоставим пошаговое руководство по использованию Aspose.PDF для .NET для установки метаданных XMP в файле PDF. Мы предоставим полный пример исходного кода в конце статьи.

## Шаг 1: Установите путь к каталогу документов

Прежде чем мы начнем, нам нужно указать путь к каталогу, в котором находится наш PDF-документ. Мы будем хранить этот путь в переменной с именем «dataDir».

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Обязательно замените`YOUR DOCUMENT DIRECTORY` с фактическим путем к вашему файлу PDF.

## Шаг 2: Откройте файл PDF

Первый шаг — открыть файл PDF, для которого вы хотите установить метаданные XMP. Для этого вам нужно создать новую`Document` object и укажите путь к вашему файлу PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Шаг 3: Установите свойства метаданных XMP

Теперь, когда у вас открыт файл PDF, вы можете приступить к настройке свойств метаданных XMP. Устанавливаемые вами свойства будут зависеть от ваших конкретных потребностей, но вот некоторые общие свойства, которые вы, возможно, захотите установить:

- `xmp:CreateDate`: Дата создания файла PDF.
- `xmp:Nickname`: Псевдоним или псевдоним для файла PDF.
- `xmp:CustomProperty`: Пользовательское свойство с указанным вами значением.

 Чтобы установить эти свойства, вы можете использовать`Metadata` собственность`Document` объект. Вот пример:

```csharp
// Установить свойства
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

В этом руководстве мы устанавливаем дату создания на текущую дату и время, псевдоним на «Псевдоним» и пользовательское свойство на «Пользовательское значение». Вы можете заменить эти значения своими.

## Шаг 4: Сохраните файл PDF

 После того, как вы установили свойства метаданных XMP, вам нужно сохранить файл PDF. Для этого можно использовать`Save` метод`Document` объект и укажите путь к тому месту, где вы хотите сохранить обновленный файл PDF.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//Сохранить документ
pdfDocument.Save(dataDir);
```

### Пример исходного кода для установки XMPMetadata с использованием Aspose.PDF для .NET

Вот полный пример исходного кода для настройки XMPMetadata с использованием Aspose.PDF для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Открыть документ
	Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

	// Установить свойства
	pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
	pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
	pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

	dataDir = dataDir + "SetXMPMetadata_out.pdf";
	//Сохранить документ
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);

```
