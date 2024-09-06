---
title: Установить информацию о файле в PDF-файле
linktitle: Установить информацию о файле в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как использовать Aspose.PDF для .NET для установки информации о файле в PDF-файле с помощью этого пошагового руководства.
type: docs
weight: 310
url: /ru/net/programming-with-document/setfileinfo/
---
Если вы работаете над проектом, требующим управления файлами PDF с помощью Aspose.PDF для .NET, одной из функций, которую вы можете захотеть использовать, является возможность задать информацию о файле для документа PDF. Информация о файле включает в себя различные сведения, такие как автор, дата создания, ключевые слова, дата изменения, тема и заголовок. Это руководство проведет вас через процесс настройки информации о файле для документа PDF с использованием исходного кода C# с Aspose.PDF для .NET.

## Пошаговое руководство по настройке информации о файле с помощью Aspose.PDF для .NET

1. Создайте новый проект C# в среде разработки Visual Studio.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET в свой проект.
3. Создайте новый объект PDF-документа, указав путь к PDF-файлу, информацию о котором вы хотите изменить.

## Шаг 1: Укажите путь к каталогу документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ.

```csharp
// Открыть документ
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Шаг 3: Используйте объект DocumentInfo для доступа к информации о файле PDF-документа.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Шаг 4: Задайте требуемые значения информации о файле, используя свойства объекта DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Шаг 5: Сохраните обновленный PDF-документ в указанном месте.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Шаг 6: Убедитесь, что информация о файле успешно обновлена.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Вы успешно установили информацию о файле для PDF-документа с помощью Aspose.PDF для .NET.

### Пример исходного кода для Set File Info с использованием Aspose.PDF для .NET


```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Укажите информацию о документе
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Сохранить выходной документ
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Заключение

В заключение, Aspose.PDF для .NET предоставляет простой и эффективный способ установки информации о файле для документов PDF. Выполнив указанные выше шаги, вы можете легко установить желаемые значения информации о файле для ваших документов PDF, используя исходный код C#.

### Часто задаваемые вопросы по информации о заданном файле в файле PDF

#### В: Могу ли я задать дополнительные свойства информации о файле, не упомянутые в примере?

 A: Да, вы можете задать дополнительные свойства информации о файле с помощью`DocumentInfo` объект в Aspose.PDF для .NET.`DocumentInfo`класс предоставляет различные свойства, которые позволяют вам задавать дополнительную информацию, такую как производитель, версия и пользовательские свойства.

#### В: Можно ли извлечь информацию о файле из существующего PDF-документа?

 A: Да, вы можете получить информацию о файле из существующего документа PDF с помощью Aspose.PDF for .NET. Для этого вы можете использовать`DocumentInfo` объект для доступа к свойствам информации о файле и чтения информации, хранящейся в документе PDF.

#### В: Изменяет ли настройка информации о файле исходный PDF-документ?

A: Нет, настройка информации о файле с помощью Aspose.PDF for .NET не изменяет исходный документ PDF. Вместо этого он создает новый документ PDF с обновленной информацией о файле. Исходный документ PDF остается неизменным.