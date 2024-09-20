---
title: محاذاة النص لمحتويات المربع العائم في ملف PDF
linktitle: محاذاة النص لمحتويات المربع العائم في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية محاذاة محتويات المربعات العائمة في ملفات PDF باستخدام Aspose.PDF لـ .NET. أنشئ مستندات مذهلة بتخطيطات احترافية.
type: docs
weight: 520
url: /ar/net/programming-with-text/text-alignment-for-floating-box-contents/
---
## مقدمة

إن إنشاء ملفات PDF جذابة بصريًا يعد مهارة بالغة الأهمية في عالمنا الرقمي اليوم، حيث يتنافس الجميع على جذب الانتباه. يجعل برنامج Aspose.PDF for .NET هذه المهمة سهلة ومرنة بشكل لا يصدق، خاصة عندما يتعلق الأمر بتخصيص تخطيط مستنداتك. في هذا البرنامج التعليمي، سنستكشف كيفية محاذاة محتويات المربعات العائمة داخل ملفات PDF الخاصة بك. سيضفي هذا النهج على مستنداتك لمسة مصقولة واحترافية تبرز من بين الحشود.

## المتطلبات الأساسية

قبل الخوض في البرنامج التعليمي، هناك بعض الأساسيات التي تحتاج إلى أن تكون لديك:

1. .NET Framework: تأكد من تثبيت .NET Framework متوافق على جهازك، حيث أنه المكان الذي ستقوم فيه بتشغيل الكود الخاص بك.
2.  مكتبة Aspose.PDF: يجب أن يكون لديك مكتبة Aspose.PDF. إذا لم تقم بتنزيلها بعد، يمكنك القيام بذلك[هنا](https://releases.aspose.com/pdf/net/).
3. IDE: ستكون بيئة التطوير المتكاملة (IDE) مثل Visual Studio مفيدة للترميز وتصحيح الأخطاء.
4. المعرفة الأساسية بلغة C#: إن الإلمام ببرمجة C# سيجعل من الأسهل متابعة وفهم مقتطفات التعليمات البرمجية.

## استيراد الحزم

للبدء، يجب عليك استيراد الحزم اللازمة في مشروع C# الخاص بك. وإليك كيفية القيام بذلك:

1. افتح مشروعك: قم بتشغيل IDE الخاص بك، وافتح المشروع الذي تريد تنفيذ وظيفة المربع العائم فيه.
2. تثبيت Aspose.PDF لـ .NET: استخدم NuGet Package Manager لتثبيت حزمة Aspose.PDF. للقيام بذلك:
   - انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول، ثم اختر "إدارة حزم NuGet".
   - ابحث عن "Aspose.PDF" وانقر على "تثبيت".
   
```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

بمجرد إعداد الحزم، ستكون جاهزًا للبدء في إنشاء ومحاذاة المربعات العائمة في ملف PDF الخاص بك.

الآن، دعنا نستعرض عملية إضافة ومحاذاة المربعات العائمة في مستند PDF. سننشئ عدة مربعات عائمة ونحاذي محتوياتها بشكل مختلف للتوضيح.

## الخطوة 1: إعداد المستند

الخطوة الأولى هي تهيئة مستند PDF جديد وإضافة صفحة إليه. يعمل هذا كلوحة رسم للمربعات العائمة.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

 في مقتطف التعليمات البرمجية هذا، استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي الذي تريد حفظ ملف PDF الخاص بك فيه.

## الخطوة 2: إنشاء الصندوق العائم الأول

بعد ذلك، دعنا ننشئ أول صندوق عائم ونحدد محاذاته. هنا، سيتم محاذاة المحتوى إلى أسفل يمين الصندوق.

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
```

- FloatingBox(100, 100): يقوم هذا بتهيئة صندوق عائم بعرض وارتفاع 100 وحدة لكل منهما.
- المحاذاة الرأسية والأفقية: نحدد أن النص يجب أن يكون محاذيًا لأسفل وإلى اليمين.
- TextFragment: يمثل النص الذي تريد عرضه داخل المربع العائم.
- BorderInfo: يؤدي ذلك إلى إنشاء حدود حول المربع العائم، مما يجعله مميزًا بصريًا.

## الخطوة 3: أضف الصندوق العائم الثاني

الآن، دعونا نقوم بإنشاء صندوق عائم ثاني يركز محتواه.

```csharp
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
```

تمامًا مثل المربع الأول، قمنا بضبط محاذاته الرأسية على المركز والأفقية على اليمين. تتيح هذه الطريقة إجراء تعديلات ديناميكية على المحتوى وتحسين المظهر المرئي.

## الخطوة 4: إنشاء الصندوق العائم الثالث

الآن، بالنسبة لصندوقنا العائم الثالث والأخير، سنقوم بمحاذاة المحتوى إلى أعلى اليمين.

```csharp
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

يقوم هذا المربع بمحاذاة المحتوى في أعلى اليمين، مما يوضح المرونة التي تتمتع بها مع مكتبة Aspose.PDF. يمكن لكل مربع عائم أن يخدم غرضًا مميزًا بناءً على الطريقة التي ترغب في توصيل المعلومات بها بصريًا.

## الخطوة 5: احفظ المستند

أخيرًا، حان الوقت لحفظ مستندك. ستحفظه في الموقع الذي حددته سابقًا.

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 سيتم حفظ الملف باسم`FloatingBox_alignment_review_out.pdf` في الدليل المحدد. تأكد من التحقق من هذا الموقع لعرض ملف PDF الذي قمت بإنشائه.

## خاتمة

يتيح لك استخدام Aspose.PDF for .NET لمعالجة تخطيطات PDF إنشاء مستندات احترافية وجذابة بصريًا بكفاءة. من خلال فهم كيفية محاذاة محتويات المربعات العائمة، يمكنك تحسين تجربة المستخدم لملفات PDF بشكل كبير. وكما رأينا، فهي بسيطة ولكنها قوية بما يكفي لجعل ملفات PDF الخاصة بك مميزة.

## الأسئلة الشائعة

### ما هو المربع العائم في Aspose.PDF؟  
يسمح لك المربع العائم بوضع المحتوى بشكل مرن داخل تخطيط PDF.

### هل يمكنني تغيير لون حدود الصندوق العائم؟  
نعم، يمكنك تحديد ألوان مختلفة للحدود عند إنشاء مربع عائم.

### هل استخدام Aspose.PDF لـ .NET مجاني؟  
يقدم Aspose.PDF نسخة تجريبية مجانية، ولكن يلزم الحصول على ترخيص مدفوع للحصول على الوظائف الكاملة.

### هل يمكنني إضافة الصور إلى الصناديق العائمة؟  
بالتأكيد! يمكنك إضافة أنواع مختلفة من المحتوى، بما في ذلك الصور، إلى المربعات العائمة.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.PDF؟  
 يمكن العثور على الوثائق التفصيلية[هنا](https://reference.aspose.com/pdf/net/).