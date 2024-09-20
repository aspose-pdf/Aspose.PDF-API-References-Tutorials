---
title: إضافة تلميح الأدوات إلى النص في ملف PDF
linktitle: إضافة تلميح الأدوات إلى النص في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة تلميحات الأدوات إلى النص في ملفات PDF باستخدام Aspose.PDF لـ .NET. قم بتحسين ملفات PDF الخاصة بك باستخدام نصوص توضيحية مفيدة دون عناء.
type: docs
weight: 90
url: /ar/net/programming-with-text/add-tooltip-to-text/
---
## مقدمة

عندما يتعلق الأمر بإنشاء ملفات PDF جذابة وتفاعلية، يمكن أن تكون الإرشادات التوضيحية ذات قيمة لا تقدر بثمن. هل تعرف تلك المربعات المنبثقة الصغيرة التي تقدم لك معلومات إضافية عندما تمرر مؤشر الماوس فوق شيء ما؟ يمكنها توفير السياق أو الأوصاف أو حتى نصائح بسيطة دون إرباك مستندك. في هذا البرنامج التعليمي، سنشرح كيفية إضافة الإرشادات التوضيحية إلى النص في ملف PDF باستخدام مكتبة Aspose.PDF for .NET. سواء كنت مطورًا متمرسًا أو كنت قد بدأت للتو في عالم ملفات PDF، فأنت في المكان المناسب! لذا فلنبدأ!

## المتطلبات الأساسية

قبل أن ننتقل إلى جزء الترميز، دعنا نتأكد من أن لديك كل ما تحتاجه لمتابعة الأمر بسلاسة.

### تم تثبيت Visual Studio
من الضروري تثبيت Visual Studio على جهازك، لأنه سيكون بيئة التطوير الأساسية لتطبيقات .NET.

### مكتبة Aspose.PDF لـ .NET
 ستحتاج أيضًا إلى توفير مكتبة Aspose.PDF تحت تصرفك. يمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/)تأكد من تضمينه في مراجع مشروعك.

### المعرفة الأساسية بلغة C#
إن معرفة لغة C# ستساعدك كثيرًا لأننا سنستخدم هذه اللغة في البرمجة. ولكن لا تقلق، سأرشدك في كل خطوة!

### وثيقة PDF للعمل بها
يمكنك البدء بمستند PDF فارغ، كما نفعل في هذا المثال، أو استخدام مستند موجود إذا كنت تفضل ذلك.

الآن، دعونا ننتقل إلى جزء الترميز!

## استيراد الحزم 

 تتضمن الخطوة الأولى في مغامرة الترميز الخاصة بنا استيراد الحزم اللازمة. افتح مشروع Visual Studio الخاص بك، وفي أعلى ملف C#، ستحتاج إلى إضافة ما يلي`using` التوجيهات:

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

تتيح لك هذه الحزم الوصول إلى جميع الفئات والوظائف التي تحتاجها لإنشاء مستندات PDF ومعالجتها.

## الخطوة 1: إعداد دليل المستندات الخاص بك

أولاً وقبل كل شيء، نحتاج إلى إعداد المسار الذي ستحفظ فيه مستنداتك. فكر في هذا الأمر باعتباره العثور على مكان مريح في نظام الملفات الخاص بك حيث ستتواجد كل إبداعاتك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

 تأكد من الاستبدال`YOUR DOCUMENT DIRECTORY` مع المسار الفعلي على جهازك.

## الخطوة 2: إنشاء مستند PDF نموذجي

بعد ذلك، حان الوقت لإنشاء ملف PDF بسيط يحتوي على بعض النصوص. وهنا نبدأ عملية الإبداع لدينا!

```csharp
//إنشاء مستند نموذجي يحتوي على نص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

في هذه الخطوة نقوم بإنشاء مستند وإضافة قطعتين نصيتين إليه وحفظه في المسار الذي حددناه مسبقًا.

## الخطوة 3: افتح المستند للمعالجة

الآن بعد أن قمنا بإنشاء المستند، فلنفتحه حتى نتمكن من العمل على أدوات التلميح تلك!

```csharp
// فتح مستند يحتوي على نص
Document document = new Document(outputFile);
```

هنا، نقوم ببساطة بتحميل المستند الذي قمنا بإنشائه للتو.

## الخطوة 4: إنشاء أداة لامتصاص النص للعثور على أجزاء النص

نحتاج إلى العثور على أجزاء النص التي نريد إضافة تلميحات الأدوات إليها. وهذا يشبه استخدام عدسة مكبرة لتسليط الضوء على جزء معين من خريطة كبيرة! 

```csharp
// إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## الخطوة 5: استخراج أجزاء النص

بعد ذلك، نقوم باستخراج أجزاء النص التي وجدناها من خطوتنا السابقة.

```csharp
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragments = absorber.TextFragments;
```

يتيح لنا هذا المقطع الاحتفاظ بالمراجع الخاصة بأجزاء النص التي نهتم بها.

## الخطوة 6: التنقل عبر الأجزاء وإضافة تلميحات الأدوات

الآن يأتي الجزء الممتع! سننتقل عبر كل جزء من أجزاء النص ونضيف تلميحًا توضيحيًا لكل جزء. تخيل أنك ستضع هدايا صغيرة (تلميحات توضيحية) حول عناصر معينة (أجزاء نصية).

```csharp
// التنقل عبر الشظايا
foreach (TextFragment fragment in textFragments)
{
	// إنشاء زر غير مرئي في موضع جزء النص
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// سيتم عرض قيمة AlternateName كإشارة توضيحية بواسطة تطبيق المشاهد
	field.AlternateName = "Tooltip for text.";
	// إضافة حقل الزر إلى المستند
	document.Form.Add(field);
}
```

في كل تكرار، نقوم بإنشاء حقل زر يتوافق مع موضع جزء النص ونقوم بتعيين نص الإرشاد إليه.

## الخطوة 7: كرر ذلك بالنسبة لأدوات التلميح الطويلة

تمامًا كما أضفنا تلميحًا بسيطًا، يمكننا فعل الشيء نفسه للنصوص الأطول. فلنوسع من نطاق إبداعنا!

```csharp
// ستكون الخطوة التالية عبارة عن عينة من تلميح الأدوات الطويل جدًا
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// تعيين نص طويل جدًا
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

هنا، نقوم بنفس النوع من العمل كما في السابق، ولكن مع تلميح أداة أوسع بكثير.

## الخطوة 8: احفظ مستندك

الخطوة الأخيرة هي حفظ مستندك مع كل أدوات التلميح الجديدة اللامعة. 

```csharp
// حفظ المستند
document.Save(outputFile);
```

وهكذا تكون قد انتهيت! لقد أضفت تلميحات الأدوات إلى ملف PDF الخاص بك، مما يجعله أكثر سهولة في الاستخدام وتفاعلية.

## خاتمة

هذا كل ما في الأمر - دليل سهل المتابعة حول كيفية إضافة تلميحات الأدوات إلى النص في ملفات PDF باستخدام Aspose.PDF لـ .NET. يمكن لهذه التقنية تحسين تجربة المستخدم بشكل كبير، مما يجعل مستنداتك أكثر إفادة دون إثقال القارئ بكمية كبيرة من النص دفعة واحدة. 

بمجرد تحريك المؤشر فوق كلمة أو عبارة، يحصل القارئ على معلومات ذات صلة تضيف قيمة دون فوضى. لذا، استعد وجرب الأمر! قبل أن تدرك ذلك، قد تكون قادرًا على إنشاء كل أنواع المستندات الجذابة التي تبرز.

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها في تطبيقات .NET.

### هل يمكنني استخدام Aspose.PDF مجانًا؟
 نعم، تقدم Aspose نسخة تجريبية مجانية لاستكشاف ميزاتها! يمكنك العثور عليها[هنا](https://releases.aspose.com/).

### هل هناك أي خيارات ترخيص متاحة لـ Aspose.PDF؟
نعم، يمكنك شراء ترخيص أو الحصول على ترخيص مؤقت. تحقق من الخيارات[هنا](https://purchase.aspose.com/).

### هل يمكنني إضافة عناصر تفاعلية أخرى غير تلميحات الأدوات باستخدام Aspose.PDF؟
بالتأكيد! يتيح لك Aspose.PDF إضافة عناصر تفاعلية متنوعة مثل الروابط التشعبية والأزرار والنماذج.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.PDF؟
 يمكنك التحقق من الوثائق[هنا](https://reference.aspose.com/pdf/net/) لمزيد من التوجيه المتعمق.