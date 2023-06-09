---
title: Текстовое окно
linktitle: Текстовое окно
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как создать текстовое поле в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 290
url: /ru/net/programming-with-forms/text-box/
---

В этом руководстве мы шаг за шагом объясним, как использовать библиотеку Aspose.PDF для .NET для создания текстового поля в документе PDF. Мы покажем вам, как открыть документ, создать текстовое поле, настроить его свойства и сохранить отредактированный PDF-файл.

## Шаг 1. Настройка каталога документов

 Первый шаг — настроить каталог документов, в котором находится файл PDF, с которым вы хотите работать. Вы можете использовать`dataDir`переменная для указания пути к каталогу.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 2. Открытие PDF-документа

 На этом шаге мы откроем документ PDF с помощью`Document`класс Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Убедитесь, что файл PDF присутствует в указанном каталоге документов.

## Шаг 3: Создание текстового поля

 Мы создадим текстовое поле, используя`TextBoxField` сорт. Вы можете указать координаты положения и размер поля с помощью`Rectangle` сорт.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

При необходимости настройте координаты, размер, частичное имя и значение текстового поля.

## Шаг 4. Настройте свойства текстового поля

На этом этапе мы настроим свойства текстового поля, такие как граница, цвет и т. д.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Настройте свойства текстового поля в соответствии со своими предпочтениями.

## Шаг 5: Добавление поля в документ

Теперь, когда мы создали и настроили текстовое поле, мы можем добавить его в документ PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Шаг 6: Сохранение измененного PDF

 Наконец, мы можем сохранить измененный PDF-файл, используя`Save` метод`Document` сорт.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Обязательно укажите полный путь и имя файла для редактируемого PDF.

### Пример исходного кода для текстового поля с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Создать поле
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = новая граница (
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Добавить поле в документ
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Сохранить измененный PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как использовать библиотеку Aspose.PDF для .NET для создания текстового поля в документе PDF. Следуя описанным шагам, вы сможете настроить свойства текстового поля и добавить его в документ по мере необходимости. Изучите возможности Aspose.PDF для .NET, чтобы расширить возможности работы с PDF-файлами.