---
title: Подпишите с помощью смарт-карты, используя поле подписи
linktitle: Подпишите с помощью смарт-карты, используя поле подписи
second_title: Справочник по Aspose.PDF для .NET API
description: Надежно подписывайте свои PDF-файлы с помощью смарт-карты, используя Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Цифровая подпись с помощью смарт-карты — это безопасный способ подписи PDF-файлов. С помощью Aspose.PDF для .NET вы можете легко подписать PDF-файл, используя поле подписи и смарт-карту, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки.

Прежде чем начать, вам необходимо импортировать необходимые библиотеки для вашего проекта C#. Вот необходимые директивы импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Шаг 2. Установите путь к папке с документами.

 На этом этапе вам необходимо указать путь к папке, содержащей PDF-файл, который вы хотите подписать. Заменять`"YOUR DOCUMENTS DIRECTORY"`в следующем коде с фактическим путем к папке ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 3. Скопируйте и откройте PDF-документ.

Теперь мы скопируем и откроем PDF-документ для подписи, используя следующий код:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Создайте поле для подписи
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

## Шаг 4. Проверьте подпись

 Наконец, мы проверяем подпись подписанного PDF-файла, используя`PdfFileSignature` сорт. Получаем имена подписей и проверяем их одно за другим. Если подпись не проходит проверку, выдается исключение. Вот соответствующий код:

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
		// Вручную выбрал сертификат в магазине
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

Поздравляем! Теперь у вас есть пошаговое руководство по подписанию PDF-файла с помощью смарт-карты с использованием поля подписи в Aspose.PDF для .NET. Вы можете использовать этот код для добавления безопасных цифровых подписей в ваши PDF-документы.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях цифровой подписи и управления сертификатами.

### Часто задаваемые вопросы

#### Вопрос. В чем преимущество использования поля подписи для цифровой подписи с помощью смарт-карты?

Ответ: Использование поля подписи для цифровой подписи с помощью смарт-карты обеспечивает выделенную область в PDF-файле, куда применяется подпись. Это повышает ясность документа и гарантирует подлинность подписи.

#### Вопрос: Как библиотека Aspose.PDF для .NET упрощает цифровую подпись на основе смарт-карты с полем подписи?

О: Aspose.PDF для .NET упрощает процесс создания поля подписи, выбора сертификата смарт-карты и применения цифровой подписи к определенной области PDF-документа.

#### Вопрос: Почему выбор конкретного сертификата важен для подписи на основе смарт-карты?

О: Выбор конкретного сертификата позволяет однозначно идентифицировать подписавшего и обеспечить целостность подписи. Это помогает установить доверие и соответствие стандартам цифровой подписи.

#### Вопрос: Как предоставленный исходный код обрабатывает процесс подписания на основе смарт-карты с полем подписи?

Ответ: Исходный код демонстрирует, как создать поле подписи, выбрать сертификат смарт-карты и применить цифровую подпись с конкретной информацией для подписи. Здесь также показано, как проверить достоверность подписи.

#### Вопрос: Могу ли я настроить внешний вид поля подписи?

О: Да, вы можете настроить внешний вид поля подписи, например его размер, положение и визуальное представление, в соответствии с макетом вашего документа.

#### Вопрос: Что произойдет, если подпись не пройдет проверку на этапе проверки?

О: Если подпись не проходит проверку, выдается исключение, указывающее, что подпись недействительна. Это гарантирует, что принимаются только действительные и проверенные подписи.

#### Вопрос: Могу ли я применить несколько полей подписи и подписи на основе смарт-карт к одному PDF-документу?

О: Конечно, вы можете применять несколько полей подписи и подписи на основе смарт-карт к различным областям одного и того же PDF-документа, обеспечивая несколько уровней безопасности.

#### Вопрос: Как использование поля подписи улучшает общий процесс подписания документа?

О: Использование поля для подписи упрощает процесс подписания документа, поскольку оно помогает подписывающему лицу разместить свою подпись в отведенном месте, что делает процесс подписания более организованным и удобным для пользователя.

#### Вопрос: Существуют ли какие-либо ограничения на использование полей подписи при подписании на основе смарт-карты?

Ответ. Никаких ограничений на использование полей подписи с подписью на основе смарт-карты не существует. Однако важно убедиться, что выбранное расположение поля подписи не закрывает важное содержимое документа.

#### Вопрос: Где я могу найти дополнительную помощь или поддержку для реализации подписи на основе смарт-карты с полем подписи?

О: Для получения дополнительных рекомендаций и поддержки вы можете обратиться к официальной документации Aspose.PDF и форумам сообщества, которые предлагают ценную информацию и решения для реализации безопасных цифровых подписей.