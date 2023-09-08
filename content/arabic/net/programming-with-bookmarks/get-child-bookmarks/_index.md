---
title: الحصول على الإشارات المرجعية للأطفال في ملف PDF
linktitle: الحصول على الإشارات المرجعية للأطفال في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على الإشارات المرجعية الفرعية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-bookmarks/get-child-bookmarks/
---
يمكن أن يكون استرداد الإشارات المرجعية الفرعية في ملف PDF مفيدًا لاستكشاف البنية الهرمية للإشارات المرجعية. باستخدام Aspose.PDF for .NET، يمكنك بسهولة الحصول على الإشارات المرجعية الفرعية باتباع كود المصدر التالي:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الإشارات المرجعية منه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد استخراج الإشارات المرجعية منه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## الخطوة 4: تصفح الإشارات المرجعية والإشارات المرجعية الفرعية

 في هذه الخطوة، سنقوم بالتكرار على جميع الإشارات المرجعية الموجودة في المستند باستخدام ملف`foreach` حلقة. بالنسبة لكل إشارة مرجعية، سنعرض المعلومات مثل العنوان والنمط المائل والنمط الغامق واللون. إذا كانت الإشارة المرجعية تحتوي على إشارات مرجعية فرعية، فسنعرضها أيضًا. هنا هو الكود المقابل:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // تصفح الإشارات المرجعية للأطفال أيضًا
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### نموذج التعليمات البرمجية المصدر للحصول على الإشارات المرجعية التابعة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// قم بالمرور عبر جميع الإشارات المرجعية
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// توجد إشارات مرجعية فرعية ثم يتم تكرارها من خلال ذلك أيضًا
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة للحصول على الإشارات المرجعية الفرعية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز لاستكشاف البنية الهرمية للإشارات المرجعية والحصول على معلومات مفصلة حول كل إشارة مرجعية وإشاراتها المرجعية الفرعية في مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.

### الأسئلة الشائعة للحصول على إشارات مرجعية فرعية في ملف PDF

#### س: ما هي الإشارات المرجعية الفرعية في ملف PDF؟

ج: الإشارات المرجعية الفرعية هي إشارات مرجعية متداخلة أسفل الإشارة المرجعية الأصلية. إنها تنشئ هيكلًا هرميًا، مما يسمح بتجربة تنقل أكثر تنظيمًا وتفصيلاً داخل مستند PDF.

#### س: لماذا أرغب في استرداد الإشارات المرجعية الفرعية من ملف PDF؟

ج: يساعدك استرداد الإشارات المرجعية الفرعية على فهم العلاقات والتسلسل الهرمي بين الأقسام المختلفة للمستند. يمكن أن تكون هذه المعلومات مفيدة بشكل خاص للمستندات ذات الهياكل المعقدة أو مستويات التنظيم المتعددة.

#### س: كيف يمكنني استيراد المكتبات اللازمة لمشروع C# الخاص بي؟

ج: لاستيراد المكتبة المطلوبة لمشروع C# الخاص بك، استخدم توجيه الاستيراد التالي:

```csharp
using Aspose.Pdf;
```

يمكّنك هذا التوجيه من الوصول إلى الفئات والأساليب التي يوفرها Aspose.PDF لـ .NET.

#### س: كيف أحدد المسار إلى مجلد المستندات؟

 ج: في كود المصدر المقدم، استبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الإشارات المرجعية الفرعية منه. وهذا يضمن أن الكود يمكنه تحديد موقع ملف PDF المستهدف.

#### س: كيف يمكنني فتح مستند PDF لاستخراج الإشارات المرجعية الفرعية؟

ج: لفتح مستند PDF لاستخراج الإشارة المرجعية، استخدم الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

 يستبدل`"GetChildBookmarks.pdf"` مع اسم الملف الفعلي.

#### س: كيف يمكنني التكرار وعرض معلومات الإشارة المرجعية التابعة؟

 ج: قم بالتمرير عبر كافة الإشارات المرجعية الموجودة في المستند باستخدام ملف`foreach` حلقة. بالنسبة لكل إشارة مرجعية، اعرض معلومات مثل العنوان والنمط المائل والنمط الغامق واللون، وإذا كانت تحتوي على إشارات مرجعية فرعية، فقم بالتكرار من خلالها أيضًا:

```csharp
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
    Console.WriteLine("Title: " + outlineItem.Title);
    Console.WriteLine("Italic: " + outlineItem.Italic);
    Console.WriteLine("Bold: " + outlineItem.Bold);
    Console.WriteLine("Color: " + outlineItem.Color);
    
    if (outlineItem.Count > 0)
    {
        Console.WriteLine("Child bookmarks");
        
        // تصفح الإشارات المرجعية للأطفال أيضًا
        foreach (OutlineItemCollection childOutline in outlineItem)
        {
            Console.WriteLine(childOutline.Title);
            Console.WriteLine(childOutline.Italic);
            Console.WriteLine(childOutline.Bold);
            Console.WriteLine(childOutline.Color);
        }
    }
}
```

#### س: هل يمكنني استخراج خصائص أخرى للإشارات المرجعية الفرعية باستخدام أسلوب مماثل؟

 ج: نعم، يمكنك استخراج خصائص مختلفة للإشارات المرجعية الفرعية باستخدام الملف`OutlineItemCollection` هدف. راجع وثائق Aspose.PDF للحصول على قائمة شاملة بالخصائص المتاحة.

#### س: هل هناك حد لعدد الإشارات المرجعية الفرعية التي يمكنني استردادها؟

ج: لا يوجد عادةً حد صارم لعدد الإشارات المرجعية الفرعية التي يمكنك استردادها باستخدام هذه الطريقة. ومع ذلك، قد تتطلب المستندات الكبيرة جدًا التي تحتوي على عدد زائد من الإشارات المرجعية الفرعية إدارة فعالة للذاكرة.

#### س: ماذا لو كانت الإشارات المرجعية الفرعية تحتوي على المزيد من الإشارات المرجعية الفرعية المتداخلة؟

ج: سيتم تكرار التعليمات البرمجية المقدمة بشكل متكرر عبر جميع مستويات الإشارات المرجعية الفرعية، مما يسمح لك باسترداد المعلومات من الإشارات المرجعية الفرعية المتداخلة أيضًا.

#### س: كيف يمكنني استخدام معلومات الإشارة المرجعية الفرعية المستخرجة؟

ج: يمكنك استخدام معلومات الإشارات المرجعية الفرعية المستخرجة للتحليل أو التوثيق أو إنشاء واجهات تنقل مخصصة داخل تطبيقاتك.