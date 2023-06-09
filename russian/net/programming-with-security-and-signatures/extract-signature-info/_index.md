---
title: Извлечь информацию о подписи
linktitle: Извлечь информацию о подписи
second_title: Aspose.PDF для справочника API .NET
description: Извлечение информации о подписи с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-security-and-signatures/extract-signature-info/
---

Процесс извлечения информации о подписи из PDF-документа может быть весьма полезен в различных сценариях. Если вам нужно проверить подлинность подписанного документа или проанализировать сертификат, используемый для подписи, библиотека Aspose.PDF для .NET предоставляет удобное решение. В этом руководстве мы проведем вас через пошаговый процесс извлечения информации о подписи с использованием предоставленного исходного кода C#.

## Требования

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Базовые знания языка программирования С#.
2. Aspose.PDF для библиотеки .NET, установленной в вашей системе.
3. Действительный PDF-документ с одним или несколькими полями для подписи.

Теперь давайте углубимся в детали реализации.

## Шаг 1: Импорт необходимых библиотек

 Для начала вам нужно импортировать необходимые библиотеки в ваш проект C#. В этом случае нам нужно импортировать`Aspose.Pdf` и`System.IO` пространства имен. Это можно сделать, добавив следующий код в начало файла C#:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Шаг 2: Установка пути к документу

 Затем вам нужно указать путь к документу PDF, из которого вы хотите извлечь информацию о подписи. Заменять`"YOUR DOCUMENTS DIRECTORY"` в следующем фрагменте кода с фактическим путем к вашему документу:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Шаг 3: Извлечение информации о подписи

Теперь давайте перейдем к основной части кода, где мы извлекаем информацию о подписи из документа PDF. Мы перебираем каждое поле в форме документа и проверяем, является ли оно полем подписи. Если поле подписи найдено, мы приступаем к извлечению сертификата. Добавьте следующий фрагмент кода:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Извлеките сертификат
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Шаг 4: Извлечение сертификата

На этом шаге мы извлекаем сертификат из поля подписи и сохраняем его как файл. Извлеченный сертификат может быть дополнительно проанализирован или использован для целей проверки. Фрагмент кода ниже демонстрирует процесс извлечения и сохранения:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Шаг 5

: Сохранение сертификата

Наконец, мы сохраняем извлеченный сертификат в виде файла. В этом примере сертификат сохраняется с именем «input.cer» в указанном каталоге. Вы можете изменить код в соответствии с вашими требованиями. Вот фрагмент кода для сохранения сертификата:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Вот и все! Вы успешно извлекли информацию о подписи с помощью Aspose.PDF для .NET. Не стесняйтесь интегрировать этот код в свои собственные приложения или модифицировать его в соответствии с вашими потребностями.

### Пример исходного кода для извлечения информации о подписи с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

В этом руководстве мы рассмотрели пошаговое руководство по извлечению информации о подписи из документа PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрели процесс импорта необходимых библиотек, установки пути к документу, извлечения информации о подписи, извлечения сертификата и сохранения его в файл. Следуя этим шагам, вы можете легко получить сведения о подписи и работать с ними по мере необходимости.