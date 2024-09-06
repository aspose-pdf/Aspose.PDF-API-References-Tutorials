---
title: معلومات الصورة في ملف PDF
linktitle: معلومات الصورة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: استخراج معلومات الصورة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-images/image-information/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية استخراج المعلومات حول الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

 تأكد من تعيين دليل المستند الصحيح. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل ملف PDF المصدر

 في هذه الخطوة، سنقوم بتحميل ملف PDF المصدر باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## الخطوة 3: تعيين الدقة الافتراضية

في هذه الخطوة، سنقوم بتعيين الدقة الافتراضية للصور. في المثال، تم تعيين الدقة الافتراضية على 72.

```csharp
int defaultResolution = 72;
```

## الخطوة 4: تهيئة الكائنات والعدادات

في هذه الخطوة، سنقوم بتهيئة الكائنات والعدادات اللازمة لاسترجاع معلومات الصورة.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## الخطوة 5: التنقل بين المشغلات في الصفحة الأولى من المستند

في هذه الخطوة، سننتقل عبر المشغلات الموجودة في الصفحة الأولى من المستند لتحديد العمليات المتعلقة بالصورة.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## الخطوة 6: إدارة المشغلين واستخراج معلومات الصورة

في هذه الخطوة، سنقوم بإدارة أنواع مختلفة من المشغلين واستخراج المعلومات حول الصور.

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
// التعامل مع عملية Do للصور
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // استرجاع الصورة
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // استرجاع أبعاد الصورة
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // احسب الدقة بناءً على المعلومات المذكورة أعلاه
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

### عينة من كود المصدر لمعلومات الصورة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل ملف PDF المصدر
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// تحديد الدقة الافتراضية للصورة
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// قم بتعريف كائن قائمة المصفوفة الذي سيحمل أسماء الصور
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// إدراج كائن للتكديس
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// احصل على جميع المشغلين في الصفحة الأولى من المستند
foreach (Operator op in doc.Pages[1].Contents)
{
	// استخدم مشغلي GSave/GRestore لإرجاع التحويلات إلى ما تم تعيينه مسبقًا
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// قم بإنشاء كائن ConcatenateMatrix كما يحدد مصفوفة التحويل الحالية.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// إنشاء عامل Do الذي يرسم الكائنات من الموارد. يرسم كائنات النموذج وكائنات الصورة
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
		// ضرب مصفوفة التيار بمصفوفة الحالة
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// في حالة أن هذا هو عامل رسم الصورة
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// إنشاء كائن XImage لحمل صور الصفحة الأولى من ملف pdf
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// الحصول على أبعاد الصورة
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// احصل على معلومات ارتفاع وعرض الصورة
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// حساب الدقة بناءً على المعلومات المذكورة أعلاه
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// عرض معلومات الأبعاد والدقة لكل صورة
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## خاتمة

تهانينا! لقد تعلمت الآن كيفية استخراج معلومات الصورة في ملف PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذه المعلومات في مهام معالجة الصور المختلفة في تطبيقاتك.

### الأسئلة الشائعة حول معلومات الصورة في ملف PDF

#### س: ما هو الغرض من استخراج معلومات الصورة من مستند PDF باستخدام Aspose.PDF لـ .NET؟

أ: إن استخراج معلومات الصورة من مستند PDF يوفر نظرة ثاقبة للأبعاد والدقة والسمات الأخرى للصور داخل المستند. ويمكن استخدام هذه المعلومات في مهام معالجة الصور أو تحليلها أو تحسينها.

#### س: كيف يساعد Aspose.PDF for .NET في استخراج معلومات الصورة من مستند PDF؟

ج: يوفر Aspose.PDF for .NET أدوات للوصول إلى محتوى مستند PDF وتحليله، بما في ذلك صوره. يوضح الكود المقدم كيفية استخراج معلومات الصورة وعرضها باستخدام مشغلات مختلفة.

#### س: ما نوع معلومات الصورة التي يمكن استخراجها باستخدام هذه الطريقة؟

ج: تتيح لك هذه الطريقة استخراج وعرض معلومات مثل الأبعاد المُدرجة والدقة وأسماء الصور داخل مستند PDF.

#### س: كيف يقوم الكود بتحديد ومعالجة مشغلي الصور المرتبطة داخل مستند PDF؟

ج: يتكرر الكود من خلال المشغلات الموجودة في صفحة محددة من مستند PDF. فهو يحدد المشغلات المتعلقة بعمليات الصور والتحويلات والرسم ويقوم بمعالجتها.

#### س: ما أهمية الدقة الافتراضية وكيف يتم استخدامها في الكود؟

ج: يتم استخدام الدقة الافتراضية كنقطة مرجعية لحساب الدقة الفعلية للصور. يحسب الكود دقة كل صورة بناءً على أبعادها وإعداد الدقة الافتراضية.

#### س: كيف يمكن الاستفادة من معلومات الصورة المستخرجة في سيناريوهات العالم الحقيقي؟

أ: يمكن استخدام معلومات الصورة المستخرجة لمهام مثل تقييم جودة الصورة، وتحسين الصورة، وإنشاء صور مصغرة للصور، وتسهيل عمليات اتخاذ القرار المتعلقة بالصورة.

#### س: هل يمكنني تعديل الكود لاستخراج سمات إضافية متعلقة بالصورة؟

ج: نعم، يمكنك تخصيص الكود لاستخراج سمات إضافية للصور، مثل مساحة اللون، أو عمق البكسل، أو نوع الصورة.

#### س: هل عملية استخراج معلومات الصورة تتطلب الكثير من الموارد أو تستغرق وقتا طويلا؟

أ: عملية استخراج معلومات الصورة فعالة ومُحسَّنة للأداء، مما يضمن الحد الأدنى من التأثير على استخدام الموارد ووقت المعالجة.

#### س: كيف يمكن للمطورين الاستفادة من تحديد معلومات الصورة واستخراجها من مستندات PDF؟

أ: يمكن للمطورين الحصول على رؤى حول خصائص الصور داخل مستندات PDF، مما يمكنهم من اتخاذ قرارات مستنيرة فيما يتعلق بمعالجة الصور وتحسينها.

#### س: هل يمكن استخدام هذه الطريقة لمعالجة دفعات من مستندات PDF التي تحتوي على صور؟

ج: نعم، يمكن توسيع هذه الطريقة لتشمل المعالجة الدفعية من خلال التكرار عبر صفحات أو مستندات متعددة، واستخراج معلومات الصورة، وتنفيذ المهام المتعلقة بالصورة.