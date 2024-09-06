---
title: التوقيع بالبطاقة الذكية باستخدام حقل التوقيع
linktitle: التوقيع بالبطاقة الذكية باستخدام حقل التوقيع
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بتوقيع ملفات PDF الخاصة بك بشكل آمن باستخدام بطاقة ذكية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
يعد التوقيع الرقمي باستخدام البطاقة الذكية طريقة آمنة لتوقيع ملفات PDF. باستخدام Aspose.PDF for .NET، يمكنك بسهولة توقيع ملف PDF باستخدام حقل التوقيع والبطاقة الذكية باتباع التعليمات البرمجية المصدرية التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، عليك استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي تعليمات الاستيراد اللازمة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد توقيعه. استبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: انسخ مستند PDF وافتحه

الآن سوف نقوم بنسخ وفتح مستند PDF المراد توقيعه باستخدام الكود التالي:

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
        
         // إنشاء توقيع خارجي بالمعلومات اللازمة
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

 وأخيرًا، نتحقق من توقيع ملف PDF الموقّع باستخدام`PdfFileSignature` الصف. نحصل على أسماء التوقيع ونتحقق منها واحدًا تلو الآخر. إذا فشل أحد التوقيعات في التحقق، يتم طرح استثناء. هذا هو الكود المقابل:

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

### عينة من كود المصدر للتوقيع باستخدام البطاقة الذكية باستخدام حقل التوقيع باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// التوقيع باستخدام اختيار الشهادة في مخزن شهادات Windows
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

تهانينا! لديك الآن دليل خطوة بخطوة لتوقيع ملف PDF باستخدام بطاقة ذكية باستخدام حقل التوقيع مع Aspose.PDF لـ .NET. يمكنك استخدام هذا الكود لإضافة توقيعات رقمية آمنة إلى مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية للحصول على مزيد من المعلومات حول ميزات التوقيع الرقمي المتقدم وإدارة الشهادات.

### الأسئلة الشائعة

#### س: ما هي فائدة استخدام حقل التوقيع للتوقيع الرقمي بالبطاقة الذكية؟

ج: إن استخدام حقل التوقيع للتوقيع الرقمي باستخدام بطاقة ذكية يوفر منطقة مخصصة داخل ملف PDF حيث يتم تطبيق التوقيع. وهذا يعزز وضوح المستند ويضمن صحة التوقيع.

#### س: كيف تعمل مكتبة Aspose.PDF لـ .NET على تسهيل التوقيع الرقمي المستند إلى البطاقة الذكية باستخدام حقل التوقيع؟

ج: يقوم Aspose.PDF لـ .NET بتبسيط عملية إنشاء حقل التوقيع، وتحديد شهادة البطاقة الذكية، وتطبيق توقيع رقمي على منطقة معينة داخل مستند PDF.

#### س: لماذا يعد اختيار شهادة معينة أمرًا مهمًا للتوقيع المعتمد على البطاقة الذكية؟

ج: يتيح لك اختيار شهادة معينة تحديد هوية المُوقِّع بشكل فريد وضمان سلامة التوقيع. وهذا يساعد في إرساء الثقة والامتثال لمعايير التوقيع الرقمي.

#### س: كيف يتعامل كود المصدر المقدم مع عملية التوقيع المعتمدة على البطاقة الذكية باستخدام حقل التوقيع؟

ج: يوضح الكود المصدر كيفية إنشاء حقل توقيع، واختيار شهادة بطاقة ذكية، وتطبيق توقيع رقمي بمعلومات توقيع محددة. كما يوضح كيفية التحقق من صحة التوقيع.

#### س: هل يمكنني تخصيص مظهر حقل التوقيع؟

ج: نعم، يمكنك تخصيص مظهر حقل التوقيع، مثل حجمه وموقعه وتمثيله المرئي، ليتوافق مع تخطيط مستندك.

#### س: ماذا يحدث إذا فشل التوقيع في التحقق أثناء خطوة التحقق؟

ج: إذا فشل التوقيع في التحقق، يتم طرح استثناء يشير إلى أن التوقيع غير صالح. وهذا يضمن قبول التوقيعات الصالحة والموثوقة فقط.

#### س: هل يمكنني تطبيق حقول توقيع متعددة وتوقيعات تعتمد على البطاقة الذكية على مستند PDF واحد؟

ج: بالتأكيد، يمكنك تطبيق حقول توقيع متعددة وتوقيعات تعتمد على البطاقة الذكية على مناطق مختلفة من نفس مستند PDF، مما يوفر طبقات متعددة من الأمان.

#### س: كيف يساعد استخدام حقل التوقيع على تعزيز عملية توقيع المستندات بشكل عام؟

أ: يؤدي استخدام حقل التوقيع إلى تبسيط عملية توقيع المستندات، لأنه يوجه المُوقِّع إلى وضع توقيعه في منطقة مخصصة، مما يجعل عملية التوقيع أكثر تنظيماً وسهولة في الاستخدام.

#### س: هل هناك أي قيود على استخدام حقول التوقيع مع التوقيع المعتمد على البطاقة الذكية؟

ج: لا توجد قيود جوهرية على استخدام حقول التوقيع مع التوقيع المستند إلى البطاقة الذكية. ومع ذلك، من المهم التأكد من أن موقع حقل التوقيع المختار لا يحجب محتوى المستند المهم.

#### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لتنفيذ التوقيع المستند إلى البطاقة الذكية مع حقل التوقيع؟

ج: للحصول على إرشادات ودعم إضافيين، يمكنك الرجوع إلى وثائق Aspose.PDF الرسمية ومنتديات المجتمع، والتي تقدم رؤى وحلولاً قيمة لتنفيذ التوقيعات الرقمية الآمنة.