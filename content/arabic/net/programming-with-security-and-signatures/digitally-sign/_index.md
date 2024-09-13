---
title: تسجيل الدخول رقميا إلى ملف PDF
linktitle: تسجيل الدخول رقميا إلى ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية التوقيع رقميًا على ملفات PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لضمان أمان مستنداتك وصحتها.
type: docs
weight: 40
url: /ar/net/programming-with-security-and-signatures/digitally-sign/
---
## مقدمة

في عالمنا الرقمي، لا يمكن المبالغة في أهمية تأمين المستندات. سواء كنت عاملًا مستقلاً يرسل العقود، أو مالكًا لشركة صغيرة تدير الفواتير، أو جزءًا من شركة كبيرة، فإن ضمان بقاء مستنداتك أصلية ومقاومة للتلاعب أمر بالغ الأهمية. إحدى الطرق الفعّالة لتحقيق هذا الأمان هي من خلال التوقيعات الرقمية. في هذه المقالة، سنستكشف كيفية التوقيع رقميًا على ملف PDF باستخدام مكتبة Aspose.PDF for .NET. سنوضح لك كل شيء خطوة بخطوة.

## المتطلبات الأساسية

قبل الخوض في التفاصيل الدقيقة، دعنا نتأكد من أنك تمتلك كل ما تحتاجه للبدء في التوقيع الرقمي على ملفات PDF. فيما يلي قائمة بالمتطلبات الأساسية:

1. .NET Framework: تأكد من تثبيت .NET Framework على جهازك. يدعم Aspose.PDF for .NET عدة إصدارات من إطار العمل.
2.  مكتبة Aspose.PDF: ستحتاج إلى تنزيل مكتبة Aspose.PDF وتثبيتها. يمكنك الحصول عليها من[رابط الاصدار](https://releases.aspose.com/pdf/net/).
3.  الشهادة الرقمية: لتوقيع ملفات PDF، ستحتاج إلى شهادة رقمية —`.pfx` الملف عادة.
4. بيئة التطوير: استخدم Visual Studio أو أي بيئة تطوير متكاملة من اختيارك والتي تدعم C#.

بمجرد توفر هذه المتطلبات الأساسية لديك، ستكون جاهزًا للبدء في توقيع مستندات PDF الخاصة بك!

## استيراد الحزم

الآن بعد أن قمت بإعداد كل شيء، فلنبدأ في استيراد الحزم اللازمة لتشغيل مشروعنا. في أعلى فئة C# الخاصة بك، قم بتضمين المساحات ذات الصلة:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System.Collections;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

توفر هذه المساحات الأسماء الفئات والطرق الأساسية التي ستستخدمها لمعالجة ملفات PDF باستخدام Aspose.PDF.

## الخطوة 1: إعداد مسارات المستندات الخاصة بك

الخطوة الأولى هي تحديد المسارات لملفات PDF المدخلة والمخرجة والشهادة الرقمية الخاصة بك. استبدل`YOUR DOCUMENTS DIRECTORY` مع المسار الفعلي على نظامك حيث توجد ملفاتك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = ""; // المسار إلى الشهادة الرقمية الخاصة بك (.pfx)
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
```
 في هذه المقتطفة،`inFile` هو ملف PDF الأصلي الذي تريد التوقيع عليه، و`outFile` هو المكان الذي سيتم فيه حفظ ملف PDF الموقع.

## الخطوة 2: تحميل مستند PDF

 بعد ذلك، نحتاج إلى تحميل مستند PDF الذي نريد توقيعه.`Document` يتم استخدام الفئة في Aspose.PDF هنا:

```csharp
using (Document document = new Document(inFile))
{
    // المضي قدما في توقيع المنطق هنا...
}
```

يفتح هذا الرمز ملف PDF الخاص بك ويجهزه للعمليات الإضافية.

## الخطوة 3: تهيئة فئة PdfFileSignature

 بمجرد تحميل المستند، نقوم بإنشاء مثيل لـ`PdfFileSignature` الفئة، التي ستسمح لنا بالعمل بالتوقيعات الرقمية على مستند PDF المحمل لدينا.

```csharp
using (PdfFileSignature signature = new PdfFileSignature(document))
{
    // إعداد عملية التوقيع
}
```

تعد هذه الدورة هي وجهتك المفضلة لكل الأشياء المتعلقة بتوقيعات PDF!

## الخطوة 4: إنشاء نسخة شهادة رقمية

هنا يمكنك إعداد الشهادة التي سيتم استخدامها لتوقيع ملف PDF. تحتاج إلى توفير مسار ملف PDF الخاص بك`.pfx` الملف مع كلمة المرور المرتبطة به.

```csharp
PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
```

 تأكد من الاستبدال`"WebSales"` مع كلمة المرور الخاصة بشهادتك الفعلية.

## الخطوة 5: تكوين مظهر التوقيع

بعد ذلك، نحدد كيفية ظهور التوقيع في ملف PDF. يمكنك تخصيص موقع ومظهر التوقيع باستخدام مستطيل. 

```csharp
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
```

هنا، نقوم بوضع التوقيع عند الإحداثيات (100، 100) بعرض 200 وارتفاع 100.

## الخطوة 6: إنشاء التوقيع وحفظه

الآن حان الوقت لإنشاء التوقيع وحفظ ملف PDF الذي وقعناه. يمكنك وصف سبب التوقيع وتفاصيل الاتصال بك وموقعك. يمكن أن يساعد هذا في عملية التحقق لاحقًا.

```csharp
DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
signature.Save(outFile);
```

## الخطوة 7: التحقق من التوقيع

بعد حفظ ملف PDF الموقّع، من الأفضل دائمًا التأكد من إضافة التوقيع بشكل صحيح. يمكننا استرداد أسماء التوقيعات والتحقق من صحتها. 

```csharp
using (Document document = new Document(outFile))
{
    using (PdfFileSignature signature = new PdfFileSignature(document))
    {
        IList<string> sigNames = signature.GetSignNames();
        if (sigNames.Count > 0) 
        {
            if (signature.VerifySigned(sigNames[0] as string)) 
            {
                if (signature.IsCertified) 
                {
                    if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) 
                    {
                        //التوقيع صالح ومصدق عليه
                    }
                }
            }
        }
    }
}
```

يضمن هذا الجزء التحقق من صحة عملك؛ ففي نهاية المطاف، لن ترغب في إرسال مستند غير موقع!

## الخطوة 8: التعامل مع الاستثناءات

من الحكمة دائمًا وضع الكود الخاص بك في كتلة try-catch للتعامل مع أي استثناءات بسلاسة. 

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

بهذه الطريقة، إذا حدث شيء غير متوقع، ستعرف بالضبط ما الذي حدث خطأ دون تعطل تطبيقك.

## خاتمة

توفر التوقيعات الرقمية حماية أساسية للمستندات، حيث تثبت صحتها وسلامتها. باستخدام Aspose.PDF لـ .NET، يصبح توقيع ملف PDF عملية مباشرة يمكنها تحسين سير عمل إدارة المستندات بشكل كبير. الآن بعد أن تعلمت كيفية رقمنة توقيعاتك، يمكنك ضمان احترافيتك وتعاملك الآمن مع المستندات للعملاء والشركاء.

## الأسئلة الشائعة

### ما هو التوقيع الرقمي؟
التوقيع الرقمي هو المعادل التشفيري للتوقيع المكتوب بخط اليد، وهو يضمن صحة البيانات وسلامتها.

### هل يمكنني استخدام Aspose.PDF لتوقيع ملفات PDF في أي تطبيق .NET؟
نعم! برنامج Aspose.PDF for .NET متوافق مع تطبيقات .NET المختلفة، بما في ذلك تطبيقات سطح المكتب والويب والخدمات.

### ما هي أنواع الشهادات الرقمية التي يمكنني استخدامها؟
 يمكنك استخدام أي شهادة PKCS#12، والتي يتم حفظها عادةً في`.pfx` أو`.p12` ملف.

### هل هناك نسخة تجريبية من Aspose.PDF متاحة؟
 نعم! يمكنك تنزيل نسخة تجريبية مجانية من[صفحة إصدارات Aspose](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
 للحصول على الدعم، يمكنك زيارة[منتدى Aspose PDF](https://forum.aspose.com/c/pdf/10).