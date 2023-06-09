---
title: تشفير
linktitle: تشفير
second_title: Aspose.PDF لمرجع .NET API
description: تشفير ملفات PDF الخاصة بك بأمان باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/programming-with-security-and-signatures/encrypt/
---

يعد تشفير ملفات PDF إجراءً أمنيًا مهمًا لحماية المعلومات السرية. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة تشفير ملفات PDF باستخدام كود المصدر التالي:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF المراد تشفيره. يستبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

بعد ذلك ، تحتاج إلى فتح مستند PDF الذي تريد تشفيره. استخدم الكود التالي لتحميل المستند:

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## الخطوة 4: تشفير ملف PDF

يمكنك الآن تشفير ملف PDF باستخدام الكود التالي:

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

في هذا المثال ، نستخدم خوارزمية تشفير RC4x128 مع كلمات مرور "المستخدم" و "المالك". يمكنك تغيير هذه الإعدادات حسب الحاجة.

## الخطوة 5: نسخ احتياطي لملفات PDF المشفرة

أخيرًا ، يمكنك حفظ ملف PDF المشفر في الموقع المحدد باستخدام الكود التالي:

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

تأكد من تحديد المسار المطلوب واسم الملف لملف PDF المشفر.

### نموذج التعليمات البرمجية المصدر لـ Encrypt باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document document = new Document(dataDir+ "Encrypt.pdf");
// تشفير PDF
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// احفظ ملف PDF المحدث
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لديك الآن نظرة عامة خطوة بخطوة على تشفير ملفات PDF باستخدام Aspose.PDF for .NET. يمكنك تضمين هذا الرمز في مشاريعك الخاصة لتأمين ملفات PDF الخاصة بك بسهولة.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات التشفير والأمان المتقدمة.