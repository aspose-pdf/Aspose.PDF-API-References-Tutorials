---
title: Подпишитесь с помощью смарт-карты, используя подпись PDF-файла
linktitle: Подпишитесь с помощью смарт-карты, используя подпись PDF-файла
second_title: Aspose.PDF для справочника API .NET
description: Надежно подписывайте файлы PDF с помощью смарт-карты с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Цифровая подпись с помощью смарт-карты — это безопасный способ подписи PDF-файлов. С помощью Aspose.PDF для .NET вы можете легко подписать файл PDF с помощью смарт-карты, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимые директивы импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, который вы хотите подписать. Заменять`"YOUR DOCUMENTS DIRECTORY"`в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 3: Загрузите PDF-документ

Теперь мы загрузим документ PDF для подписи, используя следующий код:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Шаг 4: Выполните подпись с помощью смарт-карты

 На этом этапе мы выполним подпись с помощью смарт-карты, используя`PdfFileSignature` класс из`Facades`библиотека. Выбираем сертификат смарт-карты из хранилища сертификатов Windows и указываем необходимую информацию для подписи. Вот соответствующий код:

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

## Шаг 5: Подтвердите подпись

 Наконец, мы проверяем подпись подписанного PDF-файла, используя`PdfFileSignature` сорт. Получаем имена подписей и проверяем их одно за другим. Если подпись не проходит проверку, генерируется исключение. Вот соответствующий код:

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

### Пример исходного кода для подписи со смарт-картой с использованием подписи файла PDF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Подпишитесь с выбором сертификата в хранилище сертификатов Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Вручную выбрал сертификат в магазине
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

Поздравляем! Теперь у вас есть пошаговое руководство по подписанию файла PDF с помощью смарт-карты с помощью Aspose.PDF для .NET. Вы можете использовать этот код для добавления безопасных цифровых подписей в ваши PDF-документы.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях цифровой подписи и управления сертификатами.

### Часто задаваемые вопросы

#### В: Почему мне следует подписывать PDF-файлы с помощью смарт-карты?

О: Подписание PDF-файлов с помощью смарт-карты повышает безопасность, гарантируя подлинность и целостность документа. Подписи на основе смарт-карт обеспечивают более высокий уровень доверия и соответствия требованиям.

#### Вопрос. Как работает цифровая подпись на основе смарт-карт?

О: Цифровая подпись на основе смарт-карты предполагает использование криптографического ключа, хранящегося на смарт-карте, для создания уникальной цифровой подписи. Эта подпись прикрепляется к файлу PDF, что позволяет получателям проверить происхождение и целостность документа.

#### Вопрос: Какова роль Aspose.PDF для .NET в подписывании на основе смарт-карт?

О: Aspose.PDF для .NET предоставляет полный набор инструментов и библиотек для упрощения цифровой подписи PDF-файлов на основе смарт-карт. Это упрощает процесс и обеспечивает безопасное подписание документов.

#### Вопрос. Можно ли выбрать для подписи конкретный сертификат смарт-карты?

О: Да, вы можете выбрать определенный сертификат смарт-карты из хранилища сертификатов Windows для подписи. Aspose.PDF для .NET позволяет легко интегрировать выбор сертификатов в ваше приложение.

#### Вопрос. Как предоставленный исходный код обрабатывает подпись на основе смарт-карты?

О. В исходном коде показано, как связать PDF-документ, выбрать сертификат смарт-карты, указать информацию для подписи и создать цифровую подпись. Также показано, как проверить действительность подписи.

#### Вопрос. Можно ли применить несколько подписей с помощью смарт-карт в одном файле PDF?

О: Безусловно, вы можете применить несколько подписей на основе смарт-карт к одному файлу PDF. Каждая подпись уникальна и способствует общей безопасности документа.

#### Вопрос. Что делать, если подпись не проходит проверку на этапе проверки?

О: Если подпись не проходит проверку, выдается исключение, указывающее, что подпись недействительна. Это гарантирует, что принимаются только действительные и надежные подписи.

#### В: Совместимо ли подписание на основе смарт-карты со всеми типами PDF-документов?

О: Да, подписывание на основе смарт-карты совместимо со всеми типами PDF-документов. Вы можете применять цифровые подписи к различным типам PDF-файлов, включая формы, отчеты и многое другое.

#### Вопрос. Как узнать больше о расширенном управлении цифровыми подписями и сертификатами?

О: Изучите официальную документацию Aspose.PDF, чтобы получить подробные сведения о расширенных функциях цифровой подписи, управлении сертификатами и рекомендациях по обеспечению безопасности документов.

#### Вопрос: Где я могу найти дополнительную помощь или поддержку для реализации подписи на основе смарт-карт?

О: Для получения дополнительных рекомендаций и поддержки обратитесь на форумы сообщества Aspose.PDF или обратитесь к документации для получения исчерпывающей информации о подписи на основе смарт-карт.