---
title: التوقيع رقميا مع الطابع الزمني
linktitle: التوقيع رقميا مع الطابع الزمني
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إجراء توقيع رقمي باستخدام طابع زمني على ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية التوقيع رقميًا على ملف PDF بطابع زمني باستخدام Aspose.PDF for .NET. يضمن التوقيع الرقمي مع الطابع الزمني أصالة المستند وسلامته ، عن طريق إضافة بصمة إلكترونية مع طابع زمني.

## الخطوة 1: المتطلبات الأساسية

قبل أن تبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:

- المعرفة الأساسية بلغة البرمجة C #
- تثبيت Visual Studio على جهازك
- تثبيت مكتبة Aspose.PDF لـ .NET

## الخطوة 2: إعداد البيئة

للبدء ، اتبع هذه الخطوات لإعداد بيئة التطوير الخاصة بك:

1. افتح Visual Studio وأنشئ مشروع C # جديد.
2. قم باستيراد مساحات الأسماء المطلوبة إلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## الخطوة 3: التوقيع الرقمي مع الطابع الزمني

الخطوة الأولى هي تنفيذ التوقيع الرقمي بطابع زمني على ملف PDF. يوضح الكود المقدم كيفية تحقيق هذا التوقيع باستخدام Aspose.PDF for .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

يقوم هذا الرمز بتحميل ملف PDF ، وإنشاء توقيع رقمي مع طابع زمني باستخدام ملف PFX (مفتاح خاص) ومعلمات الطابع الزمني المحددة. ثم يتم إضافة التوقيع إلى ملف PDF وحفظه مع اللاحقة "_خارج".

### عينة من التعليمات البرمجية المصدر للتوقيع رقميًا باستخدام طابع زمني باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // يمكن حذف المستخدم / كلمة المرور
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//قم بإنشاء أي من أنواع التوقيع الثلاثة
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// حفظ ملف PDF الناتج
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## خاتمة

تهنئة ! لقد نجحت في تنفيذ توقيع رقمي بطابع زمني على ملف PDF باستخدام Aspose.PDF لـ .NET. غطى هذا البرنامج التعليمي العملية خطوة بخطوة من إنشاء التوقيع إلى حفظ ملف PDF المحدث. يمكنك الآن استخدام هذه الميزة لإضافة توقيعات رقمية مع طابع زمني إلى ملفات PDF الخاصة بك.