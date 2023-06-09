---
title: Установить привилегии
linktitle: Установить привилегии
second_title: Aspose.PDF для справочника API .NET
description: Легко устанавливайте права доступа к своим PDF-файлам с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-security-and-signatures/set-privileges/
---

Часто бывает необходимо установить определенные права доступа для файлов PDF. С Aspose.PDF для .NET вы можете легко установить права доступа, используя следующий исходный код:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимые директивы импорта:

```csharp
using Aspose.Pdf;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, который вы хотите отредактировать. Заменять`"YOUR DOCUMENTS DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 3: Загрузите исходный PDF-файл

Теперь мы загрузим исходный PDF-файл, используя следующий код:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Шаг 4: Установите права доступа

 На этом шаге мы создадим экземпляр`DocumentPrivilege` объект для установки желаемых прав доступа. Вы можете применить ограничения ко всем привилегиям, используя`DocumentPrivilege.ForbidAll` . Например, если вы хотите разрешить только чтение с экрана, вы можете установить`AllowScreenReaders` к`true`. Вот соответствующий код:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Шаг 5: Зашифруйте и сохраните документ

 Наконец, мы можем зашифровать документ PDF с помощью пароля пользователя и владельца, используя`Encrypt` и указание желаемого алгоритма шифрования. Затем сохраняем обновленный документ. Вот соответствующий код:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Пример исходного кода для установки привилегий с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите исходный файл PDF
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Создание экземпляра объекта Document Privileges
	// Применение ограничений ко всем привилегиям
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Разрешить только чтение с экрана
	documentPrivilege.AllowScreenReaders = true;
	// Зашифруйте файл с помощью пароля пользователя и владельца.
	// Необходимо установить пароль, чтобы, как только пользователь просматривал файл с паролем пользователя,
	//Включена только опция чтения с экрана
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Сохранить обновленный документ
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по установке прав доступа к документу PDF с помощью Aspose.PDF для .NET. Вы можете использовать этот код, чтобы применить определенные ограничения и защитить ваши PDF-файлы по мере необходимости.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенной безопасности документов PDF и функциях управления правами доступа.