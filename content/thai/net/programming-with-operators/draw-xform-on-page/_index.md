---
title: วาด XForm บนหน้า
linktitle: วาด XForm บนหน้า
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการวาดแบบฟอร์ม XForm บนหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET เพิ่มและวางตำแหน่งแบบฟอร์มบนหน้า
type: docs
weight: 10
url: /th/net/programming-with-operators/draw-xform-on-page/
---
ในบทช่วยสอนนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการวาด XForm บนเพจโดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม การใช้ตัวดำเนินการที่ Aspose.PDF มอบให้ คุณสามารถเพิ่มและวางตำแหน่งแบบฟอร์ม XForm บนหน้า PDF ที่มีอยู่ได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio ติดตั้งด้วย .NET framework
2. ไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ทางการของ Aspose และติดตั้งลงในเครื่องของคุณ

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นในการเข้าถึงคลาสและวิธีการที่ได้รับจาก Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## ขั้นตอนที่ 3: การตั้งค่าเส้นทางไฟล์

กำหนดพาธของไฟล์สำหรับภาพพื้นหลัง ไฟล์ PDF อินพุต และไฟล์ PDF เอาต์พุต:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

อย่าลืมระบุเส้นทางไฟล์จริงบนเครื่องของคุณ

## ขั้นตอนที่ 4: กำลังโหลดไฟล์ PDF อินพุต

ใช้รหัสต่อไปนี้เพื่อโหลดไฟล์ PDF อินพุต:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// รหัสต่อไปนี้ใช้ตัวดำเนินการ GSave/GRestore
// รหัสใช้ตัวดำเนินการ ContatenateMatrix เพื่อวางตำแหน่ง XForm
// รหัสใช้ตัวดำเนินการ Do เพื่อวาด XForm บนเพจ
// ตัวดำเนินการ GSave/GRestore จะรวมเนื้อหาที่มีอยู่
// ทำเช่นนี้เพื่อรับสถานะกราฟิกเริ่มต้นที่ส่วนท้ายของเนื้อหาที่มีอยู่
// มิฉะนั้นอาจเกิดการเปลี่ยนแปลงที่ไม่ต้องการทิ้งไว้ที่ส่วนท้ายของห่วงโซ่ของผู้ปฏิบัติงานที่มีอยู่
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// เพิ่มตัวดำเนินการ GSave เพื่อรีเซ็ตสถานะกราฟิกอย่างถูกต้องหลังจากคำสั่งใหม่
pageContents. Add(new GSave());

// สร้าง XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// กำหนดความกว้างและความสูงของภาพ
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// โหลดภาพลงในสตรีม
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// เพิ่มรูปภาพลงในคอลเลกชันรูปภาพทรัพยากร XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// การใช้ตัวดำเนินการ Do: ตัวดำเนินการนี้จะวาดภาพ
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//วางตำแหน่ง XForm ที่พิกัด x=100 และ y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// วาด XForm ด้วยตัวดำเนินการ Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// วางตำแหน่ง XForm ที่พิกัด x=100 และ y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// วาด XForm ด้วยตัวดำเนินการ Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// คืนค่าสถานะกราฟิกด้วย GRestore หลังจาก GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

อย่าลืมระบุเส้นทางไฟล์จริงและปรับหมายเลขหน้าและตำแหน่ง XForm ตามต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับ Draw XForm On Page โดยใช้ Aspose.PDF สำหรับ .NET
 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// ตัวอย่างแสดงให้เห็น
	// การใช้งานตัวดำเนินการ GSave/GRestore
	// การใช้ตัวดำเนินการ ContatenateMatrix เพื่อวางตำแหน่ง xForm
	// ใช้โอเปอเรเตอร์เพื่อวาด xForm บนเพจ
	// รวมเนื้อหาที่มีอยู่ด้วยคู่ตัวดำเนินการ GSave/GRestore
	// นี่คือการรับสถานะกราฟิกเริ่มต้นที่และของเนื้อหาที่มีอยู่
	// มิฉะนั้นอาจยังมีการเปลี่ยนแปลงที่ไม่พึงประสงค์อยู่ที่ส่วนท้ายของห่วงโซ่ตัวดำเนินการที่มีอยู่
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// เพิ่มตัวดำเนินการบันทึกสถานะกราฟิกเพื่อล้างสถานะกราฟิกอย่างเหมาะสมหลังจากคำสั่งใหม่
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// สร้าง xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// กำหนดความกว้างและความสูงของภาพ
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// โหลดภาพเข้าสู่สตรีม
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//เพิ่มรูปภาพลงในคอลเลกชันรูปภาพของทรัพยากร XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// การใช้ตัวดำเนินการ Do: ตัวดำเนินการนี้จะวาดภาพ
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// วางแบบฟอร์มไว้ที่พิกัด x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// วาดแบบฟอร์มด้วยตัวดำเนินการ Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// วางแบบฟอร์มไว้ที่พิกัด x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// วาดแบบฟอร์มด้วยตัวดำเนินการ Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// คืนค่าสถานะ grahics ด้วย GRestore หลังจาก GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีการวาดแบบฟอร์ม XForm บนหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ คุณจะสามารถเพิ่มและวางตำแหน่งแบบฟอร์ม XForm บนหน้าที่มีอยู่ได้ จึงทำให้เอกสาร PDF ของคุณมีความยืดหยุ่นมากขึ้น

### คำถามที่พบบ่อยสำหรับการวาด XForm บนหน้า

#### ถาม: XForm ใน Aspose.PDF คืออะไร

ตอบ: XForm เป็นวัตถุกราฟิกที่สามารถนำมาใช้ซ้ำได้ในเอกสาร PDF ช่วยให้คุณสามารถกำหนดและวาดกราฟิก รูปภาพ หรือข้อความที่ซับซ้อนซึ่งสามารถนำมาใช้ซ้ำได้หลายครั้งในหน้าต่างๆ

#### ถาม: ฉันจะนำเข้าเนมสเปซที่จำเป็นสำหรับ Aspose.PDF ได้อย่างไร

 ตอบ: ในไฟล์โค้ด C# ของคุณ ให้ใช้นามสกุล`using` คำสั่งในการนำเข้าเนมสเปซที่จำเป็นสำหรับการเข้าถึงคลาสและวิธีการจัดทำโดย Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### ถาม: ตัวดำเนินการ GSave และ GRestore มีจุดประสงค์อะไร

 ตอบ:`GSave` และ`GRestore`ตัวดำเนินการใน Aspose.PDF ใช้เพื่อบันทึกและกู้คืนสถานะกราฟิก ช่วยให้แน่ใจว่าการเปลี่ยนแปลงและการตั้งค่าที่ใช้กับส่วนหนึ่งของเนื้อหาจะไม่ส่งผลกระทบต่อส่วนต่อๆ ไป

#### ถาม: ฉันจะกำหนด XForm โดยใช้ Aspose.PDF ได้อย่างไร

 ตอบ: หากต้องการสร้าง XForm ให้ใช้ไฟล์`XForm.CreateNewForm` วิธีการและเพิ่มลงใน`Resources.Forms` การรวบรวมหน้าเฉพาะ จากนั้นคุณสามารถเพิ่มเนื้อหาลงใน XForm ได้`Contents` คุณสมบัติ.

#### ถาม: ฉันจะวาดภาพภายใน XForm ได้อย่างไร

 ตอบ: โหลดรูปภาพลงในสตรีมและเพิ่มลงใน`Resources.Images` คอลเลกชันของ XForm ใช้`Do` โอเปอเรเตอร์ภายใน XForm's`Contents` เพื่อวาดภาพ

#### ถาม: ฉันจะวางตำแหน่ง XForm บนหน้า PDF ได้อย่างไร

 ตอบ: หากต้องการวางตำแหน่ง XForm บนเพจ ให้ใช้`ConcatenateMatrix` โอเปอเรเตอร์ภายในเพจ`Contents`. ปรับพารามิเตอร์เมทริกซ์เพื่อระบุการแปล (ตำแหน่ง) และการปรับขนาดของ XForm

#### ถาม: ฉันสามารถวาด XForms หลายอันในหน้าเดียวกันได้หรือไม่

 ตอบ: ได้ คุณสามารถวาด XForms หลายอันในหน้าเดียวกันได้โดยการปรับ`ConcatenateMatrix`พารามิเตอร์เพื่อวางตำแหน่ง XForm แต่ละรายการในพิกัดที่ต่างกัน

#### ถาม: ฉันสามารถแก้ไขเนื้อหาของ XForm หลังจากที่สร้างเสร็จแล้วได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขเนื้อหาของ XForm ได้หลังการสร้างโดยการเพิ่มตัวดำเนินการเพิ่มเติมลงไป`Contents` คุณสมบัติ.

#### ถาม: จะเกิดอะไรขึ้นถ้าฉันละเว้นตัวดำเนินการ GSave และ GRestore

ตอบ: การละเว้นตัวดำเนินการ GSave และ GRestore อาจทำให้เกิดการเปลี่ยนแปลงหรือการตั้งค่าที่ไม่ต้องการกับเนื้อหาที่ตามมา การใช้สิ่งเหล่านี้ช่วยรักษาสถานะกราฟิกที่สะอาดตา

#### ถาม: ฉันสามารถใช้ XForms ซ้ำกับหน้าต่างๆ ของเอกสาร PDF ได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้ XForms ซ้ำได้ในหลาย ๆ หน้าโดยการเพิ่ม XForm เดียวกันลงใน`Resources.Forms` การรวบรวมหน้าต่างๆ

#### ถาม: มีการจำกัดจำนวน XForms ที่ฉันสามารถสร้างได้หรือไม่?

ตอบ: แม้ว่าไม่มีการจำกัดจำนวน XForms ที่คุณสามารถสร้างได้ แต่โปรดจำไว้ว่าการมี XForms มากเกินไปอาจส่งผลต่อประสิทธิภาพและการใช้งานหน่วยความจำ ใช้พวกเขาอย่างรอบคอบ

#### ถาม: ฉันสามารถหมุน XForm หรือใช้การแปลงอื่น ๆ ได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้`ConcatenateMatrix`โอเปอเรเตอร์เพื่อใช้การแปลง เช่น การหมุน การปรับขนาด และการแปลกับ XForm
