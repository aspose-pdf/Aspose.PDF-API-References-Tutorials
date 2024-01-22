---
title: ข้อมูลรูปภาพในรูปแบบไฟล์ PDF
linktitle: ข้อมูลรูปภาพในรูปแบบไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: แยกข้อมูลรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 160
url: /th/net/programming-with-images/image-information/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนในการดึงข้อมูลเกี่ยวกับรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ตรวจสอบให้แน่ใจว่าได้ตั้งค่าไดเร็กทอรีเอกสารที่ถูกต้อง แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดไฟล์ PDF ต้นฉบับ

 ในขั้นตอนนี้ เราจะโหลดไฟล์ PDF ต้นฉบับโดยใช้นามสกุลไฟล์`Document` คลาสของ Aspose.PDF ใช้`Document` Constructor และส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## ขั้นตอนที่ 3: ตั้งค่าความละเอียดเริ่มต้น

ในขั้นตอนนี้ เราจะตั้งค่าความละเอียดเริ่มต้นสำหรับรูปภาพ ในตัวอย่าง ความละเอียดเริ่มต้นถูกตั้งค่าเป็น 72

```csharp
int defaultResolution = 72;
```

## ขั้นตอนที่ 4: เริ่มต้นวัตถุและตัวนับ

ในขั้นตอนนี้ เราจะเริ่มต้นวัตถุและตัวนับที่จำเป็นในการดึงข้อมูลรูปภาพ

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## ขั้นตอนที่ 5: วนไปตามตัวดำเนินการในหน้าแรกของเอกสาร

ในขั้นตอนนี้ เราจะแนะนำตัวดำเนินการในหน้าแรกของเอกสารเพื่อระบุการดำเนินการที่เกี่ยวข้องกับรูปภาพ

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## ขั้นตอนที่ 6: จัดการตัวดำเนินการและดึงข้อมูลรูปภาพ

ในขั้นตอนนี้ เราจะจัดการตัวดำเนินการประเภทต่างๆ และแยกข้อมูลเกี่ยวกับรูปภาพ

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
     // ใช้เมทริกซ์การแปลง
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
// จัดการการดำเนินการ Do สำหรับรูปภาพ
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // ดึงภาพ
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // ดึงมิติของภาพ
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // คำนวณความละเอียดตามข้อมูลข้างต้น
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

### ตัวอย่างซอร์สโค้ดสำหรับข้อมูลรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดไฟล์ PDF ต้นฉบับ
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// กำหนดความละเอียดเริ่มต้นของภาพ
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// กำหนดวัตถุรายการอาร์เรย์ที่จะเก็บชื่อรูปภาพ
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// แทรกวัตถุที่จะสแต็ก
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// รับตัวดำเนินการทั้งหมดไว้ในหน้าแรกของเอกสาร
foreach (Operator op in doc.Pages[1].Contents)
{
	// ใช้ตัวดำเนินการ GSave/GRestore เพื่อเปลี่ยนการแปลงกลับไปเป็นการตั้งค่าก่อนหน้า
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// สร้างอินสแตนซ์วัตถุ ConcatenateMatrix ตามที่กำหนดเมทริกซ์การแปลงปัจจุบัน
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// สร้างตัวดำเนินการ Do ซึ่งดึงวัตถุจากทรัพยากร มันดึงวัตถุแบบฟอร์มและวัตถุรูปภาพ
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//บันทึกสถานะก่อนหน้าและผลักดันสถานะปัจจุบันไปที่ด้านบนของสแต็ก
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
		// คูณเมทริกซ์ปัจจุบันกับเมทริกซ์สถานะ
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// ในกรณีนี้คือตัวดำเนินการวาดภาพ
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// สร้างวัตถุ XImage เพื่อเก็บภาพของหน้าแรกของ PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// รับขนาดภาพ
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// รับข้อมูลความสูงและความกว้างของภาพ
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// ความละเอียดในการคำนวณตามข้อมูลข้างต้น
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// แสดงข้อมูลขนาดและความละเอียดของแต่ละภาพ
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีแยกข้อมูลรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถใช้ข้อมูลนี้สำหรับงานการประมวลผลภาพต่างๆ ในแอปพลิเคชันของคุณ

### คำถามที่พบบ่อยสำหรับข้อมูลรูปภาพในรูปแบบไฟล์ PDF

#### ถาม: จุดประสงค์ของการดึงข้อมูลรูปภาพจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การแยกข้อมูลรูปภาพออกจากเอกสาร PDF จะให้ข้อมูลเชิงลึกเกี่ยวกับขนาด ความละเอียด และคุณลักษณะอื่นๆ ของรูปภาพภายในเอกสาร ข้อมูลนี้สามารถใช้สำหรับการประมวลผลภาพ การวิเคราะห์ หรืองานการปรับให้เหมาะสม

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยในการดึงข้อมูลรูปภาพจากเอกสาร PDF ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มีเครื่องมือในการเข้าถึงและวิเคราะห์เนื้อหาของเอกสาร PDF รวมถึงรูปภาพด้วย รหัสที่ให้มาสาธิตวิธีการแยกและแสดงข้อมูลภาพโดยใช้ตัวดำเนินการต่างๆ

#### ถาม: ข้อมูลภาพประเภทใดที่สามารถดึงออกมาได้ด้วยวิธีนี้

ตอบ: วิธีนี้ช่วยให้คุณสามารถแยกและแสดงข้อมูล เช่น ขนาดที่ปรับขนาด ความละเอียด และชื่อรูปภาพสำหรับรูปภาพภายในเอกสาร PDF

#### ถาม: โค้ดระบุและประมวลผลตัวดำเนินการที่เกี่ยวข้องกับรูปภาพภายในเอกสาร PDF ได้อย่างไร

ตอบ: โค้ดจะวนซ้ำผ่านตัวดำเนินการในหน้าที่ระบุของเอกสาร PDF โดยจะระบุและประมวลผลตัวดำเนินการที่เกี่ยวข้องกับการทำงานของรูปภาพ การแปลง และการเรนเดอร์

#### ถาม: ความละเอียดเริ่มต้นมีความสำคัญอย่างไร และนำไปใช้ในโค้ดอย่างไร

ตอบ: ความละเอียดเริ่มต้นจะใช้เป็นจุดอ้างอิงในการคำนวณความละเอียดที่แท้จริงของภาพ โค้ดจะคำนวณความละเอียดของแต่ละภาพตามขนาดและการตั้งค่าความละเอียดเริ่มต้น

#### ถาม: ข้อมูลภาพที่แยกออกมาสามารถนำไปใช้ในสถานการณ์จริงได้อย่างไร

ตอบ: ข้อมูลภาพที่แยกออกมาสามารถนำมาใช้สำหรับงานต่างๆ ได้ เช่น การประเมินคุณภาพของภาพ การปรับภาพให้เหมาะสม การสร้างภาพขนาดย่อของภาพ และการอำนวยความสะดวกในกระบวนการตัดสินใจที่เกี่ยวข้องกับภาพ

#### ถาม: ฉันสามารถแก้ไขโค้ดเพื่อแยกคุณลักษณะที่เกี่ยวข้องกับรูปภาพเพิ่มเติมได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งโค้ดเพื่อแยกคุณลักษณะเพิ่มเติมของรูปภาพได้ เช่น พื้นที่สี ความลึกของพิกเซล หรือประเภทรูปภาพ

#### ถาม: กระบวนการแยกข้อมูลรูปภาพใช้ทรัพยากรมากหรือใช้เวลานานหรือไม่

ตอบ: กระบวนการแยกข้อมูลรูปภาพมีประสิทธิภาพและได้รับการปรับปรุงให้เหมาะสมเพื่อให้มั่นใจว่ามีผลกระทบต่อการใช้ทรัพยากรและเวลาในการประมวลผลน้อยที่สุด

#### ถาม: นักพัฒนาจะได้รับประโยชน์จากการระบุและแยกข้อมูลรูปภาพจากเอกสาร PDF ได้อย่างไร

ตอบ: นักพัฒนาสามารถรับข้อมูลเชิงลึกเกี่ยวกับคุณลักษณะของรูปภาพภายในเอกสาร PDF ช่วยให้พวกเขาสามารถตัดสินใจได้อย่างชาญฉลาดเกี่ยวกับการจัดการรูปภาพ การประมวลผล และการเพิ่มประสิทธิภาพ

#### ถาม: สามารถใช้วิธีนี้สำหรับการประมวลผลเอกสาร PDF ที่มีรูปภาพเป็นชุดได้หรือไม่

ตอบ: ได้ วิธีนี้สามารถขยายออกไปสำหรับการประมวลผลเป็นชุดได้โดยการวนซ้ำผ่านหลายหน้าหรือเอกสาร แยกข้อมูลรูปภาพ และดำเนินงานที่เกี่ยวข้องกับรูปภาพ