---
title: البحث عن النص وإضافة ارتباط تشعبي
linktitle: البحث عن النص وإضافة ارتباط تشعبي
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن نص في ملف PDF، وإضافة ارتباطات تشعبية إلى النص الموجود، وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 450
url: /ar/net/programming-with-text/search-text-and-add-hyperlink/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF for .NET للبحث عن نص معين في مستند PDF، وإضافة ارتباط تشعبي إلى النص الموجود، وحفظ المستند المعدل. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل المتابعة بالبرنامج التعليمي، تأكد من توفر ما يلي:

- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لتثبيتها في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات الأساسية الضرورية

أضف التوجيهات التالية في بداية ملف C# الخاص بك لاستيراد المساحات المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: إنشاء TextFragmentAbsorber

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 يستبدل`"\\d{4}-\\d{4}"` مع نمط التعبير العادي المطلوب.

## الخطوة 5: تمكين البحث عن التعبيرات العادية

 تمكين البحث عن التعبيرات العادية عن طريق ضبط`TextSearchOptions` خصائص الممتص:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## الخطوة 6: افتح مستند PDF وقم بربطه

 إنشاء`PdfContentEditor` الكائن وربطه بملف PDF المصدر:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 يستبدل`"SearchRegularExpressionPage.pdf"` مع الاسم الفعلي لملف PDF الخاص بك.

## الخطوة 7: قبول الممتص للصفحة

اقبل الممتص للصفحة المطلوبة من المستند:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 يستبدل`1` مع رقم الصفحة المطلوب.

## الخطوة 8: إضافة ارتباطات تشعبية إلى النص الموجود

قم بالتنقل عبر أجزاء النص المسترجعة وأضف ارتباطات تشعبية إليها:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // إنشاء مستطيل بناءً على موضع جزء النص
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //أضف رابط ويب إلى المستطيل
    editor.CreateWebLink(rect, "http://www.aspose.com"، 1، System.Drawing.Color.Blue)؛
}
```

 يستبدل`"http://www.aspose.com"` مع عنوان URL للرابط التشعبي المطلوب.

## الخطوة 9: احفظ وأغلق المستند المعدل

احفظ المستند المعدل وأغلق المحرر:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 تأكد من الاستبدال`"SearchTextAndAddHyperlink_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر للبحث عن نص وإضافة ارتباط تشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن امتصاص للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// تمكين البحث عن التعبيرات العادية
absorber.TextSearchOptions = new TextSearchOptions(true);
// فتح المستند
PdfContentEditor editor = new PdfContentEditor();
// ربط ملف PDF المصدر
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// تقبل الممتص للصفحة
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// التنقل عبر الشظايا
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com، 1، أزرق، اسم الإجراء)؛
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية البحث عن نص معين في مستند PDF، وإضافة ارتباطات تشعبية إلى النص الموجود، وحفظ المستند المعدل باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إعداد المشروع إلى تنفيذ الإجراءات المطلوبة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لمعالجة النص وإضافة ارتباطات تشعبية في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن النص وإضافة ارتباط تشعبي"؟

أ: يهدف البرنامج التعليمي "البحث عن نص وإضافة ارتباط تشعبي" إلى توضيح كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص معين داخل مستند PDF، وإضافة ارتباطات تشعبية إلى النص الموجود، ثم حفظ المستند المعدل. يوفر البرنامج التعليمي دليلاً شاملاً وعينات من أكواد C# لتوضيح العملية خطوة بخطوة.

#### س: كيف يساعد هذا البرنامج التعليمي في إضافة ارتباطات تشعبية إلى نص محدد في مستند PDF؟

أ: يرشدك هذا البرنامج التعليمي خلال عملية استخدام مكتبة Aspose.PDF لتحديد موقع نص معين في مستند PDF، وتطبيق ارتباط تشعبي على النص المحدد، وحفظ ملف PDF المعدل. ويغطي الخطوات الأساسية مثل إعداد المشروع، وتحميل المستند، وتمكين البحث باستخدام التعبيرات العادية، وإضافة ارتباطات تشعبية إلى النص الموجود.

#### س: ما هي المتطلبات الأساسية اللازمة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة، والتي يمكن الحصول عليها من موقع Aspose على الويب أو تثبيتها باستخدام NuGet في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

أ: ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE). ثم أضف مرجعًا إلى مكتبة Aspose.PDF for .NET، مما سيمكنك من الاستفادة من إمكانيات المكتبة في مشروعك.

#### س: هل يمكنني إضافة ارتباطات تشعبية إلى نص محدد باستخدام هذا البرنامج التعليمي؟

ج: نعم، يركز هذا البرنامج التعليمي بشكل خاص على إضافة ارتباطات تشعبية إلى نص معين في مستند PDF. ويوضح كيفية العثور على النص المطلوب واستخراجه باستخدام التعبيرات العادية، وإنشاء ارتباطات تشعبية مرتبطة بأجزاء النص، وحفظ ملف PDF المعدل.

#### س: كيف أقوم بتحديد النص الذي أريد البحث عنه وإضافة ارتباط تشعبي إليه؟

 أ: لتحديد النص الذي تريد البحث عنه وإضافة ارتباط تشعبي إليه، قم بإنشاء`TextFragmentAbsorber` الكائن وتعيين نمطه باستخدام`Text` المعلمة. استبدال النمط الافتراضي`"\\d{4}-\\d{4}"` في كود البرنامج التعليمي باستخدام نمط التعبير العادي المطلوب.

#### س: كيف يمكنني تمكين البحث عن التعبيرات العادية للنص؟

 أ: يتم تمكين البحث عن التعبيرات العادية عن طريق إنشاء`TextSearchOptions` الكائن وتعيين قيمته إلى`true` . تعيين هذا الكائن إلى`TextSearchOptions` ممتلكات`TextFragmentAbsorber` يضمن هذا تطبيق نمط التعبير العادي أثناء البحث عن النص.

#### س: كيف أضيف ارتباطات تشعبية إلى النص الموجود؟

 أ: بعد تحديد أجزاء النص باستخدام`TextFragmentAbsorber` يوفر البرنامج التعليمي حلقة للتكرار خلال هذه الأجزاء. لكل جزء نصي، يوضح البرنامج التعليمي كيفية تعيين لون النص إلى اللون الأزرق وإنشاء ارتباط تشعبي باستخدام`CreateWebLink` طريقة.

#### س: ما هي خطوات حفظ ملف PDF المعدل مع الروابط التشعبية؟

 أ: بعد إضافة ارتباطات تشعبية إلى أجزاء النص المطلوبة، استخدم`PdfContentEditor` فئة لحفظ المستند المعدّل. يوضح كود العينة في البرنامج التعليمي كيفية حفظ ملف PDF المحرر وإغلاق المحرر وعرض رسالة النجاح.