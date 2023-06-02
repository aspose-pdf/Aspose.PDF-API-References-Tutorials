---
title: PDF в PDFA3b
linktitle: PDF в PDFA3b
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию PDF в PDF/A-3b с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/document-conversion/pdf-to-pdfa3b/
---

В этом руководстве мы познакомим вас с процессом преобразования файла PDF в формат PDF/A-3b с использованием Aspose.PDF для .NET. PDF/A-3b — это стандарт ISO для встраивания файлов и данных в документ PDF. Следуя приведенным ниже инструкциям, вы сможете конвертировать PDF-файлы в формат PDF/A-3b.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2. Конвертируйте в PDF/A-3b
После открытия файла PDF мы можем приступить к преобразованию в формат PDF/A-3b. Используйте следующий код:

```csharp
// Преобразование в формат PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Приведенный выше код преобразует файл PDF в формат PDF/A-3b и удаляет любые ошибки преобразования.

## Шаг 3: Сохранение полученного файла PDF/A-3b
После завершения преобразования нам нужно сохранить полученный файл PDF/A-3b. Вот последний шаг:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Сохраните выходной документ
pdfDocument.Save(dataDir);
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с желаемым каталогом, где вы хотите сохранить выходной файл PDF/A-3b.

### Пример исходного кода для преобразования PDF в PDFA3b с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Сохранить выходной документ
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла PDF в формат PDF/A-3b с использованием Aspose.PDF для .NET. Следуя приведенным выше инструкциям, теперь вы сможете конвертировать PDF-файлы в формат PDF/A-3b. Эта функция полезна, когда вы хотите встроить дополнительные файлы и данные в документ PDF, соответствующий стандарту PDF/A-3b.