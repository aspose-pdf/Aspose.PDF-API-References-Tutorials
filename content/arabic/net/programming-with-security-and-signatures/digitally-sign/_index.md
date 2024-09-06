---
title: تسجيل الدخول رقميا إلى ملف PDF
linktitle: تسجيل الدخول رقميا إلى ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تسجيل الدخول رقميًا إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-security-and-signatures/digitally-sign/
---
في هذا البرنامج التعليمي، سنوضح لك عملية التوقيع الرقمي على ملف PDF باستخدام Aspose.PDF لـ .NET. يضمن التوقيع الرقمي صحة وسلامة المستند، من خلال إضافة بصمة إلكترونية فريدة.

## الخطوة 1: المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#
- تثبيت Visual Studio على جهازك
- تم تثبيت مكتبة Aspose.PDF لـ .NET

## الخطوة 2: إعداد البيئة

للبدء، اتبع الخطوات التالية لإعداد بيئة التطوير الخاصة بك:

1. افتح Visual Studio وقم بإنشاء مشروع C# جديد.
2. استيراد المساحات المطلوبة إلى ملف الكود الخاص بك:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## الخطوة 3: التوقيع الرقمي

الخطوة الأولى هي التوقيع رقميًا على ملف PDF. يوضح الكود المقدم كيفية إنشاء توقيع رقمي باستخدام Aspose.PDF لـ .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

يقوم هذا الكود بتحميل ملف PDF، ويقوم بإنشاء توقيع رقمي بمظهر محدد، ثم يحفظ ملف PDF بالتوقيع المضاف.

## الخطوة 4: التحقق من التوقيع

بعد إضافة التوقيع الرقمي، يمكنك التحقق مما إذا كان ملف PDF يحتوي على توقيع صالح.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // افعل شيئا
                     }
                 }
             }
         }
     }
}
```

يتحقق هذا الرمز من التوقيع الأول لملف PDF ويقوم بإجراءات إضافية إذا كان التوقيع معتمدًا ولديه أذونات محددة.

### عينة من كود المصدر للتوقيع الرقمي باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // استخدام كائنات PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// تعيين مظهر التوقيع
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// إنشاء أي من أنواع التوقيع الثلاثة
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// حفظ ملف PDF الناتج
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // أي توقيعات؟
			{
				if (signature.VerifySigned(sigNames[0] as string)) // التحقق من الأول
				{
					if (signature.IsCertified) // معتمد؟
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // الحصول على إذن الوصول
						{
							// افعل شيئا
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهانينا! لقد نجحت في تنفيذ توقيع رقمي على ملف PDF باستخدام Aspose.PDF for .NET. تناول هذا البرنامج التعليمي العملية خطوة بخطوة، من إضافة التوقيع الرقمي إلى التحقق من صحته. يمكنك الآن استخدام هذه الميزة لتأمين ملفات PDF الخاصة بك بالتوقيعات الرقمية.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية التوقيع الرقمي على ملف PDF باستخدام Aspose.PDF لـ .NET. تضيف التوقيعات الرقمية بصمة إلكترونية لضمان صحة وسلامة المستند.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من أن لديك فهمًا أساسيًا للغة البرمجة C#، وأنك قمت بتثبيت Visual Studio، وأنك قمت بتثبيت مكتبة Aspose.PDF لـ .NET.

#### س: كيف أقوم بإعداد بيئة التطوير؟

أ: اتبع الخطوات المقدمة لإعداد بيئة التطوير الخاصة بك، بما في ذلك إنشاء مشروع C# جديد في Visual Studio، واستيراد المساحات الأساسية المطلوبة.

#### س: كيف أضيف توقيعًا رقميًا إلى ملف PDF؟

 أ: يوضح رمز العينة المقدم كيفية تحميل ملف PDF وإنشاء توقيع رقمي وتحديد المظهر وحفظ ملف PDF الموقّع. تتم إضافة التوقيع الرقمي باستخدام`Certify` طريقة`PdfFileSignature` هدف.

#### س: كيف يمكنني التحقق من صحة التوقيع الرقمي؟

ج: بعد إضافة التوقيع الرقمي، يمكنك استخدام الكود النموذجي للتحقق من صحة التوقيع. فهو يتحقق مما إذا كان التوقيع معتمدًا ويتمتع بأذونات وصول محددة.

####  س: ماذا يعني`PKCS7` object represent?

 أ: ال`PKCS7` يتم استخدام الكائن لتوفير وظيفة التشفير للتوقيعات الرقمية. يتم استخدامه لإنشاء التوقيع الرقمي في الكود النموذجي المقدم.

#### س: هل يمكنني تخصيص مظهر التوقيع الرقمي؟

 ج: نعم، يمكنك تخصيص مظهر التوقيع الرقمي من خلال تحديد المسار إلى الصورة في`SignatureAppearance` ممتلكات`PdfFileSignature` هدف.

#### س: ماذا يحدث إذا كان التوقيع غير صالح؟

ج: إذا لم يكن التوقيع صالحًا، فستفشل عملية التحقق، ولن يتم تنفيذ الإجراءات المقابلة داخل كتلة رمز التحقق.

#### س: كيف يمكنني ضمان أمان توقيعاتي الرقمية؟

ج: التوقيعات الرقمية آمنة من حيث التصميم وتستخدم تقنيات التشفير لضمان الأصالة والسلامة. تأكد من الحفاظ على مفتاحك الخاص آمنًا واتباع أفضل الممارسات للتعامل مع التوقيعات الرقمية.

#### س: هل يمكنني إضافة توقيعات رقمية متعددة إلى ملف PDF؟

 ج: نعم، يمكنك إضافة توقيعات رقمية متعددة إلى ملف PDF باستخدام`PdfFileSignature` أشياء`Sign` أو`Certify` الأساليب. سيكون لكل توقيع مظهره وتكوينه الخاص.