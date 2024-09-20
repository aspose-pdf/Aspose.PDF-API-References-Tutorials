---
title: البحث والحصول على صفحة نصية في ملف PDF
linktitle: البحث والحصول على صفحة نصية في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث والحصول على نص من صفحة معينة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 430
url: /ar/net/programming-with-text/search-and-get-text-page/
---
## مقدمة

هل وجدت نفسك يومًا في حاجة إلى البحث عن نص معين داخل مستند PDF واستخراجه لاستخدامه لاحقًا؟ ربما تقوم ببناء تطبيق يعالج المستندات ويتطلب استخراج البيانات بدقة، أو ربما تحتاج فقط إلى تحليل ملفات PDF بكفاءة. أياً كانت حالتك، فأنت في المكان المناسب! في هذا البرنامج التعليمي، سنتعمق في كيفية البحث عن نص والحصول عليه من صفحة في ملف PDF باستخدام Aspose.PDF لـ .NET. سواء كنت مبتدئًا أو مطورًا متمرسًا، سيرشدك هذا الدليل خلال كل خطوة بطريقة محادثة وجذابة. هل أنت مستعد للبدء؟ لنبدأ!

## المتطلبات الأساسية

قبل أن ننتقل إلى البرمجة، دعنا نتأكد من أن لديك كل ما تحتاجه:

1.  مكتبة Aspose.PDF لـ .NET: يمكنك تنزيلها من[هنا](https://releases.aspose.com/pdf/net/) أو احصل على نسخة تجريبية مجانية من نفس الرابط. للشراء، توجه إلى[متجر اسبوس](https://purchase.aspose.com/buy).
2. .NET Framework: ستحتاج إلى بيئة تطوير .NET عاملة مثل Visual Studio.
3. ملف PDF: ستحتاج إلى ملف PDF نموذجي حيث يمكننا البحث عن النص واستخراجه. في هذا البرنامج التعليمي، لنفترض أن اسم الملف هو`SearchAndGetTextPage.pdf`.

## استيراد الحزم

أولاً وقبل كل شيء، نحتاج إلى استيراد مساحات الأسماء اللازمة للعمل مع Aspose.PDF لـ .NET. تأكد من تضمينها في الجزء العلوي من الكود الخاص بك.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، فلنبدأ في تقسيم الكود خطوة بخطوة. تم توضيح كل خطوة بوضوح لتسهيل متابعتها.

## الخطوة 1: تعيين المسار إلى دليل المستندات الخاص بك

قبل التفاعل مع ملف PDF الخاص بك، ستحتاج إلى تحديد المسار الذي سيتم تخزين مستند PDF الخاص بك فيه. وهذا يضمن أن يتمكن البرنامج من الوصول إلى الملف.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: هذا هو المسار إلى المجلد الذي يتم تخزين ملفات PDF فيه. استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي الذي يقع فيه ملف PDF.

## الخطوة 2: تحميل مستند PDF

الخطوة التالية هي تحميل مستند PDF إلى الذاكرة حتى تتمكن من العمل عليه. وإليك الطريقة:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- المستند: هذه هي فئة Aspose.PDF التي تقوم بتحميل ملف PDF.
- pdfDocument: المتغير الذي سيتم تخزين ملف PDF فيه بعد تحميله.

## الخطوة 3: إنشاء كائن امتصاص النص

 ال`TextFragmentAbsorber`تتيح لك الفئة البحث عن نص معين داخل ملف PDF. دعنا ننشئ مثيلًا لهذه الفئة للعثور على جميع مثيلات عبارة بحث معينة.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: هذه الفئة مسؤولة عن العثور على النص واستخراجه من ملف PDF.
- "الشكل": استبدل هذا بأي نص تريد البحث عنه داخل ملف PDF.

## الخطوة 4: تطبيق Text Absorber على ملف PDF بأكمله

بمجرد إعداد ممتص النص، ستحتاج إلى إخبار البرنامج بالبحث خلال جميع صفحات ملف PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): تطبق هذه الطريقة ممتص النص على ملف PDF، وتفحص كل صفحة بحثًا عن النص الذي حددته.

## الخطوة 5: استرجاع النص المستخرج وتكراره

الآن بعد أن قمنا بمسح ملف PDF، حان الوقت لاسترجاع النتائج وعرضها. سنستعرض أجزاء النص المستخرجة.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: تحتوي هذه المجموعة على جميع حالات أجزاء النص التي تم العثور عليها بواسطة ممتص النص.

## الخطوة 6: تكرار كل جزء واستخراج البيانات

سنقوم الآن بالمرور عبر`textFragmentCollection` واستخراج خصائص مختلفة لكل جزء من النص، مثل موضعه، وتفاصيل الخط، واللون.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- جزء نصي: يحتوي كل جزء على أجزاء من النص الموجود.
- جزء النص: يمكن لكل جزء أن يحتوي على أجزاء متعددة تمثل أجزاء مختلفة من النص.
- حالة النص: توفر معلومات مفصلة حول الخط والحجم واللون الخاص بالنص.

في هذه الحلقة، نقوم بطباعة التفاصيل مثل النص الفعلي، وموضعه (إحداثيات X وY)، والخط، وما إذا كان الخط مضمنًا في ملف PDF، ولون مقدمة النص.

## خاتمة

والآن، لقد نجحت في البحث عن نص واستخراجه من ملف PDF باستخدام Aspose.PDF for .NET. إنه لأمر مذهل مدى المرونة التي تتمتع بها مع هذه المكتبة. سواء كنت بحاجة إلى البحث عن نص معين في مستند كبير، أو استخراجه، أو تحليل خصائصه، فإن Aspose.PDF يجعل الأمر سهلاً. بالإضافة إلى ذلك، بفضل الكود الذي قمنا بتغطيته، ستكون مجهزًا جيدًا لتكييفه مع احتياجاتك. 

## الأسئلة الشائعة

### هل يمكنني البحث عن عدة عبارات في وقت واحد؟  
 نعم، يمكنك تعديل الكود للبحث عن عبارات متعددة عن طريق إنشاء عبارات متعددة`TextFragmentAbsorber` أشياء.

### كيف يمكنني استخراج النص من صفحة معينة؟  
 يمكنك استهداف صفحة معينة من خلال تطبيق`TextFragmentAbsorber` إلى صفحة واحدة بدلاً من المستند بأكمله. على سبيل المثال:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### هل Aspose.PDF لـ .NET مجاني؟  
 Aspose.PDF هو منتج تجاري، ولكن يمكنك استخدامه مع[نسخة تجريبية مجانية](https://releases.aspose.com/).

### هل يمكنني استخراج الصور من ملف PDF باستخدام Aspose.PDF؟  
 نعم، يسمح لك برنامج Aspose.PDF باستخراج الصور بالإضافة إلى النص. تحقق من[التوثيق](https://reference.aspose.com/pdf/net/) لمزيد من التفاصيل.

### ماذا لو كنت بحاجة إلى مزيد من المساعدة أو الدعم؟  
 يمكنك دائمًا الحصول على المساعدة من[منتدى دعم Aspose](https://forum.aspose.com/c/pdf/10).