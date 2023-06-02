---
title: PDFA в PDF
linktitle: PDFA в PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию PDFA в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/document-conversion/pdfa-to-pdf/
---

В этом руководстве мы познакомим вас с процессом преобразования файла PDFA (PDF/A) в стандартный формат PDF с помощью Aspose.PDF для .NET. Формат PDFA — это особая версия формата PDF, используемая для обеспечения долгосрочного архивирования документов. Следуя приведенным ниже инструкциям, вы сможете преобразовать файл PDFA в формат PDF.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка документа PDFA
На этом этапе мы загрузим исходный файл PDFA, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ PDFA
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDFA.

## Шаг 2. Удаление информации о соответствии PDF/A
Теперь мы собираемся удалить информацию о соответствии PDF/A из документа. Используйте следующий код:

```csharp
// Удалить информацию о соответствии PDF/A
doc.RemovePdfaCompliance();
```

## Шаг 3: Сохранение полученного PDF-файла
Наконец, мы сохраним преобразованный файл PDFA в формат PDF. Используйте следующий код:

```csharp
// Сохраните обновленный документ в формате PDF.
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

Приведенный выше код сохраняет преобразованный файл PDFA в формат PDF с именем файла`"PDFAToPDF_out.pdf"`.

### Пример исходного кода для PDFA в PDF с использованием Aspose.Words для .NET


```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

// Удалить информацию о соответствии PDF/A
doc.RemovePdfaCompliance();
// Сохранить обновленный документ
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования файла PDFA в формат PDF с использованием Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете преобразовать файл PDFA в стандартный формат PDF. Эта функция полезна, когда вы хотите удалить ограничения соответствия PDF/A из документа для более гибкого использования.