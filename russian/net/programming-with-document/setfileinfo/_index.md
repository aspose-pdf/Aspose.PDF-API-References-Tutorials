---
title: Установить информацию о файле в файле PDF
linktitle: Установить информацию о файле в файле PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET для установки информации о файле в файле PDF с помощью этого пошагового руководства.
type: docs
weight: 310
url: /ru/net/programming-with-document/setfileinfo/
---
Если вы работаете над проектом, который требует управления файлами PDF с помощью Aspose.PDF для .NET, одной из функций, которую вы можете использовать, является возможность устанавливать информацию о файле для документа PDF. Информация о файле включает в себя различные сведения, такие как автор, дата создания, ключевые слова, дата изменения, тема и название. Это руководство проведет вас через процесс настройки информации о файле для документа PDF с использованием исходного кода C# с помощью Aspose.PDF для .NET.

## Пошаговое руководство по настройке информации о файле с помощью Aspose.PDF для .NET

1. Создайте новый проект C# в интегрированной среде разработки Visual Studio.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET в свой проект.
3. Создайте новый объект документа PDF, указав путь к файлу PDF, для которого вы хотите изменить информацию о файле.

## Шаг 1: Укажите путь к каталогу документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

```csharp
// Открыть документ
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Шаг 3: Используйте объект DocumentInfo для доступа к информации о файле документа PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Шаг 4: Установите нужные значения информации о файле, используя свойства объекта DocumentInfo.

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

## Шаг 6: Убедитесь, что информация о файле была успешно обновлена.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Вы успешно установили информацию о файле для документа PDF, используя Aspose.PDF для .NET.

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

В заключение, Aspose.PDF для .NET предоставляет простой и эффективный способ установки информации о файлах для документов PDF. Следуя вышеупомянутым шагам, вы можете легко установить желаемые значения информации о файле для ваших документов PDF, используя исходный код C#.

### Часто задаваемые вопросы по установке информации о файле в файле PDF

#### В: Могу ли я установить дополнительные свойства информации о файле, не упомянутые в примере?

 О: Да, вы можете установить дополнительные свойства информации о файле, используя`DocumentInfo` объект в Aspose.PDF для .NET.`DocumentInfo`class предоставляет различные свойства, которые позволяют вам установить дополнительную информацию, такую как производитель, версия и пользовательские свойства.

#### В: Можно ли получить информацию о файле из существующего документа PDF?

 О: Да, вы можете получить информацию о файле из существующего документа PDF, используя Aspose.PDF для .NET. Для этого можно использовать`DocumentInfo` объекта для доступа к свойствам информации о файле и чтения информации, хранящейся в документе PDF.

#### В: Изменяет ли установка информации о файле исходный PDF-документ?

О: Нет, установка информации о файле с помощью Aspose.PDF для .NET не изменяет исходный PDF-документ. Вместо этого он создает новый документ PDF с обновленной информацией о файле. Исходный PDF-документ остается без изменений.