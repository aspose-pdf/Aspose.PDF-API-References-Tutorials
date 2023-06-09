---
title: Проверить PDF
linktitle: Проверить PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как проверить документ PDF с помощью Aspose.PDF для .NET. Проверьте его соответствие стандартам и сгенерируйте отчет о проверке.
type: docs
weight: 240
url: /ru/net/programming-with-tagged-pdf/validate-pdf/
---
В этом руководстве мы расскажем, как проверить документ PDF с помощью Aspose.PDF для .NET. Следуйте приведенным ниже инструкциям, чтобы понять, как использовать предоставленный исходный код C# для проверки PDF-файла и создания отчета о проверке.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Подготовка PDF-документа

Поместите файл PDF для проверки в указанный каталог. Обязательно скорректируйте путь к файлу в исходном коде, используя собственный каталог документов.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Путь к входному файлу PDF
string inputFileName = dataDir + "StructureElements.pdf";

// Путь к выходному файлу отчета о проверке
string outputLogName = dataDir + "ua-20.xml";
```

Убедитесь, что проверяемый файл PDF правильно указан в исходном коде.

## Шаг 3: Проверка PDF

На этом этапе мы будем использовать Aspose.PDF для .NET для проверки указанного PDF-документа и создания отчета о проверке.

```csharp
// Откройте PDF-документ
using (var document = new Aspose.Pdf.Document(inputFileName))
{
// Подтвердите документ PDF
bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
}
```

Мы открыли PDF-документ и проверили его формат с помощью Aspose.PDF для .NET. Результат проверки будет сохранен в указанном файле отчета.

### Пример исходного кода для проверки PDF с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFileName = dataDir + "StructureElements.pdf";
string outputLogName = dataDir + "ua-20.xml";

using (var document = new Aspose.Pdf.Document(inputFileName))
{
	bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
}

```

## Заключение

В этом руководстве мы узнали, как использовать Aspose.PDF для .NET для проверки PDF-документа и создания отчета о проверке. Проверка PDF-файла позволяет убедиться, что он соответствует стандартам, и гарантирует его доступность. Используйте эти функции, чтобы улучшить качество ваших PDF-документов.
