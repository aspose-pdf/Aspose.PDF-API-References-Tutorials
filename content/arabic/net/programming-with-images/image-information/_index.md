---
title: معلومات الصورة في ملف PDF
linktitle: معلومات الصورة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم باستخراج معلومات الصورة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-images/image-information/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية استخراج المعلومات حول الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من أنك قمت بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود الذي يحتوي على المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل ملف PDF المصدر

 في هذه الخطوة، سنقوم بتحميل ملف PDF المصدر باستخدام ملف`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ وتمرير المسار إلى وثيقة PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## الخطوة 3: تعيين الدقة الافتراضية

في هذه الخطوة، سوف نقوم بتعيين الدقة الافتراضية للصور. في المثال، تم تعيين الدقة الافتراضية على 72.

```csharp
int defaultResolution = 72;
```

## الخطوة 4: تهيئة الكائنات والعدادات

في هذه الخطوة، سنقوم بتهيئة الكائنات والعدادات اللازمة لاسترداد معلومات الصورة.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## الخطوة 5: التنقل بين عوامل التشغيل في الصفحة الأولى من المستند

في هذه الخطوة، سنتعرف على عوامل التشغيل في الصفحة الأولى من المستند لتحديد العمليات المتعلقة بالصورة.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## الخطوة 6: إدارة عوامل التشغيل واستخراج معلومات الصورة

في هذه الخطوة، سنقوم بإدارة الأنواع المختلفة من العوامل واستخراج المعلومات حول الصور.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//التعامل مع عمليات GSave وGRestore للتحويلات
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// التعامل مع عملية ConcatenateMatrix للتحويلات
else if (opCtm != null)
{
     // تطبيق مصفوفة التحويل
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// التعامل مع عملية القيام بالصور
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // استرداد الصورة
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // استرجاع أبعاد الصورة
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // حساب القرار استنادا إلى المعلومات المذكورة أعلاه
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // عرض معلومات الصورة
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### نموذج التعليمات البرمجية المصدر لمعلومات الصورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل ملف PDF المصدر
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// تحديد الدقة الافتراضية للصورة
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// حدد كائن قائمة المصفوفة الذي سيحمل أسماء الصور
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// أدخل كائنًا لتكديسه
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// احصل على جميع عوامل التشغيل في الصفحة الأولى من المستند
foreach (Operator op in doc.Pages[1].Contents)
{
	// استخدم عوامل تشغيل GSave/GRestore لإعادة التحويلات إلى ما تم ضبطه مسبقًا
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// إنشاء كائن ConcatenateMatrix لأنه يحدد مصفوفة التحويل الحالية.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// قم بإنشاء عامل التشغيل Do الذي يسحب الكائنات من الموارد. يرسم كائنات النموذج وكائنات الصورة
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//احفظ الحالة السابقة وادفع الحالة الحالية إلى أعلى المكدس
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// التخلص من الحالة الحالية واستعادة الحالة السابقة
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// اضرب المصفوفة الحالية بمصفوفة الحالة
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// في حال كان هذا عامل رسم الصور
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// قم بإنشاء كائن XImage للاحتفاظ بصور صفحة pdf الأولى
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// الحصول على أبعاد الصورة
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// الحصول على معلومات الارتفاع والعرض للصورة
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// حساب القرار بناء على المعلومات المذكورة أعلاه
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// عرض معلومات البعد والدقة لكل صورة
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## خاتمة

تهنئة ! لقد تعلمت الآن كيفية استخراج معلومات الصورة من ملف PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذه المعلومات لمهام معالجة الصور المختلفة في تطبيقاتك.

### الأسئلة الشائعة للحصول على معلومات الصورة في ملف PDF

#### س: ما هو الغرض من استخراج معلومات الصورة من مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يوفر استخراج معلومات الصورة من مستند PDF نظرة ثاقبة حول الأبعاد والدقة والسمات الأخرى للصور داخل المستند. يمكن استخدام هذه المعلومات لمعالجة الصور أو التحليل أو مهام التحسين.

#### س: كيف يساعد Aspose.PDF for .NET في استخراج معلومات الصورة من مستند PDF؟

ج: يوفر Aspose.PDF for .NET أدوات للوصول إلى محتوى مستند PDF وتحليله، بما في ذلك صوره. يوضح الكود المقدم كيفية استخراج معلومات الصورة وعرضها باستخدام عوامل تشغيل مختلفة.

#### س: ما نوع معلومات الصورة التي يمكن استخراجها باستخدام هذه الطريقة؟

ج: تتيح لك هذه الطريقة استخراج المعلومات وعرضها مثل الأبعاد المقاسة والدقة وأسماء الصور داخل مستند PDF.

#### س: كيف يحدد الكود ويعالج العوامل المتعلقة بالصورة داخل مستند PDF؟

ج: يتكرر الكود من خلال عوامل التشغيل على صفحة محددة من مستند PDF. فهو يحدد ويعالج العوامل المتعلقة بعمليات الصورة والتحويلات والعرض.

#### س: ما أهمية الحل الافتراضي، وكيف يتم استخدامه في الكود؟

ج: يتم استخدام الدقة الافتراضية كنقطة مرجعية لحساب الدقة الفعلية للصور. يحسب الكود دقة كل صورة بناءً على أبعادها وإعدادات الدقة الافتراضية.

#### س: كيف يمكن استخدام معلومات الصورة المستخرجة في سيناريوهات العالم الحقيقي؟

ج: يمكن استخدام معلومات الصورة المستخرجة في مهام مثل تقييم جودة الصورة، وتحسين الصورة، وإنشاء صور مصغرة للصور، وتسهيل عمليات اتخاذ القرار المتعلقة بالصور.

#### س: هل يمكنني تعديل الكود لاستخراج سمات إضافية متعلقة بالصورة؟

ج: نعم، يمكنك تخصيص التعليمات البرمجية لاستخراج سمات إضافية للصور، مثل مساحة اللون أو عمق البكسل أو نوع الصورة.

#### س: هل عملية استخراج معلومات الصورة كثيفة الاستخدام للموارد أم تستغرق وقتًا طويلاً؟

ج: تتميز عملية استخراج معلومات الصورة بالكفاءة وتحسين الأداء، مما يضمن الحد الأدنى من التأثير على استخدام الموارد ووقت المعالجة.

#### س: كيف يمكن للمطورين الاستفادة من تحديد واستخراج معلومات الصورة من مستندات PDF؟

ج: يمكن للمطورين الحصول على رؤى حول خصائص الصور الموجودة في مستندات PDF، مما يمكنهم من اتخاذ قرارات مستنيرة فيما يتعلق بمعالجة الصور ومعالجتها وتحسينها.

#### س: هل يمكن استخدام هذه الطريقة للمعالجة المجمعة لمستندات PDF التي تحتوي على صور؟

ج: نعم، يمكن توسيع هذه الطريقة لتشمل المعالجة المجمعة من خلال التكرار عبر صفحات أو مستندات متعددة، واستخراج معلومات الصورة، وتنفيذ المهام المتعلقة بالصورة.