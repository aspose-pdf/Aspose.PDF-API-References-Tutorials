---
title: PDF в XLS
linktitle: PDF в XLS
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию PDF в XLS с помощью Aspose.PDF для .NET.
type: docs
weight: 200
url: /ru/net/document-conversion/pdf-to-xls/
---

В этом руководстве мы познакомим вас с процессом преобразования файла PDF в формат XLS (Microsoft Excel) с использованием Aspose.PDF для .NET. Следуя приведенным ниже инструкциям, вы сможете преобразовать файл PDF в формат XLS.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка PDF-документа
На этом этапе мы загрузим исходный PDF-файл, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите PDF-документ
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2. Создайте экземпляр параметров резервного копирования Excel
После загрузки файла PDF мы создадим экземпляр параметров сохранения Excel. Используйте следующий код:

```csharp
// Создание экземпляра объекта ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Шаг 3: Сохранение полученного файла XLS
Теперь мы сохраним преобразованный файл PDF в формате XLS. Используйте следующий код:

```csharp
// Сохраните результат в формате XLS.
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Приведенный выше код сохраняет преобразованный PDF-файл в формате XLS с именем файла`"PDFToXLS_out.xls"`.

### Пример исходного кода для преобразования PDF в XLS с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузить PDF-документ
Document pdfDocument = new Document(dataDir + "input.pdf");

// Создание экземпляра объекта ExcelSave Option
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Сохраните результат в формате XLS.
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла PDF в формат XLS с использованием Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете преобразовать файл PDF в формат XLS. Эта функция полезна, когда вы хотите извлечь табличные данные из файла PDF и использовать их в Microsoft Excel.