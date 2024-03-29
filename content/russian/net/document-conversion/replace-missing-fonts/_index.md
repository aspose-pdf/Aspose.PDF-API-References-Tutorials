---
title: Заменить отсутствующие шрифты
linktitle: Заменить отсутствующие шрифты
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по замене отсутствующих шрифтов в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 260
url: /ru/net/document-conversion/replace-missing-fonts/
---
В этом уроке мы покажем вам процесс замены отсутствующих шрифтов в PDF-файле с помощью Aspose.PDF для .NET. Когда вы открываете PDF-файл на компьютере, где отсутствует определенный шрифт, могут возникнуть проблемы с отображением шрифта. В таких случаях можно заменить отсутствующий шрифт другим шрифтом, имеющимся на компьютере. Выполнив следующие действия, вы сможете заменить отсутствующие шрифты в PDF-файле.

## Предварительные условия
Прежде чем начать, убедитесь, что вы соответствуете следующим предварительным условиям:

- Базовые знания языка программирования C#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Найдите недостающий шрифт
Первый шаг — найти недостающий шрифт в PDF-файле. Используйте следующий код:

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
     // Добавьте простую замену шрифта
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш PDF-файл.

## Шаг 2. Замените отсутствующий шрифт
Далее мы заменим отсутствующий шрифт другим доступным шрифтом. Используйте следующий код:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Конвертируйте PDF-файл в формат PDF/A с удалением ошибок.
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Сохраните полученный PDF-файл.
pdf.Save(fileNew.FullName);
```

 Обязательно замените`"input.pdf"` с фактическим путем к исходному PDF-файлу и`"newfile_out.pdf"` с желаемым именем полученного PDF-файла.

## Шаг 3. Сохранение полученного PDF-файла.
Наконец, мы сохраним полученный PDF-файл с замененным шрифтом. Используйте следующий код:

```csharp
// Сохраните полученный PDF-файл.
pdf.Save(fileNew.FullName);
```

Гарантирует, что вы установили правильный путь назначения для полученного PDF-файла.

### Пример исходного кода для замены отсутствующих шрифтов с помощью Aspose.PDF для .NET

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
	// Шрифт отсутствует на целевом компьютере
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Заключение
В этом уроке мы рассмотрели пошаговый процесс замены отсутствующих шрифтов в файле PDF с помощью Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, вы сможете успешно заменить отсутствующие шрифты в вашем PDF-файле.

### Часто задаваемые вопросы

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF for .NET — это мощная библиотека, позволяющая разработчикам работать с PDF-документами в приложениях C#. Он предлагает различные функции, включая возможность замены отсутствующих шрифтов в файлах PDF.

#### Вопрос: Почему я могу столкнуться с отсутствием шрифтов в PDF-файле?

О: Отсутствующие шрифты в PDF-файле могут возникнуть, если файл открыт на компьютере, на котором не установлены необходимые шрифты. Это может привести к подмене шрифта, влияющей на внешний вид документа.

#### Вопрос: Как найти и заменить отсутствующие шрифты в PDF-файле с помощью Aspose.PDF для .NET?

 О: Чтобы найти и заменить отсутствующие шрифты, вы можете использовать`FontRepository.FindFont` метод проверки наличия необходимого шрифта. Если шрифт отсутствует, вы можете добавить замену шрифта, используя`FontRepository.Substitutions` свойство.

#### Вопрос: Могу ли я настроить процесс замены шрифта?

О: Да, вы можете настроить процесс замены шрифта, указав для замены другой шрифт. В предоставленном коде мы использовали Arial вместо отсутствующего шрифта «AgencyFB», но вы можете выбрать другой шрифт в соответствии со своими предпочтениями.

#### Вопрос: Как обеспечить точность отрисовки шрифта после замены?

О: Aspose.PDF для .NET предоставляет надежные возможности обработки шрифтов, гарантируя точную визуализацию шрифтов после замены. Вы можете просмотреть полученный PDF-файл, чтобы проверить замену шрифта.