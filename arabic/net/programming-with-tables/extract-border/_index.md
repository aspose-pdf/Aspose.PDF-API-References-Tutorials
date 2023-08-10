---
title: استخراج الحدود في ملف PDF
linktitle: استخراج الحدود في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج الحدود في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-tables/extract-border/
---
في هذا البرنامج التعليمي ، سوف نتعلم كيفية استخراج الحدود في ملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري في C # خطوة بخطوة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية استخراج الحد من مستند PDF وحفظه كصورة. لنبدأ!

## الخطوة الأولى: تهيئة البيئة
أولاً ، تأكد من إعداد بيئة التطوير C # الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة 2: تحميل مستند PDF
في هذه الخطوة ، نقوم بتحميل مستند PDF من الملف المحدد.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

تأكد من استبدال "دليل المستندات" بالدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 3: استخراج الحواف
سنقوم باستخراج الحد من مستند PDF من خلال تكرار العمليات الواردة في المستند.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // معالجة جميع عمليات المحتوى
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // تحقق من نوع العملية
         // ...
         // أضف الكود لمعالجة كل عملية
     }
}
```

 نقوم بإنشاء ملف`graphicsState` مكدس لتخزين حالات الرسومات ، صورة نقطية لالتقاط الحدود المستخرجة ، أ`GraphicsPath` كائن لتخزين مسارات الرسم ، ومتغيرات أخرى لتتبع الحالة والألوان.

## الخطوة 4: معالجة المعاملات
في هذه الخطوة ، نقوم بمعالجة كل عملية من المستند لاستخراج الحدود.

```csharp
// تحقق من نوع العملية
if (opSaveState != null)
{
     // احفظ الحالة السابقة وادفع الحالة الحالية إلى أعلى المكدس
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // حذف الحالة الحالية واستعادة الحالة السابقة
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // استرجع مصفوفة التحويل الحالية
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // اضرب المصفوفة الحالية بمصفوفة الحالة
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // قم بتحديث آخر نقطة رسم
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // معالجة رسم خط
     // ...
     // أضف رمزًا للتعامل مع رسم خط
}
// ...
// أضف آخر إذا كانت الكتل لعمليات أخرى
```

نتحقق من نوع العملية باستخدام الشروط ونشغل الكود المناسب لكل عملية.

## الخطوة 5: صورة احتياطية
أخيرًا ، نحفظ الصورة النقطية التي تحتوي على الحدود المستخرجة في ملف محدد.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

تأكد من تحديد الدليل الصحيح واسم الملف لحفظ الصورة الناتجة.

### مثال على التعليمات البرمجية المصدر لاستخراج الحدود باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// قيمة مصفوفة ctm الافتراضية هي 1،0،0،1،0،0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Drawing نظام الإحداثيات هو أعلى اليسار ، في حين أن نظام الإحداثيات pdf منخفض على اليسار ، لذلك يتعين علينا تطبيق مصفوفة الانعكاس
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// قم بمعالجة جميع أوامر المحتويات
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//احفظ الحالة السابقة وادفع الحالة الحالية إلى أعلى المكدس
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// تخلص من الحالة الحالية واستعادة الحالة السابقة
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية استخراج الحدود من مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل التفصيلي خطوة بخطوة لاستخراج الحدود من مستندات PDF الأخرى.

### أسئلة وأجوبة لاستخراج الحدود في ملف PDF

#### س: ما هو الغرض من استخراج الحدود من ملف PDF؟

ج: يمكن أن يكون استخراج الحدود من ملف PDF مفيدًا لأغراض مختلفة. يسمح لك بعزل العناصر الهيكلية للمستند وتحليلها ، مثل الجداول أو المخططات أو العناصر الرسومية. يمكنك استخدام الحد المستخرج لتعريف التخطيط والأبعاد وموضع المحتوى داخل مستند PDF.

#### س: هل يمكنني استخراج الحد من صفحات أو مناطق معينة داخل مستند PDF؟

ج: نعم ، يمكنك تعديل التعليمات البرمجية المصدر C # المقدمة لاستخراج الحدود من صفحات أو مناطق معينة داخل مستند PDF. عن طريق التلاعب في`doc.Pages` جمع وتحديد معايير مخصصة ، يمكنك اختيار استخراج الحدود من صفحات أو مناطق اهتمام معينة.

#### س: كيف يمكنني تخصيص تنسيق صورة الإخراج وجودتها؟

 ج: في كود C # المقدم ، يتم حفظ الحد المستخرج كصورة PNG. إذا كنت تريد تغيير تنسيق صورة الإخراج ، فيمكنك تعديل ملف`ImageFormat.Png` المعلمة في`bitmap.Save` طريقة لتنسيقات الصور الأخرى المدعومة ، مثل JPEG أو BMP أو GIF. بالإضافة إلى ذلك ، يمكنك ضبط جودة الصورة أو إعدادات الضغط بناءً على متطلباتك.

#### س: ما هي العمليات الأخرى التي يمكنني إجراؤها على الحدود المستخرجة؟

ج: بمجرد استخراج الحدود كصورة ، يمكنك معالجتها بشكل أكبر باستخدام مكتبات أو خوارزميات معالجة الصور. يمكنك تحليل الصورة أو تطبيق مرشحات الصور أو اكتشاف الأنماط أو إجراء التعرف الضوئي على الحروف (OCR) لاستخراج النص من الصورة إذا لزم الأمر.

#### س: هل هناك أي قيود أو اعتبارات عند استخراج الحدود من مستندات PDF المعقدة؟

ج: قد تختلف عملية الاستخراج اعتمادًا على مدى تعقيد مستند PDF. قد تتطلب ملفات PDF المعقدة ذات الطبقات المتعددة أو الشفافية أو الرسومات المتقدمة معالجة أو تعديلات إضافية لاستخراج الحدود بدقة. من الضروري إجراء اختبار شامل لعملية الاستخراج على مستندات PDF المختلفة لضمان الحصول على نتائج موثوقة.