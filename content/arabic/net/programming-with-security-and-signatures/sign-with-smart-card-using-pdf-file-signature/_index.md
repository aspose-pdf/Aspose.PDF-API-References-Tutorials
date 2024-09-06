---
title: التوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
linktitle: التوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بتوقيع ملفات PDF الخاصة بك بشكل آمن باستخدام بطاقة ذكية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
يعد التوقيع الرقمي باستخدام البطاقة الذكية طريقة آمنة لتوقيع ملفات PDF. باستخدام Aspose.PDF for .NET، يمكنك بسهولة توقيع ملف PDF باستخدام بطاقة ذكية باتباع التعليمات البرمجية المصدرية التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، عليك استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي تعليمات الاستيراد اللازمة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد توقيعه. استبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: تحميل مستند PDF

الآن سوف نقوم بتحميل مستند PDF المراد توقيعه باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## الخطوة 4: قم بالتوقيع باستخدام البطاقة الذكية

 في هذه الخطوة سنقوم بالتوقيع بالبطاقة الذكية باستخدام`PdfFileSignature` الصف من`Facades`المكتبة. نختار شهادة البطاقة الذكية من مخزن شهادات Windows ونحدد معلومات التوقيع اللازمة. هذا هو الكود المقابل:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // حدد الشهادة في المتجر
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## الخطوة 5: التحقق من التوقيع

 وأخيرًا، نتحقق من توقيع ملف PDF الموقّع باستخدام`PdfFileSignature` الصف. نحصل على أسماء التوقيع ونتحقق منها واحدًا تلو الآخر. إذا فشل أحد التوقيعات في التحقق، يتم طرح استثناء. هذا هو الكود المقابل:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### عينة من كود المصدر للتوقيع باستخدام البطاقة الذكية باستخدام ملف Pdf للتوقيع باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// التوقيع باستخدام اختيار الشهادة في مخزن شهادات Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// اختيار الشهادة يدويًا في المتجر
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## خاتمة

تهانينا! لديك الآن دليل خطوة بخطوة لتوقيع ملف PDF باستخدام بطاقة ذكية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الكود لإضافة توقيعات رقمية آمنة إلى مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية للحصول على مزيد من المعلومات حول ميزات التوقيع الرقمي المتقدم وإدارة الشهادات.

### الأسئلة الشائعة

#### س: لماذا يجب أن أفكر في توقيع ملفات PDF باستخدام بطاقة ذكية؟

ج: إن التوقيع على ملفات PDF باستخدام بطاقة ذكية يعزز الأمان من خلال ضمان صحة وسلامة المستند. توفر التوقيعات المستندة إلى البطاقة الذكية مستوى أعلى من الثقة والامتثال.

#### س: كيف يعمل التوقيع الرقمي المبني على البطاقة الذكية؟

أ: يتضمن التوقيع الرقمي المستند إلى البطاقة الذكية استخدام مفتاح تشفير مخزن على بطاقة ذكية لإنشاء توقيع رقمي فريد. يتم إرفاق هذا التوقيع بملف PDF، مما يسمح للمستلمين بالتحقق من أصل المستند وسلامته.

#### س: ما هو دور Aspose.PDF لـ .NET في التوقيع المبني على البطاقة الذكية؟

ج: يوفر Aspose.PDF for .NET مجموعة شاملة من الأدوات والمكتبات لتسهيل التوقيع الرقمي على ملفات PDF باستخدام البطاقات الذكية. فهو يبسط العملية ويضمن توقيع المستندات بشكل آمن.

#### س: هل يمكنني اختيار شهادة بطاقة ذكية محددة للتوقيع؟

ج: نعم، يمكنك تحديد شهادة بطاقة ذكية معينة من مخزن شهادات Windows للتوقيع عليها. يتيح لك Aspose.PDF for .NET دمج تحديد الشهادة في تطبيقك بسلاسة.

#### س: كيف يتعامل كود المصدر المقدم مع التوقيع المستند إلى البطاقة الذكية؟

ج: يوضح الكود المصدر كيفية ربط مستند PDF، واختيار شهادة بطاقة ذكية، وتحديد معلومات التوقيع، وإنشاء توقيع رقمي. كما يوضح كيفية التحقق من صحة التوقيع.

#### س: هل يمكنني تطبيق توقيعات متعددة باستخدام البطاقات الذكية في ملف PDF واحد؟

ج: بالتأكيد، يمكنك تطبيق عدة توقيعات تعتمد على بطاقات ذكية على ملف PDF واحد. كل توقيع فريد من نوعه ويساهم في تأمين المستند بشكل عام.

#### س: ماذا لو فشل التوقيع في التحقق أثناء خطوة التحقق؟

ج: إذا فشل التوقيع في التحقق، يتم طرح استثناء يشير إلى أن التوقيع غير صالح. وهذا يضمن قبول التوقيعات الصالحة والموثوقة فقط.

#### س: هل التوقيع المعتمد على البطاقة الذكية متوافق مع جميع أنواع مستندات PDF؟

ج: نعم، التوقيع المستند إلى البطاقة الذكية متوافق مع جميع أنواع مستندات PDF. يمكنك تطبيق التوقيعات الرقمية على أنواع مختلفة من ملفات PDF، بما في ذلك النماذج والتقارير والمزيد.

#### س: كيف يمكنني معرفة المزيد حول إدارة التوقيع الرقمي والشهادات المتقدمة؟

أ: استكشف وثائق Aspose.PDF الرسمية للحصول على رؤى تفصيلية حول ميزات التوقيع الرقمي المتقدمة وإدارة الشهادات وأفضل الممارسات لضمان أمان المستندات.

#### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لتنفيذ التوقيع المبني على البطاقة الذكية؟

ج: للحصول على إرشادات ودعم إضافيين، تواصل مع منتديات مجتمع Aspose.PDF أو راجع الوثائق للحصول على معلومات شاملة حول التوقيع المستند إلى البطاقة الذكية.