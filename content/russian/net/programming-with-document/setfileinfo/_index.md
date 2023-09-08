---
title: Установить информацию о файле в PDF-файле
linktitle: Установить информацию о файле в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как использовать Aspose.PDF для .NET для установки информации о файле в PDF-файл, с помощью этого пошагового руководства.
type: docs
weight: 310
url: /ru/net/programming-with-document/setfileinfo/
---
Если вы работаете над проектом, требующим управления файлами PDF с помощью Aspose.PDF для .NET, одной из функций, которую вы можете использовать, является возможность устанавливать информацию о файле для документа PDF. Информация о файле включает в себя различные сведения, такие как автор, дата создания, ключевые слова, дата изменения, тема и название. Это руководство проведет вас через процесс настройки информации о файле для PDF-документа с использованием исходного кода C# с помощью Aspose.PDF для .NET.

## Пошаговое руководство по настройке информации о файле с помощью Aspose.PDF для .NET

1. Создайте новый проект C# в интегрированной среде разработки Visual Studio.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET в свой проект.
3. Создайте новый объект PDF-документа, указав путь к PDF-файлу, для которого вы хотите изменить информацию о файле.

## Шаг 1: Установите путь к каталогу документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте PDF-документ.

```csharp
// Открыть документ
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Шаг 3. Используйте объект DocumentInfo для доступа к информации о файле PDF-документа.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Шаг 4. Установите нужные значения информации о файле, используя свойства объекта DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Шаг 5. Сохраните обновленный PDF-документ в указанном месте.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Шаг 6. Убедитесь, что информация о файле успешно обновлена.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Вы успешно установили информацию о файле для PDF-документа с помощью Aspose.PDF для .NET.

### Пример исходного кода для установки информации о файле с использованием Aspose.PDF для .NET


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

В заключение, Aspose.PDF для .NET предоставляет простой и эффективный способ настройки информации о файле для документов PDF. Выполнив вышеупомянутые шаги, вы можете легко установить нужные значения информации о файле для ваших PDF-документов, используя исходный код C#.

### Часто задаваемые вопросы по установке информации о файле в PDF-файле

#### Вопрос: Могу ли я установить дополнительные свойства информации о файле, не упомянутые в примере?

 О: Да, вы можете установить дополнительные свойства информации о файле, используя`DocumentInfo` объект в Aspose.PDF для .NET.`DocumentInfo`Класс предоставляет различные свойства, которые позволяют вам устанавливать дополнительную информацию, такую как производитель, версия и пользовательские свойства.

#### Вопрос: Можно ли получить информацию о файле из существующего PDF-документа?

 О: Да, вы можете получить информацию о файле из существующего PDF-документа, используя Aspose.PDF для .NET. Для этого вы можете использовать`DocumentInfo` объект для доступа к свойствам информации о файле и чтения информации, хранящейся в PDF-документе.

#### Вопрос: Изменяет ли установка информации о файле исходный PDF-документ?

О: Нет, установка информации о файле с помощью Aspose.PDF для .NET не изменяет исходный PDF-документ. Вместо этого он создает новый PDF-документ с обновленной информацией о файле. Исходный PDF-документ остается неизменным.