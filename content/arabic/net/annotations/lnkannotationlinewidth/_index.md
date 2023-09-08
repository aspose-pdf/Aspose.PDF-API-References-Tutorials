---
title: عرض خط التعليق التوضيحي lnk
linktitle: عرض خط التعليق التوضيحي lnk
second_title: Aspose.PDF لمرجع .NET API
description: توفر هذه المقالة دليلاً خطوة بخطوة لتعيين عرض سطر التعليق التوضيحي lnk باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF هي أداة قوية ومستخدمة على نطاق واسع للعمل مع ملفات PDF في تطبيقات .NET. فهو يوفر مجموعة متنوعة من الميزات لإنشاء ملفات PDF وتحريرها ومعالجتها، بما في ذلك القدرة على إضافة التعليقات التوضيحية إلى الصفحات. سنشرح في هذا البرنامج التعليمي كيفية تعيين عرض سطر التعليق التوضيحي للارتباط باستخدام Aspose.PDF لـ .NET.

بمجرد حصولك على هذه المتطلبات الأساسية، قم بإنشاء مشروع تطبيق وحدة تحكم جديد في Visual Studio. بعد ذلك، قم بإضافة مرجع إلى مكتبة Aspose.PDF لـ .NET عن طريق النقر بزر الماوس الأيمن على المشروع في Solution Explorer، وتحديد "Manage NuGet Packages"، والبحث عن "Aspose.PDF" في NuGet Package Manager.

لإضافة تعليق توضيحي lnk إلى مستند PDF، اتبع الخطوات التالية:

##  الخطوة 1: إنشاء جديد`Document` object.
```csharp
Document doc = new Document();
```
## الخطوة 2: إضافة صفحة جديدة إلى المستند.
```csharp
doc.Pages.Add();
```
##  الخطوة 3: إنشاء قائمة`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  الخطوة 4: إنشاء جديد`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  الخطوة 5: إنشاء جديد`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## الخطوة 6: أضف الإيماءة إلى قائمة إيماءات الحبر.
```csharp
inkList.Add(gesture);
```
##  الخطوة 7: إنشاء جديد`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## الخطوة 8: قم بتعيين موضوع وعنوان التعليق التوضيحي.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## الخطوة 9: اضبط لون التعليق التوضيحي.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  الخطوة 10: إنشاء جديد`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## الخطوة 11: أضف التعليق التوضيحي إلى الصفحة.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## الخطوة 12: احفظ المستند في ملف.
```csharp
// حفظ ملف الإخراج
doc.Save(dataDir);


```
### يوضح المثال عرض خط التعليق التوضيحي lnk مع Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// حفظ ملف الإخراج
doc.Save(dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تعيين عرض خط التعليق التوضيحي للارتباط في مستند PDF باستخدام Aspose.PDF لـ .NET. يوفر Aspose.PDF for .NET نطاقًا واسعًا من الأدوات والميزات للعمل مع مستندات PDF، بما في ذلك القدرة على إنشاء التعليقات التوضيحية للارتباط وتخصيصها. من خلال اتباع الدليل خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين بسهولة إضافة روابط تفاعلية إلى مستندات PDF الخاصة بهم، مما يعزز تجربة المستخدم والتفاعلية لتطبيقاتهم. Aspose.PDF for .NET هي مكتبة متعددة الاستخدامات تمكن مطوري .NET من العمل مع ملفات PDF بكفاءة وفعالية.

### الأسئلة الشائعة

#### س: ما هو التعليق التوضيحي للارتباط في مستند PDF؟

ج: يعد التعليق التوضيحي للارتباط في مستند PDF عنصرًا تفاعليًا يسمح لك بإنشاء ارتباطات تشعبية أو إجراءات توجه المستخدم إلى موقع آخر داخل نفس المستند، أو موقع ويب خارجي، أو مستند PDF مختلف.

#### س: كيف يمكنني ضبط عرض سطر التعليق التوضيحي للارتباط باستخدام Aspose.PDF لـ .NET؟

ج: لتعيين عرض سطر التعليق التوضيحي للارتباط باستخدام Aspose.PDF لـ .NET، يمكنك إنشاء`InkAnnotation` الكائن وحدد خاصية عرض الخط.

#### س: ما هي الخصائص التي يمكن تخصيصها للتعليق التوضيحي للارتباط في Aspose.PDF لـ .NET؟

ج: يمكنك تخصيص خصائص مختلفة للتعليق التوضيحي للارتباط في Aspose.PDF لـ .NET، مثل موقعه وحجمه ولونه وخصائص الحدود (العرض والنمط ونمط الشرطة والتأثير) والموضوع والعنوان والرؤية.

#### س: هل يمكنني إنشاء تعليق توضيحي للارتباط يحتوي على إيماءات حبر متعددة؟

 ج: نعم، يمكنك إنشاء تعليق توضيحي للارتباط يحتوي على إيماءات حبر متعددة عن طريق إضافة عدة إيماءات`Point` المصفوفات إلى`InkAnnotation` هدف.

#### س: كيف يمكنني إضافة تعليق توضيحي للارتباط إلى صفحة معينة من مستند PDF؟

 ج: لإضافة تعليق توضيحي للارتباط إلى صفحة معينة من مستند PDF، يتعين عليك تحديد رقم الصفحة عند إنشاء الملف`InkAnnotation` هدف. على سبيل المثال،`new InkAnnotation(doc.Pages[1], ...)` يضيف تعليقًا توضيحيًا للارتباط إلى الصفحة الأولى.