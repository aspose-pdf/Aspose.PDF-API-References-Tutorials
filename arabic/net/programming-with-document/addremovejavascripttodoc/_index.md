---
title: أضف Remove Javascript To Doc
linktitle: أضف Remove Javascript To Doc
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة وإزالة JavaScript من مستندات PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع دروس تعليمات برمجية للبرمجة النصية على مستوى المستند.
type: docs
weight: 30
url: /ar/net/programming-with-document/addremovejavascripttodoc/
---

لإضافة وإزالة JavaScript من مستندات PDF ، سنستخدم Aspose.PDF لمكتبة .NET. تتيح لنا هذه المكتبة القوية معالجة ملفات PDF في تطبيقات .NET. اتبع الإرشادات خطوة بخطوة أدناه لإضافة وإزالة JavaScript باستخدام Aspose.PDF for .NET.

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