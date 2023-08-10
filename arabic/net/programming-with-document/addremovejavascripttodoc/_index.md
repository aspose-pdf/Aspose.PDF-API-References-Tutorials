---
title: إضافة إزالة جافا سكريبت إلى وثيقة PDF
linktitle: أضف Remove Javascript To Doc
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة وإزالة JavaScript إلى مستند PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع دروس تعليمات برمجية للبرمجة النصية على مستوى المستند.
type: docs
weight: 30
url: /ar/net/programming-with-document/addremovejavascripttodoc/
---
لإضافة وإزالة JavaScript إلى مستند PDF ، سنستخدم Aspose.PDF لمكتبة .NET. تتيح لنا هذه المكتبة القوية معالجة ملفات PDF في تطبيقات .NET. اتبع الإرشادات خطوة بخطوة أدناه لإضافة وإزالة JavaScript باستخدام Aspose.PDF for .NET.

## الخطوة 1: قم بإنشاء مستند PDF جديد

 ابدأ بإنشاء مثيل جديد لـ`Document` فئة مقدمة من Aspose.PDF لـ .NET. سيكون هذا بمثابة مستند PDF حيث سنضيف JavaScript.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## الخطوة 2: أضف JavaScript على مستوى المستند

 لإضافة JavaScript على مستوى المستند ، استخدم ملف`JavaScript` ممتلكات`Document` فصل. قم بتعيين وظائف JavaScript للمفاتيح الموجودة في قاموس JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 في هذا البرنامج التعليمي ، أضفنا وظيفتين من وظائف JavaScript ،`func1` و`func2`، إلى مستند PDF.

## الخطوة 3: إزالة Document Level JavaScript

لإزالة JavaScript على مستوى المستند ، قم بتحميل مستند PDF والوصول إلى ملف`JavaScript` قاموس. كرر على المفاتيح وقم بإزالة وظيفة JavaScript المطلوبة.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 في هذا البرنامج التعليمي ، نقوم بإزالة ملف`func1` وظيفة JavaScript من وثيقة PDF.

## الخطوة 4: حفظ التغييرات والتحقق منها

احفظ مستند PDF المعدل وتحقق من التغييرات.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

سيحفظ هذا الرمز مستند PDF المعدل ويعرض رسالة النجاح.

### مثال على التعليمات البرمجية المصدر لـ Add Remove Javascript من مستندات PDF باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// إزالة مستوى المستند JavaScript
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## خاتمة

في هذه المقالة ، قدمنا دليلًا تفصيليًا لإضافة وإزالة JavaScript من مستندات PDF باستخدام Aspose.PDF for .NET. باتباع التعليمات واستخدام برامج التعليمات البرمجية المقدمة ، يمكنك بسهولة دمج JavaScript في مستندات PDF الخاصة بك وإزالتها عند الحاجة. يتيح JavaScript وظائف ديناميكية وتفاعلية في ملفات PDF الخاصة بك ، مما يعزز تجربة المستخدم.


### الأسئلة الشائعة حول إضافة إزالة جافا سكريبت إلى مستند PDF

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية تسمح للمطورين بمعالجة ملفات PDF في تطبيقات .NET بشكل فعال. يوفر ميزات شاملة للعمل مع مستندات PDF برمجيًا.

#### س: كيف يمكنني إضافة JavaScript إلى مستند PDF باستخدام Aspose.PDF for .NET؟

 ج: يمكنك إضافة JavaScript على مستوى المستند باستخدام ملف`JavaScript` ممتلكات`Document` فصل. ما عليك سوى تعيين وظائف JavaScript للمفاتيح الموجودة في قاموس JavaScript.

#### س: هل يمكنني إزالة JavaScript من مستند PDF باستخدام Aspose.PDF for .NET؟

 ج: نعم ، يمكنك إزالة JavaScript من مستند PDF عن طريق الوصول إلى ملف`JavaScript` القاموس وإزالة وظيفة JavaScript المطلوبة.

#### س: هل Aspose.PDF for .NET مناسب للمشاريع الاحترافية؟

ج: بالتأكيد ، يتم استخدام Aspose.PDF for .NET على نطاق واسع في المشاريع الاحترافية لمعالجة ملفات PDF ومهام الإنشاء. إنه يوفر أداءً عاليًا ووظائف موثوقة.

#### س: ما الفوائد التي توفرها إضافة JavaScript إلى مستند PDF؟

ج: تتيح لك إضافة JavaScript إلى مستند PDF إنشاء ملفات PDF تفاعلية وديناميكية. يمكنك تنفيذ التحقق من صحة النموذج وإجراء العمليات الحسابية وإضافة ميزات تفاعلية متنوعة لتحسين تجربة المستخدم.