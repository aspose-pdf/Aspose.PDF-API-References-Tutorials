---
title: قم بالتوقيع باستخدام البطاقة الذكية باستخدام حقل التوقيع
linktitle: قم بالتوقيع باستخدام البطاقة الذكية باستخدام حقل التوقيع
second_title: Aspose.PDF لمرجع .NET API
description: قم بتوقيع ملفات PDF الخاصة بك بشكل آمن باستخدام البطاقة الذكية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
يعد التوقيع الرقمي باستخدام البطاقة الذكية طريقة آمنة لتوقيع ملفات PDF. باستخدام Aspose.PDF for .NET، يمكنك بسهولة توقيع ملف PDF باستخدام حقل التوقيع والبطاقة الذكية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد التوقيع عليه. يستبدل`"YOUR DOCUMENTS DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: انسخ وافتح مستند PDF

الآن سنقوم بنسخ وفتح وثيقة PDF للتوقيع عليها باستخدام الكود التالي:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // إنشاء حقل التوقيع
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // حدد الشهادة في المتجر
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // قم بإنشاء توقيع خارجي بالمعلومات اللازمة
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## الخطوة 4: التحقق من التوقيع

 أخيرًا، نقوم بالتحقق من توقيع ملف PDF الموقع باستخدام ملف`PdfFileSignature` فصل. نحصل على أسماء التوقيع ونتحقق منها واحدًا تلو الآخر. إذا فشل التوقيع في التحقق، فسيتم طرح استثناء. هنا هو الكود المقابل:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### نموذج التعليمات البرمجية المصدر للتسجيل باستخدام البطاقة الذكية باستخدام حقل التوقيع باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// قم بالتوقيع باستخدام اختيار الشهادة في متجر شهادات Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// اختيار الشهادة يدويًا في المتجر
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

تهنئة ! لديك الآن دليل خطوة بخطوة لتوقيع ملف PDF باستخدام بطاقة ذكية باستخدام حقل التوقيع باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز لإضافة توقيعات رقمية آمنة إلى مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات التوقيع الرقمي وإدارة الشهادات المتقدمة.

### الأسئلة الشائعة

#### س: ما فائدة استخدام حقل التوقيع للتوقيع الرقمي بالبطاقة الذكية؟

ج: يوفر استخدام حقل التوقيع للتوقيع الرقمي باستخدام البطاقة الذكية منطقة مخصصة داخل ملف PDF حيث يتم تطبيق التوقيع. وهذا يعزز وضوح الوثيقة ويضمن صحة التوقيع.

#### س: كيف يقوم Aspose.PDF لمكتبة .NET بتسهيل التوقيع الرقمي المعتمد على البطاقة الذكية باستخدام حقل التوقيع؟

ج: يعمل Aspose.PDF for .NET على تبسيط عملية إنشاء حقل التوقيع، واختيار شهادة البطاقة الذكية، وتطبيق التوقيع الرقمي على منطقة معينة داخل مستند PDF.

#### س: ما سبب أهمية اختيار شهادة معينة للتوقيع المعتمد على البطاقة الذكية؟

ج: يتيح لك تحديد شهادة معينة تحديد هوية المُوقع بشكل فريد والتأكد من سلامة التوقيع. ويساعد ذلك في بناء الثقة والامتثال لمعايير التوقيع الرقمي.

#### س: كيف يتعامل كود المصدر المقدم مع عملية التوقيع المعتمدة على البطاقة الذكية مع حقل التوقيع؟

ج: يوضح الكود المصدري كيفية إنشاء حقل توقيع، وتحديد شهادة بطاقة ذكية، وتطبيق توقيع رقمي بمعلومات توقيع محددة. كما يوضح كيفية التحقق من صحة التوقيع.

#### س: هل يمكنني تخصيص مظهر حقل التوقيع؟

ج: نعم، يمكنك تخصيص مظهر حقل التوقيع، مثل حجمه وموضعه وتمثيله المرئي، ليتوافق مع تخطيط المستند.

#### س: ماذا يحدث إذا فشل التحقق من التوقيع أثناء خطوة التحقق؟

ج: إذا فشل التوقيع في التحقق، فسيتم طرح استثناء يشير إلى أن التوقيع غير صالح. وهذا يضمن قبول التوقيعات الصحيحة والموثوقة فقط.

#### س: هل يمكنني تطبيق حقول توقيع متعددة وتوقيعات مستندة إلى البطاقة الذكية على مستند PDF واحد؟

ج: بالتأكيد، يمكنك تطبيق حقول توقيع متعددة وتوقيعات مستندة إلى البطاقة الذكية على مناطق مختلفة من نفس مستند PDF، مما يوفر طبقات متعددة من الأمان.

#### س: كيف يؤدي استخدام حقل التوقيع إلى تحسين عملية توقيع المستند بشكل عام؟

ج: يؤدي استخدام حقل التوقيع إلى تبسيط عملية توقيع المستند، لأنه يرشد المُوقع إلى وضع توقيعه في منطقة معينة، مما يجعل عملية التوقيع أكثر تنظيمًا وسهولة في الاستخدام.

#### س: هل هناك أي قيود على استخدام حقول التوقيع مع التوقيع المعتمد على البطاقة الذكية؟

ج: لا توجد قيود متأصلة على استخدام حقول التوقيع مع التوقيع المستند إلى البطاقة الذكية. ومع ذلك، من المهم التأكد من أن موقع حقل التوقيع المختار لا يحجب محتوى المستند المهم.

#### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لتنفيذ التوقيع المستند إلى البطاقة الذكية باستخدام حقل التوقيع؟

ج: للحصول على إرشادات ودعم إضافيين، يمكنك الرجوع إلى وثائق Aspose.PDF الرسمية ومنتديات المجتمع، التي تقدم رؤى وحلولًا قيمة لتنفيذ التوقيعات الرقمية الآمنة.