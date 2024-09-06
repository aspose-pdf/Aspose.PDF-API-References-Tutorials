---
title: ข้อมูลรูปภาพในไฟล์ PDF
linktitle: ข้อมูลรูปภาพในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: แยกข้อมูลรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 160
url: /th/net/programming-with-images/image-information/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีการดึงข้อมูลเกี่ยวกับรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

 ตรวจสอบให้แน่ใจว่าได้ตั้งค่าไดเรกทอรีเอกสารที่ถูกต้อง แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่เอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดไฟล์ PDF ต้นฉบับ

 ในขั้นตอนนี้เราจะโหลดไฟล์ PDF ต้นฉบับโดยใช้`Document` คลาสของ Aspose.PDF ใช้`Document` สร้างและส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## ขั้นตอนที่ 3: ตั้งค่าความละเอียดเริ่มต้น

ในขั้นตอนนี้ เราจะตั้งค่าความละเอียดเริ่มต้นสำหรับรูปภาพ ในตัวอย่างนี้ ความละเอียดเริ่มต้นถูกตั้งไว้ที่ 72

```csharp
int defaultResolution = 72;
```

## ขั้นตอนที่ 4: เริ่มต้นวัตถุและเคาน์เตอร์

ในขั้นตอนนี้เราจะเริ่มต้นวัตถุและตัวนับที่จำเป็นในการดึงข้อมูลภาพ

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## ขั้นตอนที่ 5: หมุนเวียนผ่านตัวดำเนินการบนหน้าแรกของเอกสาร

ในขั้นตอนนี้เราจะตรวจสอบตัวดำเนินการบนหน้าแรกของเอกสารเพื่อระบุการทำงานที่เกี่ยวข้องกับรูปภาพ

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## ขั้นตอนที่ 6: จัดการผู้ปฏิบัติงานและดึงข้อมูลภาพ

ในขั้นตอนนี้เราจะจัดการตัวดำเนินการประเภทต่างๆ และแยกข้อมูลเกี่ยวกับรูปภาพ

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//จัดการการดำเนินการ GSave และ GRestore สำหรับการแปลง
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// จัดการการดำเนินการ ConcatenateMatrix สำหรับการแปลง
else if (opCtm != null)
{
     // การประยุกต์ใช้เมทริกซ์การแปลง
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
// จัดการการดำเนินการสำหรับภาพ
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // ดึงภาพกลับมา
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // ดึงข้อมูลขนาดของภาพ
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // คำนวณความละเอียดตามข้อมูลด้านบน
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // แสดงข้อมูลภาพ
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### ตัวอย่างโค้ดที่มาสำหรับข้อมูลภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดไฟล์ PDF ต้นฉบับ
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// กำหนดความละเอียดเริ่มต้นสำหรับภาพ
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// กำหนดวัตถุรายการอาร์เรย์ที่จะเก็บชื่อภาพ
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// แทรกวัตถุที่จะวางซ้อน
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// รับผู้ประกอบการทั้งหมดบนหน้าแรกของเอกสาร
foreach (Operator op in doc.Pages[1].Contents)
{
	// ใช้ตัวดำเนินการ GSave/GRestore เพื่อย้อนกลับการแปลงไปยังการตั้งค่าก่อนหน้านี้
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// สร้างอินสแตนซ์ของวัตถุ ConcatenateMatrix เนื่องจากกำหนดเมทริกซ์การแปลงปัจจุบัน
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// ตัวดำเนินการ Create Do ซึ่งดึงวัตถุจากแหล่งข้อมูล ดึงวัตถุ Form และวัตถุ Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//บันทึกสถานะก่อนหน้าและผลักสถานะปัจจุบันไปที่ด้านบนสุดของสแต็ก
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// ทิ้งสถานะปัจจุบันและเรียกคืนสถานะก่อนหน้า
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
		// คูณเมทริกซ์ปัจจุบันด้วยเมทริกซ์สถานะ
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// กรณีเป็นผู้ดำเนินการวาดภาพ
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// สร้างวัตถุ XImage เพื่อเก็บรูปภาพของหน้า pdf หน้าแรก
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// รับขนาดภาพ
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// รับข้อมูลความสูงและความกว้างของภาพ
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// คำนวณความละเอียดตามข้อมูลด้านบน
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// แสดงข้อมูลขนาดและความละเอียดของภาพแต่ละภาพ
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีการแยกข้อมูลภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถใช้ข้อมูลนี้สำหรับงานประมวลผลภาพต่างๆ ในแอปพลิเคชันของคุณได้

### คำถามที่พบบ่อยเกี่ยวกับข้อมูลภาพในไฟล์ PDF

#### ถาม: จุดประสงค์ในการดึงข้อมูลรูปภาพจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การแยกข้อมูลภาพจากเอกสาร PDF จะทำให้ทราบถึงขนาด ความละเอียด และคุณลักษณะอื่นๆ ของภาพภายในเอกสาร ข้อมูลนี้ใช้สำหรับการประมวลผลภาพ การวิเคราะห์ หรือการปรับแต่งภาพได้

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยในการดึงข้อมูลรูปภาพจากเอกสาร PDF ได้อย่างไร

A: Aspose.PDF สำหรับ .NET มีเครื่องมือสำหรับเข้าถึงและวิเคราะห์เนื้อหาของเอกสาร PDF รวมถึงรูปภาพด้วย โค้ดที่ให้มาจะสาธิตวิธีการดึงและแสดงข้อมูลรูปภาพโดยใช้ตัวดำเนินการต่างๆ

#### ถาม: วิธีนี้สามารถดึงข้อมูลภาพประเภทใดออกมาได้บ้าง?

A: วิธีการนี้ช่วยให้คุณสามารถแยกและแสดงข้อมูล เช่น ขนาดที่ปรับขนาด ความละเอียด และชื่อรูปภาพสำหรับรูปภาพภายในเอกสาร PDF ได้

#### ถาม: โค้ดระบุและประมวลผลตัวดำเนินการที่เกี่ยวข้องกับรูปภาพภายในเอกสาร PDF ได้อย่างไร

A: โค้ดจะวนซ้ำผ่านตัวดำเนินการในหน้าที่ระบุของเอกสาร PDF โดยจะระบุและประมวลผลตัวดำเนินการที่เกี่ยวข้องกับการดำเนินการกับภาพ การแปลง และการเรนเดอร์

#### ถาม: ความสำคัญของการแก้ไขค่าเริ่มต้นคืออะไร และใช้ในโค้ดอย่างไร

A: ความละเอียดเริ่มต้นจะใช้เป็นจุดอ้างอิงในการคำนวณความละเอียดจริงของภาพ โค้ดจะคำนวณความละเอียดของภาพแต่ละภาพโดยอิงตามขนาดและการตั้งค่าความละเอียดเริ่มต้น

#### ถาม: ข้อมูลภาพที่แยกออกมาสามารถนำไปใช้ในสถานการณ์จริงได้อย่างไร

A: ข้อมูลภาพที่แยกออกมาสามารถใช้สำหรับงานต่างๆ เช่น การประเมินคุณภาพของภาพ การปรับปรุงภาพ การสร้างภาพขนาดย่อ และการอำนวยความสะดวกในกระบวนการตัดสินใจที่เกี่ยวข้องกับภาพ

#### ถาม: ฉันสามารถแก้ไขโค้ดเพื่อดึงคุณลักษณะที่เกี่ยวข้องกับรูปภาพเพิ่มเติมได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งโค้ดเพื่อแยกคุณลักษณะเพิ่มเติมของรูปภาพ เช่น พื้นที่สี ความลึกของพิกเซล หรือประเภทของรูปภาพ

#### ถาม: กระบวนการดึงข้อมูลภาพใช้ทรัพยากรมากหรือใช้เวลานานหรือไม่

A: กระบวนการดึงข้อมูลภาพมีประสิทธิภาพและได้รับการปรับให้เหมาะสมเพื่อการทำงาน โดยช่วยลดผลกระทบต่อการใช้ทรัพยากรและเวลาในการประมวลผลให้เหลือน้อยที่สุด

#### ถาม: นักพัฒนาสามารถได้รับประโยชน์จากการระบุและแยกข้อมูลภาพจากเอกสาร PDF ได้อย่างไร

A: นักพัฒนาสามารถรับข้อมูลเชิงลึกเกี่ยวกับคุณลักษณะของรูปภาพในเอกสาร PDF ช่วยให้พวกเขาสามารถตัดสินใจอย่างรอบรู้เกี่ยวกับการจัดการ การประมวลผล และการเพิ่มประสิทธิภาพรูปภาพ

#### ถาม: วิธีนี้ใช้สำหรับการประมวลผลเอกสาร PDF ที่มีรูปภาพเป็นชุดได้หรือไม่

A: ใช่ วิธีนี้สามารถขยายสำหรับการประมวลผลแบบแบตช์ได้ด้วยการวนซ้ำผ่านหลายหน้าหรือเอกสาร การแยกข้อมูลภาพ และการดำเนินการงานที่เกี่ยวข้องกับภาพ