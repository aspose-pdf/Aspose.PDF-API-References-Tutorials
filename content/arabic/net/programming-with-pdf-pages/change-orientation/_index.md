---
title: تغيير التوجه
linktitle: تغيير التوجه
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لتغيير اتجاه الصفحة في ملف PDF باستخدام Aspose.PDF لـ .NET. من السهل اتباعه وتنفيذه في مشاريعك.
type: docs
weight: 10
url: /ar/net/programming-with-pdf-pages/change-orientation/
---
## مقدمة

هل سبق لك أن وجدت نفسك تواجه صعوبة في التعامل مع ملف PDF حيث يكون اتجاه الصفحة... غير صحيح؟ ربما تتعامل مع مستند تم مسحه ضوئيًا أو إنشاؤه بشكل غير صحيح، وتحتاج الصفحات إلى التدوير حتى يكون لها معنى. لحسن الحظ، يوفر Aspose.PDF for .NET طريقة سهلة وقوية للتعامل مع ملفات PDF بأي طريقة يمكن تخيلها تقريبًا—بما في ذلك تغيير اتجاه الصفحات. سواء كنت تريد التبديل من الوضع الرأسي إلى الأفقي أو العكس، فسيرشدك هذا الدليل خلال العملية خطوة بخطوة.

لذا، إذا كنت مستعدًا للبدء في تدوير صفحات PDF هذه بسهولة، فلنبدأ!

## المتطلبات الأساسية

قبل أن ندخل في تفاصيل تغيير اتجاه الصفحة في ملف PDF الخاص بك، دعنا نغطي سريعًا ما ستحتاج إليه:

-  Aspose.PDF لـ .NET: تأكد من تثبيت مكتبة Aspose.PDF لـ .NET. إذا لم تقم بذلك، يمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/).
- بيئة تطوير .NET: يمكنك استخدام Visual Studio، أو JetBrains Rider، أو أي بيئة تطوير متكاملة مفضلة للعمل مع .NET.
- المعرفة الأساسية بلغة C#: على الرغم من أن هذا الدليل واضح ومباشر، إلا أن بعض الفهم الأساسي للغة C# سيجعل متابعته أسهل.
- ملف PDF: يفترض المثال أدناه أن لديك ملف PDF يحتوي على عدة صفحات. إذا لم يكن لديك ملف PDF في متناول يدك، فقم بإنشاء أو تنزيل ملف PDF نموذجي للعمل عليه.

 أيضًا، إذا كنت قد بدأت للتو، فيمكنك تجربة Aspose.PDF مع[رخصة مؤقتة مجانية](https://purchase.aspose.com/temporary-license/) قبل اتخاذ القرار[شراء النسخة الكاملة](https://purchase.aspose.com/buy).

## استيراد مساحات الأسماء

قبل أن تتمكن من معالجة اتجاه الصفحات في ملف PDF، ستحتاج إلى استيراد المساحات الأساسية اللازمة في مشروع C# الخاص بك. تأكد من توفر ما يلي:

```csharp
using System.IO;
using Aspose.Pdf;
```

بعد استيراد هذا، دعنا ننتقل إلى الجزء الرئيسي من البرنامج التعليمي.

## الخطوة 1: تحميل مستند PDF

 أول شيء يتعين علينا القيام به هو تحميل ملف PDF الذي ترغب في تعديله. يمكنك استخدام`Document` استخدم الفئة من مساحة اسم Aspose.PDF لفتح ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 يقوم هذا السطر بتحميل ملف PDF من الدليل المحدد. تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لملفك.`"input.pdf"` هو ملف PDF الذي تريد تغيير اتجاهه.

## الخطوة 2: تكرار كل صفحة

 الآن بعد أن قمنا بتحميل المستند، فلننتقل عبر كل صفحة في ملف PDF. سنستخدم`foreach` حلقة للانتقال عبر كل صفحة، مما يسمح لنا بتطبيق تغيير الاتجاه على جميع الصفحات.

```csharp
foreach (Page page in doc.Pages)
{
    // التلاعب بكل صفحة
}
```

سوف تتكرر هذه الحلقة عبر جميع الصفحات الموجودة داخل المستند.

## الخطوة 3: الحصول على MediaBox الخاص بالصفحة

 كل صفحة في ملف PDF تحتوي على`MediaBox` الذي يحدد حدود الصفحة. نحتاج إلى الوصول إلى هذا لتحديد الاتجاه الحالي وتعديله.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 ال`MediaBox` يعطينا أبعاد الصفحة، مثل العرض والارتفاع وموقعها.

## الخطوة 4: تبديل العرض والارتفاع

لتغيير اتجاه الصفحة من عمودي إلى أفقي أو أفقي إلى عمودي، ما عليك سوى تبديل قيم العرض والارتفاع. ستؤدي هذه الخطوة إلى ضبط أبعاد الصفحة.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

يقوم هذا الكود بتبديل الارتفاع والعرض وإعادة وضع الزاوية اليسرى السفلية (`LLY`) بحيث يتناسب المحتوى بشكل أنيق بعد التدوير.

## الخطوة 5: تحديث MediaBox وCropBox

الآن بعد أن أصبح لدينا الارتفاع والعرض الجديدين، فلنطبق التغييرات على الصفحة`MediaBox` و`CropBox` . ال`CropBox` من الضروري أن تكون الوثيقة الأصلية تحتوي على مجموعة واحدة، مما يضمن عرض الصفحة بأكملها بشكل صحيح.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

تؤدي هذه الخطوة إلى تغيير حجم الصفحة استنادًا إلى الأبعاد الجديدة التي حسبناها للتو.

## الخطوة 6: تدوير الصفحة

أخيرًا، نضبط زاوية دوران الصفحة. يجعل Aspose.PDF هذا الأمر بسيطًا للغاية. يمكننا تدوير الصفحة بمقدار 90 درجة للتحول من الوضع الرأسي إلى الأفقي أو العكس.

```csharp
page.Rotate = Rotation.on90;
```

يقوم هذا الكود بتدوير الصفحة بمقدار 90 درجة، مما يؤدي إلى قلبها إلى الاتجاه المطلوب.

## الخطوة 7: احفظ ملف PDF الناتج

بعد تطبيق تغييرات الاتجاه على كافة الصفحات، نقوم بحفظ المستند المعدل في ملف جديد. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 تأكد من توفير اسم ملف جديد (في هذه الحالة،`ChangeOrientation_out.pdf`) لحفظ الناتج. بهذه الطريقة، لن تقوم باستبدال الملف الأصلي.

### خاتمة

والآن لديك كل ما تحتاج إليه! إن تغيير اتجاه الصفحة في ملف PDF باستخدام Aspose.PDF for .NET أمر بسيط للغاية، حيث يكفي تحميل المستند، والتنقل بين الصفحات، وضبط MediaBox، وحفظ الملف المحدث. سواء كنت تتعامل مع مستند تم مسحه ضوئيًا بشكل سيئ أو كنت بحاجة إلى تدوير الصفحات لتتناسب مع احتياجات التنسيق الخاصة بك، فإن هذا الدليل المفصل سيساعدك على حل هذه المشكلة.

## الأسئلة الشائعة

### هل يمكنني تدوير صفحات محددة بدلاً من جميع الصفحات في ملف PDF؟  
نعم، يمكنك تعديل الحلقة لاستهداف صفحات محددة باستخدام فهرسها بدلاً من تكرار جميع الصفحات.

###  ما هو`MediaBox`?  
 ال`MediaBox` يحدد حجم وشكل الصفحة في ملف PDF. وهو المكان الذي يتم فيه وضع محتوى الصفحة.

### هل يعمل Aspose.PDF for .NET مع تنسيقات الملفات الأخرى؟  
نعم، يمكن لبرنامج Aspose.PDF التعامل مع مجموعة متنوعة من تنسيقات الملفات مثل HTML وXML وXPS والمزيد.

### هل هناك نسخة مجانية من Aspose.PDF لـ .NET؟  
 نعم، يمكنك البدء بـ[نسخة تجريبية مجانية](https://releases.aspose.com/) أو اطلب[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).

### هل يمكنني التراجع عن التغييرات بعد حفظها؟  
بمجرد حفظ المستند، تصبح التغييرات دائمة. تأكد من العمل على نسخة أو الاحتفاظ بنسخة احتياطية من الملف الأصلي.