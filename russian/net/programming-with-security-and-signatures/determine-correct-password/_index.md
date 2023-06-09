---
title: Определить правильный пароль
linktitle: Определить правильный пароль
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как определить правильный пароль для файла PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-security-and-signatures/determine-correct-password/
---

В этом руководстве мы познакомим вас с процессом определения правильного пароля для файла PDF с помощью Aspose.PDF для .NET. Эта функция позволяет вам проверить, защищен ли файл PDF паролем, и найти правильный пароль из предопределенного списка.

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
```

## Шаг 3: Загрузка исходного PDF-файла

Первый шаг — загрузить исходный PDF-файл, который вы хотите проверить. В этом примере предполагается, что у вас есть файл PDF с именем «IsPasswordProtected.pdf» в указанном каталоге.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Обязательно замените заполнители фактическим расположением вашего файла PDF.

## Шаг 4. Определите исходное шифрование PDF

 После того как вы загрузили исходный файл PDF, вы можете определить, зашифрован ли он, используя`IsEncrypted` метод`PdfFileInfo` объект.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Этот оператор показывает, защищен ли файл PDF паролем или нет.

## Шаг 5: Поиск правильного пароля

Далее мы будем искать правильный пароль, используя заранее определенный список паролей. Мы просматриваем каждый пароль в списке и пытаемся загрузить PDF-документ с этим паролем.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Этот цикл проверяет каждое слово из списка. Если пароль правильный, отображается количество страниц в документе. В противном случае отображается сообщение о том, что пароль неверен.


### Пример исходного кода для определения правильного пароля с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Загрузить исходный PDF-файл
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Определите, зашифрован ли исходный PDF-файл
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Заключение

Поздравляем! Вы успешно определили правильный пароль для файла PDF, используя Aspose.PDF для .NET. В этом руководстве описан пошаговый процесс, от проверки шифрования файла до поиска правильного пароля из предопределенного списка. Теперь вы можете использовать эту функцию, чтобы проверить и найти правильный пароль для ваших файлов PDF.