---
title: قم بالتوقيع باستخدام البطاقة الذكية باستخدام حقل التوقيع
linktitle: قم بالتوقيع باستخدام البطاقة الذكية باستخدام حقل التوقيع
second_title: Aspose.PDF لمرجع .NET API
description: قم بتسجيل ملفات PDF الخاصة بك بأمان باستخدام بطاقة ذكية باستخدام Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
يعد التوقيع الرقمي باستخدام البطاقة الذكية طريقة آمنة لتوقيع ملفات PDF. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة توقيع ملف PDF باستخدام حقل التوقيع والبطاقة الذكية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد توقيعه. يستبدل`"YOUR DOCUMENTS DIRECTORY"`في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: انسخ مستند PDF وافتحه

سنقوم الآن بنسخ وفتح مستند PDF للتوقيع باستخدام الكود التالي:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // قم بإنشاء حقل توقيع
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

 أخيرًا ، نتحقق من توقيع ملف PDF الموقع باستخدام امتداد`PdfFileSignature` فصل. نحصل على أسماء التوقيعات ونتحقق منها واحدة تلو الأخرى. إذا فشل التحقق من التوقيع ، يتم طرح استثناء. هذا هو الكود المقابل:

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

### نموذج التعليمات البرمجية المصدر للتوقيع باستخدام البطاقة الذكية باستخدام حقل التوقيع باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// قم بالتوقيع مع تحديد الشهادة في مخزن شهادات Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// اختر الشهادة يدويًا في المتجر
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

تهنئة ! لديك الآن دليل تفصيلي خطوة بخطوة لتوقيع ملف PDF ببطاقة ذكية باستخدام حقل التوقيع مع Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإضافة توقيعات رقمية آمنة إلى مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات إدارة الشهادات والتوقيع الرقمي المتقدمة.

### التعليمات

#### س: ما فائدة استخدام حقل التوقيع للتوقيع الرقمي بالبطاقة الذكية؟

ج: يوفر استخدام حقل التوقيع للتوقيع الرقمي باستخدام البطاقة الذكية منطقة مخصصة داخل ملف PDF حيث يتم تطبيق التوقيع. هذا يعزز وضوح الوثيقة ويضمن أصالة التوقيع.

#### س: كيف تسهل مكتبة Aspose.PDF for .NET التوقيع الرقمي المستند إلى البطاقة الذكية مع حقل التوقيع؟

ج: Aspose.PDF for .NET يبسط عملية إنشاء حقل التوقيع ، واختيار شهادة البطاقة الذكية ، وتطبيق التوقيع الرقمي على منطقة معينة في وثيقة PDF.

#### س: لماذا يعد تحديد شهادة معينة مهمًا للتوقيع المستند إلى البطاقة الذكية؟

ج: يسمح لك تحديد شهادة معينة بتحديد هوية الموقع بشكل فريد والتأكد من سلامة التوقيع. يساعد هذا في بناء الثقة والامتثال لمعايير التوقيع الرقمي.

#### س: كيف يتعامل كود المصدر المقدم مع عملية التوقيع المستندة إلى البطاقة الذكية مع حقل التوقيع؟

ج: يوضح كود المصدر كيفية إنشاء حقل توقيع وتحديد شهادة بطاقة ذكية وتطبيق توقيع رقمي بمعلومات توقيع محددة. كما يوضح كيفية التحقق من صحة التوقيع.

#### س: هل يمكنني تخصيص مظهر حقل التوقيع؟

ج: نعم ، يمكنك تخصيص مظهر حقل التوقيع ، مثل حجمه وموضعه وتمثيله المرئي ، لمحاذاة تخطيط المستند.

#### س: ماذا يحدث إذا فشل التوقيع في التحقق أثناء خطوة التحقق؟

ج: إذا فشل التوقيع في التحقق ، يتم طرح استثناء ، يشير إلى أن التوقيع غير صالح. هذا يضمن قبول التوقيعات الصالحة والموثوقة فقط.

#### س: هل يمكنني تطبيق عدة حقول توقيع وتوقيعات مستندة إلى البطاقة الذكية على مستند PDF واحد؟

ج: بالتأكيد ، يمكنك تطبيق العديد من حقول التوقيع والتوقيعات المستندة إلى البطاقة الذكية على مناطق مختلفة من وثيقة PDF نفسها ، مما يوفر طبقات متعددة من الأمان.

#### س: كيف يؤدي استخدام حقل التوقيع إلى تحسين عملية توقيع المستند الإجمالية؟

ج: يؤدي استخدام حقل التوقيع إلى تبسيط عملية توقيع المستند ، حيث يوجه الموقع لوضع توقيعه في منطقة معينة ، مما يجعل عملية التوقيع أكثر تنظيماً وسهولة في الاستخدام.

#### س: هل هناك أي قيود على استخدام حقول التوقيع مع التوقيع المستند إلى البطاقة الذكية؟

ج: لا توجد قيود متأصلة لاستخدام حقول التوقيع مع التوقيع المستند إلى البطاقة الذكية. ومع ذلك ، من المهم التأكد من أن موقع حقل التوقيع المختار لا يحجب محتوى المستند المهم.

#### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لتنفيذ التوقيع المستند إلى البطاقة الذكية باستخدام حقل التوقيع؟

ج: للحصول على إرشادات ودعم إضافي ، يمكنك الرجوع إلى منتديات Aspose.PDF الرسمية ، التي تقدم رؤى وحلولًا قيّمة لتنفيذ التوقيعات الرقمية الآمنة.