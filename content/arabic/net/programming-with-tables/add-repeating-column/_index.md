---
title: إضافة عمود متكرر في مستند PDF
linktitle: إضافة عمود متكرر في مستند PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة أعمدة متكررة إلى مستندات PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع أمثلة وأكواد. مثالي للمطورين.
type: docs
weight: 20
url: /ar/net/programming-with-tables/add-repeating-column/
---
## مقدمة

إذا كنت تعمل مع مستندات PDF وتحتاج إلى إضافة أعمدة متكررة، فأنت في المكان الصحيح! باستخدام Aspose.PDF for .NET، يمكنك بسهولة إدارة الجداول والمحتوى داخل ملف PDF. سواء كنت تقوم ببناء تقارير ديناميكية أو فواتير أو أي مستند منظم آخر، فإن الأعمدة المتكررة يمكن أن تكون بمثابة تغيير جذري في تنظيم البيانات. دعنا نتعمق في دليل خطوة بخطوة حول كيفية إضافة أعمدة متكررة إلى مستند PDF.

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، دعنا نتأكد من إعداد كل شيء:

- Aspose.PDF لـ .NET: يجب أن يكون لديك مكتبة Aspose.PDF لـ .NET مثبتة في مشروعك.
- [تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net/)
- [نسخة تجريبية مجانية](https://releases.aspose.com/)
- بيئة التطوير: تأكد من تثبيت IDE متوافق مع .NET مثل Visual Studio.
- الفهم الأساسي للغة C#: على الرغم من أننا سنقوم بتقسيم كل شيء، إلا أن الفهم الأساسي للغة C# سيساعدك على المتابعة بسلاسة.
  
 إذا لم يكن لديك Aspose.PDF لـ .NET حتى الآن، فيمكنك الحصول على[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للبدء في استكشاف ميزاته.

## استيراد الحزم

للبدء، تحتاج إلى استيراد المساحات الأساسية اللازمة من Aspose.PDF لـ .NET. إليك كيفية القيام بذلك:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

توفر هذه الحزم الفئات والطرق الأساسية المطلوبة للعمل مع مستندات PDF ومعالجة الجداول.

الآن، دعنا نقسم العملية إلى عدة خطوات لإضافة أعمدة متكررة إلى مستند PDF. تابع معنا!

## الخطوة 1: تعيين المسار إلى دليل المستندات الخاص بك

قبل إنشاء أو معالجة أي ملفات، نحتاج إلى تحديد المسار الذي سيتم حفظ ملف PDF الناتج فيه. في مشروع C# الخاص بك، اضبط مسار الدليل حيث سيتم حفظ ملفاتك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 يشير هذا المسار إلى الدليل الذي سيتم حفظ ملف PDF الناتج فيه. استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي على جهازك.

## الخطوة 2: إنشاء مستند PDF جديد

 للبدء، قم بإنشاء مثيل جديد`Document` الكائن. سيكون هذا بمثابة الحاوية لجميع الصفحات والمحتوى داخل ملف PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 هنا، قمنا بإنشاء مستند PDF جديد وأضفنا إليه صفحة فارغة.`doc.Pages.Add()` تقوم هذه الطريقة بإدراج صفحة جديدة في المستند.

## الخطوة 3: إنشاء الجدول الخارجي

بعد ذلك، نقوم بإنشاء جدول خارجي. سيغطي هذا الجدول عرض الصفحة بالكامل وسيعمل كحاوية للجداول الأخرى، بما في ذلك الجدول الذي سيحتوي على الأعمدة المتكررة.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 لقد وضعنا`ColumnWidths` قم بتوسيع الخاصية إلى "100%"، مما يعني أن الجدول سوف يمتد عبر عرض الصفحة بالكامل.

## الخطوة 4: إنشاء الجدول الداخلي

 الآن، دعنا ننشئ الجدول الداخلي، والذي سيحتوي على أعمدة متكررة. الخصائص الرئيسية هنا هي`Broken` ، مما يسمح للجدول بالاستمرار عبر نفس الصفحة، و`ColumnAdjustment`، الذي يضبط عرض الأعمدة تلقائيًا ليناسب المحتوى.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

سيتم تضمين هذا الجدول الداخلي ضمن الجدول الخارجي.

## الخطوة 5: إضافة الجداول إلى الصفحة

الآن بعد أن أصبح لدينا كل من الجداول الخارجية والداخلية جاهزة، فلنقم بإضافتها إلى الصفحة. تضمن هذه الخطوة تضمين الجداول في بنية المستند.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 هنا، أضفنا`outerTable` إلى الصفحة، ثم داخل الجدول الخارجي، قمنا بتضمين`mytable` بالإضافة إلى ذلك، قمنا بتعيين`RepeatingColumnsCount`إلى 5، لتحديد عدد الأعمدة التي يجب تكرارها عند إضافة البيانات.

## الخطوة 6: إضافة صف الرأس

الآن حان الوقت لإضافة العناوين إلى الجدول. يوفر صف العناوين السياق للبيانات ويساعد في تنظيم الأعمدة. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

تضيف مقتطفات التعليمات البرمجية هذه الصف الأول (الذي سنستخدمه كعناوين)، وتملأه بالخلايا التي تحتوي على نص مثل "رأس 1"، "رأس 2"، وما إلى ذلك.

## الخطوة 7: إضافة صفوف البيانات

أخيرًا، يمكننا إضافة بعض البيانات إلى الجدول. تعمل هذه الحلقة على إنشاء صفوف ديناميكيًا وملء الخلايا بالمحتوى:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

تتكرر الحلقة ست مرات، وتضيف الصفوف وتملأ كل خلية ببيانات العمود المقابلة (على سبيل المثال، "العمود 1، 1"، "العمود 2، 2"، وما إلى ذلك).

## الخطوة 8: حفظ المستند

بمجرد إضافة كافة الصفوف والأعمدة، فإن الخطوة الأخيرة هي حفظ المستند في مسار الملف المحدد.

```csharp
doc.Save(outFile);
```

لقد تم الآن حفظ مستندك مع الأعمدة المتكررة!

## خاتمة

ها أنت ذا! باتباع هذه الخطوات البسيطة، يمكنك إنشاء مستند PDF بأعمدة متكررة باستخدام Aspose.PDF for .NET. ومن خلال الاستفادة من مرونة الجداول المتداخلة، يمكنك تحقيق تخطيطات معقدة تجعل ملفات PDF تبدو احترافية ومنظمة. جرّب هذا في مشروعك التالي واستكشف الإمكانات الكاملة لـ Aspose.PDF لتلبية احتياجاتك من إنشاء ملفات PDF.

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة قوية تسمح للمطورين بإنشاء مستندات PDF وتحريرها وإدارتها برمجيًا.

### هل يمكنني تعديل عدد الأعمدة المتكررة بشكل ديناميكي؟
 نعم، يمكنك تغيير عدد الأعمدة المتكررة عن طريق تعديل`RepeatingColumnsCount` ملكية.

### كيف يمكنني التقدم بطلب ترخيص لـ Aspose.PDF لـ .NET؟
 يمكنك تطبيق ترخيص من ملف أو دفق باتباع[التوثيق](https://reference.aspose.com/pdf/net/).

### هل من الممكن إضافة الصور إلى خلايا الجدول؟
نعم، يدعم Aspose.PDF لـ .NET إضافة أنواع مختلفة من المحتوى، بما في ذلك الصور، إلى خلايا الجدول.

### هل يمكنني تخصيص تخطيط الجدول بشكل أكبر؟
بالتأكيد! يوفر Aspose.PDF ميزات شاملة لتخصيص أنماط الجدول، بما في ذلك الحدود والحشو والمحاذاة والمزيد.