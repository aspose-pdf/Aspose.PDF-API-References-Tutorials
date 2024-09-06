---
title: วาด XForm บนหน้า
linktitle: วาด XForm บนหน้า
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการวาดแบบฟอร์ม XForm บนหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET เพิ่มและวางตำแหน่งแบบฟอร์มบนหน้า
type: docs
weight: 10
url: /th/net/programming-with-operators/draw-xform-on-page/
---
ในบทช่วยสอนนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการวาด XForm บนหน้าโดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสร้าง จัดการ และแปลงเอกสาร PDF ได้ด้วยโปรแกรม โดยใช้ตัวดำเนินการที่ Aspose.PDF จัดเตรียมไว้ให้ คุณสามารถเพิ่มและวางตำแหน่งฟอร์ม XForm บนหน้า PDF ที่มีอยู่ได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. ติดตั้ง Visual Studio ด้วย .NET framework
2. ไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการของ Aspose และติดตั้งบนเครื่องของคุณได้

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

ในไฟล์โค้ด C# ของคุณ นำเข้าเนมสเปซที่จำเป็นในการเข้าถึงคลาสและวิธีการที่ Aspose.PDF จัดเตรียมไว้:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## ขั้นตอนที่ 3: การตั้งค่าเส้นทางไฟล์

กำหนดเส้นทางไฟล์สำหรับภาพพื้นหลัง ไฟล์ PDF อินพุต และไฟล์ PDF เอาท์พุต:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

อย่าลืมระบุเส้นทางไฟล์จริงบนเครื่องของคุณ

## ขั้นตอนที่ 4: โหลดไฟล์ PDF อินพุต

ใช้โค้ดต่อไปนี้เพื่อโหลดไฟล์ PDF อินพุต:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// โค้ดต่อไปนี้ใช้ตัวดำเนินการ GSave/GRestore
// โค้ดนี้ใช้ตัวดำเนินการ ContatenateMatrix เพื่อวางตำแหน่ง XForm
// โค้ดนี้ใช้ตัวดำเนินการ Do เพื่อวาด XForm บนหน้า
// ตัวดำเนินการ GSave/GRestore ห่อเนื้อหาที่มีอยู่
//สิ่งนี้ทำขึ้นเพื่อให้ได้สถานะกราฟิกเริ่มต้นในตอนท้ายของเนื้อหาที่มีอยู่
// มิฉะนั้นอาจมีการแปลงที่ไม่ต้องการเหลืออยู่ที่ปลายสุดของห่วงโซ่ของตัวดำเนินการที่มีอยู่
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// เพิ่มตัวดำเนินการ GSave เพื่อรีเซ็ตสถานะกราฟิกอย่างถูกต้องหลังจากคำสั่งใหม่
pageContents. Add(new GSave());

// สร้าง XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// ตั้งค่าความกว้างและความสูงของภาพ
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// โหลดภาพเข้าสู่สตรีม
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// เพิ่มรูปภาพลงในคอลเล็กชันรูปภาพทรัพยากร XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// การใช้ตัวดำเนินการ Do: ตัวดำเนินการนี้จะวาดภาพ
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// วางตำแหน่ง XForm ที่พิกัด x=100 และ y=500
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

อย่าลืมระบุเส้นทางไฟล์จริงและปรับหมายเลขหน้าและตำแหน่ง XForm ตามที่จำเป็น

### ตัวอย่างโค้ดต้นฉบับสำหรับ Draw XForm On Page โดยใช้ Aspose.PDF สำหรับ .NET
 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// ตัวอย่างสาธิต
	// การใช้งานตัวดำเนินการ GSave/GRestore
	// การใช้ตัวดำเนินการ ContatenateMatrix เพื่อกำหนดตำแหน่ง xForm
	//การใช้งานตัวดำเนินการในการวาด xForm บนหน้า
	// ห่อเนื้อหาที่มีอยู่ด้วยคู่ตัวดำเนินการ GSave/GRestore
	// นี่คือการรับสถานะกราฟิกเริ่มต้นที่และเนื้อหาที่มีอยู่
	// มิฉะนั้น อาจมีการเปลี่ยนแปลงที่ไม่พึงประสงค์บางอย่างเกิดขึ้นที่ปลายห่วงโซ่ของตัวดำเนินการที่มีอยู่
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// เพิ่มตัวดำเนินการบันทึกสถานะกราฟิกเพื่อล้างสถานะกราฟิกอย่างถูกต้องหลังจากคำสั่งใหม่
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
	// เพิ่มรูปภาพลงในคอลเล็กชันรูปภาพของทรัพยากร XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// การใช้ตัวดำเนินการ Do: ตัวดำเนินการนี้จะวาดภาพ
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// วางแบบฟอร์มลงในพิกัด x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// การวาดแบบฟอร์มด้วยตัวดำเนินการ Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// วางแบบฟอร์มลงในพิกัด x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// การวาดแบบฟอร์มด้วยตัวดำเนินการ Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// คืนค่าสถานะกราฟิกด้วย GRestore หลังจาก GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการวาดแบบฟอร์ม XForm บนหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนที่อธิบายไว้ คุณจะสามารถเพิ่มและวางตำแหน่งแบบฟอร์ม XForm บนหน้าที่มีอยู่ได้ ทำให้เอกสาร PDF ของคุณมีความยืดหยุ่นมากขึ้น

### คำถามที่พบบ่อยสำหรับการวาด XForm บนหน้า

#### ถาม: XForm ใน Aspose.PDF คืออะไร

A: XForm คืออ็อบเจ็กต์กราฟิกที่นำมาใช้ซ้ำได้ในเอกสาร PDF ช่วยให้คุณสามารถกำหนดและวาดกราฟิก รูปภาพ หรือข้อความที่ซับซ้อนซึ่งสามารถนำมาใช้ซ้ำได้หลายครั้งบนหน้าต่างๆ

#### ถาม: ฉันจะนำเข้าเนมสเปซที่จำเป็นสำหรับ Aspose.PDF ได้อย่างไร

 A: ในไฟล์โค้ด C# ของคุณ ให้ใช้`using` คำสั่งในการนำเข้าเนมสเปซที่จำเป็นสำหรับการเข้าถึงคลาสและวิธีการที่จัดทำโดย Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### ถาม: จุดประสงค์ของตัวดำเนินการ GSave และ GRestore คืออะไร

 ก. การ`GSave` และ`GRestore` ตัวดำเนินการใน Aspose.PDF ใช้เพื่อบันทึกและกู้คืนสถานะกราฟิก ช่วยให้มั่นใจได้ว่าการแปลงและการตั้งค่าที่ใช้กับเนื้อหาส่วนหนึ่งจะไม่ส่งผลกระทบต่อส่วนถัดไป

#### ถาม: ฉันจะกำหนด XForm โดยใช้ Aspose.PDF ได้อย่างไร

 ตอบ หากต้องการสร้าง XForm ให้ใช้`XForm.CreateNewForm` วิธีการและเพิ่มมันลงใน`Resources.Forms` การรวบรวมหน้าเฉพาะ จากนั้นคุณสามารถเพิ่มเนื้อหาลงใน XForm ได้`Contents` คุณสมบัติ.

#### ถาม: ฉันจะวาดภาพภายใน XForm ได้อย่างไร

ก: โหลดภาพลงในสตรีมและเพิ่มลงใน`Resources.Images` การรวบรวม XForm ใช้`Do` ผู้ปฏิบัติงานภายใน XForm`Contents` การวาดภาพ

#### ถาม: ฉันจะวางตำแหน่ง XForm บนหน้า PDF ได้อย่างไร

 ก: หากต้องการวาง XForm บนหน้า ให้ใช้`ConcatenateMatrix` ตัวดำเนินการภายในหน้า`Contents`. ปรับพารามิเตอร์เมทริกซ์เพื่อระบุการแปล (ตำแหน่ง) และการปรับขนาดของ XForm

#### ถาม: ฉันสามารถวาด XForms หลาย ๆ อันในหน้าเดียวกันได้หรือไม่

 A: ใช่ คุณสามารถวาด XForms หลาย ๆ อันบนหน้าเดียวกันได้โดยการปรับ`ConcatenateMatrix` พารามิเตอร์ในการวางตำแหน่ง XForm แต่ละอันในพิกัดที่แตกต่างกัน

#### ถาม: ฉันสามารถแก้ไขเนื้อหาของ XForm หลังจากที่สร้างแล้วได้หรือไม่

 A: ใช่ คุณสามารถแก้ไขเนื้อหาของ XForm หลังจากสร้างโดยเพิ่มตัวดำเนินการเพิ่มเติมลงไป`Contents` คุณสมบัติ.

#### ถาม: จะเกิดอะไรขึ้นหากฉันละเว้นตัวดำเนินการ GSave และ GRestore?

A: การละเว้นตัวดำเนินการ GSave และ GRestore อาจทำให้การแปลงหรือการตั้งค่าที่ไม่ต้องการถูกนำไปใช้กับเนื้อหาในภายหลัง การใช้ตัวดำเนินการเหล่านี้จะช่วยรักษาสถานะกราฟิกให้สะอาด

#### ถาม: ฉันสามารถนำ XForms มาใช้ซ้ำในหน้าต่างๆ ของเอกสาร PDF ได้หรือไม่

 A: ใช่ คุณสามารถนำ XForms กลับมาใช้ซ้ำบนหลายหน้าได้โดยการเพิ่ม XForm เดียวกันลงใน`Resources.Forms` รวมหน้าต่างๆ

#### ถาม: จำนวน XForms ที่ฉันสามารถสร้างได้มีขีดจำกัดหรือไม่

A: แม้ว่าจะไม่มีข้อจำกัดที่เข้มงวดเกี่ยวกับจำนวน XForms ที่คุณสามารถสร้างได้ แต่โปรดจำไว้ว่า XForms มากเกินไปอาจส่งผลต่อประสิทธิภาพและการใช้หน่วยความจำ ดังนั้นจึงควรใช้ XForms อย่างรอบคอบ

#### ถาม: ฉันสามารถหมุน XForm หรือใช้การแปลงอื่น ๆ ได้หรือไม่

 A: ใช่ คุณสามารถใช้`ConcatenateMatrix` ตัวดำเนินการเพื่อใช้การเปลี่ยนแปลงต่างๆ เช่น การหมุน การปรับขนาด และการแปลไปใน XForm
