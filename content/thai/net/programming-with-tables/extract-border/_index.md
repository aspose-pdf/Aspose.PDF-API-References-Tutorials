---
title: แยกเส้นขอบในไฟล์ PDF
linktitle: แยกเส้นขอบในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแยกเส้นขอบในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-tables/extract-border/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีแยกเส้นขอบในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดใน C# ทีละขั้นตอน ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีแยกเส้นขอบออกจากเอกสาร PDF และบันทึกเป็นรูปภาพ เริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา C# ของคุณด้วย Aspose.PDF สำหรับ .NET เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร PDF
ในขั้นตอนนี้ เราจะโหลดเอกสาร PDF จากไฟล์ที่ระบุ

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยไดเรกทอรีจริงที่มีไฟล์ PDF ของคุณอยู่

## ขั้นตอนที่ 3: การแยกขอบ
เราจะแยกเส้นขอบออกจากเอกสาร PDF โดยวนซ้ำการดำเนินการที่มีอยู่ในเอกสาร

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
     // ประมวลผลการดำเนินการเนื้อหาทั้งหมด
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // ตรวจสอบประเภทของการทำงาน
         // ...
         // เพิ่มโค้ดเพื่อประมวลผลแต่ละการดำเนินการ
     }
}
```

 เราสร้างก`graphicsState` สแต็กเพื่อจัดเก็บสถานะกราฟิก รูปภาพบิตแมปเพื่อจับภาพเส้นขอบที่แยกออกมา`GraphicsPath` วัตถุเพื่อจัดเก็บเส้นทางการวาด และตัวแปรอื่น ๆ เพื่อติดตามสถานะและสี

## ขั้นตอนที่ 4: การประมวลผลธุรกรรม
ในขั้นตอนนี้ เราประมวลผลแต่ละการดำเนินการของเอกสารเพื่อแยกเส้นขอบ

```csharp
// ตรวจสอบประเภทของการทำงาน
if (opSaveState != null)
{
     // บันทึกสถานะก่อนหน้าและดันสถานะปัจจุบันไปที่ด้านบนของสแต็ก
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // ลบสถานะปัจจุบันและเรียกคืนสถานะก่อนหน้า
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // รับเมทริกซ์การแปลงปัจจุบัน
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // คูณเมทริกซ์ปัจจุบันกับเมทริกซ์สถานะ
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // อัพเดตจุดวาดล่าสุด
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // ประมวลผลการวาดเส้น
     // ...
     // เพิ่มโค้ดเพื่อจัดการการวาดเส้น
}
// ...
// เพิ่ม else if เพื่อบล็อกการดำเนินการอื่นๆ
```

เราตรวจสอบประเภทของการดำเนินการโดยใช้เงื่อนไขและรันโค้ดที่เหมาะสมสำหรับแต่ละการดำเนินการ

## ขั้นตอนที่ 5: สำรองข้อมูลรูปภาพ
สุดท้าย เราจะบันทึกภาพบิตแมปที่มีเส้นขอบที่แยกออกมาไปยังไฟล์ที่ระบุ

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

อย่าลืมระบุไดเร็กทอรีและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกอิมเมจเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับ Extract Border โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// ค่าเมทริกซ์ CTM เริ่มต้นคือ 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.ระบบพิกัดการวาดจะอิงด้านซ้ายบน ในขณะที่ระบบพิกัด pdf จะอิงด้านซ้ายล่าง ดังนั้นเราจึงต้องใช้เมทริกซ์ผกผัน
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
			//บันทึกสถานะก่อนหน้าและผลักดันสถานะปัจจุบันไปที่ด้านบนของสแต็ก
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

			// คูณเมทริกซ์ปัจจุบันกับเมทริกซ์สถานะ
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
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแยกเส้นขอบออกจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อแยกเส้นขอบออกจากเอกสาร PDF อื่นๆ

### คำถามที่พบบ่อยสำหรับการแยกเส้นขอบในไฟล์ PDF

#### ถาม: จุดประสงค์ของการแยกเส้นขอบออกจากไฟล์ PDF คืออะไร

ตอบ: การแยกเส้นขอบออกจากไฟล์ PDF มีประโยชน์หลายวัตถุประสงค์ ช่วยให้คุณสามารถแยกและวิเคราะห์องค์ประกอบโครงสร้างของเอกสาร เช่น ตาราง ไดอะแกรม หรือองค์ประกอบกราฟิก คุณสามารถใช้เส้นขอบที่แยกออกมาเพื่อระบุเค้าโครง ขนาด และตำแหน่งของเนื้อหาภายในเอกสาร PDF

#### ถาม: ฉันสามารถแยกเส้นขอบออกจากหน้าหรือพื้นที่เฉพาะภายในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขซอร์สโค้ด C# ที่ให้มาเพื่อแยกเส้นขอบออกจากหน้าหรือภูมิภาคที่ระบุภายในเอกสาร PDF โดยการจัดการ`doc.Pages` การรวบรวมและระบุเกณฑ์ที่กำหนดเอง คุณสามารถเลือกที่จะแยกเส้นขอบออกจากหน้าเฉพาะหรือพื้นที่ที่สนใจได้

#### ถาม: ฉันจะปรับแต่งรูปแบบและคุณภาพของภาพที่ส่งออกได้อย่างไร

 ตอบ: ในโค้ด C# ที่ให้มา เส้นขอบที่แยกออกมาจะถูกบันทึกเป็นรูปภาพ PNG หากคุณต้องการเปลี่ยนรูปแบบภาพที่ส่งออก คุณสามารถแก้ไขได้`ImageFormat.Png` พารามิเตอร์ใน`bitmap.Save` เป็นรูปแบบภาพอื่นๆ ที่รองรับ เช่น JPEG, BMP หรือ GIF นอกจากนี้ คุณยังสามารถปรับคุณภาพของภาพหรือการตั้งค่าการบีบอัดได้ตามความต้องการของคุณ

#### ถาม: ฉันสามารถดำเนินการอื่นใดได้บ้างกับเส้นขอบที่แยกออกมา?

ตอบ: เมื่อคุณแยกเส้นขอบออกเป็นรูปภาพแล้ว คุณสามารถประมวลผลเพิ่มเติมได้โดยใช้ไลบรารีหรืออัลกอริธึมการประมวลผลรูปภาพ คุณสามารถวิเคราะห์รูปภาพ ใช้ฟิลเตอร์รูปภาพ ตรวจจับรูปแบบ หรือดำเนินการ OCR (การรู้จำอักขระด้วยแสง) เพื่อแยกข้อความออกจากรูปภาพได้หากจำเป็น

#### ถาม: มีข้อจำกัดหรือข้อควรพิจารณาเมื่อแยกเส้นขอบออกจากเอกสาร PDF ที่ซับซ้อนหรือไม่

ตอบ: กระบวนการแยกอาจแตกต่างกันไปขึ้นอยู่กับความซับซ้อนของเอกสาร PDF PDF ที่ซับซ้อนซึ่งมีหลายเลเยอร์ ความโปร่งใส หรือกราฟิกขั้นสูงอาจต้องมีการประมวลผลเพิ่มเติมหรือการปรับเปลี่ยนเพื่อแยกเส้นขอบอย่างแม่นยำ จำเป็นอย่างยิ่งที่จะต้องทดสอบกระบวนการแยกเอกสาร PDF ต่างๆ อย่างละเอียดเพื่อให้แน่ใจว่าได้ผลลัพธ์ที่เชื่อถือได้