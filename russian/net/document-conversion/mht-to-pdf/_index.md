---
title: MHT в PDF
linktitle: MHT в PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию MHT в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/document-conversion/mht-to-pdf/
---

В этом руководстве мы проведем вас через процесс преобразования файла MHT в PDF с помощью Aspose.PDF для .NET. MHT (MIME HTML) — это формат, используемый для сохранения полной веб-страницы, включая изображения и связанный с ними контент. Следуя приведенным ниже инструкциям, вы сможете конвертировать файлы MHT в формат PDF.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка файла MHT
На этом этапе мы загрузим файл MHT, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Загрузите документ
Document document = new Document(dataDir + "test.mht", options);
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл MHT.

## Шаг 2. Преобразование MHT в PDF
После загрузки файла MHT мы можем приступить к преобразованию в PDF. Используйте следующий код:

```csharp
// Сохраните результат в виде PDF-документа
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Приведенный выше код преобразует файл MHT в формат PDF и сохраняет его как имя файла.`"MHTToPDF_out.pdf"`.

### Пример исходного кода для преобразования MHT в PDF с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Загрузить документ
Document document = new Document(dataDir  + "test.mht", options);
// Сохраните результат в виде документа PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла MHT в PDF с использованием Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете конвертировать файлы MHT в формат PDF. Эта функция может быть полезна, когда вам нужно преобразовать целые веб-страницы в документы PDF.