---
title: Заполнение арабского текста
linktitle: Заполнение арабского текста
second_title: Aspose.PDF для справочника API .NET
description: Легко заполняйте поля форм PDF арабским текстом с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-forms/arabic-text-filling/
---

В этом уроке мы узнаем, как заполнить поле формы PDF арабским текстом, используя Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет разработчикам программно манипулировать PDF-документами. Мы шаг за шагом проведем вас через весь процесс, объясняя исходный код C#, необходимый для выполнения этой задачи.

## Шаг 1. Загрузите содержимое формы PDF

Во-первых, нам нужно загрузить форму PDF, содержащую поле, которое мы хотим заполнить. Начнем с определения пути к каталогу, в котором находится форма:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Далее мы создаем`FileStream` объект для чтения и записи файла формы:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 Далее мы создаем экземпляр`Document` объект, используя поток, содержащий файл формы:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Шаг 2. Доступ к полю TextBoxField

 Чтобы заполнить поле формы арабским текстом, нам нужно получить доступ к определенному`TextBoxField` поле, которое мы хотим заполнить. В этом примере мы предполагаем, что имя поля — «textbox1». Мы можем получить ссылку на поле с помощью`Form` собственность`pdfDocument` объект:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Шаг 3: Заполните поле формы арабским текстом

 Теперь, когда у нас есть`TextBoxField` ссылка, мы можем присвоить арабский текст его`Value` свойство:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Шаг 4: Сохраните обновленный документ

Наконец, мы сохраняем обновленный документ в новый файл:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

Мы также отображаем сообщение об успешном заполнении арабского текста:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Пример исходного кода для заполнения арабского текста с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить содержимое формы PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//Создание экземпляра документа с потоком, содержащим файл формы
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Получить ссылку на конкретный TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Заполнить поле формы арабским текстом
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы рассмотрели, как заполнить поле формы PDF арабским текстом с помощью Aspose.PDF для .NET. Мы прошли этот процесс шаг за шагом и объяснили соответствующий исходный код C#. Следуя этим инструкциям, вы сможете легко интегрировать функции заполнения текста на арабском языке в свои приложения .NET. Если у вас есть дополнительные вопросы или вам нужна дополнительная информация, не стесняйтесь обращаться в службу поддержки Aspose.PDF или ознакомьтесь с дополнительными ресурсами ниже.