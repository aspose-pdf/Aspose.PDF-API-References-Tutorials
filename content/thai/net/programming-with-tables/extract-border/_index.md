---
title: การแยกเส้นขอบออกจากไฟล์ PDF
linktitle: การแยกเส้นขอบออกจากไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแยกเส้นขอบในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-tables/extract-border/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีแยกเส้นขอบในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับใน C# ทีละขั้นตอน เมื่อจบบทช่วยสอนนี้ คุณจะทราบวิธีแยกเส้นขอบจากเอกสาร PDF และบันทึกเป็นรูปภาพ มาเริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา C# ด้วย Aspose.PDF สำหรับ .NET แล้ว เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การโหลดเอกสาร PDF
ในขั้นตอนนี้เราโหลดเอกสาร PDF จากไฟล์ที่ระบุ

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยไดเรกทอรีจริงที่ไฟล์ PDF ของคุณตั้งอยู่

## ขั้นตอนที่ 3: การสกัดขอบ
เราจะแยกเส้นขอบออกจากเอกสาร PDF โดยทำซ้ำตามการดำเนินการที่มีอยู่ในเอกสาร

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
     // ดำเนินการประมวลผลเนื้อหาทั้งหมด
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // ตรวจสอบประเภทการดำเนินการ
         // -
         // เพิ่มโค้ดเพื่อประมวลผลการทำงานแต่ละอย่าง
     }
}
```

 เราสร้าง`graphicsState` สแต็คเพื่อเก็บสถานะกราฟิก ภาพบิตแมปเพื่อจับภาพเส้นขอบที่แยกออกมา`GraphicsPath` วัตถุสำหรับเก็บเส้นทางการวาดและตัวแปรอื่น ๆ เพื่อติดตามสถานะและสี

## ขั้นตอนที่ 4: การประมวลผลธุรกรรม
ในขั้นตอนนี้เราจะประมวลผลการดำเนินการแต่ละอย่างของเอกสารเพื่อแยกขอบเขตออกมา

```csharp
// ตรวจสอบประเภทการดำเนินการ
if (opSaveState != null)
{
     // บันทึกสถานะก่อนหน้าและผลักสถานะปัจจุบันไปที่ด้านบนสุดของสแต็ก
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // ลบสถานะปัจจุบันและคืนสถานะก่อนหน้า
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // ดึงข้อมูลเมทริกซ์การแปลงปัจจุบัน
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // คูณเมทริกซ์ปัจจุบันด้วยเมทริกซ์สถานะ
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // อัพเดทจุดวาดล่าสุด
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // กระบวนการวาดเส้น
     // -
     // เพิ่มโค้ดสำหรับจัดการการวาดเส้น
}
// -
// เพิ่มบล็อคอื่น ๆ สำหรับการดำเนินการอื่น ๆ
```

เราตรวจสอบประเภทการดำเนินการโดยใช้เงื่อนไขและรันโค้ดที่เหมาะสมสำหรับการดำเนินการแต่ละอย่าง

## ขั้นตอนที่ 5: สำรองภาพ
ในที่สุด เราจะบันทึกภาพบิตแมปที่มีเส้นขอบที่แยกออกมาลงในไฟล์ที่ระบุ

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

โปรดแน่ใจว่าระบุไดเร็กทอรีและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกภาพเอาต์พุต

### ตัวอย่างโค้ดต้นฉบับสำหรับการดึงเส้นขอบโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// ค่าเมทริกซ์ ctm เริ่มต้นคือ 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//ระบบพิกัดของ System.Drawing นั้นจะอิงจากซ้ายบน ในขณะที่ระบบพิกัดของ pdf นั้นจะอิงจากซ้ายล่าง ดังนั้นเราจะต้องใช้เมทริกซ์การผกผัน
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// ประมวลผลคำสั่งเนื้อหาทั้งหมด
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
			// บันทึกสถานะก่อนหน้าและผลักสถานะปัจจุบันไปที่ด้านบนสุดของสแต็ก
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// ทิ้งสถานะปัจจุบันและเรียกคืนสถานะก่อนหน้า
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

			// คูณเมทริกซ์ปัจจุบันด้วยเมทริกซ์สถานะ
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

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการแยกเส้นขอบจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คู่มือทีละขั้นตอนนี้เพื่อแยกเส้นขอบจากเอกสาร PDF อื่นๆ

### คำถามที่พบบ่อยสำหรับการแยกขอบออกจากไฟล์ PDF

#### ถาม: จุดประสงค์ในการแยกขอบออกจากไฟล์ PDF คืออะไร

A: การแยกเส้นขอบออกจากไฟล์ PDF สามารถเป็นประโยชน์ได้หลายประการ โดยช่วยให้คุณสามารถแยกและวิเคราะห์องค์ประกอบโครงสร้างของเอกสาร เช่น ตาราง ไดอะแกรม หรือองค์ประกอบกราฟิก คุณสามารถใช้เส้นขอบที่แยกออกมาเพื่อระบุเค้าโครง ขนาด และตำแหน่งของเนื้อหาภายในเอกสาร PDF

#### ถาม: ฉันสามารถแยกเส้นขอบจากหน้าหรือพื้นที่เฉพาะในเอกสาร PDF ได้หรือไม่

 A: ใช่ คุณสามารถแก้ไขโค้ดต้นฉบับ C# ที่ให้มาเพื่อแยกเส้นขอบจากหน้าหรือภูมิภาคเฉพาะภายในเอกสาร PDF ได้ โดยการจัดการ`doc.Pages` เมื่อรวบรวมและระบุเกณฑ์ที่กำหนดเองแล้ว คุณสามารถเลือกที่จะแยกเส้นขอบจากหน้าหรือพื้นที่ที่สนใจโดยเฉพาะได้

#### ถาม: ฉันจะปรับแต่งรูปแบบและคุณภาพของภาพเอาท์พุตได้อย่างไร

 A: ในโค้ด C# ที่ให้มา ขอบที่แยกออกมาจะถูกบันทึกเป็นรูปภาพ PNG หากคุณต้องการเปลี่ยนรูปแบบรูปภาพเอาต์พุต คุณสามารถแก้ไข`ImageFormat.Png` พารามิเตอร์ใน`bitmap.Save` วิธีการแปลงไฟล์ภาพที่รองรับรูปแบบอื่น เช่น JPEG, BMP หรือ GIF นอกจากนี้ คุณยังสามารถปรับคุณภาพของภาพหรือการตั้งค่าการบีบอัดได้ตามความต้องการของคุณ

#### ถาม: ฉันสามารถดำเนินการอื่นใดกับพรมแดนที่ถูกแยกออกมาได้บ้าง?

A: เมื่อคุณแยกเส้นขอบออกมาเป็นภาพแล้ว คุณสามารถประมวลผลเพิ่มเติมโดยใช้ไลบรารีหรืออัลกอริทึมการประมวลผลภาพ คุณสามารถวิเคราะห์ภาพ ใช้ฟิลเตอร์ภาพ ตรวจจับรูปแบบ หรือดำเนินการ OCR (การจดจำอักขระด้วยแสง) เพื่อแยกข้อความออกจากภาพหากจำเป็น

#### ถาม: มีข้อจำกัดหรือข้อควรพิจารณาใดๆ เมื่อแยกขอบออกจากเอกสาร PDF ที่ซับซ้อนหรือไม่

A: กระบวนการแยกไฟล์อาจแตกต่างกันไป ขึ้นอยู่กับความซับซ้อนของเอกสาร PDF ไฟล์ PDF ที่ซับซ้อนที่มีหลายเลเยอร์ ความโปร่งใส หรือกราฟิกขั้นสูงอาจต้องใช้การประมวลผลเพิ่มเติมหรือการปรับแต่งเพื่อแยกขอบได้อย่างแม่นยำ จำเป็นต้องทดสอบกระบวนการแยกไฟล์อย่างละเอียดในเอกสาร PDF ต่างๆ เพื่อให้แน่ใจว่าจะได้ผลลัพธ์ที่เชื่อถือได้