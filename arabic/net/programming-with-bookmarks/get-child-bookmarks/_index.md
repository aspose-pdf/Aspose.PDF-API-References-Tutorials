---
title: احصل على إشارات مرجعية للأطفال في ملف PDF
linktitle: احصل على إشارات مرجعية للأطفال في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على إشارات مرجعية فرعية في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-bookmarks/get-child-bookmarks/
---
يمكن أن يكون استرداد الإشارات المرجعية الفرعية في ملف PDF مفيدًا لاستكشاف الهيكل الهرمي للإشارات المرجعية. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة الحصول على الإشارات المرجعية الفرعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الإشارات المرجعية منه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد استخراج الإشارات المرجعية منه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## الخطوة 4: تصفح الإشارات المرجعية والإشارات المرجعية الفرعية

 في هذه الخطوة ، سنقوم بتكرار جميع الإشارات المرجعية في المستند باستخدام ملف`foreach` حلقة. لكل إشارة مرجعية ، سنعرض المعلومات مثل العنوان والنمط المائل والأسلوب الغامق واللون. إذا كانت الإشارة المرجعية تحتوي على إشارات مرجعية فرعية ، فسنعرضها أيضًا. هذا هو الكود المقابل:

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
        
         // تصفح المواقع الفرعية كذلك
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

### عينة من التعليمات البرمجية المصدر للحصول على إشارات مرجعية تابعة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// حلقة من خلال جميع الإشارات المرجعية
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// هناك إشارات مرجعية فرعية ثم حلقة من خلال ذلك أيضًا
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

تهنئة ! الآن لديك دليل خطوة بخطوة للحصول على إشارات مرجعية فرعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لاستكشاف الهيكل الهرمي للإشارات المرجعية والحصول على معلومات مفصلة حول كل إشارة مرجعية والإشارات المرجعية الفرعية الخاصة بها في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.

### الأسئلة الشائعة للحصول على إشارات مرجعية فرعية في ملف PDF

#### س: ما هي الإشارات المرجعية الفرعية في ملف PDF؟

ج: الإشارات المرجعية الفرعية هي إشارات مرجعية متداخلة ضمن إشارة مرجعية رئيسية. يقومون بإنشاء هيكل هرمي ، مما يسمح بتجربة تنقل أكثر تنظيماً وتفصيلاً داخل مستند PDF.

#### س: لماذا أرغب في استرداد الإشارات المرجعية الفرعية من ملف PDF؟

ج: يساعدك استرداد الإشارات المرجعية الفرعية على فهم العلاقات والتسلسل الهرمي بين الأقسام المختلفة من المستند. يمكن أن تكون هذه المعلومات مفيدة بشكل خاص للمستندات ذات الهياكل المعقدة أو مستويات متعددة من التنظيم.

#### س: كيف يمكنني استيراد المكتبات اللازمة لمشروع C # الخاص بي؟

ج: لاستيراد المكتبة المطلوبة لمشروع C # الخاص بك ، استخدم توجيه الاستيراد التالي:

```csharp
using Aspose.Pdf;
```

يمكّنك هذا التوجيه من الوصول إلى الفئات والطرق التي يوفرها Aspose.PDF لـ .NET.

#### س: كيف يمكنني تحديد المسار إلى مجلد المستندات؟

 ج: في كود المصدر المقدم ، استبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي للمجلد الذي يحتوي على ملف PDF الذي تريد استخراج الإشارات المرجعية الفرعية منه. هذا يضمن أن الكود يمكنه تحديد موقع ملف PDF الهدف.

#### س: كيف أقوم بفتح مستند PDF لاستخراج الإشارات المرجعية الفرعية؟

ج: لفتح مستند PDF لاستخراج الإشارة المرجعية ، استخدم الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

 يستبدل`"GetChildBookmarks.pdf"` مع اسم الملف الفعلي.

#### س: كيف يمكنني تكرار عرض معلومات الإشارات المرجعية الفرعية وعرضها؟

 ج: قم بالتكرار خلال جميع الإشارات المرجعية في المستند باستخدام ملف`foreach` حلقة. لكل إشارة مرجعية ، اعرض معلومات مثل العنوان ، والنمط المائل ، والنمط الغامق ، واللون ، وإذا كانت تحتوي على إشارات مرجعية فرعية ، فكررها أيضًا:

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
        
        // تصفح المواقع الفرعية كذلك
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

#### س: هل يمكنني استخراج خصائص أخرى للإشارات المرجعية الفرعية باستخدام نهج مماثل؟

 ج: نعم ، يمكنك استخراج خصائص متنوعة للإشارات المرجعية الفرعية باستخدام`OutlineItemCollection` هدف. راجع وثائق Aspose.PDF للحصول على قائمة شاملة بالخصائص المتاحة.

#### س: هل هناك حد لعدد الإشارات المرجعية الفرعية التي يمكنني استردادها؟

ج: لا يوجد عادةً حد صارم لعدد الإشارات المرجعية الفرعية التي يمكنك استردادها باستخدام هذه الطريقة. ومع ذلك ، قد تتطلب المستندات الكبيرة جدًا التي تحتوي على عدد كبير من الإشارات المرجعية الفرعية إدارة فعالة للذاكرة.

#### س: ماذا لو كانت الإشارات المرجعية الفرعية تحتوي على إشارات مرجعية فرعية متداخلة أخرى؟

ج: سوف يتم تكرار الكود المقدم بشكل متكرر عبر جميع مستويات الإشارات المرجعية الفرعية ، مما يسمح لك باسترداد المعلومات من الإشارات المرجعية الفرعية المتداخلة أيضًا.

#### س: كيف يمكنني استخدام معلومات الإشارات المرجعية الفرعية المستخرجة؟

ج: يمكنك استخدام معلومات الإشارات المرجعية الفرعية المستخرجة للتحليل أو التوثيق أو إنشاء واجهات تنقل مخصصة داخل تطبيقاتك.