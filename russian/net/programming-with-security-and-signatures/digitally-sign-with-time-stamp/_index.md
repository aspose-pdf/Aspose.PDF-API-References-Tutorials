---
title: Цифровая подпись с отметкой времени
linktitle: Цифровая подпись с отметкой времени
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как выполнить цифровую подпись с отметкой времени в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

В этом руководстве мы познакомим вас с процессом цифровой подписи PDF-файла с отметкой времени с помощью Aspose.PDF для .NET. Цифровая подпись с отметкой времени гарантирует подлинность и целостность документа за счет добавления электронного отпечатка пальца с отметкой времени.

## Шаг 1: Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания языка программирования С#
- Установка Visual Studio на ваш компьютер
- Установлена библиотека Aspose.PDF для .NET

## Шаг 2: Настройка среды

Чтобы приступить к работе, выполните следующие действия, чтобы настроить среду разработки:

1. Откройте Visual Studio и создайте новый проект C#.
2. Импортируйте необходимые пространства имен в файл кода:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Шаг 3: Цифровая подпись с отметкой времени

Первым шагом является выполнение цифровой подписи с отметкой времени в файле PDF. В предоставленном коде показано, как получить эту подпись с помощью Aspose.PDF для .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Этот код загружает файл PDF, создает цифровую подпись с отметкой времени, используя файл PFX (закрытый ключ) и указанные параметры отметки времени. Затем подпись добавляется в файл PDF и сохраняется с суффиксом "_вне".

### Пример исходного кода для цифровой подписи с отметкой времени с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Пользователь/пароль можно не указывать
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Создайте любой из трех типов подписи
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Сохранить выходной PDF-файл
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Заключение

Поздравляем! Вы успешно выполнили цифровую подпись с отметкой времени в файле PDF, используя Aspose.PDF для .NET. В этом руководстве описан пошаговый процесс от создания подписи до сохранения обновленного PDF-файла. Теперь вы можете использовать эту функцию для добавления цифровых подписей с отметкой времени в файлы PDF.