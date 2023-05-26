---
title: تحديد التقدم
linktitle: تحديد التقدم
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد تقدم عملية تحويل مستند PDF باستخدام Aspose.PDF for .NET مع هذا الدليل خطوة بخطوة ومثال التعليمات البرمجية.
type: docs
weight: 110
url: /ar/net/programming-with-document/determineprogress/
---

يوفر Aspose.PDF for .NET ميزة تسمح لك بتحديد تقدم عملية تحويل مستند PDF. في هذا البرنامج التعليمي ، سنقدم دليلًا تفصيليًا حول كيفية تنفيذ هذه الميزة باستخدام C # و Aspose.PDF لـ .NET.

## الخطوة 1: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الذي تريد تحويله. في هذا البرنامج التعليمي ، سوف نستخدم ملف "AddTOC.pdf". استبدل المسار إلى هذا الملف بالمسار إلى مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## الخطوة 2: إعداد معالج التقدم المخصص

 بعد ذلك ، نحتاج إلى إعداد معالج التقدم المخصص الذي سيتم استدعاؤه أثناء عملية التحويل. في هذا البرنامج التعليمي ، سوف نستخدم ملف`ConversionProgressEventHandler` المندوب المقدم من Aspose.PDF لـ .NET.

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## الخطوة 3: حفظ مستند PDF

 أخيرًا ، نحتاج إلى حفظ مستند PDF باستخدام امتداد`Save()` طريقة`Document`هدف. سنقوم بتمرير معالج التقدم المخصص الذي قمنا بإعداده في الخطوة السابقة كمعامل.

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## الخطوة 4: تنفيذ معالج التقدم

 لتنفيذ معالج التقدم ، نحتاج إلى تحديد طريقة تأخذ معلمة واحدة من النوع`ConversionProgressEventArgs`. سيتم استدعاء هذه الطريقة أثناء عملية التحويل للإبلاغ عن تقدم التحويل.

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### مثال على التعليمات البرمجية المصدر لتحديد التقدم باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## خاتمة

في هذا البرنامج التعليمي ، قدمنا دليلًا تفصيليًا حول كيفية تحديد تقدم عملية تحويل مستند PDF باستخدام Aspose.PDF for .NET. لقد قدمنا أيضًا مثالًا للرمز يمكنك استخدامه كمرجع عند تنفيذ هذه الميزة في تطبيقك الخاص.