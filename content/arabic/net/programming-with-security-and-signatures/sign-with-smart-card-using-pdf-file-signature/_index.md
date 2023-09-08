---
title: قم بالتوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
linktitle: قم بالتوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتوقيع ملفات PDF الخاصة بك بشكل آمن باستخدام البطاقة الذكية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
يعد التوقيع الرقمي باستخدام البطاقة الذكية طريقة آمنة لتوقيع ملفات PDF. باستخدام Aspose.PDF for .NET، يمكنك بسهولة توقيع ملف PDF باستخدام بطاقة ذكية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد التوقيع عليه. يستبدل`"YOUR DOCUMENTS DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: قم بتحميل مستند PDF

الآن سنقوم بتحميل مستند PDF للتوقيع عليه باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## الخطوة الرابعة: قم بالتوقيع باستخدام البطاقة الذكية

 في هذه الخطوة سوف نقوم بالتوقيع بالبطاقة الذكية باستخدام`PdfFileSignature` فئة من`Facades`مكتبة. نختار شهادة البطاقة الذكية من مخزن شهادات Windows ونحدد معلومات التوقيع الضرورية. هنا هو الكود المقابل:

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

 أخيرًا، نقوم بالتحقق من توقيع ملف PDF الموقع باستخدام ملف`PdfFileSignature` فصل. نحصل على أسماء التوقيع ونتحقق منها واحدًا تلو الآخر. إذا فشل التوقيع في التحقق، فسيتم طرح استثناء. هنا هو الكود المقابل:

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

### نموذج التعليمات البرمجية المصدر للتوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف Pdf باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// قم بالتوقيع باستخدام اختيار الشهادة في متجر شهادات Windows
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

تهنئة! لديك الآن دليل خطوة بخطوة لتوقيع ملف PDF باستخدام بطاقة ذكية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز لإضافة توقيعات رقمية آمنة إلى مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات التوقيع الرقمي وإدارة الشهادات المتقدمة.

### الأسئلة الشائعة

#### س: لماذا يجب أن أفكر في توقيع ملفات PDF باستخدام البطاقة الذكية؟

ج: إن توقيع ملفات PDF باستخدام البطاقة الذكية يعزز الأمان من خلال ضمان صحة الوثيقة وسلامتها. توفر التوقيعات المستندة إلى البطاقة الذكية مستوى أعلى من الثقة والامتثال.

#### س: كيف يعمل التوقيع الرقمي المعتمد على البطاقة الذكية؟

ج: يتضمن التوقيع الرقمي المعتمد على البطاقة الذكية استخدام مفتاح التشفير المخزن على البطاقة الذكية لإنشاء توقيع رقمي فريد. يتم إرفاق هذا التوقيع بملف PDF، مما يسمح للمستلمين بالتحقق من أصل الوثيقة وسلامتها.

#### س: ما هو دور Aspose.PDF لـ .NET في التوقيع المعتمد على البطاقة الذكية؟

ج: يوفر Aspose.PDF for .NET مجموعة شاملة من الأدوات والمكتبات لتسهيل التوقيع الرقمي القائم على البطاقة الذكية لملفات PDF. إنه يبسط العملية ويضمن التوقيع الآمن للمستندات.

#### س: هل يمكنني اختيار شهادة بطاقة ذكية معينة للتوقيع عليها؟

ج: نعم، يمكنك تحديد شهادة بطاقة ذكية معينة من مخزن شهادات Windows للتوقيع عليها. يسمح لك Aspose.PDF for .NET بدمج اختيار الشهادة في تطبيقك بسلاسة.

#### س: كيف يتعامل كود المصدر المقدم مع التوقيع المعتمد على البطاقة الذكية؟

ج: يوضح الكود المصدري كيفية ربط مستند PDF، واختيار شهادة البطاقة الذكية، وتحديد معلومات التوقيع، وإنشاء توقيع رقمي. كما يوضح كيفية التحقق من صحة التوقيع.

#### س: هل يمكنني تطبيق توقيعات متعددة باستخدام البطاقات الذكية في ملف PDF واحد؟

ج: بالتأكيد، يمكنك تطبيق العديد من التوقيعات المستندة إلى البطاقة الذكية على ملف PDF واحد. كل توقيع فريد من نوعه ويساهم في الأمان العام للمستند.

#### س: ماذا لو فشل التوقيع في التحقق أثناء خطوة التحقق؟

ج: إذا فشل التوقيع في التحقق، فسيتم طرح استثناء يشير إلى أن التوقيع غير صالح. وهذا يضمن قبول التوقيعات الصحيحة والموثوقة فقط.

#### س: هل التوقيع المعتمد على البطاقة الذكية متوافق مع جميع أنواع مستندات PDF؟

ج: نعم، التوقيع المعتمد على البطاقة الذكية متوافق مع جميع أنواع مستندات PDF. يمكنك تطبيق التوقيعات الرقمية على أنواع مختلفة من ملفات PDF، بما في ذلك النماذج والتقارير والمزيد.

#### س: كيف يمكنني معرفة المزيد حول التوقيع الرقمي المتقدم وإدارة الشهادات؟

ج: استكشف وثائق Aspose.PDF الرسمية للحصول على رؤى تفصيلية حول ميزات التوقيع الرقمي المتقدمة وإدارة الشهادات وأفضل الممارسات لضمان أمان المستندات.

#### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لتنفيذ التوقيع المعتمد على البطاقة الذكية؟

ج: للحصول على إرشادات ودعم إضافيين، تواصل مع منتديات مجتمع Aspose.PDF أو ارجع إلى الوثائق للحصول على معلومات شاملة حول التوقيع المعتمد على البطاقة الذكية.