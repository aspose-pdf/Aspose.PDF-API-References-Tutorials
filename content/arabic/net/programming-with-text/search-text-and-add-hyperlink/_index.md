---
title: البحث عن نص وإضافة ارتباط تشعبي
linktitle: البحث عن نص وإضافة ارتباط تشعبي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن نص في ملف PDF وإضافة ارتباطات تشعبية إلى النص الذي تم العثور عليه وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 450
url: /ar/net/programming-with-text/search-text-and-add-hyperlink/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص محدد في مستند PDF وإضافة ارتباط تشعبي إلى النص الذي تم العثور عليه وحفظ المستند المعدل. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل متابعة البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف ما يلي باستخدام التوجيهات في بداية ملف C# الخاص بك لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: إنشاء TextFragmentAbsorter

 إنشاء`TextFragmentAbsorber` كائن للعثور على كافة مثيلات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 يستبدل`"\\d{4}-\\d{4}"` بنمط التعبير العادي الذي تريده.

## الخطوة 5: تمكين البحث بالتعبير العادي

 تمكين البحث بالتعبير العادي عن طريق تعيين`TextSearchOptions` خاصية الامتصاص:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## الخطوة 6: افتح مستند PDF واربطه

 إنشاء`PdfContentEditor` الكائن وربطه بملف PDF المصدر:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 يستبدل`"SearchRegularExpressionPage.pdf"` بالاسم الفعلي لملف PDF الخاص بك.

## الخطوة 7: قبول الممتص للصفحة

قبول الممتص للصفحة المطلوبة من المستند:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 يستبدل`1` مع رقم الصفحة المطلوبة

## الخطوة 8: إضافة ارتباطات تشعبية إلى النص الذي تم العثور عليه

قم بالمراجعة عبر أجزاء النص المستردة وأضف روابط تشعبية إليها:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // قم بإنشاء مستطيل بناءً على موضع جزء النص
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //أضف رابط الويب إلى المستطيل
    editor.CreateWebLink(rect, "http://www.aspose.com"، 1، System.Drawing.Color.Blue)؛
}
```

 يستبدل`"http://www.aspose.com"` باستخدام عنوان URL للارتباط التشعبي المطلوب.

## الخطوة 9: احفظ وأغلق المستند المعدل

احفظ المستند المعدل وأغلق المحرر:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 تأكد من استبدال`"SearchTextAndAddHyperlink_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر للبحث عن نص وإضافة ارتباط تشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء كائن ممتص للعثور على كافة مثيلات عبارة البحث المدخلة
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// تمكين البحث بالتعبير العادي
absorber.TextSearchOptions = new TextSearchOptions(true);
// افتح المستند
PdfContentEditor editor = new PdfContentEditor();
// ربط ملف PDF المصدر
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// قبول الممتص للصفحة
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// حلقة من خلال الشظايا
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com"، 1، أزرق، اسم الإجراء)؛
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث عن نص معين في مستند PDF، وإضافة ارتباطات تشعبية إلى النص الذي تم العثور عليه، وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إعداد المشروع وحتى تنفيذ الإجراءات المطلوبة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لمعالجة النص وإضافة ارتباطات تشعبية في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن نص وإضافة ارتباط تشعبي"؟

ج: يهدف البرنامج التعليمي "Search Text And Add Hyperlink" إلى توضيح كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص محدد داخل مستند PDF، وإضافة ارتباطات تشعبية إلى النص الذي تم العثور عليه، ثم حفظ المستند المعدل. يوفر البرنامج التعليمي دليلاً شاملاً وعينات من أكواد C# لتوضيح العملية خطوة بخطوة.

#### س: كيف يساعد هذا البرنامج التعليمي في إضافة ارتباطات تشعبية إلى نص معين في مستند PDF؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية استخدام مكتبة Aspose.PDF لتحديد موقع نص معين في مستند PDF، وتطبيق ارتباط تشعبي على النص المحدد، وحفظ ملف PDF المعدل. ويغطي الخطوات الأساسية مثل إعداد المشروع، وتحميل المستند، وتمكين البحث بالتعبير العادي، وإضافة ارتباطات تشعبية إلى النص الذي تم العثور عليه.

#### س: ما هي المتطلبات الأساسية اللازمة لمتابعة هذا البرنامج التعليمي؟

ج: قبل أن تبدأ، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET، والتي يمكن الحصول عليها من موقع Aspose على الويب أو تثبيتها باستخدام NuGet في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE). بعد ذلك، قم بإضافة مرجع إلى مكتبة Aspose.PDF for .NET، والتي ستمكنك من الاستفادة من إمكانيات المكتبة في مشروعك.

#### س: هل يمكنني إضافة ارتباطات تشعبية إلى نص محدد باستخدام هذا البرنامج التعليمي؟

ج: نعم، يركز هذا البرنامج التعليمي بشكل خاص على إضافة ارتباطات تشعبية إلى نص معين في مستند PDF. ويوضح كيفية البحث عن النص المطلوب واستخراجه باستخدام التعبيرات العادية، وإنشاء ارتباطات تشعبية مرتبطة بأجزاء النص، وحفظ ملف PDF المعدل.

#### س: كيف يمكنني تحديد النص الذي أريد البحث عنه وإضافة ارتباط تشعبي إليه؟

 ج: لتحديد النص الذي تريد البحث عنه وإضافة ارتباط تشعبي إليه، قم بإنشاء ملف`TextFragmentAbsorber` كائن وتعيين نمطه باستخدام`Text` معامل. استبدل النمط الافتراضي`"\\d{4}-\\d{4}"` في رمز البرنامج التعليمي بنمط التعبير العادي الذي تريده.

#### س: كيف يمكنني تمكين البحث بالتعبير العادي عن النص؟

 ج: يتم تمكين البحث عن التعبير العادي عن طريق إنشاء ملف`TextSearchOptions` الكائن وتحديد قيمته`true` . قم بتعيين هذا الكائن إلى`TextSearchOptions` ملكية`TextFragmentAbsorber` مثال. وهذا يضمن تطبيق نمط التعبير العادي أثناء البحث عن النص.

#### س: كيف يمكنني إضافة ارتباطات تشعبية إلى النص الذي تم العثور عليه؟

 ج: بعد تحديد أجزاء النص باستخدام`TextFragmentAbsorber` ، يوفر البرنامج التعليمي حلقة للتكرار عبر هذه الأجزاء. بالنسبة لكل جزء من النص، يوضح البرنامج التعليمي كيفية تعيين لون النص إلى اللون الأزرق وإنشاء رابط تشعبي باستخدام`CreateWebLink` طريقة.

#### س: ما هي خطوات حفظ ملف PDF المعدل بالارتباطات التشعبية؟

 ج: بعد إضافة الارتباطات التشعبية إلى أجزاء النص المطلوبة، استخدم ملف`PdfContentEditor` فئة لحفظ المستند المعدل. يعرض نموذج التعليمات البرمجية الخاص بالبرنامج التعليمي كيفية حفظ ملف PDF المحرر وإغلاق المحرر وعرض رسالة النجاح.