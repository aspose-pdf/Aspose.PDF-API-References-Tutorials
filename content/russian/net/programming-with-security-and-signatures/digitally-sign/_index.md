---
title: Цифровая регистрация в PDF-файле
linktitle: Цифровая регистрация в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как поставить цифровую подпись на PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-security-and-signatures/digitally-sign/
---
В этом уроке мы проведем вас через процесс цифровой подписи в PDF-файле с использованием Aspose.PDF для .NET. Цифровая подпись гарантирует подлинность и целостность документа, добавляя уникальный электронный отпечаток.

## Шаг 1: Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания языка программирования C#
- Установка Visual Studio на ваш компьютер
- Установлена библиотека Aspose.PDF для .NET

## Шаг 2: Настройка среды

Чтобы начать работу, выполните следующие действия по настройке среды разработки:

1. Откройте Visual Studio и создайте новый проект C#.
2. Импортируйте необходимые пространства имен в ваш файл кода:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Шаг 3: Цифровая подпись

Первый шаг — цифровая подпись файла PDF. Приведенный код показывает, как сделать цифровую подпись с помощью Aspose.PDF для .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Этот код загружает PDF-файл, создает цифровую подпись с указанным внешним видом, а затем сохраняет PDF-файл с добавленной подписью.

## Шаг 4: Проверка подписи

После добавления цифровой подписи вы можете проверить, содержит ли PDF-файл действительную подпись.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Сделай что-нибудь
                     }
                 }
             }
         }
     }
}
```

Этот код проверяет первую подпись PDF-файла и выполняет дополнительные действия, если подпись сертифицирована и имеет определенные разрешения.

### Пример исходного кода для цифровой подписи с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Использовать объекты PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Установить внешний вид подписи
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Создайте любой из трех типов подписи
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Сохранить выходной PDF-файл
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Есть подписи?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Проверить первый
				{
					if (signature.IsCertified) // Проверенный?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Получить разрешение на доступ
						{
							// Сделай что-нибудь
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

Поздравляем! Вы успешно выполнили цифровую подпись PDF-файла с помощью Aspose.PDF для .NET. В этом руководстве был рассмотрен пошаговый процесс, от добавления цифровой подписи до проверки ее действительности. Теперь вы можете использовать эту функцию для защиты ваших PDF-файлов с помощью цифровых подписей.

### Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: Это руководство проведет вас через процесс цифровой подписи PDF-файла с помощью Aspose.PDF для .NET. Цифровые подписи добавляют электронный отпечаток пальца для обеспечения подлинности и целостности документа.

#### В: Какие предварительные условия необходимы перед началом работы?

A: Прежде чем начать, убедитесь, что у вас есть базовые знания языка программирования C#, установлены Visual Studio и библиотека Aspose.PDF для .NET.

#### В: Как настроить среду разработки?

A: Следуйте предоставленным инструкциям по настройке среды разработки, включая создание нового проекта C# в Visual Studio и импорт необходимых пространств имен.

#### В: Как добавить цифровую подпись в PDF-файл?

 A: Приведенный пример кода демонстрирует, как загрузить файл PDF, создать цифровую подпись, указать внешний вид и сохранить подписанный файл PDF. Цифровая подпись добавляется с помощью`Certify` Метод`PdfFileSignature` объект.

#### В: Как проверить действительность цифровой подписи?

A: После добавления цифровой подписи вы можете использовать пример кода для проверки действительности подписи. Он проверяет, сертифицирована ли подпись и имеет ли она определенные разрешения на доступ.

####  В: Что означает`PKCS7` object represent?

 А:`PKCS7` объект используется для предоставления криптографической функциональности для цифровых подписей. Он используется для создания цифровой подписи в предоставленном примере кода.

#### В: Могу ли я настроить внешний вид цифровой подписи?

 A: Да, вы можете настроить внешний вид цифровой подписи, указав путь к изображению в`SignatureAppearance` собственность`PdfFileSignature` объект.

#### В: Что произойдет, если подпись недействительна?

A: Если подпись недействительна, процесс проверки завершится неудачей, и соответствующие действия в блоке кода проверки не будут выполнены.

#### В: Как я могу обеспечить безопасность своих цифровых подписей?

A: Цифровые подписи безопасны по своей сути и используют криптографические методы для обеспечения подлинности и целостности. Убедитесь, что вы храните свой закрытый ключ в безопасности и следуйте лучшим практикам обработки цифровых подписей.

#### В: Могу ли я добавить несколько цифровых подписей в PDF-файл?

 A: Да, вы можете добавить несколько цифровых подписей в PDF-файл с помощью`PdfFileSignature` объект`Sign` или`Certify` методы. Каждая подпись будет иметь свой собственный внешний вид и конфигурацию.