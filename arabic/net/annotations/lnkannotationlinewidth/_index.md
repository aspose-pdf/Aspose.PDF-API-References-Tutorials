---
title: عرض خط التعليق التوضيحي lnk
linktitle: عرض خط التعليق التوضيحي lnk
second_title: Aspose.PDF لمرجع .NET API
description: توفر هذه المقالة دليلاً خطوة بخطوة لتعيين عرض خط التعليق التوضيحي lnk باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF هي أداة قوية ومستخدمة على نطاق واسع للعمل مع ملفات PDF في تطبيقات .NET. يوفر مجموعة متنوعة من الميزات لإنشاء ملفات PDF وتحريرها ومعالجتها ، بما في ذلك القدرة على إضافة التعليقات التوضيحية إلى الصفحات. في هذا البرنامج التعليمي ، سنشرح كيفية تعيين عرض خط التعليق التوضيحي للرابط باستخدام Aspose.PDF لـ .NET.

بمجرد حصولك على هذه المتطلبات الأساسية ، قم بإنشاء مشروع تطبيق وحدة تحكم جديد في Visual Studio. ثم قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET عن طريق النقر بزر الماوس الأيمن على المشروع في Solution Explorer ، واختيار "Manage NuGet Packages" ، والبحث عن Aspose.PDF في NuGet Package Manager.

لإضافة تعليق توضيحي لـ lnk إلى مستند PDF ، اتبع الخطوات التالية:

##  الخطوة 1: إنشاء ملف`Document` object.
```csharp
Document doc = new Document();
```
## الخطوة 2: أضف صفحة جديدة إلى المستند.
```csharp
doc.Pages.Add();
```
##  الخطوة 3: قم بإنشاء قائمة بملفات`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  الخطوة 4: إنشاء ملف`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## الخطوة 5: إنشاء ملف`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
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
##  الخطوة 7: إنشاء ملف`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## الخطوة 8: حدد موضوع التعليق التوضيحي وعنوانه.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## الخطوة 9: اضبط لون التعليق التوضيحي.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  الخطوة 10: إنشاء ملف`Border` object that defines the properties of the annotation's border.
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
### يعرض المثال lnk Annotation Line Width مع Aspose.PDF for .NET

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
