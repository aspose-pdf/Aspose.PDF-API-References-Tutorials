---
title: قم بالتوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
linktitle: قم بالتوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
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

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد توقيعه. يستبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: قم بتحميل مستند PDF

سنقوم الآن بتحميل مستند PDF ليتم توقيعه باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## الخطوة 4: قم بالتوقيع بالبطاقة الذكية

 في هذه الخطوة ، سنقوم بالتوقيع بالبطاقة الذكية باستخدام ملف`PdfFileSignature` فئة من`Facades` مكتبة. نختار شهادة البطاقة الذكية من مخزن شهادات Windows ونحدد معلومات التوقيع الضرورية. هذا هو الكود المقابل:

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