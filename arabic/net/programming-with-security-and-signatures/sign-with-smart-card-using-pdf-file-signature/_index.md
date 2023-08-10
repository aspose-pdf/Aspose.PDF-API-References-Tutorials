---
title: التوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
linktitle: التوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتسجيل ملفات PDF الخاصة بك بأمان باستخدام بطاقة ذكية باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
يعد التوقيع الرقمي باستخدام البطاقة الذكية طريقة آمنة لتوقيع ملفات PDF. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة تسجيل ملف PDF باستخدام بطاقة ذكية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد توقيعه. يستبدل`"YOUR DOCUMENTS DIRECTORY"`في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: قم بتحميل مستند PDF

سنقوم الآن بتحميل مستند PDF ليتم توقيعه باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## الخطوة 4: قم بالتوقيع بالبطاقة الذكية

 في هذه الخطوة ، سنقوم بالتوقيع بالبطاقة الذكية باستخدام ملف`PdfFileSignature` فئة من`Facades`مكتبة. نختار شهادة البطاقة الذكية من مخزن شهادات Windows ونحدد معلومات التوقيع الضرورية. هذا هو الكود المقابل:

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

 أخيرًا ، نتحقق من توقيع ملف PDF الموقع باستخدام امتداد`PdfFileSignature` فصل. نحصل على أسماء التوقيعات ونتحقق منها واحدة تلو الأخرى. إذا فشل التحقق من التوقيع ، يتم طرح استثناء. هذا هو الكود المقابل:

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

### نموذج التعليمات البرمجية المصدر للتوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف Pdf باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// قم بالتوقيع مع تحديد الشهادة في مخزن شهادات Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// اختر الشهادة يدويًا في المتجر
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

تهنئة! لديك الآن دليل تفصيلي خطوة بخطوة لتوقيع ملف PDF باستخدام بطاقة ذكية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإضافة توقيعات رقمية آمنة إلى مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات إدارة الشهادات والتوقيع الرقمي المتقدمة.

### التعليمات

#### س: لماذا يجب علي التفكير في توقيع ملفات PDF ببطاقة ذكية؟

ج: إن توقيع ملفات PDF ببطاقة ذكية يعزز الأمان من خلال ضمان مصداقية الوثيقة وسلامتها. توفر التوقيعات المستندة إلى البطاقة الذكية مستوى أعلى من الثقة والامتثال.

#### س: كيف يعمل التوقيع الرقمي المستند إلى البطاقة الذكية؟

ج: يتضمن التوقيع الرقمي المستند إلى البطاقة الذكية استخدام مفتاح تشفير مخزن على بطاقة ذكية لإنشاء توقيع رقمي فريد. يتم إرفاق هذا التوقيع بملف PDF ، مما يسمح للمستلمين بالتحقق من أصل المستند وسلامته.

#### س: ما هو دور Aspose.PDF لـ .NET في التوقيع المستند إلى البطاقة الذكية؟

ج: يوفر Aspose.PDF for .NET مجموعة شاملة من الأدوات والمكتبات لتسهيل التوقيع الرقمي المستند إلى البطاقة الذكية لملفات PDF. إنه يبسط العملية ويضمن توقيعًا آمنًا للمستند.

#### س: هل يمكنني اختيار شهادة بطاقة ذكية معينة للتوقيع؟

ج: نعم ، يمكنك تحديد شهادة بطاقة ذكية معينة من مخزن شهادات Windows للتوقيع. يسمح لك Aspose.PDF for .NET بدمج اختيار الشهادة بسلاسة في تطبيقك.

#### س: كيف يتعامل كود المصدر المقدم مع التوقيع المستند إلى البطاقة الذكية؟

ج: يوضح كود المصدر كيفية ربط مستند PDF وتحديد شهادة البطاقة الذكية وتحديد معلومات التوقيع وإنشاء توقيع رقمي. كما يوضح كيفية التحقق من صحة التوقيع.

#### س: هل يمكنني تطبيق عدة توقيعات باستخدام البطاقات الذكية في ملف PDF واحد؟

ج: بالتأكيد ، يمكنك تطبيق عدة تواقيع قائمة على البطاقة الذكية على ملف PDF واحد. كل توقيع فريد ويساهم في الأمان العام للمستند.

#### س: ماذا لو فشل التوقيع في التحقق أثناء خطوة التحقق؟

ج: إذا فشل التوقيع في التحقق ، يتم طرح استثناء ، يشير إلى أن التوقيع غير صالح. هذا يضمن قبول التوقيعات الصالحة والموثوقة فقط.

#### س: هل التوقيع المستند إلى البطاقة الذكية متوافق مع جميع أنواع مستندات PDF؟

ج: نعم ، التوقيع المستند إلى البطاقة الذكية متوافق مع جميع أنواع مستندات PDF. يمكنك تطبيق التوقيعات الرقمية على أنواع مختلفة من ملفات PDF ، بما في ذلك النماذج والتقارير والمزيد.

#### س: كيف يمكنني معرفة المزيد حول إدارة الشهادات والتوقيع الرقمي المتقدم؟

ج: استكشف وثائق Aspose.PDF الرسمية للحصول على رؤى تفصيلية حول ميزات التوقيع الرقمي المتقدمة وإدارة الشهادات وأفضل الممارسات لضمان أمان المستندات.

#### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لتنفيذ التوقيع المستند إلى البطاقة الذكية؟

ج: للحصول على إرشادات ودعم إضافيين ، يمكنك الوصول إلى منتديات مجتمع Aspose.PDF أو الرجوع إلى الوثائق للحصول على معلومات شاملة حول التوقيع المستند إلى البطاقة الذكية.