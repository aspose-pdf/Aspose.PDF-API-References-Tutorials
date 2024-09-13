---
title: Скрытый текстовый блок в PDF-файле
linktitle: Скрытый текстовый блок в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как создавать скрытые текстовые блоки в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 230
url: /ru/net/programming-with-text/hidden-text-block/
---
В этом уроке мы объясним, как создать скрытый текстовый блок в файле PDF с помощью библиотеки Aspose.PDF для .NET. Скрытый текстовый блок — это плавающий текст, который становится видимым при наведении курсора мыши на определенную область. Мы рассмотрим пошаговый процесс создания скрытого текстового блока с помощью предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовые знания программирования на C#.

## Шаг 1: Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменить`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменную с путем к нужному вам каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте образец документа

На этом этапе мы создаем образец PDF-документа и добавляем в него текстовый фрагмент. Текстовый фрагмент будет служить триггером для отображения скрытого текстового блока.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Шаг 3: Откройте документ.

 Теперь откроем ранее созданный документ с помощью`Document` сорт.

```csharp
Document document = new Document(outputFile);
```

## Шаг 4: Найдите фрагмент текста

 Мы используем`TextFragmentAbsorber`объект для поиска фрагмента текста, который вызовет отображение скрытого текстового блока. В этом случае мы ищем точный текст "Переместите курсор мыши сюда, чтобы отобразить плавающий текст".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Шаг 5: Создайте скрытое текстовое поле

 Мы создаем`TextBoxField` объект для представления скрытого текстового поля. Это поле будет содержать текст, который станет видимым при наведении курсора мыши на текст триггера.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Шаг 6: Добавьте скрытое текстовое поле в документ

Мы добавляем скрытое текстовое поле в коллекцию форм документа.

```csharp
document.Form.Add(floatingField);
```

## Шаг 7: Создайте невидимую кнопку

Мы создаем невидимое поле кнопки, которое будет располагаться поверх фрагмента текста триггера. Это поле кнопки будет иметь действия, связанные с событиями входа и выхода мыши.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Шаг 8: Сохраните документ.

Наконец, сохраняем измененный документ со скрытым текстовым блоком.

```csharp
document. Save(outputFile);
```

### Пример исходного кода для скрытого текстового блока с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Создать образец документа с текстом
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Открыть документ с текстом
Document document = new Document(outputFile);
//Создайте объект TextAbsorber для поиска всех фраз, соответствующих регулярному выражению.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Принять поглотитель для страниц документа
document.Pages.Accept(absorber);
// Получить первый извлеченный фрагмент текста
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Создать скрытое текстовое поле для плавающего текста в указанном прямоугольнике страницы
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Установить текст, который будет отображаться как значение поля
floatingField.Value = "This is the \"floating text field\".";
// Для этого сценария мы рекомендуем сделать поле доступным только для чтения.
floatingField.ReadOnly = true;
// Установите флаг «скрытый», чтобы сделать поле невидимым при открытии документа.
floatingField.Flags |= AnnotationFlags.Hidden;
// Задавать уникальное имя поля не обязательно, но разрешено.
floatingField.PartialName = "FloatingField_1";
// Настройка характеристик внешнего вида поля не является обязательной, но делает его лучше
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Добавить текстовое поле в документ
document.Form.Add(floatingField);
// Создать невидимую кнопку в позиции текстового фрагмента
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Создать новое действие скрытия для указанного поля (аннотации) и флага невидимости.
// (Вы также можете ссылаться на плавающее поле по имени, если вы указали его выше.)
// Добавить действия при входе/выходе мыши в поле невидимой кнопки
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Добавить поле кнопки в документ
document.Form.Add(buttonField);
// Сохранить документ
document.Save(outputFile);
```

## Заключение

В этом уроке вы узнали, как создать скрытый текстовый блок с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству, вы можете создать PDF-документ со скрытым текстовым полем, которое становится видимым при наведении курсора мыши на определенную область. Вы можете настроить внешний вид и поведение скрытого текстового блока в соответствии с вашими требованиями.

### Часто задаваемые вопросы

#### В: Какова цель урока «Скрытый текстовый блок в PDF-файле»?

A: В руководстве "Скрытый текстовый блок в файле PDF" объясняется, как создать скрытый текстовый блок в файле PDF с помощью библиотеки Aspose.PDF для .NET. Скрытый текстовый блок — это плавающий текст, который становится видимым при наведении курсора мыши на определенную область. В этом руководстве представлено пошаговое руководство с использованием исходного кода C#.

#### В: Зачем мне может понадобиться создать скрытый текстовый блок в PDF-файле?

A: Создание скрытого текстового блока может быть полезно для интерактивных PDF-документов, где вы хотите предоставить дополнительную информацию или контекст, который становится видимым только тогда, когда пользователь наводит курсор мыши на определенную область.

#### В: Как настроить каталог документов?

A: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором вы хотите сохранить сгенерированный PDF-файл.

#### В: Как создать образец документа и добавить в него фрагмент текста?

 A: В этом уроке вы используете`Document` класс для создания образца PDF-документа и добавления текстового фрагмента. Этот текстовый фрагмент служит триггером для отображения скрытого текстового блока.

#### В: Как найти фрагмент текста, который активирует скрытый текстовый блок?

 A: В руководстве показано, как использовать`TextFragmentAbsorber` объект для поиска фрагмента текста, который запускает отображение скрытого текстового блока. Он ищет определенную текстовую строку в документе PDF.

#### В: Как создать и настроить скрытое текстовое поле?

 A: Вы создаете`TextBoxField`объект для представления скрытого текстового поля. В руководстве представлен код для установки различных свойств, таких как положение, значение, внешний вид и поведение скрытого текстового поля.

#### В: Как создать невидимую кнопку, связанную со скрытым текстовым блоком?

 A: Невидимое поле кнопки создается с помощью`ButtonField` class. Это поле кнопки располагается поверх фрагмента текста триггера и имеет действия, связанные с событиями входа и выхода мыши. Эти действия управляют видимостью скрытого текстового блока.

#### В: Могу ли я настроить внешний вид скрытого текстового блока и области триггера?

A: Да, вы можете настраивать различные свойства как скрытого текстового поля, так и невидимой кнопки, включая шрифт, цвет, размер и расположение.

#### В: Как сохранить измененный документ со скрытым текстовым блоком?

 A: В руководстве показано, как сохранить измененный документ с помощью`Save` Метод`Document` сорт.