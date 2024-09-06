---
title: Подпишите с помощью смарт-карты, используя поле подписи
linktitle: Подпишите с помощью смарт-карты, используя поле подписи
second_title: Справочник по API Aspose.PDF для .NET
description: Подписывайте свои PDF-файлы безопасно с помощью смарт-карты, используя Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Цифровая подпись с помощью смарт-карты — это безопасный способ подписывать файлы PDF. С Aspose.PDF для .NET вы можете легко подписать файл PDF, используя поле подписи и смарт-карту, следуя следующему исходному коду:

## Шаг 1: Импорт необходимых библиотек

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимые директивы импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Шаг 2: Укажите путь к папке с документами

 На этом шаге вам необходимо указать путь к папке, содержащей PDF-файл, который вы хотите подписать. Заменить`"YOUR DOCUMENTS DIRECTORY"` в следующем коде укажите фактический путь к папке с вашими документами:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 3: Скопируйте и откройте PDF-документ.

Теперь скопируем и откроем PDF-документ для подписания, используя следующий код:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Создать поле подписи
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Выберите сертификат в магазине
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Создайте внешнюю подпись с необходимой информацией
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Шаг 4: Проверка подписи

 Наконец, мы проверяем подпись подписанного PDF-файла с помощью`PdfFileSignature` класс. Мы получаем имена подписей и проверяем их по одному. Если подпись не проходит проверку, выбрасывается исключение. Вот соответствующий код:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Пример исходного кода для подписи с помощью смарт-карты с использованием поля подписи с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Подписать с выбором сертификата в хранилище сертификатов Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Вручную выберите сертификат в магазине
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

Поздравляем! Теперь у вас есть пошаговое руководство по подписанию PDF-файла с помощью смарт-карты с использованием поля подписи с Aspose.PDF для .NET. Вы можете использовать этот код для добавления защищенных цифровых подписей в ваши PDF-документы.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях цифровой подписи и управления сертификатами.

### Часто задаваемые вопросы

#### В: В чем преимущество использования поля подписи для цифровой подписи с помощью смарт-карты?

A: Использование поля подписи для цифровой подписи с помощью смарт-карты обеспечивает обозначенную область в PDF-файле, где применяется подпись. Это повышает ясность документа и гарантирует подлинность подписи.

#### В: Каким образом библиотека Aspose.PDF для .NET упрощает цифровую подпись на основе смарт-карт с полем подписи?

A: Aspose.PDF для .NET упрощает процесс создания поля подписи, выбора сертификата смарт-карты и применения цифровой подписи к определенной области в документе PDF.

#### В: Почему выбор конкретного сертификата важен для подписи с использованием смарт-карт?

A: Выбор определенного сертификата позволяет вам однозначно идентифицировать подписчика и гарантировать целостность подписи. Это помогает установить доверие и соответствие стандартам цифровой подписи.

#### В: Каким образом предоставленный исходный код обрабатывает процесс подписания на основе смарт-карты с полем подписи?

A: Исходный код демонстрирует, как создать поле подписи, выбрать сертификат смарт-карты и применить цифровую подпись с определенной информацией подписи. Он также показывает, как проверить действительность подписи.

#### В: Могу ли я настроить внешний вид поля подписи?

A: Да, вы можете настроить внешний вид поля подписи, например его размер, положение и визуальное представление, чтобы оно соответствовало макету вашего документа.

#### В: Что произойдет, если подпись не пройдет проверку на этапе проверки?

A: Если подпись не проходит проверку, выдается исключение, указывающее, что подпись недействительна. Это гарантирует, что принимаются только действительные и доверенные подписи.

#### В: Могу ли я применить несколько полей подписи и подписей на основе смарт-карт к одному PDF-документу?

О: Конечно, вы можете применять несколько полей подписи и подписи на основе смарт-карт к разным областям одного и того же PDF-документа, обеспечивая несколько уровней безопасности.

#### В: Как использование поля подписи улучшает общий процесс подписания документов?

A: Использование поля для подписи упрощает процесс подписания документа, поскольку позволяет подписывающему лицу поставить свою подпись в специально отведенном месте, что делает процесс подписания более организованным и удобным для пользователя.

#### В: Существуют ли какие-либо ограничения на использование полей подписи при подписании с помощью смарт-карт?

A: Нет никаких неотъемлемых ограничений для использования полей подписи с подписью на основе смарт-карт. Однако важно убедиться, что выбранное расположение поля подписи не заслоняет важное содержимое документа.

#### В: Где я могу найти дополнительную помощь или поддержку по внедрению подписи на основе смарт-карт с полем подписи?

A: Для получения дополнительных рекомендаций и поддержки вы можете обратиться к официальной документации Aspose.PDF и форумам сообщества, которые предлагают ценную информацию и решения для внедрения защищенных цифровых подписей.