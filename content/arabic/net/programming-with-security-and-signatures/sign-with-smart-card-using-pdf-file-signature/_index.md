---
title: التوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
linktitle: التوقيع باستخدام البطاقة الذكية باستخدام توقيع ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية توقيع ملفات PDF باستخدام بطاقة ذكية باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل خطوة بخطوة للحصول على توقيعات رقمية آمنة.
type: docs
weight: 110
url: /ar/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## مقدمة

في العصر الرقمي، أصبح تأمين المستندات أكثر أهمية من أي وقت مضى. سواء كان عقدًا أو اتفاقية أو أي معلومات حساسة، فإن التأكد من أن المستند أصلي ولم يتم العبث به أمر بالغ الأهمية. أدخل التوقيعات الرقمية! اليوم، سنتعمق في كيفية توقيع ملف PDF باستخدام بطاقة ذكية مع Aspose.PDF لـ .NET. تتيح هذه المكتبة القوية للمطورين التعامل مع مستندات PDF وإنشائها بكفاءة، بما في ذلك إضافة توقيعات رقمية آمنة. لذا، احصل على بطاقتك الذكية، ولنبدأ!

## المتطلبات الأساسية

قبل أن ننتقل إلى التفاصيل الدقيقة لتوقيع ملف PDF، دعنا نتأكد من أنك تمتلك كل ما تحتاجه. إليك قائمة مرجعية لمساعدتك على الاستعداد:

1.  Aspose.PDF لـ .NET: تأكد من تثبيت مكتبة Aspose.PDF. يمكنك تنزيلها من[موقع](https://releases.aspose.com/pdf/net/).
2. Visual Studio: بيئة تطوير يمكنك من خلالها كتابة وتشغيل كود .NET الخاص بك.
3. البطاقة الذكية: ستحتاج إلى بطاقة ذكية مثبت عليها شهادة رقمية صالحة.
4. الفهم الأساسي للغة C#: سيكون من المفيد التعرف على برمجة C# لأننا سنكتب مقتطفات من التعليمات البرمجية بهذه اللغة.
5. مستند PDF: ملف PDF نموذجي (مثل`blank.pdf`) لاختبار عملية التوقيع الخاصة بنا.

مع توفر هذه المتطلبات الأساسية، ستكون جاهزًا للبدء في التعرف على الكود!

## استيراد الحزم

أولاً وقبل كل شيء، دعنا نستورد الحزم اللازمة. ستحتاج إلى إضافة مراجع إلى مكتبة Aspose.PDF في مشروعك. إليك كيفية القيام بذلك:

1. افتح Visual Studio.
2. إنشاء مشروع جديد أو فتح مشروع موجود.
3.  انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول وحدد`Manage NuGet Packages`.
4.  بحث عن`Aspose.PDF` وتثبيت الإصدار الأحدث.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

الآن بعد أن قمنا باستيراد الحزم اللازمة، دعونا نقوم بتقسيم الكود خطوة بخطوة.

## الخطوة 1: إعداد المستند الخاص بك

الخطوة الأولى في عمليتنا هي إعداد مستند PDF الذي نريد توقيعه. إليك كيفية القيام بذلك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 في هذا المقطع، نقوم بتحديد المسار إلى دليل المستندات الخاص بنا وإنشاء مثيل لـ`Document` الفصل باستخدام ملف PDF عينة يسمى`blank.pdf` . تأكد من الاستبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي الذي يوجد به ملف PDF الخاص بك.

## الخطوة 2: تهيئة PdfFileSignature

 بعد ذلك، سنقوم بتهيئة`PdfFileSignature` الفئة المسؤولة عن التعامل مع عملية التوقيع.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
هنا، نقوم بإنشاء مثيل لـ`PdfFileSignature`وربطها بمستند PDF الخاص بنا. يؤدي هذا إلى إعداد المستند للتوقيع.

## الخطوة 3: الوصول إلى شهادة البطاقة الذكية

الآن يأتي الجزء الحاسم - الوصول إلى الشهادة الرقمية المخزنة على البطاقة الذكية. وهذه هي الطريقة التي يمكننا بها القيام بذلك:

### افتح مخزن الشهادات

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
نقوم بفتح مخزن الشهادات الموجود في ملف تعريف المستخدم الحالي. وهذا يسمح لنا بالوصول إلى الشهادات المثبتة على جهازك، بما في ذلك تلك الموجودة على بطاقتك الذكية.

### حدد الشهادة

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
يطالب هذا الرمز المستخدم باختيار شهادة من المجموعة. ستعرض واجهة المستخدم جميع الشهادات المتاحة، مما يسمح لك باختيار الشهادة المرتبطة بالبطاقة الذكية الخاصة بك.

## الخطوة 4: إنشاء التوقيع الخارجي

بمجرد تحديد الشهادة، فإن الخطوة التالية هي إنشاء توقيع خارجي باستخدام الشهادة المحددة.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
هنا، نقوم بإنشاء مثيل لـ`ExternalSignature` باستخدام الشهادة المحددة. سيتم استخدام هذا الكائن لتوقيع مستند PDF.

## الخطوة 5: تعيين مظهر التوقيع

الآن، دعنا نحدد مظهر توقيعنا. هنا يمكنك تخصيص مظهر توقيعك على المستند.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 في هذا المقطع، نحدد مظهر التوقيع من خلال توفير المسار إلى ملف صورة (مثل شعار أو رسم توقيع). تأكد من استبدال`"demo.png"` مع الصورة الفعلية التي تريد استخدامها.

## الخطوة 6: التوقيع على ملف PDF

بعد إعداد كل شيء، حان الوقت لتوقيع مستند PDF!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
في هذه الخطوة، نسميها`Sign` الطريقة على موقعنا`pdfSign` الكائن. إليك ما يعنيه كل معلمة:
- `1`:رقم الصفحة التي سيظهر فيها التوقيع.
- `"Reason"`:سبب التوقيع على الوثيقة.
- `"Contact"`:معلومات الاتصال بالموقع.
- `"Location"`:مكان المُوقِّع.
- `true`: يشير إلى ما إذا كان سيتم إنشاء توقيع مرئي.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`:موضع وحجم التوقيع على ملف PDF.
- `externalSignature`:كائن التوقيع الذي أنشأناه سابقًا.

 وأخيرًا، نحفظ المستند الموقع باسم`externalSignature2.pdf`.

## الخطوة 7: التحقق من التوقيع

بعد التوقيع على الوثيقة، من الضروري التأكد من صحة التوقيع. وإليك كيفية القيام بذلك:

### بدء عملية التحقق

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 نقوم بإنشاء مثيل جديد لـ`PdfFileSignature` للوثيقة الموقعة. ثم نقوم باسترجاع أسماء جميع التوقيعات الموجودة في الوثيقة.

### التحقق من صحة التوقيع

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
نقوم بفحص كل اسم توقيع والتحقق من صحته. إذا فشل أي توقيع في التحقق، يتم طرح استثناء يشير إلى أن التوقيع غير صالح.

## خاتمة

والآن، لقد نجحت في التوقيع على مستند PDF باستخدام بطاقة ذكية مع Aspose.PDF لـ .NET. لا تعمل هذه العملية على تأمين مستندك فحسب، بل تضيف أيضًا طبقة من الأصالة التي تعد بالغة الأهمية في عالمنا الرقمي اليوم. سواء كنت تتعامل مع عقود أو مستندات قانونية أو أي معلومات حساسة، فإن معرفة كيفية تنفيذ التوقيعات الرقمية تعد مهارة قيمة. 

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة قوية تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وتحويلها داخل تطبيقات .NET.

### هل أحتاج إلى بطاقة ذكية لتوقيع ملفات PDF؟
على الرغم من أن البطاقة الذكية ليست إلزامية، إلا أنها يوصى بها بشدة للتوقيعات الرقمية الآمنة، حيث إنها توفر طبقة إضافية من الأمان.

### هل يمكنني استخدام أي ملف PDF للتوقيع؟
نعم، يمكنك استخدام أي ملف PDF، ولكن تأكد من أنه غير محمي بكلمة مرور. إذا كان الأمر كذلك، فستحتاج إلى إلغاء قفله أولاً.

### ماذا لو لم يكن لدي شهادة رقمية؟
يمكنك الحصول على شهادة رقمية من هيئة تصديق موثوقة (CA) أو استخدام شهادة موقعة ذاتيًا لأغراض الاختبار.

### هل هناك نسخة تجريبية من Aspose.PDF متاحة؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع اسبوس](https://releases.aspose.com/).