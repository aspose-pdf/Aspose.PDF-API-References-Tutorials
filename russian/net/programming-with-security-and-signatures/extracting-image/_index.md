---
title: Извлечение изображения
linktitle: Извлечение изображения
second_title: Aspose.PDF для справочника API .NET
description: Легко извлекайте изображения из документов PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-security-and-signatures/extracting-image/
---

Извлечение изображений из документа PDF может быть полезным во многих случаях. С помощью Aspose.PDF для .NET вы можете легко извлекать изображения, используя следующий исходный код:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимые директивы импорта:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Шаг 2. Укажите путь к папке с документами.

На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите извлечь изображение. Заменять`"YOUR DOCUMENTS DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Шаг 3: Извлеките изображение из документа PDF

Теперь мы извлечем изображение из документа PDF, используя следующий код:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

В этом примере мы просматриваем каждое поле формы в документе PDF. Если поле подписи найдено, мы извлекаем связанное изображение и сохраняем его в файл JPEG.

### Пример исходного кода для извлечения изображения с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по извлечению изображений из документа PDF с помощью Aspose.PDF для .NET. Вы можете интегрировать этот код в свои собственные проекты, чтобы извлекать изображения и использовать их по мере необходимости.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных возможностях извлечения изображений и работе с PDF-документами.