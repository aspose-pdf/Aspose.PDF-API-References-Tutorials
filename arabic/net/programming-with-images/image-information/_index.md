---
title: معلومات الصورة
linktitle: معلومات الصورة
second_title: Aspose.PDF لمرجع .NET API
description: استخراج معلومات الصورة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-images/image-information/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية استخراج المعلومات حول الصور في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل ملف PDF المصدر

 في هذه الخطوة ، سنقوم بتحميل ملف PDF المصدر باستخدام الامتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## الخطوة 3: تعيين الدقة الافتراضية

في هذه الخطوة ، سنقوم بتعيين الدقة الافتراضية للصور. في المثال ، تم تعيين الدقة الافتراضية على 72.

```csharp
int defaultResolution = 72;
```

## الخطوة 4: تهيئة الكائنات والعدادات

في هذه الخطوة ، سنهيئ الكائنات والعدادات اللازمة لاسترداد معلومات الصورة.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## الخطوة 5: التنقل بين عوامل التشغيل في الصفحة الأولى من المستند

في هذه الخطوة ، سننتقل عبر المشغلين في الصفحة الأولى من المستند لتحديد العمليات المتعلقة بالصور.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## الخطوة 6: إدارة المشغلين واستخراج معلومات الصورة

في هذه الخطوة ، سندير الأنواع المختلفة من المشغلين ونستخرج المعلومات حول الصور.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//التعامل مع عمليات GSave و GRestore للتحولات
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// تعامل مع عملية ConcatenateMatrix للتحولات
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
// تعامل مع عملية Do للصور
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // استرجع الصورة
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // استرجع أبعاد الصورة
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // احسب القرار بناءً على المعلومات الواردة أعلاه
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
// حدد الدقة الافتراضية للصورة
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// تحديد كائن قائمة الصفيف الذي سيحمل أسماء الصور
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// قم بإدراج كائن في المكدس
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// احصل على جميع العوامل في الصفحة الأولى من المستند
foreach (Operator op in doc.Pages[1].Contents)
{
	// استخدم مشغلي GSave / GRestore لإعادة التحويلات إلى ما تم تعيينه مسبقًا
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// إنشاء كائن ConcatenateMatrix لأنه يعرف مصفوفة التحويل الحالية.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// إنشاء عامل تشغيل يقوم بسحب الأشياء من الموارد. يرسم كائنات النموذج وكائنات الصورة
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//احفظ الحالة السابقة وادفع الحالة الحالية إلى أعلى المكدس
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// تخلص من الحالة الحالية واستعادة الحالة السابقة
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
		// في حال كان هذا عامل رسم صورة
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// قم بإنشاء كائن XImage للاحتفاظ بصور صفحة pdf الأولى
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// احصل على أبعاد الصورة
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// احصل على معلومات الطول والعرض للصورة
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// دقة الحساب على أساس المعلومات المذكورة أعلاه
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

تهنئة ! لقد تعلمت الآن كيفية استخراج معلومات الصورة في ملف PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذه المعلومات في العديد من مهام معالجة الصور في تطبيقاتك.