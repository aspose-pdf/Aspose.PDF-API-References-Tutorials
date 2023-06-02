---
title: CGM в PDF
linktitle: CGM в PDF
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте файлы CGM в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/document-conversion/cgm-to-pdf/
---

В этом руководстве мы шаг за шагом расскажем вам, как преобразовать CGM в PDF с помощью Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и предоставим пошаговые инструкции, которые помогут вам легко следовать.

## Введение

Преобразование файла CGM в PDF позволяет вам обмениваться техническими чертежами и просматривать их повсеместно. С Aspose.PDF для .NET вы можете легко выполнить это преобразование и получить PDF-файлы высокого качества.

## Настройка среды

Прежде чем начать, убедитесь, что ваша среда разработки настроена для работы с Aspose.PDF для .NET. Выполните следующие действия:

1. Установите Visual Studio или другую интегрированную среду разработки, совместимую с разработкой на C#.
2. Создайте новый проект C#.
3. Установите пакет Aspose.PDF для .NET через NuGet, чтобы добавить необходимые зависимости.

## Конвертировать файл CGM в PDF

Чтобы преобразовать файл CGM в PDF, выполните следующие действия:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте экземпляр объекта LoadOption с помощью CGMLoadOption.
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Создание экземпляра объекта Document
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Сохраните полученный PDF-документ
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 В приведенном выше коде обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш файл CGM для преобразования. Этот код загружает файл CGM, используя`CgmLoadOptions` class, затем создает PDF-документ, используя`Document` объект. Наконец, полученный PDF-документ сохраняется.

### Пример исходного кода для CGM в PDF с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создание экземпляра объекта LoadOption с помощью CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Создать объект документа
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Сохраните полученный PDF-документ
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Заключение

Поздравляем! Теперь вы знаете, как преобразовать файл CGM в PDF с помощью Aspose.PDF для .NET. Мы прошли каждый шаг процесса, от инициализации параметров загрузки CGM до сохранения итогового PDF-документа. Используйте предоставленные примеры кода, чтобы интегрировать эту функциональность в свои собственные проекты. Поэкспериментируйте с Aspose.PDF для .NET и откройте для себя расширенные возможности, которые он предлагает для работы с PDF-файлами.
