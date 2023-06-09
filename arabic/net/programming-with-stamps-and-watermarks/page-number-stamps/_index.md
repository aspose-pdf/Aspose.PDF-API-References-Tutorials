---
title: طوابع رقم الصفحة
linktitle: طوابع رقم الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة أختام رقم الصفحة إلى مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 160
url: /ar/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة أختام رقم الصفحة إلى مستند PDF باستخدام Aspose.PDF for .NET. سنستخدم الكود المصدري C # المقدم لفتح مستند PDF موجود ، وإنشاء طابع رقم الصفحة ، وتعيين خصائصه ، وإضافته إلى صفحة معينة في مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF الحالي

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء وتكوين طابع ترقيم الصفحة

الآن بعد أن تم تحميل مستند PDF ، يمكننا إنشاء مخزن مؤقت لترقيم الصفحات وتهيئته وفقًا لاحتياجاتنا. إليك الطريقة:

```csharp
// قم بإنشاء مخزن مؤقت لرقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// حدد ما إذا كان المخزن المؤقت في الخلفية أم لا
pageNumberStamp.Background = false;

// تنسيق المخزن المؤقت لترقيم الصفحات
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// الهامش السفلي من المخزن المؤقت لترقيم الصفحات
pageNumberStamp.BottomMargin = 10;

// المحاذاة الأفقية لمخزن ترقيم الصفحات المؤقت
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// رقم بدء ترقيم الصفحات
pageNumberStamp.StartingNumber = 1;

// تعيين خصائص نص المخزن المؤقت لرقم الصفحة
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

يقوم الكود أعلاه بإنشاء طابع رقم الصفحة بخصائص مثل تنسيق رقم الصفحة والهامش السفلي والمحاذاة الأفقية ورقم البداية وخصائص النص.

## الخطوة 4: إضافة طابع رقم الصفحة إلى صفحة معينة

بمجرد تكوين طابع رقم الصفحة ، يمكننا إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف المخزن المؤقت لرقم الصفحة إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

يضيف الكود أعلاه طابع رقم الصفحة إلى الصفحة الأولى من مستند PDF. يمكنك تغيير رقم الصفحة حسب الحاجة.

## الخطوة 5: حفظ مستند PDF المعدل

بمجرد إضافة طابع رقم الصفحة إلى مستند PDF ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF المحرر.

### نموذج التعليمات البرمجية المصدر لطوابع رقم الصفحة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// إنشاء طابع رقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// ما إذا كان الطابع هو الخلفية
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// تعيين خصائص النص
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// أضف طابعًا إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة أختام رقم الصفحة إلى مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص مستندات PDF الخاصة بك عن طريق إضافة أرقام صفحات واضحة وغنية بالمعلومات.
