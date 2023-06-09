---
title: حدد المحاذاة
linktitle: حدد المحاذاة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ضبط محاذاة النص بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-stamps-and-watermarks/define-alignment/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية ضبط محاذاة النص في مستند PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإنشاء طابع نصي مركزي في مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن مستند بملف الإدخال
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: تحديد المحاذاة

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك ضبط محاذاة ختم النص. إليك الطريقة:

```csharp
// إنشاء كائن FormattedText بسلسلة المثال
FormattedText text = new FormattedText("This");

// أضف سطرًا جديدًا من النص إلى FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// قم بإنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// حدد المحاذاة الأفقية للمخزن المؤقت للنص كتوسيط
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// حدد المحاذاة الرأسية للمخزن المؤقت للنص كتوسيط
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد المحاذاة الأفقية للنص في TextStamp كتوسيط
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن المخزن المؤقت
stamp. TopMargin = 20;

// أضف كائن الختم إلى الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
```

ينشئ الكود أعلاه مخزنًا مؤقتًا للنص المركزي باستخدام فئة FormattedText لتحديد المحتوى وتعيين المحاذاة الأفقية والرأسية لمخزن النص المؤقت.

## الخطوة 4: احفظ المستند الناتج

بمجرد تعيين محاذاة ختم النص ، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند المحدث
doc.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Define Alignment باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//إنشاء كائن المستند مع ملف الإدخال
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// إنشاء كائن FormattedText بسلسلة نموذجية
FormattedText text = new FormattedText("This");

// إضافة سطر نص جديد إلى FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// قم بإنشاء كائن TextStamp باستخدام FormattedText
TextStamp stamp = new TextStamp(text);

// حدد المحاذاة الأفقية لختم النص كمحاذاة للوسط
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// حدد المحاذاة الرأسية لختم النص كمحاذاة للوسط
stamp.VerticalAlignment = VerticalAlignment.Center;

// حدد محاذاة النص الأفقية لختم النص كمحاذاة للوسط
stamp.TextAlignment = HorizontalAlignment.Center;

// تعيين الهامش العلوي لكائن الطوابع
stamp.TopMargin = 20;

// أضف كائن الختم على الصفحة الأولى من المستند
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// احفظ المستند الذي تم تحديثه
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية ضبط محاذاة النص في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة لإنشاء أختام نصية بمحاذاة مختلفة في مستندات PDF الخاصة بك.
