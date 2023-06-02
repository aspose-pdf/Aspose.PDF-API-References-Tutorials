---
title: PDF в PDFA
linktitle: PDF в PDFA
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию PDF в PDFA с помощью Aspose.PDF для .NET.
type: docs
weight: 140
url: /ru/net/document-conversion/pdf-to-pdfa/
---

В этом руководстве мы познакомим вас с процессом преобразования файла PDF в формат PDF/A с использованием Aspose.PDF для .NET. Формат PDF/A — это стандарт ISO, гарантирующий долгосрочную сохранность электронных документов. Следуя приведенным ниже инструкциям, вы сможете конвертировать PDF-файлы в формат PDF/A.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Открытие исходного PDF-документа
На этом этапе мы откроем исходный PDF-файл, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Откройте исходный PDF-документ
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2. Преобразование в формат PDF/A
После открытия файла PDF мы можем приступить к преобразованию в формат PDF/A. Используйте следующий код:

```csharp
// Преобразование в документ, совместимый с PDF/A
// В процессе преобразования также выполняется проверка
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 Приведенный выше код преобразует файл PDF в формат PDF/A-1b, а также выполняет проверку в процессе преобразования. Все ошибки записываются в`"log.xml"` файл.

## Шаг 3: Сохранение полученного файла PDF/A
После завершения преобразования нам нужно сохранить полученный файл PDF/A. Вот последний шаг:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Сохраните выходной документ
pdfDocument.Save(dataDir);
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с желаемым каталогом, где вы хотите сохранить выходной файл PDF/A.

### Пример исходного кода для преобразования PDF в HTML с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Преобразование в документ, совместимый с PDF/A
// В процессе преобразования также выполняется проверка
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Сохранить выходной документ
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла PDF в формат PDF/A с использованием Aspose.PDF для .NET. Следуя инструкциям, описанным выше, теперь вы сможете конвертировать PDF-файлы в формат PDF/A. Эта функция полезна, когда вы хотите обеспечить долгосрочное соответствие ваших электронных документов.