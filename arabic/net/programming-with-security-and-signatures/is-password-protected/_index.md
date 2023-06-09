---
title: محمي بكلمة مرور
linktitle: محمي بكلمة مرور
second_title: Aspose.PDF لمرجع .NET API
description: تحقق بسهولة مما إذا كان مستند PDF محميًا بكلمة مرور باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-security-and-signatures/is-password-protected/
---

غالبًا ما يكون من المهم معرفة ما إذا كان مستند PDF محميًا بكلمة مرور قبل معالجته. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة التحقق مما إذا كان مستند PDF محميًا باستخدام التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد التحقق منه. يستبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: تحميل مستند PDF المصدر

سنقوم الآن بتحميل مستند PDF المصدر والتحقق مما إذا كان محميًا بكلمة مرور باستخدام الكود التالي:

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## الخطوة 4: تحقق مما إذا كان ملف PDF محميًا

 في هذه الخطوة ، سنحدد ما إذا كان مستند PDF محميًا بكلمة مرور باستخدام امتداد`IsEncrypted` طريقة`PdfFileInfo` هدف. هذا هو الكود المقابل:

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## الخطوة 5: عرض حالة التشفير

 أخيرًا ، يمكننا عرض حالة التشفير الحالية لملف PDF باستخدام امتداد`Console.WriteLine` طريقة. هذا هو الكود المقابل:

```csharp
Console.WriteLine(encrypted.ToString());
```

ستشير الرسالة المعروضة إلى ما إذا كان مستند PDF محميًا بكلمة مرور أم لا.

### عينة من التعليمات البرمجية المصدر لـ "محمية بكلمة مرور" باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF المصدر
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//حدد أن ملف PDF المصدر مشفر بكلمة مرور
bool encrypted = fileInfo.IsEncrypted;
// يعرض MessageBox الحالة الحالية المتعلقة بتشفير PDf
Console.WriteLine(encrypted.ToString());
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة للتحقق مما إذا كانت وثيقة PDF محمية بكلمة مرور باستخدام Aspose.PDF for .NET. يمكنك دمج هذا الرمز في مشاريعك الخاصة لإجراء عمليات محددة بناءً على حالة حماية ملف PDF.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات أمان مستندات PDF المتقدمة وإدارة كلمة المرور.