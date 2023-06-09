---
title: Текстовая структура стиля
linktitle: Текстовая структура стиля
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как форматировать структуру текста в документе PDF с помощью Aspose.PDF для .NET. Пошаговое руководство по стилю текста.
type: docs
weight: 190
url: /ru/net/programming-with-tagged-pdf/style-text-structure/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C# для форматирования текстовой структуры с помощью Aspose.PDF для .NET. Следуйте приведенным ниже инструкциям, чтобы понять, как стилизовать и форматировать текст в документе PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Создание PDF-документа

На этом этапе мы создадим новый объект документа PDF с помощью Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте PDF-документ
Document document = new Document();
```

Мы создали новый PDF-документ с помощью Aspose.PDF.

## Шаг 3. Настройте содержимое для работы с TaggedPdf

На этом этапе мы получим содержимое документа PDF для работы с теговой структурой.

```csharp
// Получите содержимое для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

Мы получили содержимое PDF-документа для работы с теговой структурой.

## Шаг 4: Установите название документа и язык

Теперь мы установим заголовок и язык PDF-документа.

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Мы определили название и язык PDF-документа.

## Шаг 5: Создание элемента абзаца

На этом шаге мы создадим новый элемент абзаца и добавим его в структуру с тегами.

```csharp
// Создать элемент абзаца
ParagraphElement p = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(p);
```

Мы создали новый элемент абзаца и добавили его в корень помеченной структуры.

## Шаг 6: Форматирование текста

Теперь давайте стилизуем и отформатируем текст элемента абзаца.

```csharp
// Форматировать текст
p.StructureTextState.FontSize = 18F;
p.StructureTextState.ForegroundColor = Color.Red;
p.StructureTextState.FontStyle = FontStyles.Italic;
p.SetText("Text in italic red.");
```

Мы применили форматирование к тексту, установив размер шрифта, цвет и стиль шрифта.

## Шаг 7: Сохранение документа PDF с тегами

Теперь, когда мы стилизовали текст в нашем PDF-документе, давайте сохраним его как PDF-документ с тегами.

```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "StyleTextStructure.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

### Пример исходного кода для структуры текста стиля с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать PDF-документ
Document document = new Document();

// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Установить заголовок и язык для Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
ParagraphElement p = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(p);

// В разработке
p.StructureTextState.FontSize = 18F;
p.StructureTextState.ForegroundColor = Color.Red;
p.StructureTextState.FontStyle = FontStyles.Italic;
p.SetText("Red italic text.");

// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "StyleTextStructure.pdf");

```

## Заключение

В этом руководстве мы узнали, как стилизовать и форматировать структуру текста в документе PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать Aspose.PDF для создания PDF-документов с пользовательским форматированием текста.
