---
title: Скрытый текстовый блок
linktitle: Скрытый текстовый блок
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как создавать скрытые текстовые блоки в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 230
url: /ru/net/programming-with-text/hidden-text-block/
---

В этом руководстве мы объясним, как создать скрытый текстовый блок с помощью библиотеки Aspose.PDF для .NET. Скрытый текстовый блок — это плавающий текст, который становится видимым при наведении курсора мыши на определенную область. Мы пройдем пошаговый процесс создания скрытого текстового блока, используя предоставленный исходный код C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором вы хотите сохранить сгенерированный файл PDF. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к нужному каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте образец документа

На этом шаге мы создаем образец PDF-документа и добавляем в него текстовый фрагмент. Текстовый фрагмент будет служить триггером для отображения скрытого текстового блока.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Шаг 3: Откройте документ

 Теперь мы открываем ранее созданный документ с помощью`Document` сорт.

```csharp
Document document = new Document(outputFile);
```

## Шаг 4: Найдите фрагмент текста

 Мы используем`TextFragmentAbsorber` объект, чтобы найти фрагмент текста, который вызовет отображение скрытого текстового блока. В данном случае мы ищем точный текст «Переместите сюда курсор мыши, чтобы отобразить плавающий текст».

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Шаг 5: Создайте скрытое текстовое поле

 Мы создаем`TextBoxField`объект для представления скрытого текстового поля. Это поле будет содержать текст, который становится видимым при наведении курсора мыши на текст триггера.

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

## Шаг 6: добавьте скрытое текстовое поле в документ

Мы добавляем скрытое текстовое поле в коллекцию форм документа.

```csharp
document.Form.Add(floatingField);
```

## Шаг 7: создайте невидимую кнопку

Мы создаем невидимое поле кнопки, которое будет располагаться поверх фрагмента текста триггера. Это поле кнопки будет иметь действия, связанные с событиями входа и выхода мыши.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Шаг 8: Сохраните документ

Наконец, мы сохраняем измененный документ со скрытым текстовым блоком.

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
// Создайте объект TextAbsorber, чтобы найти все фразы, соответствующие регулярному выражению.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Примите абсорбер для страниц документа
document.Pages.Accept(absorber);
// Получить первый извлеченный фрагмент текста
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Создать скрытое текстовое поле для плавающего текста в указанном прямоугольнике страницы
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Установить текст, который будет отображаться как значение поля
floatingField.Value = "This is the \"floating text field\".";
// Мы рекомендуем сделать поле «только для чтения» для этого сценария
floatingField.ReadOnly = true;
// Установите флаг «скрытый», чтобы сделать поле невидимым при открытии документа
floatingField.Flags |= AnnotationFlags.Hidden;
//Установка уникального имени поля необязательна, но разрешена
floatingField.PartialName = "FloatingField_1";
// Настройка характеристик внешнего вида поля не обязательна, но делает ее лучше
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Добавить текстовое поле в документ
document.Form.Add(floatingField);
//Создать невидимую кнопку на позиции текстового фрагмента
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

В этом руководстве вы узнали, как создать скрытый текстовый блок с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству, вы можете создать PDF-документ со скрытым текстовым полем, которое становится видимым при наведении курсора мыши на определенную область. Вы можете настроить внешний вид и поведение скрытого текстового блока в соответствии с вашими требованиями.