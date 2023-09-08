---
title: الحصول على الموارد من الشرح
linktitle: الحصول على الموارد من الشرح
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استرداد مصدر التعليق التوضيحي باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 90
url: /ar/net/annotations/getresourceofannotation/
---
يوضح المثال كيفية الحصول على مصدر التعليقات التوضيحية باستخدام Aspose.PDF لـ .NET. للحصول على مصدر التعليق التوضيحي باستخدام Aspose.PDF لـ .NET، اتبع الخطوات التالية:

## الخطوة 1: قم بتعيين مسار الدليل الذي يوجد به المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF الذي يحتوي على التعليق التوضيحي الذي تريد الحصول على مصدره.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## الخطوة 3: إنشاء تعليق توضيحي.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## الخطوة 4: أضف التعليق التوضيحي إلى صفحة في المستند.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## الخطوة 5: احفظ المستند.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## الخطوة 6: افتح المستند المعدل.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## الخطوة 7: احصل على إجراء التعليق التوضيحي.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## الخطوة 7: احصل على عرض الإجراء.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## الخطوة 8: احصل على مقطع الوسائط.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## الخطوة 9: الحصول على مواصفات الملف.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## الخطوة 10: قراءة بيانات الوسائط.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## الخطوة 11: اطبع اسم التسليم وعملية التسليم.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

باتباع هذه الخطوات، يمكنك بسهولة الحصول على مصدر التعليق التوضيحي في مستند PDF باستخدام Aspose.PDF لـ .NET.

### مثال على التعليمات البرمجية المصدر للحصول على مورد التعليق التوضيحي باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//إنشاء تعليق توضيحي
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// حفظ المستند
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// افتح المستند
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//الحصول على إجراء للتعليق التوضيحي
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//الحصول على التسليم لإجراء التسليم
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// مقطع الوسائط
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//يمكن الوصول إلى بيانات الوسائط في FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية الحصول على مصدر تعليق توضيحي معين من مستند PDF باستخدام Aspose.PDF لـ .NET. من خلال اتباع الدليل خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين الوصول بسهولة إلى التعليقات التوضيحية وإدارتها، بما في ذلك التعليقات التوضيحية الخاصة بالتسليم، في مستندات PDF الخاصة بهم.

### الأسئلة الشائعة

#### س: ما هو التسليم في سياق التعليقات التوضيحية بتنسيق PDF؟

ج: في سياق التعليقات التوضيحية بتنسيق PDF، يعتبر التسليم عرضًا تقديميًا لمحتوى الوسائط المتعددة. فهو يسمح بتضمين الوسائط المتعددة، مثل الصوت أو الفيديو، داخل مستند PDF. يحدد التعليق التوضيحي للتسليم الوسائط التي سيتم تقديمها وكيفية تشغيلها.

#### س: هل يمكنني الحصول على اسم ملف الوسائط المرتبط بالتعليق التوضيحي للتسليم؟

ج: نعم، يمكنك الحصول على اسم ملف الوسائط المرتبط بالتعليق التوضيحي للتسليم باستخدام Aspose.PDF لـ .NET. يمكن الوصول إلى اسم ملف الوسائط من خلال`FileSpecification` التابع`MediaClip` هدف.

#### س: هل يمكن لـ Aspose.PDF لـ .NET استخراج ملفات الوسائط من تعليق توضيحي للتسليم؟

ج: نعم، يمكن لـ Aspose.PDF for .NET استخراج بيانات الوسائط من تعليق توضيحي للتسليم، والذي يتضمن محتوى صوتي أو فيديو، وحفظه كملف منفصل.

#### س: كيف يمكنني الوصول إلى بيانات الوسائط الخاصة بالتعليق التوضيحي للتسليم؟

 ج: يمكن الوصول إلى بيانات الوسائط الخاصة بالتعليق التوضيحي للتسليم من خلال`FileSpecification.Contents` ملكية`MediaClipData` هدف.

#### س: هل يمكنني تعديل الوسائط المرتبطة بالتعليق التوضيحي للتسليم باستخدام Aspose.PDF لـ .NET؟

ج: يوفر Aspose.PDF for .NET طرقًا للوصول إلى بيانات الوسائط المرتبطة بالتعليق التوضيحي للتسليم وتعديلها. يمكنك تحديث أو استبدال ملف الوسائط الذي يستخدمه التعليق التوضيحي للتسليم.