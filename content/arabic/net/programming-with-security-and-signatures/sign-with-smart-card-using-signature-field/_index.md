---
title: التوقيع بالبطاقة الذكية باستخدام حقل التوقيع
linktitle: التوقيع بالبطاقة الذكية باستخدام حقل التوقيع
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية التوقيع على ملفات PDF بأمان باستخدام بطاقة ذكية باستخدام Aspose.PDF for .NET. اتبع دليلنا خطوة بخطوة لسهولة التنفيذ.
type: docs
weight: 120
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## مقدمة

في عالمنا الرقمي اليوم، أصبح تأمين المستندات أكثر أهمية من أي وقت مضى. سواء كنت مطورًا أو مالكًا لشركة أو مجرد شخص يتعامل مع معلومات حساسة، فإن معرفة كيفية توقيع ملفات PDF إلكترونيًا يمكن أن يوفر لك الوقت ويضمن مصادقة مستنداتك. في هذا الدليل، سنوضح لك عملية توقيع ملف PDF باستخدام بطاقة ذكية وحقل توقيع باستخدام Aspose.PDF لـ .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في تفاصيل عملية التوقيع، دعنا نتأكد من أنك تمتلك كل ما تحتاجه للبدء. إليك قائمة بالمتطلبات الأساسية:

1. Aspose.PDF لـ .NET: تأكد من تثبيت مكتبة Aspose.PDF في بيئة .NET الخاصة بك. يمكنك تنزيلها من[موقع](https://releases.aspose.com/pdf/net/).

2. Visual Studio: ستحتاج إلى بيئة تطوير متكاملة لكتابة وتشغيل كود .NET. يعد Visual Studio Community Edition خيارًا مجانيًا رائعًا.

3. البطاقة الذكية: تعد هذه البطاقة ضرورية لتوقيع ملف PDF الخاص بك. تأكد من تثبيت قارئ البطاقات الذكية والشهادات اللازمة على جهازك.

4. المعرفة الأساسية بلغة C#: ستساعدك المعرفة ببرمجة C# على فهم مقتطفات التعليمات البرمجية التي سنستخدمها.

5. نموذج مستند PDF: قم بإعداد نموذج مستند PDF جاهز للاختبار. يمكنك إنشاء ملف PDF فارغ أو استخدام ملف PDF موجود.

## استيراد الحزم

قبل أن نبدأ في كتابة التعليمات البرمجية، دعنا نستورد الحزم اللازمة. ستحتاج إلى تضمين المساحات التالية في ملف C# الخاص بك:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

ستتيح لك هذه المساحات الوصول إلى الفئات والطرق المطلوبة للعمل مع ملفات PDF ومعالجة التوقيعات الرقمية.

## دليل خطوة بخطوة لتوقيع ملف PDF باستخدام بطاقة ذكية

الآن بعد أن حددنا المتطلبات الأساسية، فلنبدأ في تقسيم عملية التوقيع إلى خطوات يمكن إدارتها. سنتناول كل خطوة بالتفصيل، لضمان فهمك لما يحدث تحت الغطاء.

### الخطوة 1: إعداد دليل المستندات الخاص بك

ماذا تفعل: قم بتحديد المسار إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 شرح: استبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي الذي توجد به ملفات PDF الخاصة بك. هذا هو المكان الذي سنقرأ فيه ملف PDF الفارغ ونحفظ المستند الموقّع.

### الخطوة 2: نسخ ملف PDF الفارغ

ما يجب فعله: قم بإنشاء نسخة من ملف PDF الفارغ الخاص بك للعمل عليه.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 الشرح: هذا الخط ينسخ`blank.pdf`ملف إلى ملف جديد يسمى`externalSignature1.pdf` . ال`true` تسمح المعلمة بالكتابة فوق الملف إذا كان موجودًا بالفعل.

### الخطوة 3: افتح مستند PDF

ماذا تفعل: افتح ملف PDF المنسوخ للقراءة والكتابة.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // الخطوات التالية سوف تذهب هنا
    }
}
```

 الشرح: نحن نستخدم`FileStream` لفتح ملف PDF الخاص بنا.`Document` تسمح لنا الفئة من Aspose.PDF بالتعامل مع محتوى PDF.

### الخطوة 4: إنشاء حقل التوقيع

ما يجب فعله: قم بتحديد حقل التوقيع في ملف PDF حيث سيتم وضع التوقيع.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 الشرح: هنا، نقوم بإنشاء`SignatureField` في الصفحة الثانية (يبدأ فهرس الصفحة من 1) من ملف PDF.`Rectangle` يحدد موضع وحجم حقل التوقيع.

### الخطوة 5: الوصول إلى مخزن شهادات البطاقة الذكية

ما يجب فعله: افتح مخزن الشهادات لتحديد شهادة البطاقة الذكية الخاصة بك.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

الشرح: نقوم بالوصول إلى مخزن الشهادات للمستخدم الحالي. هذا هو المكان الذي يتم فيه تخزين شهادات البطاقة الذكية الخاصة بك.

### الخطوة 6: حدد الشهادة

ماذا تفعل: مطالبة المستخدم باختيار شهادة من المتجر.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

الشرح: يفتح هذا السطر مربع حوار لاختيار شهادة. يمكنك اختيار الشهادة المرتبطة بالبطاقة الذكية الخاصة بك.

### الخطوة 7: إنشاء توقيع خارجي

 ما يجب فعله: إنشاء مثيل لـ`ExternalSignature` باستخدام الشهادة المحددة.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 الشرح: نقوم بتهيئة`ExternalSignature` مع الشهادة المحددة. يمكنك أيضًا تعيين السلطة وسبب التوقيع ومعلومات الاتصال.

### الخطوة 8: إضافة حقل التوقيع إلى المستند

ماذا تفعل: أضف حقل التوقيع إلى المستند.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

الشرح: نعطي حقل التوقيع اسمًا ونضيفه إلى الصفحة الأولى من المستند. يؤدي هذا إلى تحضير ملف PDF للتوقيع.

### الخطوة 9: توقيع الوثيقة

ما يجب فعله: استخدم التوقيع الخارجي لتوقيع ملف PDF.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

الشرح: يوقع هذا السطر المستند باستخدام التوقيع الخارجي ويحفظ التغييرات في ملف PDF. تم توقيع المستند الآن!

### الخطوة 10: التحقق من التوقيع

ماذا تفعل: تحقق من صحة التوقيع.

```csharp
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

الشرح: نقوم بإنشاء مثيل لـ`PdfFileSignature` للتحقق من صحة التوقيعات في المستند. إذا لم يكن التوقيع صالحًا، فسيتم طرح استثناء.

## خاتمة

تهانينا! لقد تعلمت للتو كيفية التوقيع على مستند PDF باستخدام بطاقة ذكية وحقل توقيع باستخدام Aspose.PDF لـ .NET. لا تعمل هذه العملية على تأمين مستنداتك فحسب، بل تضمن أيضًا مصداقيتها، مما يجعلها مهارة أساسية في المشهد الرقمي اليوم. سواء كنت توقع عقودًا أو فواتير أو أي مستندات مهمة أخرى، فإن معرفة كيفية تنفيذ التوقيعات الرقمية يمكن أن يوفر لك الوقت ويمنحك راحة البال.

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة قوية تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وتحويلها في تطبيقات .NET.

### هل أحتاج إلى بطاقة ذكية لتوقيع ملفات PDF؟
نعم، يلزم وجود بطاقة ذكية لتوقيع ملفات PDF بشكل آمن باستخدام شهادة رقمية.

### هل يمكنني استخدام Aspose.PDF مجانًا؟
 يقدم Aspose.PDF نسخة تجريبية مجانية، يمكنك تنزيلها[هنا](https://releases.aspose.com/).

### كيف يمكنني التحقق من ملف PDF الموقّع؟
 يمكنك استخدام`PdfFileSignature` قم بإنشاء فئة في Aspose.PDF للتحقق من التوقيعات في مستند PDF الخاص بك.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.PDF؟
 يمكنك التحقق من[توثيق Aspose.PDF](https://reference.aspose.com/pdf/net/) لمزيد من التفاصيل والأمثلة.