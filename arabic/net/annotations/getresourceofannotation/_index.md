---
title: احصل على مورد من التعليقات التوضيحية
linktitle: احصل على مورد من التعليقات التوضيحية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استرداد مورد أحد التعليقات التوضيحية باستخدام Aspose.PDF for .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 90
url: /ar/net/annotations/getresourceofannotation/
---

يوضح المثال كيفية الحصول على مورد التعليق التوضيحي باستخدام Aspose.PDF لـ .NET. للحصول على مورد أحد التعليقات التوضيحية باستخدام Aspose.PDF لـ .NET ، اتبع الخطوات التالية:

## حدد مسار الدليل حيث يوجد المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## افتح مستند PDF الذي يحتوي على التعليق التوضيحي الذي تريد الحصول على مصدره.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## أنشئ تعليقًا توضيحيًا.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## أضف التعليق التوضيحي إلى صفحة في المستند.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## احفظ المستند.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## افتح المستند المعدل.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## احصل على إجراء التعليق التوضيحي.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## احصل على أداء العمل.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## احصل على مقطع الوسائط.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## احصل على مواصفات الملف.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## اقرأ بيانات وسائل الإعلام.

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

## اطبع اسم التسليم وعملية التسليم.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

باتباع هذه الخطوات ، يمكنك بسهولة الحصول على مورد التعليق التوضيحي في مستند PDF باستخدام Aspose.PDF لـ .NET.

### مثال على التعليمات البرمجية المصدر للحصول على مورد من التعليقات التوضيحية باستخدام Aspose.PDF لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// افتح المستند
	Document doc = new Document(dataDir + "AddAnnotation.pdf");
	//أنشئ تعليقًا توضيحيًا
	ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
	doc.Pages[1].Annotations.Add(sa);
	// حفظ Doucument
	doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
	// افتح المستند
	Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
	//احصل على إجراء للتعليق التوضيحي
	RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
	//احصل على أداء التسليم
	Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
	// مقطع وسائط
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