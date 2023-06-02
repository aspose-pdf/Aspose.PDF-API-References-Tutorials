---
title: Замените отсутствующие шрифты
linktitle: Замените отсутствующие шрифты
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по замене отсутствующих шрифтов в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 260
url: /ru/net/document-conversion/replace-missing-fonts/
---

В этом руководстве мы познакомим вас с процессом замены отсутствующих шрифтов в файле PDF с помощью Aspose.PDF для .NET. Когда вы открываете файл PDF на компьютере, где отсутствует определенный шрифт, могут возникнуть проблемы с отображением шрифта. В таких случаях можно заменить отсутствующий шрифт другим шрифтом, доступным на машине. Следуя приведенным ниже инструкциям, вы сможете заменить отсутствующие шрифты в файле PDF.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Поиск недостающего шрифта
Первый шаг — найти отсутствующий шрифт в файле PDF. Используйте следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Найдите оригинальный шрифт
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Шрифт отсутствует на целевом компьютере
     // Добавить простую замену шрифта
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2. Замените отсутствующий шрифт
Далее мы заменим отсутствующий шрифт другим доступным шрифтом. Используйте следующий код:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Преобразование файла PDF в формат PDF/A с удалением ошибок
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Сохраните полученный PDF-файл
pdf.Save(fileNew.FullName);
```

 Обязательно замените`"input.pdf"` с фактическим путем к исходному файлу PDF и`"newfile_out.pdf"` с желаемым именем для полученного PDF-файла.

## Шаг 3: Сохранение полученного PDF-файла
Наконец, мы сохраним полученный файл PDF с замененным шрифтом. Используйте следующий код:

```csharp
// Сохраните полученный PDF-файл
pdf.Save(fileNew.FullName);
```

Гарантирует, что вы установили правильный путь назначения для результирующего PDF-файла.

### Пример исходного кода для замены отсутствующих шрифтов с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Шрифт отсутствует на целевой машине
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс замены отсутствующих шрифтов в файле PDF с помощью Aspose.PDF для .NET. Следуя приведенным выше инструкциям, вы сможете успешно заменить отсутствующие шрифты в файле PDF.