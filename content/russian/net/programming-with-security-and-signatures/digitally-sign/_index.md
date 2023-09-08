---
title: Цифровой вход PDF-файл
linktitle: Цифровой вход PDF-файл
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как выполнить цифровую подпись в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-security-and-signatures/digitally-sign/
---
В этом руководстве мы познакомим вас с процессом цифровой подписи PDF-файла с помощью Aspose.PDF для .NET. Цифровая подпись гарантирует подлинность и целостность документа путем добавления уникального электронного отпечатка пальца.

## Шаг 1: Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания языка программирования C#.
- Установка Visual Studio на ваш компьютер
- Установлена библиотека Aspose.PDF для .NET.

## Шаг 2. Настройка среды

Чтобы начать работу, выполните следующие действия, чтобы настроить среду разработки:

1. Откройте Visual Studio и создайте новый проект C#.
2. Импортируйте необходимые пространства имен в файл кода:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Шаг 3: Цифровая подпись

Первым шагом является цифровая подпись PDF-файла. Приведенный код показывает, как сделать цифровую подпись с помощью Aspose.PDF для .NET.

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

Этот код загружает PDF-файл, создает цифровую подпись с заданным внешним видом, а затем сохраняет PDF-файл с добавленной подписью.

## Шаг 4. Проверка подписи

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
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Используйте объекты PKCS7/PKCS7Detached.
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Установить внешний вид подписи
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Создайте любой из трех типов подписей.
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
				if (signature.VerifySigned(sigNames[0] as string)) // Проверьте первый
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

Поздравляем! Вы успешно поставили цифровую подпись в PDF-файле с помощью Aspose.PDF для .NET. В этом руководстве описан пошаговый процесс: от добавления цифровой подписи до проверки ее действительности. Теперь вы можете использовать эту функцию для защиты своих PDF-файлов с помощью цифровых подписей.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого урока?

О: Это руководство проведет вас через процесс цифровой подписи PDF-файла с помощью Aspose.PDF для .NET. Цифровые подписи добавляют электронный отпечаток пальца, чтобы гарантировать подлинность и целостность документа.

#### Вопрос: Какие предварительные условия необходимы перед запуском?

О: Прежде чем начать, убедитесь, что у вас есть базовые знания языка программирования C#, установлена Visual Studio и установлена библиотека Aspose.PDF для .NET.

#### Вопрос: Как настроить среду разработки?

Ответ: Следуйте предоставленным инструкциям, чтобы настроить среду разработки, включая создание нового проекта C# в Visual Studio и импорт необходимых пространств имен.

#### Вопрос: Как добавить цифровую подпись в PDF-файл?

 О: Приведенный пример кода демонстрирует, как загрузить PDF-файл, создать цифровую подпись, указать внешний вид и сохранить подписанный PDF-файл. Цифровая подпись добавляется с помощью`Certify` метод`PdfFileSignature` объект.

#### Вопрос: Как проверить действительность цифровой подписи?

О: После добавления цифровой подписи вы можете использовать образец кода для проверки действительности подписи. Он проверяет, сертифицирована ли подпись и имеет ли она определенные права доступа.

####  Вопрос: Что означает`PKCS7` object represent?

 А:`PKCS7` Объект используется для обеспечения криптографических функций цифровых подписей. Он используется для создания цифровой подписи в предоставленном образце кода.

#### Вопрос: Могу ли я настроить внешний вид цифровой подписи?

 О: Да, вы можете настроить внешний вид цифровой подписи, указав путь к изображению в поле`SignatureAppearance` собственность`PdfFileSignature` объект.

#### Вопрос: Что произойдет, если подпись недействительна?

О: Если подпись недействительна, процесс проверки завершится неудачно, и соответствующие действия в блоке кода проверки не будут выполнены.

#### Вопрос: Как я могу обеспечить безопасность своих цифровых подписей?

Ответ: Цифровые подписи безопасны по своей конструкции и используют криптографические методы для обеспечения подлинности и целостности. Убедитесь, что вы храните свой закрытый ключ в безопасности и следуете рекомендациям по работе с цифровыми подписями.

#### Вопрос: Могу ли я добавить несколько цифровых подписей в PDF-файл?

 О: Да, вы можете добавить несколько цифровых подписей в PDF-файл, используя`PdfFileSignature` объекты`Sign` или`Certify` методы. Каждая подпись будет иметь свой внешний вид и конфигурацию.