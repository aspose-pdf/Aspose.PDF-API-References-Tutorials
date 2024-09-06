---
title: Подпишите с помощью смарт-карты, используя подпись в файле PDF
linktitle: Подпишите с помощью смарт-карты, используя подпись в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Подписывайте свои PDF-файлы безопасно с помощью смарт-карты, используя Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Цифровая подпись с помощью смарт-карты — это безопасный способ подписывать файлы PDF. С Aspose.PDF для .NET вы можете легко подписать файл PDF с помощью смарт-карты, следуя следующему исходному коду:

## Шаг 1: Импорт необходимых библиотек

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимые директивы импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Шаг 2: Укажите путь к папке с документами

 На этом шаге вам необходимо указать путь к папке, содержащей PDF-файл, который вы хотите подписать. Заменить`"YOUR DOCUMENTS DIRECTORY"` в следующем коде укажите фактический путь к папке с вашими документами:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 3: Загрузите PDF-документ.

Теперь загрузим PDF-документ для подписания, используя следующий код:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Шаг 4: Выполните подпись с помощью смарт-карты.

 На этом этапе мы выполним подпись с помощью смарт-карты, используя`PdfFileSignature` класс из`Facades`Библиотека. Выбираем сертификат смарт-карты из хранилища сертификатов Windows и указываем необходимую информацию для подписи. Вот соответствующий код:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Выберите сертификат в магазине
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Шаг 5: Проверка подписи

 Наконец, мы проверяем подпись подписанного PDF-файла с помощью`PdfFileSignature` класс. Мы получаем имена подписей и проверяем их по одному. Если подпись не проходит проверку, выбрасывается исключение. Вот соответствующий код:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Пример исходного кода для подписи с помощью смарт-карты с использованием подписи в файле PDF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Подписать с выбором сертификата в хранилище сертификатов Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Вручную выберите сертификат в магазине
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по подписанию PDF-файла с помощью смарт-карты с использованием Aspose.PDF для .NET. Вы можете использовать этот код для добавления защищенных цифровых подписей в ваши PDF-документы.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях цифровой подписи и управления сертификатами.

### Часто задаваемые вопросы

#### В: Почему мне следует рассмотреть возможность подписания PDF-файлов с помощью смарт-карты?

A: Подписание PDF-файлов с помощью смарт-карты повышает безопасность, гарантируя подлинность и целостность документа. Подписи на основе смарт-карт обеспечивают более высокий уровень доверия и соответствия.

#### В: Как работает цифровая подпись на основе смарт-карт?

A: Цифровая подпись на основе смарт-карты подразумевает использование криптографического ключа, хранящегося на смарт-карте, для создания уникальной цифровой подписи. Эта подпись прикрепляется к файлу PDF, позволяя получателям проверить происхождение и целостность документа.

#### В: Какова роль Aspose.PDF для .NET в подписании с использованием смарт-карт?

A: Aspose.PDF для .NET предоставляет полный набор инструментов и библиотек для упрощения цифровой подписи PDF-файлов на основе смарт-карт. Он упрощает процесс и обеспечивает безопасную подпись документов.

#### В: Могу ли я выбрать определенный сертификат смарт-карты для подписи?

A: Да, вы можете выбрать определенный сертификат смарт-карты из хранилища сертификатов Windows для подписи. Aspose.PDF для .NET позволяет вам легко интегрировать выбор сертификата в ваше приложение.

#### В: Как предоставленный исходный код обрабатывает подписание с помощью смарт-карт?

A: Исходный код демонстрирует, как связать PDF-документ, выбрать сертификат смарт-карты, указать информацию для подписи и создать цифровую подпись. Он также показывает, как проверить действительность подписи.

#### В: Могу ли я применить несколько подписей с помощью смарт-карт в одном PDF-файле?

A: Конечно, вы можете применить несколько подписей на основе смарт-карт к одному файлу PDF. Каждая подпись уникальна и вносит вклад в общую безопасность документа.

#### В: Что делать, если подпись не прошла проверку на этапе проверки?

A: Если подпись не проходит проверку, выдается исключение, указывающее, что подпись недействительна. Это гарантирует, что принимаются только действительные и доверенные подписи.

#### В: Совместима ли подпись с помощью смарт-карт со всеми типами PDF-документов?

A: Да, подпись на основе смарт-карт совместима со всеми типами PDF-документов. Вы можете применять цифровые подписи к различным типам PDF-файлов, включая формы, отчеты и многое другое.

#### В: Как я могу узнать больше о расширенной цифровой подписи и управлении сертификатами?

A: Изучите официальную документацию Aspose.PDF, чтобы получить подробную информацию о расширенных функциях цифровой подписи, управлении сертификатами и передовых методах обеспечения безопасности документов.

#### В: Где я могу найти дополнительную помощь или поддержку по внедрению подписи на основе смарт-карт?

A: Для получения дополнительных рекомендаций и поддержки обратитесь на форумы сообщества Aspose.PDF или ознакомьтесь с документацией, где вы найдете исчерпывающую информацию о подписи с использованием смарт-карт.