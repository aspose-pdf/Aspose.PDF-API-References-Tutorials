---
title: تسجيل الدخول رقميا في ملف PDF
linktitle: تسجيل الدخول رقميا في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تسجيل الدخول رقميًا إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-security-and-signatures/digitally-sign/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية تسجيل الدخول رقميًا إلى ملف PDF باستخدام Aspose.PDF لـ .NET. يضمن التوقيع الرقمي صحة الوثيقة وسلامتها، وذلك عن طريق إضافة بصمة إلكترونية فريدة.

## الخطوة 1: المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#
- تثبيت Visual Studio على جهازك
- تم تثبيت مكتبة Aspose.PDF لـ .NET

## الخطوة 2: إعداد البيئة

للبدء، اتبع الخطوات التالية لإعداد بيئة التطوير الخاصة بك:

1. افتح Visual Studio وقم بإنشاء مشروع C# جديد.
2. قم باستيراد مساحات الأسماء المطلوبة إلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## الخطوة 3: التوقيع الرقمي

الخطوة الأولى هي التوقيع رقميًا على ملف PDF. يوضح الكود المقدم كيفية عمل توقيع رقمي باستخدام Aspose.PDF لـ .NET.

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

يقوم هذا الرمز بتحميل ملف PDF، وإنشاء توقيع رقمي بمظهر محدد، ثم حفظ ملف PDF مع التوقيع المضاف.

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
                         // قم بعمل ما
                     }
                 }
             }
         }
     }
}
```

يتحقق هذا الرمز من التوقيع الأول لملف PDF وينفذ إجراءات إضافية إذا كان التوقيع معتمدًا وله أذونات محددة.

### نموذج التعليمات البرمجية المصدر للتوقيع الرقمي باستخدام Aspose.PDF لـ .NET 
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
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // استخدم كائنات PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// ضبط مظهر التوقيع
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// قم بإنشاء أي من أنواع التوقيع الثلاثة
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
			if (sigNames.Count > 0) // أي التوقيعات؟
			{
				if (signature.VerifySigned(sigNames[0] as string)) // التحقق من أول واحد
				{
					if (signature.IsCertified) // معتمد؟
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // الحصول على إذن الوصول
						{
							// قم بعمل ما
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

تهنئة ! لقد نجحت في تنفيذ توقيع رقمي على ملف PDF باستخدام Aspose.PDF لـ .NET. يغطي هذا البرنامج التعليمي العملية خطوة بخطوة، بدءًا من إضافة التوقيع الرقمي وحتى التحقق من صحته. يمكنك الآن استخدام هذه الميزة لتأمين ملفات PDF الخاصة بك بالتوقيعات الرقمية.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية التوقيع الرقمي على ملف PDF باستخدام Aspose.PDF لـ .NET. تضيف التوقيعات الرقمية بصمة إلكترونية لضمان صحة الوثيقة وسلامتها.

#### س: ما هي المتطلبات الأساسية المطلوبة قبل البدء؟

ج: قبل أن تبدأ، تأكد من أن لديك الفهم الأساسي للغة البرمجة C#، ومن تثبيت Visual Studio، ومن تثبيت مكتبة Aspose.PDF لـ .NET.

#### س: كيف أقوم بإعداد بيئة التطوير؟

ج: اتبع الخطوات المتوفرة لإعداد بيئة التطوير الخاصة بك، بما في ذلك إنشاء مشروع C# جديد في Visual Studio، واستيراد مساحات الأسماء المطلوبة.

#### س: كيف يمكنني إضافة توقيع رقمي إلى ملف PDF؟

 ج: يوضح نموذج التعليمات البرمجية المقدم كيفية تحميل ملف PDF وإنشاء توقيع رقمي وتحديد المظهر وحفظ ملف PDF الموقع. تتم إضافة التوقيع الرقمي باستخدام`Certify` طريقة`PdfFileSignature` هدف.

#### س: كيف يمكنني التحقق من صحة التوقيع الرقمي؟

ج: بعد إضافة التوقيع الرقمي، يمكنك استخدام نموذج التعليمات البرمجية للتحقق من صحة التوقيع. يتحقق مما إذا كان التوقيع معتمدًا ولديه أذونات وصول محددة.

####  س: ماذا يفعل`PKCS7` object represent?

 ج: ال`PKCS7` يتم استخدام الكائن لتوفير وظيفة التشفير للتوقيعات الرقمية. يتم استخدامه لإنشاء التوقيع الرقمي في نموذج التعليمات البرمجية المقدم.

#### س: هل يمكنني تخصيص مظهر التوقيع الرقمي؟

 ج: نعم، يمكنك تخصيص مظهر التوقيع الرقمي عن طريق تحديد المسار إلى الصورة في الملف`SignatureAppearance` ملكية`PdfFileSignature` هدف.

#### س: ماذا يحدث إذا كان التوقيع غير صالح؟

ج: إذا كان التوقيع غير صالح، فستفشل عملية التحقق، ولن يتم تنفيذ الإجراءات المقابلة داخل كتلة رمز التحقق.

#### س: كيف يمكنني ضمان أمان التوقيعات الرقمية الخاصة بي؟

ج: التوقيعات الرقمية آمنة حسب التصميم وتستخدم تقنيات التشفير لضمان الأصالة والنزاهة. تأكد من الحفاظ على أمان مفتاحك الخاص واتباع أفضل الممارسات للتعامل مع التوقيعات الرقمية.

#### س: هل يمكنني إضافة توقيعات رقمية متعددة إلى ملف PDF؟

 ج: نعم، يمكنك إضافة توقيعات رقمية متعددة إلى ملف PDF باستخدام`PdfFileSignature` أشياء`Sign` أو`Certify` طُرق. سيكون لكل توقيع مظهره وتكوينه الخاص.